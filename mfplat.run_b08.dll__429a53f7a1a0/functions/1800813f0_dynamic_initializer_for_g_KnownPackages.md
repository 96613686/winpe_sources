# _dynamic_initializer_for__g_KnownPackages__

- ea: `0x1800813f0`
- end: `0x180081a9f`
- name: `_dynamic_initializer_for__g_KnownPackages__`
- size: `1711`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## string_xrefs

- `0x180081915`: `DolbyLaboratories.DolbyVisionAccess_rz1tebttyb220`
- `0x180081511`: `Microsoft.RawImageExtension_8wekyb3d8bbwe`
- `0x180081706`: `Microsoft.WebMediaExtensions`
- `0x1800816af`: `Microsoft.HEVCVideoExtensions`
- `0x1800818cd`: `Microsoft.DolbyAudioExtensions_8wekyb3d8bbwe`
- `0x1800816d3`: `Microsoft.AV1VideoExtension`
- `0x18008164b`: `Microsoft.VP9VideoExtensions_8wekyb3d8bbwe`
- `0x1800816f1`: `Microsoft.WebMediaExtensions_8wekyb3d8bbwe`
- `0x18008151f`: `Microsoft.RawImageExtension`
- `0x180081885`: `Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe`
- `0x18008168b`: `Microsoft.HEVCVideoExtension`
- `0x1800818db`: `Microsoft.DolbyAudioExtensions`
- `0x1800816a1`: `Microsoft.HEVCVideoExtensions_8wekyb3d8bbwe`
- `0x180081893`: `Microsoft.AV1EncoderVideoExtension`
- `0x18008142b`: `Microsoft.MPEG2VideoExtension_8wekyb3d8bbwe`
- `0x1800814c9`: `Microsoft.JPEG-XLImageExtension_8wekyb3d8bbwe`
- `0x18008149d`: `Microsoft.HEIFImageExtension`
- `0x18008146b`: `Microsoft.WebpImageExtension`
- `0x18008167d`: `Microsoft.HEVCVideoExtension_8wekyb3d8bbwe`
- `0x18008145d`: `Microsoft.WebpImageExtension_8wekyb3d8bbwe`
- `0x1800816c5`: `Microsoft.AV1VideoExtension_8wekyb3d8bbwe`
- `0x18008192b`: `DolbyLaboratories.DolbyVisionAccess`
- `0x1800814de`: `Microsoft.JPEG-XLImageExtension`
- `0x180081659`: `Microsoft.VP9VideoExtensions`
- `0x180081439`: `Microsoft.MPEG2VideoExtension`
- `0x18008148f`: `Microsoft.HEIFImageExtension_8wekyb3d8bbwe`

## pseudocode

```c
__int64 dynamic_initializer_for__g_KnownPackages__()
{
  __int64 result; // rax

  dword_1801F9F64 = 0;
  qword_1801F9F70 = (__int64)&word_1801CC94C;
  qword_1801F9F68 = (__int64)L"windows.mediaCodec.avc";
  qword_1801F9F78 = (__int64)L"Microsoft.MPEG2VideoExtension_8wekyb3d8bbwe";
  qword_1801F9F80 = (__int64)L"Microsoft.MPEG2VideoExtension";
  dword_1801F9FCC = 0;
  qword_1801F9FD0 = (__int64)L"windows.mediaCodec.mpeg2";
  qword_1801F9FE0 = (__int64)L"Microsoft.WebpImageExtension_8wekyb3d8bbwe";
  qword_1801F9FE8 = (__int64)L"Microsoft.WebpImageExtension";
  dword_1801FA034 = 0;
  qword_1801FA038 = (__int64)L"windows.mediaCodec.webp";
  qword_1801FA048 = (__int64)L"Microsoft.HEIFImageExtension_8wekyb3d8bbwe";
  qword_1801FA050 = (__int64)L"Microsoft.HEIFImageExtension";
  dword_1801FA09C = 0;
  xmmword_1801F9F44 = (__int128)MFVideoFormat_H264;
  qword_1801FA0A0 = (__int64)L"windows.mediaCodec.heif";
  qword_1801FA0B0 = (__int64)L"Microsoft.JPEG-XLImageExtension_8wekyb3d8bbwe";
  qword_1801FA0B8 = (__int64)L"Microsoft.JPEG-XLImageExtension";
  xmmword_1801F9F8C = (__int128)MFVideoFormat_MPG1;
  dword_1801FA104 = 0;
  qword_1801FA108 = (__int64)L"windows.mediaCodec.jpegXL";
  qword_1801FA118 = (__int64)L"Microsoft.RawImageExtension_8wekyb3d8bbwe";
  xmmword_1801F9FF4 = (__int128)CLSID_WICWebpDecoder;
  qword_1801FA120 = (__int64)L"Microsoft.RawImageExtension";
  word_1801F9F88 = 1;
  byte_1801F9F8A = 0;
  xmmword_1801FA05C = (__int128)CLSID_WICHeifDecoder;
  qword_1801F9FD8 = (__int64)&word_1801CC94C;
  word_1801F9FF0 = 1;
  xmmword_1801F9F9C = (__int128)MFVideoFormat_MPEG2;
  byte_1801F9FF2 = 0;
  xmmword_1801FA07C = (__int128)CLSID_WICHeifEncoder;
  qword_1801FA040 = (__int64)&word_1801CC94C;
  word_1801FA058 = 1;
  xmmword_1801F9FAC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  byte_1801FA05A = 0;
  xmmword_1801FA0C4 = (__int128)CLSID_WICJpegXLDecoder;
  qword_1801FA0A8 = (__int64)&word_1801CC94C;
  word_1801FA0C0 = 1;
  xmmword_1801F9FBC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  byte_1801FA0C2 = 0;
  xmmword_1801FA004 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA110 = (__int64)&word_1801CC94C;
  xmmword_1801FA014 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA024 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA06C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA08C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA0D4 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA0E4 = (__int128)CLSID_WICJpegXLEncoder;
  xmmword_1801FA0F4 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  dword_1801FA16C = 0;
  qword_1801FA170 = (__int64)L"windows.mediaCodec.raw";
  qword_1801FA180 = (__int64)L"Microsoft.VP9VideoExtensions_8wekyb3d8bbwe";
  qword_1801FA188 = (__int64)L"Microsoft.VP9VideoExtensions";
  dword_1801FA1D4 = 0;
  qword_1801FA1D8 = (__int64)L"windows.mediaCodec.vp9";
  qword_1801FA1E8 = (__int64)L"Microsoft.HEVCVideoExtension_8wekyb3d8bbwe";
  qword_1801FA1F0 = (__int64)L"Microsoft.HEVCVideoExtension";
  dword_1801FA23C = 0;
  qword_1801FA250 = (__int64)L"Microsoft.HEVCVideoExtensions_8wekyb3d8bbwe";
  qword_1801FA258 = (__int64)L"Microsoft.HEVCVideoExtensions";
  dword_1801FA2A4 = 0;
  qword_1801FA2B8 = (__int64)L"Microsoft.AV1VideoExtension_8wekyb3d8bbwe";
  qword_1801FA2C0 = (__int64)L"Microsoft.AV1VideoExtension";
  xmmword_1801FA12C = (__int128)CLSID_WICRAWDecoder;
  dword_1801FA30C = 0;
  qword_1801FA320 = (__int64)L"Microsoft.WebMediaExtensions_8wekyb3d8bbwe";
  xmmword_1801FA194 = (__int128)MFVideoFormat_VP90;
  qword_1801FA240 = (__int64)L"windows.mediaCodec.hevc";
  xmmword_1801FA1A4 = (__int128)MFVideoFormat_VP80;
  qword_1801FA2A8 = (__int64)L"windows.mediaCodec.hevc";
  xmmword_1801FA1B4 = (__int128)MFVideoFormat_VP90;
  qword_1801FA328 = (__int64)L"Microsoft.WebMediaExtensions";
  word_1801FA128 = 0;
  xmmword_1801FA1C4 = (__int128)MFVideoFormat_VP80;
  byte_1801FA12A = 0;
  qword_1801FA178 = (__int64)&word_1801CC94C;
  xmmword_1801FA13C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  word_1801FA190 = 257;
  xmmword_1801FA14C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  byte_1801FA192 = 0;
  xmmword_1801FA15C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA1E0 = (__int64)&word_1801CC94C;
  word_1801FA1F8 = 257;
  byte_1801FA1FA = 0;
  xmmword_1801FA1FC = (__int128)MFVideoFormat_HEVC;
  qword_1801FA248 = (__int64)&word_1801CC94C;
  xmmword_1801FA20C = (__int128)MFVideoFormat_HEVC_ES;
  word_1801FA260 = 257;
  xmmword_1801FA21C = (__int128)MFVideoFormat_HEVC;
  byte_1801FA262 = 1;
  xmmword_1801FA22C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA2B0 = (__int64)&word_1801CC94C;
  xmmword_1801FA264 = (__int128)MFVideoFormat_HEVC;
  word_1801FA2C8 = 257;
  xmmword_1801FA274 = (__int128)MFVideoFormat_HEVC_ES;
  byte_1801FA2CA = 0;
  xmmword_1801FA284 = (__int128)MFVideoFormat_HEVC;
  qword_1801FA310 = (__int64)L"windows.mediaCodec.av1";
  xmmword_1801FA294 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA318 = (__int64)&word_1801CC94C;
  xmmword_1801FA2CC = (__int128)MFVideoFormat_AV1;
  word_1801FA330 = 256;
  xmmword_1801FA2DC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA2EC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA2FC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA3E0 = (__int64)L"windows.mediaCodec.av1";
  dword_1801FA374 = 0;
  qword_1801FA448 = (__int64)L"windows.mediaCodec.dolbyDigitalPlus";
  qword_1801FA378 = (__int64)L"windows.mediaCodec.wme";
  qword_1801FA388 = (__int64)L"Microsoft.AV1EncoderVideoExtension_8wekyb3d8bbwe";
  qword_1801FA390 = (__int64)L"Microsoft.AV1EncoderVideoExtension";
  dword_1801FA3DC = 0;
  qword_1801FA3F0 = (__int64)L"DolbyLaboratories.DolbyDigitalPlusDecoderOEM_rz1tebttyb220";
  qword_1801FA3F8 = (__int64)L"DolbyLaboratories.DolbyDigitalPlusDecoderOEM";
  dword_1801FA444 = 0;
  qword_1801FA458 = (__int64)L"Microsoft.DolbyAudioExtensions_8wekyb3d8bbwe";
  qword_1801FA460 = (__int64)L"Microsoft.DolbyAudioExtensions";
  dword_1801FA4AC = 0;
  qword_1801FA4C0 = (__int64)L"DolbyLaboratories.DolbyVisionHDR_rz1tebttyb220";
  qword_1801FA4C8 = (__int64)L"DolbyLaboratories.DolbyVisionHDR";
  dword_1801FA514 = 0;
  xmmword_1801FA334 = MFVideoFormat_Theora;
  qword_1801FA528 = (__int64)L"DolbyLaboratories.DolbyVisionAccess_rz1tebttyb220";
  qword_1801FA4B0 = (__int64)L"windows.mediaCodec.dolbyDigitalPlus";
  xmmword_1801FA344 = (__int128)MFAudioFormat_Vorbis;
  qword_1801FA530 = (__int64)L"DolbyLaboratories.DolbyVisionAccess";
  byte_1801FA332 = 0;
  xmmword_1801FA354 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA380 = (__int64)&word_1801CC94C;
  xmmword_1801FA364 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  word_1801FA398 = 1;
  byte_1801FA39A = 0;
  xmmword_1801FA39C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA3E8 = (__int64)&word_1801CC94C;
  xmmword_1801FA3AC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  word_1801FA400 = 257;
  xmmword_1801FA3BC = (__int128)MFVideoFormat_AV1;
  byte_1801FA402 = 0;
  xmmword_1801FA3CC = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA450 = (__int64)&word_1801CC94C;
  xmmword_1801FA404 = (__int128)MFAudioFormat_Dolby_DDPlus;
  word_1801FA468 = 257;
  xmmword_1801FA414 = (__int128)MFAudioFormat_Dolby_AC3;
  byte_1801FA46A = 0;
  xmmword_1801FA424 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA4B8 = (__int64)&word_1801CC94C;
  xmmword_1801FA434 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  word_1801FA4D0 = 1;
  xmmword_1801FA46C = (__int128)MFAudioFormat_Dolby_DDPlus;
  byte_1801FA4D2 = 0;
  xmmword_1801FA47C = (__int128)MFAudioFormat_Dolby_AC3;
  qword_1801FA518 = (__int64)L"windows.mediaCodec.dolbyVision";
  xmmword_1801FA48C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA520 = (__int64)&word_1801CC94C;
  xmmword_1801FA49C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  word_1801FA538 = 1;
  xmmword_1801FA4D4 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  byte_1801FA53A = 0;
  xmmword_1801FA4E4 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA4F4 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA504 = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA53C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA54C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  xmmword_1801FA55C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  result = 0;
  qword_1801FA580 = (__int64)L"windows.mediaCodec.dolbyVision";
  dword_1801FA57C = 0;
  xmmword_1801FA56C = (__int128)GUID_00000000_0000_0000_0000_000000000000;
  qword_1801FA588 = (__int64)&word_1801CC94C;
  return result;
}

```

## disassembly

```asm
0x1800813f0  movups  xmm3, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800813f7  xor     eax, eax
0x1800813f9  xor     edx, edx
0x1800813fb  movups  xmm0, xmmword ptr cs:MFVideoFormat_H264.Data1
0x180081402  mov     cs:dword_1801F9F64, eax
0x180081408  lea     r8, word_1801CC94C
0x18008140f  movups  xmm1, xmmword ptr cs:MFVideoFormat_MPEG2.Data1
0x180081416  lea     rax, aWindowsMediaco_11; "windows.mediaCodec.avc"
0x18008141d  mov     cs:qword_1801F9F70, r8
0x180081424  mov     cs:qword_1801F9F68, rax
0x18008142b  lea     rax, aMicrosoftMpeg2_0; "Microsoft.MPEG2VideoExtension_8wekyb3d8"...
0x180081432  mov     cs:qword_1801F9F78, rax
0x180081439  lea     rax, aMicrosoftMpeg2; "Microsoft.MPEG2VideoExtension"
0x180081440  mov     cs:qword_1801F9F80, rax
0x180081447  xor     eax, eax
0x180081449  mov     cs:dword_1801F9FCC, eax
0x18008144f  lea     rax, aWindowsMediaco_4; "windows.mediaCodec.mpeg2"
0x180081456  mov     cs:qword_1801F9FD0, rax
0x18008145d  lea     rax, aMicrosoftWebpi; "Microsoft.WebpImageExtension_8wekyb3d8b"...
0x180081464  mov     cs:qword_1801F9FE0, rax
0x18008146b  lea     rax, aMicrosoftWebpi_0; "Microsoft.WebpImageExtension"
0x180081472  mov     cs:qword_1801F9FE8, rax
0x180081479  xor     eax, eax
0x18008147b  mov     cs:dword_1801FA034, eax
0x180081481  lea     rax, aWindowsMediaco_12; "windows.mediaCodec.webp"
0x180081488  mov     cs:qword_1801FA038, rax
0x18008148f  lea     rax, aMicrosoftHeifi_0; "Microsoft.HEIFImageExtension_8wekyb3d8b"...
0x180081496  mov     cs:qword_1801FA048, rax
0x18008149d  lea     rax, aMicrosoftHeifi; "Microsoft.HEIFImageExtension"
0x1800814a4  mov     cs:qword_1801FA050, rax
0x1800814ab  xor     eax, eax
0x1800814ad  mov     cs:dword_1801FA09C, eax
0x1800814b3  lea     rax, aWindowsMediaco; "windows.mediaCodec.heif"
0x1800814ba  movdqu  cs:xmmword_1801F9F44, xmm0
0x1800814c2  mov     cs:qword_1801FA0A0, rax
0x1800814c9  lea     rax, aMicrosoftJpegX; "Microsoft.JPEG-XLImageExtension_8wekyb3"...
0x1800814d0  movups  xmm0, xmmword ptr cs:MFVideoFormat_MPG1.Data1
0x1800814d7  mov     cs:qword_1801FA0B0, rax
0x1800814de  lea     rax, aMicrosoftJpegX_0; "Microsoft.JPEG-XLImageExtension"
0x1800814e5  mov     cs:qword_1801FA0B8, rax
0x1800814ec  xor     eax, eax
0x1800814ee  movdqu  cs:xmmword_1801F9F8C, xmm0
0x1800814f6  mov     cs:dword_1801FA104, eax
0x1800814fc  lea     rax, aWindowsMediaco_10; "windows.mediaCodec.jpegXL"
0x180081503  movups  xmm0, xmmword ptr cs:CLSID_WICWebpDecoder.Data1
0x18008150a  mov     cs:qword_1801FA108, rax
0x180081511  lea     rax, aMicrosoftRawim; "Microsoft.RawImageExtension_8wekyb3d8bb"...
0x180081518  mov     cs:qword_1801FA118, rax
0x18008151f  lea     rax, aMicrosoftRawim_0; "Microsoft.RawImageExtension"
0x180081526  movdqu  cs:xmmword_1801F9FF4, xmm0
0x18008152e  mov     cs:qword_1801FA120, rax
0x180081535  movups  xmm0, xmmword ptr cs:CLSID_WICHeifDecoder.Data1
0x18008153c  mov     cs:word_1801F9F88, 1
0x180081545  mov     cs:byte_1801F9F8A, dl
0x18008154b  movdqu  cs:xmmword_1801FA05C, xmm0
0x180081553  mov     cs:qword_1801F9FD8, r8
0x18008155a  movups  xmm0, xmmword ptr cs:CLSID_WICHeifEncoder.Data1
0x180081561  mov     cs:word_1801F9FF0, 1
0x18008156a  movdqu  cs:xmmword_1801F9F9C, xmm1
0x180081572  mov     cs:byte_1801F9FF2, dl
0x180081578  movdqu  cs:xmmword_1801FA07C, xmm0
0x180081580  mov     cs:qword_1801FA040, r8
0x180081587  movups  xmm0, xmmword ptr cs:CLSID_WICJpegXLDecoder.Data1
0x18008158e  mov     cs:word_1801FA058, 1
0x180081597  movdqu  cs:xmmword_1801F9FAC, xmm3
0x18008159f  mov     cs:byte_1801FA05A, dl
0x1800815a5  movdqu  cs:xmmword_1801FA0C4, xmm0
0x1800815ad  mov     cs:qword_1801FA0A8, r8
0x1800815b4  movups  xmm0, xmmword ptr cs:CLSID_WICJpegXLEncoder.Data1
0x1800815bb  mov     cs:word_1801FA0C0, 1
0x1800815c4  movdqu  cs:xmmword_1801F9FBC, xmm3
0x1800815cc  mov     cs:byte_1801FA0C2, dl
0x1800815d2  movdqu  cs:xmmword_1801FA004, xmm3
0x1800815da  mov     cs:qword_1801FA110, r8
0x1800815e1  movdqu  cs:xmmword_1801FA014, xmm3
0x1800815e9  movdqu  cs:xmmword_1801FA024, xmm3
0x1800815f1  movdqu  cs:xmmword_1801FA06C, xmm3
0x1800815f9  movdqu  cs:xmmword_1801FA08C, xmm3
0x180081601  movdqu  cs:xmmword_1801FA0D4, xmm3
0x180081609  movdqu  cs:xmmword_1801FA0E4, xmm0
0x180081611  movdqu  cs:xmmword_1801FA0F4, xmm3
0x180081619  movups  xmm1, xmmword ptr cs:MFVideoFormat_VP90.Data1
0x180081620  xor     eax, eax
0x180081622  lea     rcx, aWindowsMediaco_2; "windows.mediaCodec.hevc"
0x180081629  movups  xmm0, xmmword ptr cs:CLSID_WICRAWDecoder.Data1
0x180081630  mov     cs:dword_1801FA16C, eax
0x180081636  lea     rax, aWindowsMediaco_6; "windows.mediaCodec.raw"
0x18008163d  movups  xmm2, xmmword ptr cs:MFVideoFormat_AV1.Data1
0x180081644  mov     cs:qword_1801FA170, rax
0x18008164b  lea     rax, aMicrosoftVp9vi_0; "Microsoft.VP9VideoExtensions_8wekyb3d8b"...
0x180081652  mov     cs:qword_1801FA180, rax
0x180081659  lea     rax, aMicrosoftVp9vi; "Microsoft.VP9VideoExtensions"
0x180081660  mov     cs:qword_1801FA188, rax
0x180081667  xor     eax, eax
0x180081669  mov     cs:dword_1801FA1D4, eax
0x18008166f  lea     rax, aWindowsMediaco_8; "windows.mediaCodec.vp9"
0x180081676  mov     cs:qword_1801FA1D8, rax
0x18008167d  lea     rax, aMicrosoftHevcv_1; "Microsoft.HEVCVideoExtension_8wekyb3d8b"...
0x180081684  mov     cs:qword_1801FA1E8, rax
0x18008168b  lea     rax, aMicrosoftHevcv_0; "Microsoft.HEVCVideoExtension"
0x180081692  mov     cs:qword_1801FA1F0, rax
0x180081699  xor     eax, eax
0x18008169b  mov     cs:dword_1801FA23C, eax
0x1800816a1  lea     rax, aMicrosoftHevcv_2; "Microsoft.HEVCVideoExtensions_8wekyb3d8"...
0x1800816a8  mov     cs:qword_1801FA250, rax
0x1800816af  lea     rax, aMicrosoftHevcv; "Microsoft.HEVCVideoExtensions"
0x1800816b6  mov     cs:qword_1801FA258, rax
0x1800816bd  xor     eax, eax
0x1800816bf  mov     cs:dword_1801FA2A4, eax
0x1800816c5  lea     rax, aMicrosoftAv1vi_0; "Microsoft.AV1VideoExtension_8wekyb3d8bb"...
0x1800816cc  mov     cs:qword_1801FA2B8, rax
0x1800816d3  lea     rax, aMicrosoftAv1vi; "Microsoft.AV1VideoExtension"
0x1800816da  mov     cs:qword_1801FA2C0, rax
0x1800816e1  xor     eax, eax
0x1800816e3  movdqu  cs:xmmword_1801FA12C, xmm0
0x1800816eb  mov     cs:dword_1801FA30C, eax
0x1800816f1  lea     rax, aMicrosoftWebme; "Microsoft.WebMediaExtensions_8wekyb3d8b"...
0x1800816f8  movups  xmm0, xmmword ptr cs:MFVideoFormat_VP80.Data1
0x1800816ff  mov     cs:qword_1801FA320, rax
0x180081706  lea     rax, aMicrosoftWebme_0; "Microsoft.WebMediaExtensions"
0x18008170d  movdqu  cs:xmmword_1801FA194, xmm1
0x180081715  mov     cs:qword_1801FA240, rcx
0x18008171c  movdqu  cs:xmmword_1801FA1A4, xmm0
0x180081724  mov     cs:qword_1801FA2A8, rcx
0x18008172b  lea     rcx, aWindowsMediaco_5; "windows.mediaCodec.av1"
0x180081732  movdqu  cs:xmmword_1801FA1B4, xmm1
0x18008173a  mov     cs:qword_1801FA328, rax
0x180081741  movups  xmm1, xmmword ptr cs:MFVideoFormat_HEVC.Data1
0x180081748  mov     cs:word_1801FA128, dx
0x18008174f  movdqu  cs:xmmword_1801FA1C4, xmm0
0x180081757  mov     cs:byte_1801FA12A, dl
0x18008175d  movups  xmm0, xmmword ptr cs:MFVideoFormat_HEVC_ES.Data1
0x180081764  mov     cs:qword_1801FA178, r8
0x18008176b  movdqu  cs:xmmword_1801FA13C, xmm3
0x180081773  mov     cs:word_1801FA190, 101h
0x18008177c  movdqu  cs:xmmword_1801FA14C, xmm3
0x180081784  mov     cs:byte_1801FA192, dl
0x18008178a  movdqu  cs:xmmword_1801FA15C, xmm3
0x180081792  mov     cs:qword_1801FA1E0, r8
0x180081799  mov     cs:word_1801FA1F8, 101h
0x1800817a2  mov     cs:byte_1801FA1FA, dl
0x1800817a8  movdqu  cs:xmmword_1801FA1FC, xmm1
0x1800817b0  mov     cs:qword_1801FA248, r8
0x1800817b7  movdqu  cs:xmmword_1801FA20C, xmm0
0x1800817bf  mov     cs:word_1801FA260, 101h
0x1800817c8  movdqu  cs:xmmword_1801FA21C, xmm1
0x1800817d0  mov     cs:byte_1801FA262, 1
0x1800817d7  movdqu  cs:xmmword_1801FA22C, xmm3
0x1800817df  mov     cs:qword_1801FA2B0, r8
0x1800817e6  movdqu  cs:xmmword_1801FA264, xmm1
0x1800817ee  mov     cs:word_1801FA2C8, 101h
0x1800817f7  movdqu  cs:xmmword_1801FA274, xmm0
0x1800817ff  mov     cs:byte_1801FA2CA, dl
0x180081805  movdqu  cs:xmmword_1801FA284, xmm1
0x18008180d  mov     cs:qword_1801FA310, rcx
0x180081814  movdqu  cs:xmmword_1801FA294, xmm3
0x18008181c  mov     cs:qword_1801FA318, r8
0x180081823  movdqu  cs:xmmword_1801FA2CC, xmm2
0x18008182b  mov     cs:word_1801FA330, 100h
0x180081834  movdqu  cs:xmmword_1801FA2DC, xmm3
0x18008183c  movdqu  cs:xmmword_1801FA2EC, xmm3
0x180081844  movdqu  cs:xmmword_1801FA2FC, xmm3
0x18008184c  movups  xmm0, cs:MFVideoFormat_Theora
0x180081853  xor     eax, eax
0x180081855  mov     cs:qword_1801FA3E0, rcx
0x18008185c  movups  xmm1, xmmword ptr cs:MFAudioFormat_Vorbis.Data1
0x180081863  mov     cs:dword_1801FA374, eax
0x180081869  lea     rcx, aWindowsMediaco_7; "windows.mediaCodec.dolbyDigitalPlus"
0x180081870  lea     rax, aWindowsMediaco_3; "windows.mediaCodec.wme"
0x180081877  mov     cs:qword_1801FA448, rcx
0x18008187e  mov     cs:qword_1801FA378, rax
0x180081885  lea     rax, aMicrosoftAv1en; "Microsoft.AV1EncoderVideoExtension_8wek"...
0x18008188c  mov     cs:qword_1801FA388, rax
0x180081893  lea     rax, aMicrosoftAv1en_0; "Microsoft.AV1EncoderVideoExtension"
0x18008189a  mov     cs:qword_1801FA390, rax
0x1800818a1  xor     eax, eax
0x1800818a3  mov     cs:dword_1801FA3DC, eax
0x1800818a9  lea     rax, aDolbylaborator_1; "DolbyLaboratories.DolbyDigitalPlusDecod"...
0x1800818b0  mov     cs:qword_1801FA3F0, rax
0x1800818b7  lea     rax, aDolbylaborator_4; "DolbyLaboratories.DolbyDigitalPlusDecod"...
0x1800818be  mov     cs:qword_1801FA3F8, rax
0x1800818c5  xor     eax, eax
0x1800818c7  mov     cs:dword_1801FA444, eax
0x1800818cd  lea     rax, aMicrosoftDolby; "Microsoft.DolbyAudioExtensions_8wekyb3d"...
0x1800818d4  mov     cs:qword_1801FA458, rax
0x1800818db  lea     rax, aMicrosoftDolby_0; "Microsoft.DolbyAudioExtensions"
0x1800818e2  mov     cs:qword_1801FA460, rax
0x1800818e9  xor     eax, eax
0x1800818eb  mov     cs:dword_1801FA4AC, eax
0x1800818f1  lea     rax, aDolbylaborator; "DolbyLaboratories.DolbyVisionHDR_rz1teb"...
0x1800818f8  mov     cs:qword_1801FA4C0, rax
0x1800818ff  lea     rax, aDolbylaborator_0; "DolbyLaboratories.DolbyVisionHDR"
0x180081906  mov     cs:qword_1801FA4C8, rax
0x18008190d  xor     eax, eax
0x18008190f  mov     cs:dword_1801FA514, eax
0x180081915  lea     rax, aDolbylaborator_3; "DolbyLaboratories.DolbyVisionAccess_rz1"...
0x18008191c  movdqu  cs:xmmword_1801FA334, xmm0
0x180081924  mov     cs:qword_1801FA528, rax
0x18008192b  lea     rax, aDolbylaborator_2; "DolbyLaboratories.DolbyVisionAccess"
0x180081932  movups  xmm0, xmmword ptr cs:MFAudioFormat_Dolby_AC3.Data1
0x180081939  mov     cs:qword_1801FA4B0, rcx
0x180081940  lea     rcx, aWindowsMediaco_1; "windows.mediaCodec.dolbyVision"
0x180081947  movdqu  cs:xmmword_1801FA344, xmm1
0x18008194f  mov     cs:qword_1801FA530, rax
0x180081956  movups  xmm1, xmmword ptr cs:MFAudioFormat_Dolby_DDPlus.Data1
0x18008195d  mov     cs:byte_1801FA332, dl
0x180081963  movdqu  cs:xmmword_1801FA354, xmm3
0x18008196b  mov     cs:qword_1801FA380, r8
0x180081972  movdqu  cs:xmmword_1801FA364, xmm3
0x18008197a  mov     cs:word_1801FA398, 1
0x180081983  mov     cs:byte_1801FA39A, dl
0x180081989  movdqu  cs:xmmword_1801FA39C, xmm3
0x180081991  mov     cs:qword_1801FA3E8, r8
0x180081998  movdqu  cs:xmmword_1801FA3AC, xmm3
0x1800819a0  mov     cs:word_1801FA400, 101h
0x1800819a9  movdqu  cs:xmmword_1801FA3BC, xmm2
0x1800819b1  mov     cs:byte_1801FA402, dl
0x1800819b7  movdqu  cs:xmmword_1801FA3CC, xmm3
0x1800819bf  mov     cs:qword_1801FA450, r8
0x1800819c6  movdqu  cs:xmmword_1801FA404, xmm1
0x1800819ce  mov     cs:word_1801FA468, 101h
0x1800819d7  movdqu  cs:xmmword_1801FA414, xmm0
0x1800819df  mov     cs:byte_1801FA46A, dl
0x1800819e5  movdqu  cs:xmmword_1801FA424, xmm3
0x1800819ed  mov     cs:qword_1801FA4B8, r8
0x1800819f4  movdqu  cs:xmmword_1801FA434, xmm3
0x1800819fc  mov     cs:word_1801FA4D0, 1
0x180081a05  movdqu  cs:xmmword_1801FA46C, xmm1
0x180081a0d  mov     cs:byte_1801FA4D2, dl
0x180081a13  movdqu  cs:xmmword_1801FA47C, xmm0
0x180081a1b  mov     cs:qword_1801FA518, rcx
0x180081a22  movdqu  cs:xmmword_1801FA48C, xmm3
0x180081a2a  mov     cs:qword_1801FA520, r8
0x180081a31  movdqu  cs:xmmword_1801FA49C, xmm3
0x180081a39  mov     cs:word_1801FA538, 1
0x180081a42  movdqu  cs:xmmword_1801FA4D4, xmm3
0x180081a4a  mov     cs:byte_1801FA53A, dl
0x180081a50  movdqu  cs:xmmword_1801FA4E4, xmm3
0x180081a58  movdqu  cs:xmmword_1801FA4F4, xmm3
0x180081a60  movdqu  cs:xmmword_1801FA504, xmm3
0x180081a68  movdqu  cs:xmmword_1801FA53C, xmm3
0x180081a70  movdqu  cs:xmmword_1801FA54C, xmm3
0x180081a78  movdqu  cs:xmmword_1801FA55C, xmm3
0x180081a80  xor     eax, eax
0x180081a82  mov     cs:qword_1801FA580, rcx
0x180081a89  mov     cs:dword_1801FA57C, eax
0x180081a8f  movdqu  cs:xmmword_1801FA56C, xmm3
0x180081a97  mov     cs:qword_1801FA588, r8
0x180081a9e  retn
```
