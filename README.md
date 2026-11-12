# Coca-Cola Hindi documentary — 60-second pilot

This is a small, testable starter project. It creates:
- `output/cocacola_hindi_pilot.mp4`
- `output/cocacola_hindi_pilot.srt`
- `output/image_attributions.txt`

## What it uses
- Microsoft Edge's online text-to-speech service through `edge-tts` (no API key; requires internet).
- Wikimedia Commons search for still images. The script records source/creator/license metadata when available.
- FFmpeg for video rendering.
- GitHub Actions for cloud rendering, so your Android phone does not have to render the video.

## Android setup (GitHub website)
1. Sign in to GitHub and create a **public or private** repository (for a private repo, check your Actions minutes allowance).
2. Upload all files and folders from this project ZIP, preserving `.github/workflows/build.yml`.
3. Open the repository's **Actions** tab.
4. If prompted, enable workflows.
5. Select **Build Hindi Coca-Cola Pilot** → **Run workflow**.
6. Wait for the run to finish. Open the completed run and download the `cocacola-hindi-pilot` artifact.
7. Extract it on your phone. Play the MP4 and inspect the SRT and attribution file.

## Important limitations
- This is a pilot, not a fully autonomous documentary research system.
- Edge TTS is an online service; availability, voice quality and access can change. It is not an unlimited guaranteed API.
- GitHub Actions has usage limits and public repositories/private repositories have different allowances. Check your account's current quota.
- Wikimedia search can return irrelevant or unsuitable material. Review every image and its license/attribution before uploading. Replace unsuitable images manually.
- The script deliberately does not download background music, to avoid silently using copyrighted music.
- The SRT timing is generated from actual audio segment durations, but check subtitle readability and line breaks.
- The first render may take several minutes.

## Local rendering (optional)
Install Python 3.11+, FFmpeg, and packages in `requirements.txt`, then run:
```bash
python build.py
```

## Changing the narration
Edit `script.json`. Each scene has `text` and `visual_query`. Keep the Hindi text factual and verify claims against reliable sources before publishing. You can change the voice by editing `voice`, for example `hi-IN-MadhurNeural`.
