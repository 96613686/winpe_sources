# CheckRequiredFilesAndGetSize(_MANIFEST_CALLBACK_CONTEXT *,_FILELIST_CALLBACK_CONTEXT *)

- ea: `0x180031a74`
- end: `0x180031e60`
- name: `?CheckRequiredFilesAndGetSize@@YAJPEAU_MANIFEST_CALLBACK_CONTEXT@@PEAU_FILELIST_CALLBACK_CONTEXT@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(struct _MANIFEST_CALLBACK_CONTEXT *, struct _FILELIST_CALLBACK_CONTEXT *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x180033398`

## callees

- `0x18000b200`
- `0x18000d290`
- `0x18000d57c`
- `0x18000d624`
- `0x180017810`
- `0x180023eb4`
- `0x180026498`
- `0x1800318d8`
- `0x180031a74`
- `0x180032168`
- `0x180032210`
- `0x180033e28`
- `0x180034a60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031bae`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b58`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b6c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b86`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031b9a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180031bae`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031b0d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031b3a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031d4a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031b0d`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031b3a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x180031d4a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031c0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031c4a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031c0b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180031c4a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031da7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180031da7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031aa8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180031aa8`

## string_xrefs

- `0x180031b90`: `Unires.dll`
- `0x180031ba4`: `xpssvcs.dll`
- `0x180031b62`: `V3HostingFilter-pipelineconfig.xml`
- `0x180031b4e`: `V3HostingFilter.dll`

## pseudocode

```c
__int64 __fastcall CheckRequiredFilesAndGetSize(const WCHAR *a1, struct _FILELIST_CALLBACK_CONTEXT *a2)
{
  HLOCAL v4; // rax
  int v5; // r13d
  unsigned __int16 *v6; // rdi
  wchar_t *v7; // rsi
  __int64 LastErrorAsFailHR; // r15
  int StringFromManifest; // eax
  unsigned __int16 *v10; // rax
  const unsigned __int16 *v11; // r12
  WCHAR *v12; // rbx
  int v13; // ecx
  NCoreLibrary *v14; // rcx
  unsigned int v15; // ecx
  int v16; // eax
  SplLogType *v17; // rsi
  const unsigned __int16 **v18; // r10
  struct SplLogType *v19; // rax
  __int64 v20; // r10
  __int64 v21; // r11
  NCoreLibrary::TString *v22; // rcx
  int v23; // ebx
  NCoreLibrary::TString *v24; // rcx
  __int64 result; // rax
  unsigned int v26; // edx
  int v27; // eax
  unsigned int v28; // ecx
  unsigned int v29; // edx
  int v30; // eax
  unsigned int v31; // edx
  int v32; // eax
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned __int64 v35; // [rsp+40h] [rbp-69h] BYREF
  __int64 v36; // [rsp+48h] [rbp-61h]
  HLOCAL hMem; // [rsp+50h] [rbp-59h]
  _BYTE v38[24]; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v39[24]; // [rsp+70h] [rbp-39h] BYREF
  _BYTE v40[24]; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v41[24]; // [rsp+A0h] [rbp-9h] BYREF
  _BYTE v42[72]; // [rsp+B8h] [rbp+Fh] BYREF
  int v43; // [rsp+118h] [rbp+6Fh]
  wchar_t *Context; // [rsp+120h] [rbp+77h] BYREF
  LPCWSTR lpFileName; // [rsp+128h] [rbp+7Fh] BYREF

  v36 = *((_QWORD *)a2 + 12);
  v4 = LocalAlloc(0x40u, 0x800u);
  v5 = -1;
  LODWORD(v6) = 0;
  hMem = v4;
  v7 = (wchar_t *)v4;
  if ( !v4 )
  {
    LODWORD(LastErrorAsFailHR) = -2147024882;
LABEL_33:
    v23 = LastErrorAsFailHR;
    goto LABEL_34;
  }
  StringFromManifest = GetStringFromManifest(L"RequiredFiles", (LPWSTR)v4, 0x400u, a1 + 1);
  v43 = StringFromManifest;
  LODWORD(LastErrorAsFailHR) = StringFromManifest;
  if ( StringFromManifest < 0 )
  {
    v23 = StringFromManifest;
    goto LABEL_34;
  }
  Context = 0;
  v6 = wcstok_s(v7, L",", &Context);
  if ( !v6 )
  {
    LODWORD(v6) = 0;
    goto LABEL_33;
  }
  while ( 1 )
  {
    v10 = StripWhitespaceAndQuotes(v6);
    LODWORD(v6) = 0;
    v11 = v10;
    if ( !*v10
      || *((_BYTE *)a2 + 42)
      && (!(unsigned int)_o__wcsicmp(v10, L"V3HostingFilter.dll")
       || !(unsigned int)_o__wcsicmp(v11, L"V3HostingFilter-pipelineconfig.xml"))
      || *((_BYTE *)a2 + 43)
      && (!(unsigned int)_o__wcsicmp(v11, L"StdNames.gpd") || !(unsigned int)_o__wcsicmp(v11, L"Unires.dll"))
      || !(unsigned int)_o__wcsicmp(v11, L"xpssvcs.dll") )
    {
      v6 = wcstok_s(0, L",", &Context);
      goto LABEL_27;
    }
    v35 = 0;
    LODWORD(LastErrorAsFailHR) = StringCchLengthW(v11, 0x104u, &v35);
    NCoreLibrary::TString::TString((NCoreLibrary::TString *)&lpFileName, (const unsigned __int16 *)a2 + 576);
    if ( (int)LastErrorAsFailHR < 0 )
      break;
    LODWORD(LastErrorAsFailHR) = NCoreLibrary::TString::Cat((NCoreLibrary::TString *)&lpFileName, v11);
    if ( (int)LastErrorAsFailHR < 0 )
      break;
    v12 = (WCHAR *)lpFileName;
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      v13 = v35 + 9;
LABEL_21:
      v15 = *((_DWORD *)a2 + 12) + v13;
      v16 = -1;
      if ( v15 >= *((_DWORD *)a2 + 12) )
        v16 = v15;
      LODWORD(LastErrorAsFailHR) = v15 < *((_DWORD *)a2 + 12) ? 0x80070216 : 0;
      *((_DWORD *)a2 + 12) = v16;
      goto LABEL_25;
    }
    LODWORD(LastErrorAsFailHR) = NCoreLibrary::TString::Format(
                                   (NCoreLibrary::TString *)&lpFileName,
                                   L"%ws%ws",
                                   (char *)a2 + 1672,
                                   v11);
    if ( (int)LastErrorAsFailHR < 0 )
      break;
    v12 = (WCHAR *)lpFileName;
    if ( GetFileAttributesW(lpFileName) != -1 )
    {
      v13 = v35 + 10;
      goto LABEL_21;
    }
    LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v14);
    ClassInstallerTelemetry::WriteDbgTraceError(
      "CheckRequiredFilesAndGetSize",
      L"Could not find required file '%ws': hr: 0x%x",
      v11,
      LastErrorAsFailHR);
    v17 = SplLogType::SplLogType((SplLogType *)v38, v11);
    v6 = (unsigned __int16 *)SplLogType::SplLogType((SplLogType *)v39, L"RequiredFiles");
    SplLogType::SplLogType((SplLogType *)v40, *(const unsigned __int16 **)(v36 + 112));
    SplLogType::SplLogType((SplLogType *)v41, *v18);
    v19 = SplLogType::SplLogType((SplLogType *)v42, *(const unsigned __int16 **)(v36 + 8));
    SplLogEvent2(&SETUP_INSTALL_PRINTER_DRIVER_MISSING_FILE, v19, v20, v21, v6, v17, 0);
    LODWORD(v6) = 0;
LABEL_25:
    if ( (int)LastErrorAsFailHR < 0 )
      goto LABEL_30;
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "CheckRequiredFilesAndGetSize",
      L"Found required file for driver: '%ws'",
      v11);
    *((_BYTE *)a2 + 41) = 1;
    v6 = wcstok_s(0, L",", &Context);
    NCoreLibrary::TString::vFree(v22, v12);
LABEL_27:
    if ( !v6 )
      goto LABEL_28;
  }
  v12 = (WCHAR *)lpFileName;
LABEL_30:
  ClassInstallerTelemetry::WriteDbgTraceError(
    "CheckRequiredFilesAndGetSize",
    L"GetRequiredFilesSize failed: hr: 0x%x",
    (unsigned int)LastErrorAsFailHR);
  NCoreLibrary::TString::vFree(v24, v12);
LABEL_28:
  v23 = v43;
LABEL_34:
  LocalFree(hMem);
  result = (unsigned int)v6;
  if ( v23 != -2147024894 )
    result = (unsigned int)LastErrorAsFailHR;
  if ( (int)result >= 0 )
  {
    if ( *((_BYTE *)a2 + 42) == (_BYTE)v6 )
      goto LABEL_45;
    v26 = *((_DWORD *)a2 + 12);
    v27 = -1;
    v28 = v26 + 29;
    if ( v26 + 29 >= v26 )
      v27 = v26 + 29;
    *((_DWORD *)a2 + 12) = v27;
    result = v28 < v26 ? 0x80070216 : 0;
    if ( v28 >= v26 )
    {
      if ( *((_BYTE *)a2 + 42) != (_BYTE)v6 )
      {
        v29 = *((_DWORD *)a2 + 12);
        v30 = -1;
        *((_BYTE *)a2 + 41) = 1;
        if ( v29 + 44 >= v29 )
          v30 = v29 + 44;
        *((_DWORD *)a2 + 12) = v30;
        result = v29 + 44 < v29 ? 0x80070216 : 0;
      }
LABEL_45:
      if ( (int)result >= 0 && *((_BYTE *)a2 + 43) != (_BYTE)v6 )
      {
        v31 = *((_DWORD *)a2 + 12);
        v32 = -1;
        v33 = v31 + 21;
        if ( v31 + 21 >= v31 )
          v32 = v31 + 21;
        *((_DWORD *)a2 + 12) = v32;
        result = v33 < v31 ? 0x80070216 : 0;
        if ( v33 >= v31 )
        {
          v34 = *((_DWORD *)a2 + 12);
          *((_BYTE *)a2 + 41) = 1;
          if ( v34 + 19 >= v34 )
            v5 = v34 + 19;
          result = v34 + 19 < v34 ? 0x80070216 : 0;
          *((_DWORD *)a2 + 12) = v5;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031a74  mov     [rsp-8+arg_0], rbx
0x180031a79  push    rbp
0x180031a7a  push    rsi
0x180031a7b  push    rdi
0x180031a7c  push    r12
0x180031a7e  push    r13
0x180031a80  push    r14
0x180031a82  push    r15
0x180031a84  lea     rbp, [rsp-27h]
0x180031a89  sub     rsp, 0D0h
0x180031a90  mov     rax, [rdx+60h]
0x180031a94  mov     r14, rdx
0x180031a97  mov     rbx, rcx
0x180031a9a  mov     [rbp+57h+var_B8], rax
0x180031a9e  mov     edx, 800h; uBytes
0x180031aa3  mov     ecx, 40h ; '@'; uFlags
0x180031aa8  call    cs:__imp_LocalAlloc
0x180031aae  or      r13d, 0FFFFFFFFh
0x180031ab2  xor     edi, edi
0x180031ab4  mov     [rbp+57h+hMem], rax
0x180031ab8  mov     rsi, rax
0x180031abb  mov     r12d, 80070216h
0x180031ac1  test    rax, rax
0x180031ac4  jnz     short loc_180031AD1
0x180031ac6  mov     r15d, 8007000Eh
0x180031acc  jmp     loc_180031DA0
0x180031ad1  lea     r9, [rbx+2]; lpFileName
0x180031ad5  mov     r8d, 400h; nSize
0x180031adb  mov     rdx, rsi; lpReturnedString
0x180031ade  lea     rcx, aRequiredfiles; "RequiredFiles"
0x180031ae5  call    ?GetStringFromManifest@@YAJPEBGPEAGK0@Z; GetStringFromManifest(ushort const *,ushort *,ulong,ushort const *)
0x180031aea  mov     [rbp+57h+arg_8], eax
0x180031aed  mov     r15d, eax
0x180031af0  test    eax, eax
0x180031af2  js      loc_180031D9A
0x180031af8  lea     rbx, Delimiter; ","
0x180031aff  mov     [rbp+57h+Context], rdi
0x180031b03  mov     rdx, rbx; Delimiter
0x180031b06  lea     r8, [rbp+57h+Context]; Context
0x180031b0a  mov     rcx, rsi; String
0x180031b0d  call    cs:__imp_wcstok_s
0x180031b13  mov     rdi, rax
0x180031b16  test    rax, rax
0x180031b19  jz      loc_180031D9E
0x180031b1f  mov     rcx, rdi; unsigned __int16 *
0x180031b22  call    ?StripWhitespaceAndQuotes@@YAPEAGPEAG@Z; StripWhitespaceAndQuotes(ushort *)
0x180031b27  xor     edi, edi
0x180031b29  mov     r12, rax
0x180031b2c  cmp     [rax], di
0x180031b2f  jnz     short loc_180031B48
0x180031b31  lea     r8, [rbp+57h+Context]; Context
0x180031b35  mov     rdx, rbx; Delimiter
0x180031b38  xor     ecx, ecx; String
0x180031b3a  call    cs:__imp_wcstok_s
0x180031b40  mov     rdi, rax
0x180031b43  jmp     loc_180031D62
0x180031b48  cmp     [r14+2Ah], dil
0x180031b4c  jz      short loc_180031B76
0x180031b4e  lea     rdx, aV3hostingfilte; "V3HostingFilter.dll"
0x180031b55  mov     rcx, r12
0x180031b58  call    cs:__imp__o__wcsicmp
0x180031b5e  test    eax, eax
0x180031b60  jz      short loc_180031B31
0x180031b62  lea     rdx, aV3hostingfilte_0; "V3HostingFilter-pipelineconfig.xml"
0x180031b69  mov     rcx, r12
0x180031b6c  call    cs:__imp__o__wcsicmp
0x180031b72  test    eax, eax
0x180031b74  jz      short loc_180031B31
0x180031b76  cmp     [r14+2Bh], dil
0x180031b7a  jz      short loc_180031BA4
0x180031b7c  lea     rdx, aStdnamesGpd; "StdNames.gpd"
0x180031b83  mov     rcx, r12
0x180031b86  call    cs:__imp__o__wcsicmp
0x180031b8c  test    eax, eax
0x180031b8e  jz      short loc_180031B31
0x180031b90  lea     rdx, aUniresDll; "Unires.dll"
0x180031b97  mov     rcx, r12
0x180031b9a  call    cs:__imp__o__wcsicmp
0x180031ba0  test    eax, eax
0x180031ba2  jz      short loc_180031B31
0x180031ba4  lea     rdx, aXpssvcsDll; "xpssvcs.dll"
0x180031bab  mov     rcx, r12
0x180031bae  call    cs:__imp__o__wcsicmp
0x180031bb4  test    eax, eax
0x180031bb6  jz      loc_180031B31
0x180031bbc  lea     r8, [rbp+57h+var_C0]; unsigned __int64 *
0x180031bc0  mov     [rbp+57h+var_C0], rdi
0x180031bc4  mov     edx, 104h; unsigned __int64
0x180031bc9  mov     rcx, r12; unsigned __int16 *
0x180031bcc  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031bd1  lea     rdx, [r14+480h]; unsigned __int16 *
0x180031bd8  mov     r15d, eax
0x180031bdb  lea     rcx, [rbp+57h+lpFileName]; this
0x180031bdf  call    ??0TString@NCoreLibrary@@QEAA@PEBG@Z; NCoreLibrary::TString::TString(ushort const *)
0x180031be4  test    r15d, r15d
0x180031be7  js      loc_180031D76
0x180031bed  mov     rdx, r12; unsigned __int16 *
0x180031bf0  lea     rcx, [rbp+57h+lpFileName]; this
0x180031bf4  call    ?Cat@TString@NCoreLibrary@@QEAAJPEBG@Z; NCoreLibrary::TString::Cat(ushort const *)
0x180031bf9  mov     r15d, eax
0x180031bfc  test    eax, eax
0x180031bfe  js      loc_180031D76
0x180031c04  mov     rbx, [rbp+57h+lpFileName]
0x180031c08  mov     rcx, rbx; lpFileName
0x180031c0b  call    cs:__imp_GetFileAttributesW
0x180031c11  cmp     eax, r13d
0x180031c14  jz      short loc_180031C1E
0x180031c16  mov     ecx, dword ptr [rbp+57h+var_C0]
0x180031c19  add     ecx, 9
0x180031c1c  jmp     short loc_180031C5B
0x180031c1e  lea     r8, [r14+688h]
0x180031c25  mov     r9, r12
0x180031c28  lea     rdx, aWsWs; "%ws%ws"
0x180031c2f  lea     rcx, [rbp+57h+lpFileName]; this
0x180031c33  call    ?Format@TString@NCoreLibrary@@QEAAJPEBGZZ; NCoreLibrary::TString::Format(ushort const *,...)
0x180031c38  mov     r15d, eax
0x180031c3b  test    eax, eax
0x180031c3d  js      loc_180031D76
0x180031c43  mov     rbx, [rbp+57h+lpFileName]
0x180031c47  mov     rcx, rbx; lpFileName
0x180031c4a  call    cs:__imp_GetFileAttributesW
0x180031c50  cmp     eax, r13d
0x180031c53  jz      short loc_180031C7C
0x180031c55  mov     ecx, dword ptr [rbp+57h+var_C0]
0x180031c58  add     ecx, 0Ah
0x180031c5b  add     ecx, [r14+30h]
0x180031c5f  mov     eax, r13d
0x180031c62  cmp     ecx, [r14+30h]
0x180031c66  cmovnb  eax, ecx
0x180031c69  sbb     r15d, r15d
0x180031c6c  and     r15d, 80070216h
0x180031c73  mov     [r14+30h], eax
0x180031c77  jmp     loc_180031D1D
0x180031c7c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180031c81  mov     r9d, eax
0x180031c84  lea     rdx, aCouldNotFindRe; "Could not find required file '%ws': hr:"...
0x180031c8b  mov     r8, r12
0x180031c8e  lea     rcx, aCheckrequiredf; "CheckRequiredFilesAndGetSize"
0x180031c95  mov     r15d, eax
0x180031c98  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180031c9d  mov     rdx, r12; unsigned __int16 *
0x180031ca0  lea     rcx, [rbp+57h+var_A8]; this
0x180031ca4  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180031ca9  lea     rdx, aRequiredfiles; "RequiredFiles"
0x180031cb0  mov     rsi, rax
0x180031cb3  lea     rcx, [rbp+57h+var_90]; this
0x180031cb7  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180031cbc  mov     r10, [rbp+57h+var_B8]
0x180031cc0  lea     rcx, [rbp+57h+var_78]; this
0x180031cc4  mov     rdi, rax
0x180031cc7  mov     rdx, [r10+70h]; unsigned __int16 *
0x180031ccb  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180031cd0  mov     rdx, [r10]; unsigned __int16 *
0x180031cd3  lea     rcx, [rbp+57h+var_60]; this
0x180031cd7  mov     r11, rax
0x180031cda  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180031cdf  mov     rdx, [rbp+57h+var_B8]
0x180031ce3  lea     rcx, [rbp+57h+var_48]; this
0x180031ce7  mov     r10, rax
0x180031cea  mov     rdx, [rdx+8]; unsigned __int16 *
0x180031cee  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180031cf3  mov     [rsp+100h+var_D0], 0
0x180031cfc  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_MISSING_FILE; struct _EVENT_DESCRIPTOR *
0x180031d03  mov     [rsp+100h+var_D8], rsi
0x180031d08  mov     r9, r11
0x180031d0b  mov     r8, r10
0x180031d0e  mov     [rsp+100h+var_E0], rdi
0x180031d13  mov     rdx, rax; struct SplLogType *
0x180031d16  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180031d1b  xor     edi, edi
0x180031d1d  test    r15d, r15d
0x180031d20  js      short loc_180031D7A
0x180031d22  mov     r8, r12
0x180031d25  lea     rdx, aFoundRequiredF; "Found required file for driver: '%ws'"
0x180031d2c  lea     rcx, aCheckrequiredf; "CheckRequiredFilesAndGetSize"
0x180031d33  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180031d38  lea     r8, [rbp+57h+Context]; Context
0x180031d3c  mov     byte ptr [r14+29h], 1
0x180031d41  lea     rdx, Delimiter; ","
0x180031d48  xor     ecx, ecx; String
0x180031d4a  call    cs:__imp_wcstok_s
0x180031d50  mov     rdx, rbx; void *
0x180031d53  mov     rdi, rax
0x180031d56  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180031d5b  lea     rbx, Delimiter; ","
0x180031d62  test    rdi, rdi
0x180031d65  jnz     loc_180031B1F
0x180031d6b  mov     ebx, [rbp+57h+arg_8]
0x180031d6e  mov     r12d, 80070216h
0x180031d74  jmp     short loc_180031DA3
0x180031d76  mov     rbx, [rbp+57h+lpFileName]
0x180031d7a  mov     r8d, r15d
0x180031d7d  lea     rdx, aGetrequiredfil; "GetRequiredFilesSize failed: hr: 0x%x"
0x180031d84  lea     rcx, aCheckrequiredf; "CheckRequiredFilesAndGetSize"
0x180031d8b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180031d90  mov     rdx, rbx; void *
0x180031d93  call    ?vFree@TString@NCoreLibrary@@AEAAXPEAX@Z; NCoreLibrary::TString::vFree(void *)
0x180031d98  jmp     short loc_180031D6B
0x180031d9a  mov     ebx, eax
0x180031d9c  jmp     short loc_180031DA3
0x180031d9e  xor     edi, edi
0x180031da0  mov     ebx, r15d
0x180031da3  mov     rcx, [rbp+57h+hMem]; hMem
0x180031da7  call    cs:__imp_LocalFree
0x180031dad  cmp     ebx, 80070002h
0x180031db3  mov     eax, edi
0x180031db5  cmovnz  eax, r15d
0x180031db9  test    eax, eax
0x180031dbb  js      loc_180031E45
0x180031dc1  cmp     [r14+2Ah], dil
0x180031dc5  jz      short loc_180031E06
0x180031dc7  mov     edx, [r14+30h]
0x180031dcb  mov     eax, r13d
0x180031dce  lea     ecx, [rdx+1Dh]
0x180031dd1  cmp     ecx, edx
0x180031dd3  cmovnb  eax, ecx
0x180031dd6  mov     [r14+30h], eax
0x180031dda  sbb     eax, eax
0x180031ddc  and     eax, r12d
0x180031ddf  cmp     ecx, edx
0x180031de1  jb      short loc_180031E45
0x180031de3  cmp     [r14+2Ah], dil
0x180031de7  jz      short loc_180031E06
0x180031de9  mov     edx, [r14+30h]
0x180031ded  mov     eax, r13d
0x180031df0  mov     byte ptr [r14+29h], 1
0x180031df5  lea     ecx, [rdx+2Ch]
0x180031df8  cmp     ecx, edx
0x180031dfa  cmovnb  eax, ecx
0x180031dfd  mov     [r14+30h], eax
0x180031e01  sbb     eax, eax
0x180031e03  and     eax, r12d
0x180031e06  test    eax, eax
0x180031e08  js      short loc_180031E45
0x180031e0a  cmp     [r14+2Bh], dil
0x180031e0e  jz      short loc_180031E45
0x180031e10  mov     edx, [r14+30h]
0x180031e14  mov     eax, r13d
0x180031e17  lea     ecx, [rdx+15h]
0x180031e1a  cmp     ecx, edx
0x180031e1c  cmovnb  eax, ecx
0x180031e1f  mov     [r14+30h], eax
0x180031e23  sbb     eax, eax
0x180031e25  and     eax, r12d
0x180031e28  jl      short loc_180031E45
0x180031e2a  mov     ecx, [r14+30h]
0x180031e2e  mov     byte ptr [r14+29h], 1
0x180031e33  lea     eax, [rcx+13h]
0x180031e36  cmp     eax, ecx
0x180031e38  cmovnb  r13d, eax
0x180031e3c  sbb     eax, eax
0x180031e3e  and     eax, r12d
0x180031e41  mov     [r14+30h], r13d
0x180031e45  mov     rbx, [rsp+100h+arg_0]
0x180031e4d  add     rsp, 0D0h
0x180031e54  pop     r15
0x180031e56  pop     r14
0x180031e58  pop     r13
0x180031e5a  pop     r12
0x180031e5c  pop     rdi
0x180031e5d  pop     rsi
0x180031e5e  pop     rbp
0x180031e5f  retn
```
