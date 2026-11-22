# TikTok Video Maker (GitHub Actions + Pexels + apni music)

Ye project roz (ya jab aap chahein) naye 1080x1920 videos banata hai:
asli free footage (Pexels) + aap ki royalty-free music + title text. Video aur caption (hashtags ke saath) download ho jate hain.

## Set up (sirf ek baar, lagbhag 10 minute)

1. **GitHub par naya repository banayein** (Public rakhein, to Actions free aur unlimited hai).
2. Is zip ki saari files us repository mein upload karein (folder `.github/workflows` bhi sath).
3. **Pexels API key lein** (free): pexels.com/api par account banayein, key copy karein.
4. Repository mein: **Settings > Secrets and variables > Actions > New repository secret**
   - Name: `PEXELS_API_KEY`  |  Value: aap ki key.
5. **Music daalein**: `music/` folder mein apni royalty-free `.mp3` files upload karein
   (Pixabay Music, YouTube Audio Library, ya khud ki bani hui). Jis music par license na ho wo na daalein.
6. **Chalayein**: tab **Actions > Make TikTok videos > Run workflow**. Videos ki tadaad aur topic likh sakte hain.
   Ye har roz subah khud bhi chalta hai (`make-video.yml` mein `cron` se waqt badal sakte hain).
7. Kaam khatam hone par us run ke page ke neeche **Artifacts > tiktok-videos** se zip download karein.
   Mobile par bhi browser se ho jata hai. Zip mein `.mp4` aur sath `.txt` (title + hashtags) hoti hai.
8. Video TikTok par khud upload karein aur `.txt` se caption copy karein.

## Apni marzi ke topics

`config.json` mein `topics` badlein (query English mein, jaise "ocean waves"). Clips ki tadaad, har clip ke second,
title on/off aur music ki awaz bhi wahin se badalti hai.

## Zaroori baatein

- **Pexels license**: free hai aur attribution zaroori nahi, magar footage ko bina badle bechna ya kisi ke naam se jorna mana hai.
- **Music**: sirf wo jis ka aap ke paas haq ya license ho. Mashhoor gaane lagaye to TikTok video hata sakta hai ya awaz band kar sakta hai.
- **TikTok ki policy**: bilkul ek jaise ya sirf automatic bane videos ki pahunch kam ho sakti hai. Har video mein topic, clips aur music badalte rahein aur kabhi kabhi apna kuch add karein.
- **Automatic upload**: TikTok ki official API ke liye approval chahiye, is liye upload yahan manual rakha hai.
- `used.json` yaad rakhta hai ke kaun si clips pehle lag chuki hain, taake dohrayi na jaye.

## Computer par test (optional)
`pip install requests`, FFmpeg install karein, phir:
`python make_video.py --local apni_clips_ka_folder --count 1` (bina Pexels ke test).
