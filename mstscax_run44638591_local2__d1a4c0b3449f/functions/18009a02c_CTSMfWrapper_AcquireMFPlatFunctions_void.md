# CTSMfWrapper::AcquireMFPlatFunctions(void)

- ea: `0x18009a02c`
- end: `0x18009ab74`
- name: `?AcquireMFPlatFunctions@CTSMfWrapper@@AEAAJXZ`
- size: `2888`
- prototype: `__int64 __fastcall(CTSMfWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x180445080`

## callees

- `0x18002a334`
- `0x180039c98`
- `0x180039ce4`
- `0x18009a02c`
- `0x1800e9b1c`
- `0x180444e74`
- `0x180688f3e`
- `0x180688fc0`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18009a0a7`
- `msvcrt!wcsnlen` at `0x18009a0a7`
- `msvcrt!wcscat_s` at `0x18009a0c7`
- `msvcrt!wcscat_s` at `0x18009a0c7`
- `KERNEL32!LoadLibraryW` at `0x18009a132`
- `KERNEL32!LoadLibraryW` at `0x18009a132`
- `KERNEL32!SetErrorMode` at `0x18009a05a`
- `KERNEL32!SetErrorMode` at `0x18009ab48`
- `KERNEL32!SetErrorMode` at `0x18009a05a`
- `KERNEL32!SetErrorMode` at `0x18009ab48`
- `KERNEL32!GetLastError` at `0x18009a147`
- `KERNEL32!GetLastError` at `0x18009a195`
- `KERNEL32!GetLastError` at `0x18009a23f`
- `KERNEL32!GetLastError` at `0x18009a2ba`
- `KERNEL32!GetLastError` at `0x18009a335`
- `KERNEL32!GetLastError` at `0x18009a3b0`
- `KERNEL32!GetLastError` at `0x18009a42b`
- `KERNEL32!GetLastError` at `0x18009a4a6`
- `KERNEL32!GetLastError` at `0x18009a521`
- `KERNEL32!GetLastError` at `0x18009a59c`
- `KERNEL32!GetLastError` at `0x18009a617`
- `KERNEL32!GetLastError` at `0x18009a692`
- `KERNEL32!GetLastError` at `0x18009a70d`
- `KERNEL32!GetLastError` at `0x18009a788`
- `KERNEL32!GetLastError` at `0x18009a803`
- `KERNEL32!GetLastError` at `0x18009a87e`
- `KERNEL32!GetLastError` at `0x18009a8f9`
- `KERNEL32!GetLastError` at `0x18009a974`
- `KERNEL32!GetLastError` at `0x18009a9ef`
- `KERNEL32!GetLastError` at `0x18009aa6a`
- `KERNEL32!GetLastError` at `0x18009aae5`
- `KERNEL32!GetLastError` at `0x18009a147`
- `KERNEL32!GetLastError` at `0x18009a195`
- `KERNEL32!GetLastError` at `0x18009a23f`
- `KERNEL32!GetLastError` at `0x18009a2ba`
- `KERNEL32!GetLastError` at `0x18009a335`
- `KERNEL32!GetLastError` at `0x18009a3b0`
- `KERNEL32!GetLastError` at `0x18009a42b`
- `KERNEL32!GetLastError` at `0x18009a4a6`
- `KERNEL32!GetLastError` at `0x18009a521`
- `KERNEL32!GetLastError` at `0x18009a59c`
- `KERNEL32!GetLastError` at `0x18009a617`
- `KERNEL32!GetLastError` at `0x18009a692`
- `KERNEL32!GetLastError` at `0x18009a70d`
- `KERNEL32!GetLastError` at `0x18009a788`
- `KERNEL32!GetLastError` at `0x18009a803`
- `KERNEL32!GetLastError` at `0x18009a87e`
- `KERNEL32!GetLastError` at `0x18009a8f9`
- `KERNEL32!GetLastError` at `0x18009a974`
- `KERNEL32!GetLastError` at `0x18009a9ef`
- `KERNEL32!GetLastError` at `0x18009aa6a`
- `KERNEL32!GetLastError` at `0x18009aae5`
- `KERNEL32!GetProcAddress` at `0x18009a213`
- `KERNEL32!GetProcAddress` at `0x18009a2a8`
- `KERNEL32!GetProcAddress` at `0x18009a323`
- `KERNEL32!GetProcAddress` at `0x18009a39e`
- `KERNEL32!GetProcAddress` at `0x18009a419`
- `KERNEL32!GetProcAddress` at `0x18009a494`
- `KERNEL32!GetProcAddress` at `0x18009a50f`
- `KERNEL32!GetProcAddress` at `0x18009a58a`
- `KERNEL32!GetProcAddress` at `0x18009a605`
- `KERNEL32!GetProcAddress` at `0x18009a680`
- `KERNEL32!GetProcAddress` at `0x18009a6fb`
- `KERNEL32!GetProcAddress` at `0x18009a776`
- `KERNEL32!GetProcAddress` at `0x18009a7f1`
- `KERNEL32!GetProcAddress` at `0x18009a86c`
- `KERNEL32!GetProcAddress` at `0x18009a8e7`
- `KERNEL32!GetProcAddress` at `0x18009a962`
- `KERNEL32!GetProcAddress` at `0x18009a9dd`
- `KERNEL32!GetProcAddress` at `0x18009aa58`
- `KERNEL32!GetProcAddress` at `0x18009aad3`
- `KERNEL32!GetProcAddress` at `0x18009a213`
- `KERNEL32!GetProcAddress` at `0x18009a2a8`
- `KERNEL32!GetProcAddress` at `0x18009a323`
- `KERNEL32!GetProcAddress` at `0x18009a39e`
- `KERNEL32!GetProcAddress` at `0x18009a419`
- `KERNEL32!GetProcAddress` at `0x18009a494`
- `KERNEL32!GetProcAddress` at `0x18009a50f`
- `KERNEL32!GetProcAddress` at `0x18009a58a`
- `KERNEL32!GetProcAddress` at `0x18009a605`
- `KERNEL32!GetProcAddress` at `0x18009a680`
- `KERNEL32!GetProcAddress` at `0x18009a6fb`
- `KERNEL32!GetProcAddress` at `0x18009a776`
- `KERNEL32!GetProcAddress` at `0x18009a7f1`
- `KERNEL32!GetProcAddress` at `0x18009a86c`
- `KERNEL32!GetProcAddress` at `0x18009a8e7`
- `KERNEL32!GetProcAddress` at `0x18009a962`
- `KERNEL32!GetProcAddress` at `0x18009a9dd`
- `KERNEL32!GetProcAddress` at `0x18009aa58`
- `KERNEL32!GetProcAddress` at `0x18009aad3`
- `KERNEL32!GetSystemDirectoryW` at `0x18009a08e`
- `KERNEL32!GetSystemDirectoryW` at `0x18009a08e`

## string_xrefs

- `0x18009a209`: `MFCreateAudioMediaType`
- `0x18009a412`: `MFCreateAMMediaTypeFromMFMediaType`
- `0x18009a508`: `MFCreatePresentationDescriptor`
- `0x18009aa51`: `MFCreateFile`
- `0x18009a583`: `MFCreateMemoryBuffer`
- `0x18009a7ea`: `MFCreateAsyncResult`
- `0x18009a9d6`: `MFCreateSystemTimeSource`
- `0x18009a2a1`: `MFCreateMediaType`
- `0x18009a48d`: `MFCreateStreamDescriptor`
- `0x18009a865`: `MFCreateMediaEvent`
- `0x18009aacc`: `MFCreateDXGIDeviceManager`
- `0x18009a76f`: `MFCreateSample`
- `0x18009a95b`: `MFCreateEventQueue`
- `0x18009a2ed`: `GetProcAddress( MFCreateMediaType ) failed.  Non-Fatal.`
- `0x18009a272`: `GetProcAddress( MFCreateAudioMediaType ) failed.  Non-Fatal.`
- `0x18009a0a0`: `\MFPlat.dll`
- `0x18009a0b9`: `\MFPlat.dll`
- `0x18009a554`: `GetProcAddress( MFCreatePresentationDescriptor ) failed.  Non-Fatal.`
- `0x18009a4d9`: `GetProcAddress( MFCreateStreamDescriptor ) failed.  Non-Fatal.`
- `0x18009a45e`: `GetProcAddress( MFCreateAMMediaTypeFromMFMediaType ) failed.  Non-Fatal.`
- `0x18009a7bb`: `GetProcAddress( MFCreateSample ) failed.  Non-Fatal.`
- `0x18009a5cf`: `GetProcAddress( MFCreateMemoryBuffer ) failed.  Non-Fatal.`
- `0x18009a9a7`: `GetProcAddress( MFCreateEventQueue ) failed.  Non-Fatal.`
- `0x18009a8b1`: `GetProcAddress( MFCreateMediaEvent ) failed.  Non-Fatal.`
- `0x18009a836`: `GetProcAddress( MFCreateAsyncResult ) failed.  Non-Fatal.`
- `0x18009ab18`: `GetProcAddress( MFCreateDXGIDeviceManager ) failed.  Non-Fatal.`
- `0x18009aa9d`: `GetProcAddress( MFCreateFile ) failed.  Non-Fatal.`
- `0x18009aa22`: `GetProcAddress( MFCreateSystemTimeSource ) failed.  Non-Fatal.`

## pseudocode

```c
__int64 __fastcall CTSMfWrapper::AcquireMFPlatFunctions(CTSMfWrapper *this)
{
  UINT v2; // r12d
  HMODULE LibraryW; // rax
  UINT SystemDirectoryW; // eax
  signed int v5; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  bool v7; // zf
  signed int LastError; // eax
  unsigned int v9; // eax
  __int64 v10; // rdx
  signed int v11; // eax
  FARPROC ProcAddress; // rax
  signed int v13; // eax
  signed int v14; // ebx
  unsigned int v15; // eax
  FARPROC v16; // rax
  signed int v17; // eax
  signed int v18; // ebx
  unsigned int v19; // eax
  FARPROC v20; // rax
  signed int v21; // eax
  signed int v22; // ebx
  unsigned int v23; // eax
  FARPROC v24; // rax
  signed int v25; // eax
  signed int v26; // ebx
  unsigned int v27; // eax
  FARPROC v28; // rax
  signed int v29; // eax
  signed int v30; // ebx
  unsigned int v31; // eax
  FARPROC v32; // rax
  signed int v33; // eax
  signed int v34; // ebx
  unsigned int v35; // eax
  FARPROC v36; // rax
  signed int v37; // eax
  signed int v38; // ebx
  unsigned int v39; // eax
  FARPROC v40; // rax
  signed int v41; // eax
  signed int v42; // ebx
  unsigned int v43; // eax
  FARPROC v44; // rax
  signed int v45; // eax
  signed int v46; // ebx
  unsigned int v47; // eax
  FARPROC v48; // rax
  signed int v49; // eax
  signed int v50; // ebx
  unsigned int v51; // eax
  FARPROC v52; // rax
  signed int v53; // eax
  signed int v54; // ebx
  unsigned int v55; // eax
  FARPROC v56; // rax
  signed int v57; // eax
  signed int v58; // ebx
  unsigned int v59; // eax
  FARPROC v60; // rax
  signed int v61; // eax
  signed int v62; // ebx
  unsigned int v63; // eax
  FARPROC v64; // rax
  signed int v65; // eax
  signed int v66; // ebx
  unsigned int v67; // eax
  FARPROC v68; // rax
  signed int v69; // eax
  signed int v70; // ebx
  unsigned int v71; // eax
  FARPROC v72; // rax
  signed int v73; // eax
  signed int v74; // ebx
  unsigned int v75; // eax
  FARPROC v76; // rax
  signed int v77; // eax
  signed int v78; // ebx
  unsigned int v79; // eax
  FARPROC v80; // rax
  signed int v81; // eax
  signed int v82; // ebx
  unsigned int v83; // eax
  FARPROC v84; // rax
  signed int v85; // eax
  signed int v86; // ebx
  unsigned int v87; // eax
  WCHAR Buffer[264]; // [rsp+30h] [rbp-268h] BYREF

  v2 = SetErrorMode(0x8001u);
  LibraryW = (HMODULE)*((_QWORD *)this + 8);
  if ( LibraryW )
    goto LABEL_26;
  memset_0(Buffer, 0, 0x208u);
  SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
  if ( SystemDirectoryW )
  {
    if ( SystemDirectoryW + wcsnlen(L"\\MFPlat.dll", 0x104u) <= 0x104 )
    {
      if ( wcscat_s(Buffer, 0x104u, L"\\MFPlat.dll") )
      {
        v5 = -2147467259;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            37,
            WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            CurrentThreadActivityIdPrefix);
        }
        goto LABEL_25;
      }
      LibraryW = LoadLibraryW(Buffer);
      v7 = *((_QWORD *)this + 7) == 0;
      *((_QWORD *)this + 8) = LibraryW;
      if ( v7 )
      {
        LastError = GetLastError();
        v5 = LastError;
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v9 = RdpWppGetCurrentThreadActivityIdPrefix();
          v10 = 38;
LABEL_23:
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids, v9, v5);
          goto LABEL_24;
        }
        goto LABEL_24;
      }
LABEL_26:
      ProcAddress = GetProcAddress(LibraryW, "MFCreateAudioMediaType");
      *((_QWORD *)this + 22) = ProcAddress;
      if ( !ProcAddress )
      {
        v13 = GetLastError();
        v14 = v13;
        if ( v13 > 0 )
          v14 = (unsigned __int16)v13 | 0x80070000;
        if ( v14 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v15,
            (__int64)"GetProcAddress( MFCreateAudioMediaType ) failed.  Non-Fatal.",
            v14);
        }
      }
      v16 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateMediaType");
      *((_QWORD *)this + 23) = v16;
      if ( !v16 )
      {
        v17 = GetLastError();
        v18 = v17;
        if ( v17 > 0 )
          v18 = (unsigned __int16)v17 | 0x80070000;
        if ( v18 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v19 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            40,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v19,
            (__int64)"GetProcAddress( MFCreateMediaType ) failed.  Non-Fatal.",
            v18);
        }
      }
      v20 = GetProcAddress(*((HMODULE *)this + 8), "MFInitMediaTypeFromMFVideoFormat");
      *((_QWORD *)this + 24) = v20;
      if ( !v20 )
      {
        v21 = GetLastError();
        v22 = v21;
        if ( v21 > 0 )
          v22 = (unsigned __int16)v21 | 0x80070000;
        if ( v22 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v23 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            41,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v23,
            (__int64)"GetProcAddress( MFInitMediaTypeFromMFVideoFormat ) failed.  Non-Fatal.",
            v22);
        }
      }
      v24 = GetProcAddress(*((HMODULE *)this + 8), "MFInitMediaTypeFromAMMediaType");
      *((_QWORD *)this + 25) = v24;
      if ( !v24 )
      {
        v25 = GetLastError();
        v26 = v25;
        if ( v25 > 0 )
          v26 = (unsigned __int16)v25 | 0x80070000;
        if ( v26 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v27 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            42,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v27,
            (__int64)"GetProcAddress( MFInitMediaTypeFromAMMediaType ) failed.  Non-Fatal.",
            v26);
        }
      }
      v28 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateAMMediaTypeFromMFMediaType");
      *((_QWORD *)this + 26) = v28;
      if ( !v28 )
      {
        v29 = GetLastError();
        v30 = v29;
        if ( v29 > 0 )
          v30 = (unsigned __int16)v29 | 0x80070000;
        if ( v30 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v31 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            43,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v31,
            (__int64)"GetProcAddress( MFCreateAMMediaTypeFromMFMediaType ) failed.  Non-Fatal.",
            v30);
        }
      }
      v32 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateStreamDescriptor");
      *((_QWORD *)this + 27) = v32;
      if ( !v32 )
      {
        v33 = GetLastError();
        v34 = v33;
        if ( v33 > 0 )
          v34 = (unsigned __int16)v33 | 0x80070000;
        if ( v34 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v35 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            44,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v35,
            (__int64)"GetProcAddress( MFCreateStreamDescriptor ) failed.  Non-Fatal.",
            v34);
        }
      }
      v36 = GetProcAddress(*((HMODULE *)this + 8), "MFCreatePresentationDescriptor");
      *((_QWORD *)this + 28) = v36;
      if ( !v36 )
      {
        v37 = GetLastError();
        v38 = v37;
        if ( v37 > 0 )
          v38 = (unsigned __int16)v37 | 0x80070000;
        if ( v38 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v39 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v39,
            (__int64)"GetProcAddress( MFCreatePresentationDescriptor ) failed.  Non-Fatal.",
            v38);
        }
      }
      v40 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateMemoryBuffer");
      *((_QWORD *)this + 29) = v40;
      if ( !v40 )
      {
        v41 = GetLastError();
        v42 = v41;
        if ( v41 > 0 )
          v42 = (unsigned __int16)v41 | 0x80070000;
        if ( v42 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v43 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v43,
            (__int64)"GetProcAddress( MFCreateMemoryBuffer ) failed.  Non-Fatal.",
            v42);
        }
      }
      v44 = GetProcAddress(*((HMODULE *)this + 8), "MFStartup");
      *((_QWORD *)this + 30) = v44;
      if ( !v44 )
      {
        v45 = GetLastError();
        v46 = v45;
        if ( v45 > 0 )
          v46 = (unsigned __int16)v45 | 0x80070000;
        if ( v46 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v47 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v47,
            (__int64)"GetProcAddress( MFStartup ) failed.  Non-Fatal.",
            v46);
        }
      }
      v48 = GetProcAddress(*((HMODULE *)this + 8), "MFShutdown");
      *((_QWORD *)this + 31) = v48;
      if ( !v48 )
      {
        v49 = GetLastError();
        v50 = v49;
        if ( v49 > 0 )
          v50 = (unsigned __int16)v49 | 0x80070000;
        if ( v50 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v51 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            48,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v51,
            (__int64)"GetProcAddress( MFShutdown ) failed.  Non-Fatal.",
            v50);
        }
      }
      v52 = GetProcAddress(*((HMODULE *)this + 8), "MFInitMediaTypeFromWaveFormatEx");
      *((_QWORD *)this + 32) = v52;
      if ( !v52 )
      {
        v53 = GetLastError();
        v54 = v53;
        if ( v53 > 0 )
          v54 = (unsigned __int16)v53 | 0x80070000;
        if ( v54 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v55 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            49,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v55,
            (__int64)"GetProcAddress( MFInitMediaTypeFromWaveFormatEx ) failed.  Non-Fatal.",
            v54);
        }
      }
      v56 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateSample");
      *((_QWORD *)this + 33) = v56;
      if ( !v56 )
      {
        v57 = GetLastError();
        v58 = v57;
        if ( v57 > 0 )
          v58 = (unsigned __int16)v57 | 0x80070000;
        if ( v58 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v59 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v59,
            (__int64)"GetProcAddress( MFCreateSample ) failed.  Non-Fatal.",
            v58);
        }
      }
      v60 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateAsyncResult");
      *((_QWORD *)this + 34) = v60;
      if ( !v60 )
      {
        v61 = GetLastError();
        v62 = v61;
        if ( v61 > 0 )
          v62 = (unsigned __int16)v61 | 0x80070000;
        if ( v62 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v63 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v63,
            (__int64)"GetProcAddress( MFCreateAsyncResult ) failed.  Non-Fatal.",
            v62);
        }
      }
      v64 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateMediaEvent");
      *((_QWORD *)this + 35) = v64;
      if ( !v64 )
      {
        v65 = GetLastError();
        v66 = v65;
        if ( v65 > 0 )
          v66 = (unsigned __int16)v65 | 0x80070000;
        if ( v66 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v67 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v67,
            (__int64)"GetProcAddress( MFCreateMediaEvent ) failed.  Non-Fatal.",
            v66);
        }
      }
      v68 = GetProcAddress(*((HMODULE *)this + 8), "MFInvokeCallback");
      *((_QWORD *)this + 36) = v68;
      if ( !v68 )
      {
        v69 = GetLastError();
        v70 = v69;
        if ( v69 > 0 )
          v70 = (unsigned __int16)v69 | 0x80070000;
        if ( v70 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v71 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v71,
            (__int64)"GetProcAddress( MFInvokeCallback ) failed.  Non-Fatal.",
            v70);
        }
      }
      v72 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateEventQueue");
      *((_QWORD *)this + 37) = v72;
      if ( !v72 )
      {
        v73 = GetLastError();
        v74 = v73;
        if ( v73 > 0 )
          v74 = (unsigned __int16)v73 | 0x80070000;
        if ( v74 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v75 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v75,
            (__int64)"GetProcAddress( MFCreateEventQueue ) failed.  Non-Fatal.",
            v74);
        }
      }
      v76 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateSystemTimeSource");
      *((_QWORD *)this + 38) = v76;
      if ( !v76 )
      {
        v77 = GetLastError();
        v78 = v77;
        if ( v77 > 0 )
          v78 = (unsigned __int16)v77 | 0x80070000;
        if ( v78 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v79 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            55,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v79,
            (__int64)"GetProcAddress( MFCreateSystemTimeSource ) failed.  Non-Fatal.",
            v78);
        }
      }
      v80 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateFile");
      *((_QWORD *)this + 39) = v80;
      if ( !v80 )
      {
        v81 = GetLastError();
        v82 = v81;
        if ( v81 > 0 )
          v82 = (unsigned __int16)v81 | 0x80070000;
        if ( v82 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v83 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            56,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v83,
            (__int64)"GetProcAddress( MFCreateFile ) failed.  Non-Fatal.",
            v82);
        }
      }
      v84 = GetProcAddress(*((HMODULE *)this + 8), "MFCreateDXGIDeviceManager");
      *((_QWORD *)this + 40) = v84;
      if ( !v84 )
      {
        v85 = GetLastError();
        v86 = v85;
        if ( v85 > 0 )
          v86 = (unsigned __int16)v85 | 0x80070000;
        if ( v86 < 0
          && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v87 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            (unsigned int)WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids,
            v87,
            (__int64)"GetProcAddress( MFCreateDXGIDeviceManager ) failed.  Non-Fatal.",
            v86);
        }
      }
      v5 = 0;
      goto LABEL_179;
    }
    v5 = -2147467259;
  }
  else
  {
    v11 = GetLastError();
    v5 = v11;
    if ( v11 > 0 )
      v5 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = RdpWppGetCurrentThreadActivityIdPrefix();
    v10 = 36;
    goto LABEL_23;
  }
LABEL_24:
  if ( v5 < 0 )
LABEL_25:
    CTSMfWrapper::ClearMFPlatFunctions(this);
LABEL_179:
  SetErrorMode(v2);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18009a02c  push    rbx
0x18009a02e  push    rbp
0x18009a02f  push    rsi
0x18009a030  push    rdi
0x18009a031  push    r12
0x18009a033  push    r13
0x18009a035  push    r14
0x18009a037  push    r15
0x18009a039  sub     rsp, 258h
0x18009a040  mov     rax, cs:__security_cookie
0x18009a047  xor     rax, rsp
0x18009a04a  mov     [rsp+298h+var_58], rax
0x18009a052  mov     rdi, rcx
0x18009a055  mov     ecx, 8001h; uMode
0x18009a05a  call    cs:__imp_SetErrorMode
0x18009a060  mov     r12d, eax
0x18009a063  mov     rax, [rdi+40h]
0x18009a067  test    rax, rax
0x18009a06a  jnz     loc_18009A209
0x18009a070  xor     edx, edx; Val
0x18009a072  lea     rcx, [rsp+298h+Buffer]; void *
0x18009a077  mov     r8d, 208h; Size
0x18009a07d  call    memset_0
0x18009a082  mov     esi, 104h
0x18009a087  lea     rcx, [rsp+298h+Buffer]; lpBuffer
0x18009a08c  mov     edx, esi; uSize
0x18009a08e  call    cs:__imp_GetSystemDirectoryW
0x18009a094  mov     ebx, eax
0x18009a096  test    eax, eax
0x18009a098  jz      loc_18009A195
0x18009a09e  mov     edx, esi; MaxCount
0x18009a0a0  lea     rcx, aMfplatDll_0; "\\MFPlat.dll"
0x18009a0a7  call    cs:__imp_wcsnlen
0x18009a0ad  add     rax, rbx
0x18009a0b0  cmp     rax, rsi
0x18009a0b3  ja      loc_18009A18E
0x18009a0b9  lea     r8, aMfplatDll_0; "\\MFPlat.dll"
0x18009a0c0  mov     edx, esi; SizeInWords
0x18009a0c2  lea     rcx, [rsp+298h+Buffer]; Destination
0x18009a0c7  call    cs:__imp_wcscat_s
0x18009a0cd  test    eax, eax
0x18009a0cf  jz      short loc_18009A12D
0x18009a0d1  mov     ebx, 80004005h
0x18009a0d6  mov     rax, cs:WPP_GLOBAL_Control
0x18009a0dd  lea     rbp, WPP_GLOBAL_Control
0x18009a0e4  cmp     rax, rbp
0x18009a0e7  jz      loc_18009A1FC
0x18009a0ed  test    byte ptr [rax+1Ch], 1
0x18009a0f1  jz      loc_18009A1FC
0x18009a0f7  mov     sil, 2
0x18009a0fa  cmp     [rax+19h], sil
0x18009a0fe  jb      loc_18009A1FC
0x18009a104  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a109  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a110  lea     r8, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x18009a117  mov     edx, 25h ; '%'
0x18009a11c  mov     r9d, eax
0x18009a11f  mov     rcx, [rcx+10h]
0x18009a123  call    WPP_SF_d
0x18009a128  jmp     loc_18009A1FC
0x18009a12d  lea     rcx, [rsp+298h+Buffer]; lpLibFileName
0x18009a132  call    cs:__imp_LoadLibraryW
0x18009a138  cmp     qword ptr [rdi+38h], 0
0x18009a13d  mov     [rdi+40h], rax
0x18009a141  jnz     loc_18009A209
0x18009a147  call    cs:__imp_GetLastError
0x18009a14d  mov     ebx, eax
0x18009a14f  test    eax, eax
0x18009a151  jle     short loc_18009A15C
0x18009a153  movzx   ebx, ax
0x18009a156  or      ebx, 80070000h
0x18009a15c  mov     rax, cs:WPP_GLOBAL_Control
0x18009a163  lea     rbp, WPP_GLOBAL_Control
0x18009a16a  cmp     rax, rbp
0x18009a16d  jz      loc_18009A1F4
0x18009a173  test    byte ptr [rax+1Ch], 1
0x18009a177  jz      short loc_18009A1F4
0x18009a179  mov     sil, 2
0x18009a17c  cmp     [rax+19h], sil
0x18009a180  jb      short loc_18009A1F4
0x18009a182  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a187  mov     edx, 26h ; '&'
0x18009a18c  jmp     short loc_18009A1D6
0x18009a18e  mov     ebx, 80004005h
0x18009a193  jmp     short loc_18009A1AA
0x18009a195  call    cs:__imp_GetLastError
0x18009a19b  mov     ebx, eax
0x18009a19d  test    eax, eax
0x18009a19f  jle     short loc_18009A1AA
0x18009a1a1  movzx   ebx, ax
0x18009a1a4  or      ebx, 80070000h
0x18009a1aa  mov     rax, cs:WPP_GLOBAL_Control
0x18009a1b1  lea     rbp, WPP_GLOBAL_Control
0x18009a1b8  cmp     rax, rbp
0x18009a1bb  jz      short loc_18009A1F4
0x18009a1bd  test    byte ptr [rax+1Ch], 1
0x18009a1c1  jz      short loc_18009A1F4
0x18009a1c3  mov     sil, 2
0x18009a1c6  cmp     [rax+19h], sil
0x18009a1ca  jb      short loc_18009A1F4
0x18009a1cc  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a1d1  mov     edx, 24h ; '$'
0x18009a1d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a1dd  lea     r8, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x18009a1e4  mov     r9d, eax
0x18009a1e7  mov     dword ptr [rsp+298h+var_278], ebx
0x18009a1eb  mov     rcx, [rcx+10h]
0x18009a1ef  call    WPP_SF_Dd
0x18009a1f4  test    ebx, ebx
0x18009a1f6  jns     loc_18009AB45
0x18009a1fc  mov     rcx, rdi; this
0x18009a1ff  call    ?ClearMFPlatFunctions@CTSMfWrapper@@AEAAJXZ; CTSMfWrapper::ClearMFPlatFunctions(void)
0x18009a204  jmp     loc_18009AB45
0x18009a209  lea     rdx, aMfcreateaudiom; "MFCreateAudioMediaType"
0x18009a210  mov     rcx, rax; hModule
0x18009a213  call    cs:__imp_GetProcAddress
0x18009a219  mov     [rdi+0B0h], rax
0x18009a220  mov     sil, 2
0x18009a223  lea     r15, WPP_224c8f16d6ef32194fc46946d1f7a8fb_Traceguids
0x18009a22a  mov     r13b, 8
0x18009a22d  lea     rbp, WPP_GLOBAL_Control
0x18009a234  mov     r14d, 80070000h
0x18009a23a  test    rax, rax
0x18009a23d  jnz     short loc_18009A29D
0x18009a23f  call    cs:__imp_GetLastError
0x18009a245  mov     ebx, eax
0x18009a247  test    eax, eax
0x18009a249  jle     short loc_18009A251
0x18009a24b  movzx   ebx, ax
0x18009a24e  or      ebx, r14d
0x18009a251  test    ebx, ebx
0x18009a253  jns     short loc_18009A29D
0x18009a255  mov     rax, cs:WPP_GLOBAL_Control
0x18009a25c  cmp     rax, rbp
0x18009a25f  jz      short loc_18009A29D
0x18009a261  test    [rax+1Ch], r13b
0x18009a265  jz      short loc_18009A29D
0x18009a267  cmp     [rax+19h], sil
0x18009a26b  jb      short loc_18009A29D
0x18009a26d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a272  lea     rcx, aGetprocaddress_21; "GetProcAddress( MFCreateAudioMediaType "...
0x18009a279  mov     [rsp+298h+var_270], ebx
0x18009a27d  mov     [rsp+298h+var_278], rcx
0x18009a282  mov     edx, 27h ; '''
0x18009a287  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a28e  mov     r9d, eax
0x18009a291  mov     r8, r15
0x18009a294  mov     rcx, [rcx+10h]
0x18009a298  call    WPP_SF_DsD
0x18009a29d  mov     rcx, [rdi+40h]; hModule
0x18009a2a1  lea     rdx, aMfcreatemediat; "MFCreateMediaType"
0x18009a2a8  call    cs:__imp_GetProcAddress
0x18009a2ae  mov     [rdi+0B8h], rax
0x18009a2b5  test    rax, rax
0x18009a2b8  jnz     short loc_18009A318
0x18009a2ba  call    cs:__imp_GetLastError
0x18009a2c0  mov     ebx, eax
0x18009a2c2  test    eax, eax
0x18009a2c4  jle     short loc_18009A2CC
0x18009a2c6  movzx   ebx, ax
0x18009a2c9  or      ebx, r14d
0x18009a2cc  test    ebx, ebx
0x18009a2ce  jns     short loc_18009A318
0x18009a2d0  mov     rax, cs:WPP_GLOBAL_Control
0x18009a2d7  cmp     rax, rbp
0x18009a2da  jz      short loc_18009A318
0x18009a2dc  test    [rax+1Ch], r13b
0x18009a2e0  jz      short loc_18009A318
0x18009a2e2  cmp     [rax+19h], sil
0x18009a2e6  jb      short loc_18009A318
0x18009a2e8  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a2ed  lea     rcx, aGetprocaddress_3; "GetProcAddress( MFCreateMediaType ) fai"...
0x18009a2f4  mov     [rsp+298h+var_270], ebx
0x18009a2f8  mov     [rsp+298h+var_278], rcx
0x18009a2fd  mov     edx, 28h ; '('
0x18009a302  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a309  mov     r9d, eax
0x18009a30c  mov     r8, r15
0x18009a30f  mov     rcx, [rcx+10h]
0x18009a313  call    WPP_SF_DsD
0x18009a318  mov     rcx, [rdi+40h]; hModule
0x18009a31c  lea     rdx, aMfinitmediatyp_1; "MFInitMediaTypeFromMFVideoFormat"
0x18009a323  call    cs:__imp_GetProcAddress
0x18009a329  mov     [rdi+0C0h], rax
0x18009a330  test    rax, rax
0x18009a333  jnz     short loc_18009A393
0x18009a335  call    cs:__imp_GetLastError
0x18009a33b  mov     ebx, eax
0x18009a33d  test    eax, eax
0x18009a33f  jle     short loc_18009A347
0x18009a341  movzx   ebx, ax
0x18009a344  or      ebx, r14d
0x18009a347  test    ebx, ebx
0x18009a349  jns     short loc_18009A393
0x18009a34b  mov     rax, cs:WPP_GLOBAL_Control
0x18009a352  cmp     rax, rbp
0x18009a355  jz      short loc_18009A393
0x18009a357  test    [rax+1Ch], r13b
0x18009a35b  jz      short loc_18009A393
0x18009a35d  cmp     [rax+19h], sil
0x18009a361  jb      short loc_18009A393
0x18009a363  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a368  lea     rcx, aGetprocaddress_25; "GetProcAddress( MFInitMediaTypeFromMFVi"...
0x18009a36f  mov     [rsp+298h+var_270], ebx
0x18009a373  mov     [rsp+298h+var_278], rcx
0x18009a378  mov     edx, 29h ; ')'
0x18009a37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a384  mov     r9d, eax
0x18009a387  mov     r8, r15
0x18009a38a  mov     rcx, [rcx+10h]
0x18009a38e  call    WPP_SF_DsD
0x18009a393  mov     rcx, [rdi+40h]; hModule
0x18009a397  lea     rdx, aMfinitmediatyp; "MFInitMediaTypeFromAMMediaType"
0x18009a39e  call    cs:__imp_GetProcAddress
0x18009a3a4  mov     [rdi+0C8h], rax
0x18009a3ab  test    rax, rax
0x18009a3ae  jnz     short loc_18009A40E
0x18009a3b0  call    cs:__imp_GetLastError
0x18009a3b6  mov     ebx, eax
0x18009a3b8  test    eax, eax
0x18009a3ba  jle     short loc_18009A3C2
0x18009a3bc  movzx   ebx, ax
0x18009a3bf  or      ebx, r14d
0x18009a3c2  test    ebx, ebx
0x18009a3c4  jns     short loc_18009A40E
0x18009a3c6  mov     rax, cs:WPP_GLOBAL_Control
0x18009a3cd  cmp     rax, rbp
0x18009a3d0  jz      short loc_18009A40E
0x18009a3d2  test    [rax+1Ch], r13b
0x18009a3d6  jz      short loc_18009A40E
0x18009a3d8  cmp     [rax+19h], sil
0x18009a3dc  jb      short loc_18009A40E
0x18009a3de  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a3e3  lea     rcx, aGetprocaddress_2; "GetProcAddress( MFInitMediaTypeFromAMMe"...
0x18009a3ea  mov     [rsp+298h+var_270], ebx
0x18009a3ee  mov     [rsp+298h+var_278], rcx
0x18009a3f3  mov     edx, 2Ah ; '*'
0x18009a3f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a3ff  mov     r9d, eax
0x18009a402  mov     r8, r15
0x18009a405  mov     rcx, [rcx+10h]
0x18009a409  call    WPP_SF_DsD
0x18009a40e  mov     rcx, [rdi+40h]; hModule
0x18009a412  lea     rdx, aMfcreateammedi_0; "MFCreateAMMediaTypeFromMFMediaType"
0x18009a419  call    cs:__imp_GetProcAddress
0x18009a41f  mov     [rdi+0D0h], rax
0x18009a426  test    rax, rax
0x18009a429  jnz     short loc_18009A489
0x18009a42b  call    cs:__imp_GetLastError
0x18009a431  mov     ebx, eax
0x18009a433  test    eax, eax
0x18009a435  jle     short loc_18009A43D
0x18009a437  movzx   ebx, ax
0x18009a43a  or      ebx, r14d
0x18009a43d  test    ebx, ebx
0x18009a43f  jns     short loc_18009A489
0x18009a441  mov     rax, cs:WPP_GLOBAL_Control
0x18009a448  cmp     rax, rbp
0x18009a44b  jz      short loc_18009A489
0x18009a44d  test    [rax+1Ch], r13b
0x18009a451  jz      short loc_18009A489
0x18009a453  cmp     [rax+19h], sil
0x18009a457  jb      short loc_18009A489
0x18009a459  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a45e  lea     rcx, aGetprocaddress_20; "GetProcAddress( MFCreateAMMediaTypeFrom"...
0x18009a465  mov     [rsp+298h+var_270], ebx
0x18009a469  mov     [rsp+298h+var_278], rcx
0x18009a46e  mov     edx, 2Bh ; '+'
0x18009a473  mov     rcx, cs:WPP_GLOBAL_Control
0x18009a47a  mov     r9d, eax
0x18009a47d  mov     r8, r15
0x18009a480  mov     rcx, [rcx+10h]
0x18009a484  call    WPP_SF_DsD
0x18009a489  mov     rcx, [rdi+40h]; hModule
0x18009a48d  lea     rdx, aMfcreatestream; "MFCreateStreamDescriptor"
0x18009a494  call    cs:__imp_GetProcAddress
0x18009a49a  mov     [rdi+0D8h], rax
0x18009a4a1  test    rax, rax
0x18009a4a4  jnz     short loc_18009A504
0x18009a4a6  call    cs:__imp_GetLastError
0x18009a4ac  mov     ebx, eax
0x18009a4ae  test    eax, eax
0x18009a4b0  jle     short loc_18009A4B8
0x18009a4b2  movzx   ebx, ax
0x18009a4b5  or      ebx, r14d
0x18009a4b8  test    ebx, ebx
0x18009a4ba  jns     short loc_18009A504
0x18009a4bc  mov     rax, cs:WPP_GLOBAL_Control
0x18009a4c3  cmp     rax, rbp
0x18009a4c6  jz      short loc_18009A504
0x18009a4c8  test    [rax+1Ch], r13b
0x18009a4cc  jz      short loc_18009A504
0x18009a4ce  cmp     [rax+19h], sil
0x18009a4d2  jb      short loc_18009A504
0x18009a4d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009a4d9  lea     rcx, aGetprocaddress_24; "GetProcAddress( MFCreateStreamDescripto"...
0x18009a4e0  mov     [rsp+298h+var_270], ebx
0x18009a4e4  mov     [rsp+298h+var_278], rcx
0x18009a4e9  mov     edx, 2Ch ; ','
0x18009a4ee  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
