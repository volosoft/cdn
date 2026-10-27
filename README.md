# cdn.volosoft.com

Static files served at `https://cdn.volosoft.com/<path>` through GitHub Pages (Cloudflare in front).
A file at `abp-studio/black-friday-2026.png` in this repo is served at
`https://cdn.volosoft.com/abp-studio/black-friday-2026.png` about a minute after it is pushed to `main`.

**This repository is public.** Everything committed here, including its history, can be seen by anyone:

- Never commit secrets, `.env` files, reports or internal documents.
- A campaign banner is visible as soon as it is pushed. Push it close to the campaign start if it must not
  be seen before.

## Folders

| Folder | Used by |
|---|---|
| `abp-studio/` | ABP Studio campaign banner (`CampaignBannerService`) |
| `aspnetzero/` | Images in ASP.NET Zero release e-mails and newsletters |
| `abp-commercial/` | E-mail signature image |

## ABP Studio campaign banner

ABP Studio reads `abp-studio/banner-config.json`; released versions have this URL built in, so the path must
not change.

```json
{
  "IsEnabled": "true",
  "ImageUrl": "https://cdn.volosoft.com/abp-studio/black-friday-2026.png",
  "TargetUrl": "https://abp.io/pricing",
  "StartAtUtc": "2026-11-23",
  "EndAtUtc": "2026-12-02"
}
```

To change the banner, add the image under `abp-studio/` and update `ImageUrl`, `TargetUrl` and the dates.
Set `IsEnabled` to `"false"` to hide it. GitHub Pages and Cloudflare cache files for up to 10 minutes.
