# Live-streaming-using-YouTube-Data-API-v3
Scripts to automate one-click creation of YouTube live broadcasts and streaming H.265 video from an IP camera using FFmpeg

Przygotowanie:
- server linux np. ubuntu, zainstalowany python, ffmpeg i składniki potrzebne do autoryzacji i obsługi youtube api
- utwórz /mnt/ramdisk w nim będą zapisywane pliki log służące do sprawdzania stanu strumienia ffmpeg
- potrzebne jest konto youtube i uruchomiona możliwość strumieniowania video 
- na puplicie umieść pliki i katalogi z archiwum

Działanie:
- skrótem z pulpitu uruchamiam skrypt /home/polcraft/Pulpit/python/start_squirrel.py
- skrypt zamyka i kończy poprzednie transmisje na kanale oraz tworzy nową transmisję youtube, usyskuje klucz transmisji i zapisuje go w katalogu /home/polcraft/Pulpit/BOCIANY/klucz_squirrel.txt, uzyskuje videoId transmisji i zapisuje go w katalogu /home/polcraft/Pulpit/python/current_video_id_squirrel.txt oraz wysyła przez ssh na serwer www. Uruchomiony przy starcie systemu jako usługa squirrel.service skrypt /home/polcraft/Pulpit/BOCIANY/SQUIRREL.sh uruchamia usługę squirrelSRV.service która uruchamia skrypt ffmpeg /home/polcraft/Pulpit/BOCIANY/squirrelSRV.sh
