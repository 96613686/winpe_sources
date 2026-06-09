# InstallPrinterDriverFromTheWeb

- ea: `0x18000ed30`
- end: `0x18000f692`
- name: `InstallPrinterDriverFromTheWeb`
- size: `2402`
- prototype: ``
- caller_count: `3`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000ca40`
- `0x1800113c0`
- `0x18002bfc0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d7f0`
- `0x18000ed30`
- `0x180010c9c`
- `0x18001ddf4`
- `0x180026820`
- `0x180027750`
- `0x1800284d0`
- `0x180034bec`
- `0x180035208`
- `0x1800356a8`
- `0x180035728`
- `0x1800359b0`
- `0x180036470`
- `0x180036664`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f604`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000f604`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5f4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5e1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f5f4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f01d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000ee2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000f01d`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x18000f4f5`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x18000f4f5`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000f1ea`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18000f1ea`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x18000f526`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x18000f526`

## string_xrefs

- `0x18000ee5a`: `InstallPrinterDriverFromTheWeb`
- `0x18000eebf`: `InstallPrinterDriverFromTheWeb`
- `0x18000f116`: `InstallPrinterDriverFromTheWeb`
- `0x18000f15e`: `InstallPrinterDriverFromTheWeb`
- `0x18000f22c`: `InstallPrinterDriverFromTheWeb`
- `0x18000f2a4`: `InstallPrinterDriverFromTheWeb`
- `0x18000f32a`: `InstallPrinterDriverFromTheWeb`
- `0x18000f3aa`: `InstallPrinterDriverFromTheWeb`
- `0x18000f43a`: `InstallPrinterDriverFromTheWeb`
- `0x18000f560`: `InstallPrinterDriverFromTheWeb`
- `0x18000f611`: `InstallPrinterDriverFromTheWeb`
- `0x18000f220`: `CreatePrinterDeviceInfoList failed`
- `0x18000f298`: `PSetupBuildDriversFromPath failed`
- `0x18000f42e`: `FindFirstFile failed (directory in additional info)`
- `0x18000f554`: `InstallPrinterDriverFromPackage failed (driver store inf path in additional info`

## pseudocode

```c
__int64 __fastcall InstallPrinterDriverFromTheWeb(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        _OWORD *a6)
{
  const unsigned __int16 *v6; // rsi
  _OWORD *v8; // rbx
  __int64 v10; // r12
  unsigned __int16 *v11; // r15
  __int64 v12; // rax
  unsigned int v13; // edi
  HLOCAL v14; // rax
  unsigned int v15; // edi
  int v16; // ecx
  void *v17; // r11
  unsigned int v18; // eax
  __int64 v19; // rax
  char *v20; // rcx
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm0
  __int128 v27; // xmm1
  int v28; // eax
  __int16 *v29; // rcx
  __int64 v30; // rbx
  __int64 v31; // r12
  __int64 v32; // r15
  int v33; // ecx
  int v34; // r15d
  int FailureLastError; // eax
  HDEVINFO DeviceInfoList; // rbx
  signed int v37; // eax
  unsigned int v38; // ecx
  int v39; // eax
  int v40; // eax
  const unsigned __int16 **v41; // rbx
  signed int v42; // eax
  unsigned int v43; // ecx
  int v44; // eax
  unsigned int v45; // ebx
  int v46; // edx
  int v47; // r8d
  HRESULT v48; // eax
  int v49; // eax
  wchar_t *v50; // rax
  int v51; // ecx
  bool v53; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v54; // [rsp+68h] [rbp-98h]
  __int64 v55; // [rsp+70h] [rbp-90h] BYREF
  int v56; // [rsp+78h] [rbp-88h] BYREF
  int v57; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h]
  HLOCAL v59; // [rsp+98h] [rbp-68h]
  char v60; // [rsp+A0h] [rbp-60h] BYREF
  int v61; // [rsp+1B4h] [rbp+B4h]
  int v62; // [rsp+1C0h] [rbp+C0h]
  _BYTE v63[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  int v64; // [rsp+210h] [rbp+110h] BYREF
  __int16 v65; // [rsp+214h] [rbp+114h]
  wchar_t Str[264]; // [rsp+220h] [rbp+120h] BYREF
  WCHAR pszInfPath[264]; // [rsp+430h] [rbp+330h] BYREF

  v6 = a5;
  v8 = a6;
  v10 = a1;
  v55 = a1;
  v54 = a4;
  v56 = 0;
  v11 = a4;
  memset_0(Str, 0, 0x208u);
  memset_0(&v57, 0, 0x148u);
  v64 = 0;
  v65 = 0;
  if ( a6 && gpCodeDownLoadInfo && v11 && a3 && a2 )
  {
    v57 = 328;
    v62 = 0;
    if ( a5 )
    {
      v12 = -1;
      do
        ++v12;
      while ( a5[v12] );
    }
    else
    {
      LODWORD(v12) = 0;
      v6 = (const unsigned __int16 *)&v64;
    }
    v13 = v12 + 2;
    v14 = LocalAlloc(0x40u, (unsigned int)(2 * (v12 + 2)));
    hMem = v14;
    if ( v14 )
    {
      v18 = StringCchCopyW((unsigned __int16 *)v14, v13, v6);
      v15 = StatusFromHResult(v18);
    }
    else
    {
      v15 = 8;
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"InstallPrinterDriverFromTheWeb",
        L"Not enough memory (1)",
        a2,
        0,
        0,
        0,
        0,
        0,
        0,
        8u,
        0x80070008);
      v17 = 0;
    }
  }
  else
  {
    v15 = 87;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InstallPrinterDriverFromTheWeb",
      L"Invalid parameter",
      a2,
      0,
      0,
      0,
      0,
      0,
      0,
      0x57u,
      0x80070057);
    v17 = 0;
    if ( !a2 || !a3 || !v11 )
      goto LABEL_82;
  }
  if ( v6 && (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
  {
    McTemplateU0zzzz_EventWriteTransfer(
      v16,
      (unsigned int)DocPerf_Setup_InstallPrinterDriverFromTheWeb_Start,
      (_DWORD)a2,
      (_DWORD)a3,
      (__int64)v11,
      (__int64)v6);
    v17 = 0;
  }
  if ( !v15 )
  {
    v19 = 2;
    v20 = &v60;
    do
    {
      v21 = v8[1];
      *(_OWORD *)v20 = *v8;
      v22 = v8[2];
      *((_OWORD *)v20 + 1) = v21;
      v23 = v8[3];
      *((_OWORD *)v20 + 2) = v22;
      v24 = v8[4];
      *((_OWORD *)v20 + 3) = v23;
      v25 = v8[5];
      *((_OWORD *)v20 + 4) = v24;
      v26 = v8[6];
      *((_OWORD *)v20 + 5) = v25;
      v27 = v8[7];
      v8 += 8;
      *((_OWORD *)v20 + 6) = v26;
      *((_OWORD *)v20 + 7) = v27;
      v20 += 128;
      --v19;
    }
    while ( v19 );
    v28 = *((_DWORD *)v8 + 4);
    *(_OWORD *)v20 = *v8;
    *((_DWORD *)v20 + 4) = v28;
    v29 = &_ImageBase;
    v59 = v17;
    v61 = (unsigned __int16)word_180047CE4[4 * MyPlatform];
    v30 = -1;
    do
      ++v30;
    while ( v11[v30] != (_WORD)v17 );
    if ( (_DWORD)v30 )
    {
      v31 = -1;
      do
        ++v31;
      while ( a3[v31] != (_WORD)v17 );
      if ( (_DWORD)v31 )
      {
        v32 = -1;
        do
          ++v32;
        while ( a2[v32] != (_WORD)v17 );
        if ( (_DWORD)v32 )
        {
          v59 = LocalAlloc(0x40u, (unsigned int)(2 * (v30 + v32 + v31) + 8));
          if ( !v59 )
          {
            v15 = 8;
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
              L"InstallPrinterDriverFromTheWeb",
              L"Not enough memory (2)",
              a2,
              0,
              0,
              0,
              0,
              0,
              0,
              8u,
              0x80070008);
LABEL_43:
            v11 = v54;
            goto LABEL_82;
          }
          StringCchCopyW((unsigned __int16 *)v59, (int)v30 + 1, v54);
          StringCchCopyW((unsigned __int16 *)v59 + (int)v30 + 1, (int)v31 + 1, a3);
          StringCchCopyW((unsigned __int16 *)v59 + (int)v30 + (__int64)(int)v31 + 2, (int)v32 + 1, a2);
        }
        v11 = v54;
      }
      v10 = v55;
    }
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McTemplateU0zzzz_EventWriteTransfer(
        (_DWORD)v29,
        (unsigned int)DocPerf_Setup_DownloadDriverFromWindowsUpdate_Start,
        (_DWORD)a2,
        (_DWORD)a3,
        (__int64)v11,
        (__int64)v6);
    if ( (*((unsigned int (__fastcall **)(_QWORD, __int64, int *, wchar_t *, int, int *))gpCodeDownLoadInfo + 3))(
           *((_QWORD *)gpCodeDownLoadInfo + 1),
           v10,
           &v57,
           Str,
           260,
           &v56) )
    {
      v34 = 1;
    }
    else
    {
      v34 = 0;
      FailureLastError = GetFailureLastError();
      v15 = FailureLastError;
      if ( FailureLastError > 0 )
        FailureLastError = (unsigned __int16)FailureLastError | 0x80070000;
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"InstallPrinterDriverFromTheWeb",
        L"Download failed",
        a2,
        0,
        0,
        0,
        0,
        0,
        0,
        v15,
        FailureLastError);
    }
    if ( (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
      McTemplateU0zzzz_EventWriteTransfer(
        v33,
        (unsigned int)DocPerf_Setup_DownloadDriverFromWindowsUpdate_Stop,
        (_DWORD)a2,
        (_DWORD)a3,
        (__int64)v54,
        (__int64)v6);
    if ( !v15 )
    {
      DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, HWND_MESSAGE|0x2LL);
      if ( DeviceInfoList != (HDEVINFO)-1LL
        || ((v37 = GetFailureLastError(), v15 = v37, v37 > 0) ? (v38 = (unsigned __int16)v37 | 0x80070000) : (v38 = v37),
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
              L"InstallPrinterDriverFromTheWeb",
              L"CreatePrinterDeviceInfoList failed",
              Str,
              0,
              0,
              0,
              0,
              0,
              0,
              v37,
              v38),
            !v15) )
      {
        if ( (unsigned int)PSetupBuildDriversFromPath(DeviceInfoList, Str) )
          goto LABEL_98;
        v39 = GetFailureLastError();
        v15 = v39;
        if ( v39 > 0 )
          v39 = (unsigned __int16)v39 | 0x80070000;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"InstallPrinterDriverFromTheWeb",
          L"PSetupBuildDriversFromPath failed",
          Str,
          0,
          0,
          0,
          0,
          0,
          0,
          v15,
          v39);
        if ( !v15 )
        {
LABEL_98:
          if ( (unsigned int)PreSelectDriverEx((int)DeviceInfoList, a3, a2, MyPlatform, 0) )
            goto LABEL_61;
          v40 = GetFailureLastError();
          v15 = v40;
          if ( v40 > 0 )
            v40 = (unsigned __int16)v40 | 0x80070000;
          SplLogPrinterSetupCoreDriverEvent(
            &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
            L"InstallPrinterDriverFromTheWeb",
            L"PreSelectDriverEx failed",
            Str,
            0,
            0,
            0,
            0,
            0,
            0,
            v15,
            v40);
          if ( !v15 )
          {
LABEL_61:
            v41 = (const unsigned __int16 **)BuildInternalData((int)DeviceInfoList, 0);
            if ( v41
              || ((v42 = GetFailureLastError(), v15 = v42, v42 > 0)
                ? (v43 = (unsigned __int16)v42 | 0x80070000)
                : (v43 = v42),
                  SplLogPrinterSetupCoreDriverEvent(
                    &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                    L"InstallPrinterDriverFromTheWeb",
                    L"BuildInternalData failed",
                    Str,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    v42,
                    v43),
                  !v15) )
            {
              memset_0(Str, 0, 0x208u);
              if ( (int)StringCchCopyW(Str, 0x104u, *v41) >= 0 )
                goto LABEL_70;
              v44 = GetFailureLastError();
              v15 = v44;
              if ( v44 > 0 )
                v44 = (unsigned __int16)v44 | 0x80070000;
              SplLogPrinterSetupCoreDriverEvent(
                &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                L"InstallPrinterDriverFromTheWeb",
                L"FindFirstFile failed (directory in additional info)",
                Str,
                0,
                0,
                0,
                0,
                0,
                0,
                v15,
                v44);
              if ( !v15 )
              {
LABEL_70:
                memset_0(pszInfPath, 0, 0x208u);
                LODWORD(v55) = 260;
                v45 = 0;
                v53 = 0;
                NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v63, v46, v47);
                if ( (int)NSecurityLibrary::TSidUserContext::IsLocalSystem(
                            (NSecurityLibrary::TSidUserContext *)v63,
                            &v53) >= 0
                  && v53 )
                {
                  v45 = 64;
                }
                v48 = DriverStoreAddDriverPackageW(
                        Str,
                        v45,
                        0,
                        (unsigned __int16)word_180047CE4[4 * MyPlatform],
                        pszInfPath,
                        &v55);
                if ( v48 < 0
                  || (v48 = InstallPrinterDriverFromPackageW(0, pszInfPath, a2, (LPCWSTR)PlatformEnv[MyPlatform], 0),
                      v48 < 0) )
                {
                  v49 = StatusFromHResult((unsigned int)v48);
                  v15 = v49;
                  if ( v49 > 0 )
                    v49 = (unsigned __int16)v49 | 0x80070000;
                  SplLogPrinterSetupCoreDriverEvent(
                    &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
                    L"InstallPrinterDriverFromTheWeb",
                    L"InstallPrinterDriverFromPackage failed (driver store inf path in additional info",
                    pszInfPath,
                    0,
                    0,
                    0,
                    0,
                    0,
                    0,
                    v15,
                    v49);
                }
                NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v63);
              }
            }
          }
        }
      }
    }
    if ( v34 )
    {
      v50 = wcsrchr(Str, 0x5Cu);
      if ( v50 )
      {
        *v50 = 0;
        RecursivelyDeleteDirectory(Str, 5);
      }
    }
    goto LABEL_43;
  }
LABEL_82:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v59 )
  {
    LocalFree(v59);
    v59 = 0;
  }
  if ( v15 )
    SetLastError(v15);
  else
    SplLogPrinterSetupGenericEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
      L"InstallPrinterDriverFromTheWeb",
      0,
      a2,
      0,
      0,
      0);
  if ( a2 && a3 && v11 && v6 && (Microsoft_Windows_DocumentsEnableBits & 2) != 0 )
    McTemplateU0zzzz_EventWriteTransfer(
      v51,
      (unsigned int)DocPerf_Setup_InstallPrinterDriverFromTheWeb_Stop,
      (_DWORD)a2,
      (_DWORD)a3,
      (__int64)v11,
      (__int64)v6);
  return v15;
}

```

## disassembly

```asm
0x18000ed30  push    rbp
0x18000ed32  push    rbx
0x18000ed33  push    rsi
0x18000ed34  push    rdi
0x18000ed35  push    r12
0x18000ed37  push    r13
0x18000ed39  push    r14
0x18000ed3b  push    r15
0x18000ed3d  lea     rbp, [rsp-558h]
0x18000ed45  sub     rsp, 658h
0x18000ed4c  mov     rax, cs:__security_cookie
0x18000ed53  xor     rax, rsp
0x18000ed56  mov     [rbp+590h+var_50], rax
0x18000ed5d  mov     rsi, [rbp+590h+arg_20]
0x18000ed64  mov     r13, r8
0x18000ed67  mov     rbx, [rbp+590h+arg_28]
0x18000ed6e  mov     r14, rdx
0x18000ed71  mov     r12, rcx
0x18000ed74  mov     [rsp+690h+var_620], rcx
0x18000ed79  xor     eax, eax
0x18000ed7b  mov     [rsp+690h+var_628], r9
0x18000ed80  xor     edx, edx; Val
0x18000ed82  mov     [rsp+690h+var_618], eax
0x18000ed86  mov     r8d, 208h; Size
0x18000ed8c  lea     rcx, [rbp+590h+Str]; void *
0x18000ed93  mov     r15, r9
0x18000ed96  call    memset_0
0x18000ed9b  mov     edi, 148h
0x18000eda0  lea     rcx, [rbp+590h+var_610]; void *
0x18000eda4  mov     r8d, edi; Size
0x18000eda7  xor     edx, edx; Val
0x18000eda9  call    memset_0
0x18000edae  mov     eax, cs:dword_18003E2C8
0x18000edb4  xor     ecx, ecx
0x18000edb6  mov     [rbp+590h+var_480], eax
0x18000edbc  movzx   eax, cs:word_18003E2CC
0x18000edc3  mov     [rbp+590h+var_47C], ax
0x18000edca  test    rbx, rbx
0x18000edcd  jz      loc_18000EEAB
0x18000edd3  cmp     cs:gpCodeDownLoadInfo, rcx
0x18000edda  jz      loc_18000EEAB
0x18000ede0  test    r15, r15
0x18000ede3  jz      loc_18000EEAB
0x18000ede9  test    r13, r13
0x18000edec  jz      loc_18000EEAB
0x18000edf2  test    r14, r14
0x18000edf5  jz      loc_18000EEAB
0x18000edfb  mov     [rbp+590h+var_610], edi
0x18000edfe  mov     [rbp+590h+var_4D0], ecx
0x18000ee04  test    rsi, rsi
0x18000ee07  jz      short loc_18000EE18
0x18000ee09  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ee0d  inc     rax
0x18000ee10  cmp     [rsi+rax*2], cx
0x18000ee14  jnz     short loc_18000EE0D
0x18000ee16  jmp     short loc_18000EE21
0x18000ee18  mov     eax, ecx
0x18000ee1a  lea     rsi, [rbp+590h+var_480]
0x18000ee21  lea     edi, [rax+2]
0x18000ee24  mov     ecx, 40h ; '@'; uFlags
0x18000ee29  lea     edx, [rdi+rdi]; uBytes
0x18000ee2c  call    cs:__imp_LocalAlloc
0x18000ee32  xor     r11d, r11d
0x18000ee35  mov     [rbp+590h+hMem], rax
0x18000ee39  test    rax, rax
0x18000ee3c  jnz     short loc_18000EE93
0x18000ee3e  mov     [rsp+690h+var_638], 80070008h; unsigned int
0x18000ee46  lea     eax, [r11+8]
0x18000ee4a  mov     [rsp+690h+var_640], eax; unsigned int
0x18000ee4e  lea     r8, aNotEnoughMemor_4; "Not enough memory (1)"
0x18000ee55  mov     [rsp+690h+var_648], r11; unsigned __int16 *
0x18000ee5a  lea     rdx, aInstallprinter_0; "InstallPrinterDriverFromTheWeb"
0x18000ee61  mov     [rsp+690h+var_650], r11d; int
0x18000ee66  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000ee6d  mov     [rsp+690h+var_658], r11; unsigned __int16 *
0x18000ee72  mov     r9, r14; unsigned __int16 *
0x18000ee75  mov     [rsp+690h+var_660], r11; unsigned __int16 *
0x18000ee7a  mov     edi, eax
0x18000ee7c  mov     [rsp+690h+var_668], r11; unsigned __int16 *
0x18000ee81  mov     qword ptr [rsp+690h+dwFlags], r11; unsigned __int16 *
0x18000ee86  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000ee8b  xor     r11d, r11d
0x18000ee8e  jmp     loc_18000EF14
0x18000ee93  mov     edx, edi; unsigned __int64
0x18000ee95  mov     r8, rsi; unsigned __int16 *
0x18000ee98  mov     rcx, rax; unsigned __int16 *
0x18000ee9b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eea0  mov     ecx, eax
0x18000eea2  call    StatusFromHResult
0x18000eea7  mov     edi, eax
0x18000eea9  jmp     short loc_18000EF14
0x18000eeab  mov     [rsp+690h+var_638], 80070057h; unsigned int
0x18000eeb3  lea     r8, aInvalidParamet; "Invalid parameter"
0x18000eeba  mov     edi, 57h ; 'W'
0x18000eebf  lea     rdx, aInstallprinter_0; "InstallPrinterDriverFromTheWeb"
0x18000eec6  mov     [rsp+690h+var_640], edi; unsigned int
0x18000eeca  mov     r9, r14; unsigned __int16 *
0x18000eecd  mov     [rsp+690h+var_648], rcx; unsigned __int16 *
0x18000eed2  mov     [rsp+690h+var_650], ecx; int
0x18000eed6  mov     [rsp+690h+var_658], rcx; unsigned __int16 *
0x18000eedb  mov     [rsp+690h+var_660], rcx; unsigned __int16 *
0x18000eee0  mov     [rsp+690h+var_668], rcx; unsigned __int16 *
0x18000eee5  mov     qword ptr [rsp+690h+dwFlags], rcx; unsigned __int16 *
0x18000eeea  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000eef1  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000eef6  xor     r11d, r11d
0x18000eef9  test    r14, r14
0x18000eefc  jz      loc_18000F5D5
0x18000ef02  test    r13, r13
0x18000ef05  jz      loc_18000F5D5
0x18000ef0b  test    r15, r15
0x18000ef0e  jz      loc_18000F5D5
0x18000ef14  test    rsi, rsi
0x18000ef17  jz      short loc_18000EF41
0x18000ef19  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000ef20  jz      short loc_18000EF41
0x18000ef22  mov     [rsp+690h+var_668], rsi
0x18000ef27  lea     rdx, DocPerf_Setup_InstallPrinterDriverFromTheWeb_Start
0x18000ef2e  mov     r9, r13
0x18000ef31  mov     qword ptr [rsp+690h+dwFlags], r15
0x18000ef36  mov     r8, r14
0x18000ef39  call    McTemplateU0zzzz_EventWriteTransfer
0x18000ef3e  xor     r11d, r11d
0x18000ef41  test    edi, edi
0x18000ef43  jnz     loc_18000F5D5
0x18000ef49  lea     eax, [rdi+2]
0x18000ef4c  lea     edx, [rax+7Eh]
0x18000ef4f  lea     rcx, [rbp+590h+var_5F0]
0x18000ef53  movups  xmm0, xmmword ptr [rbx]
0x18000ef56  movups  xmm1, xmmword ptr [rbx+10h]
0x18000ef5a  movups  xmmword ptr [rcx], xmm0
0x18000ef5d  movups  xmm0, xmmword ptr [rbx+20h]
0x18000ef61  movups  xmmword ptr [rcx+10h], xmm1
0x18000ef65  movups  xmm1, xmmword ptr [rbx+30h]
0x18000ef69  movups  xmmword ptr [rcx+20h], xmm0
0x18000ef6d  movups  xmm0, xmmword ptr [rbx+40h]
0x18000ef71  movups  xmmword ptr [rcx+30h], xmm1
0x18000ef75  movups  xmm1, xmmword ptr [rbx+50h]
0x18000ef79  movups  xmmword ptr [rcx+40h], xmm0
0x18000ef7d  movups  xmm0, xmmword ptr [rbx+60h]
0x18000ef81  movups  xmmword ptr [rcx+50h], xmm1
0x18000ef85  movups  xmm1, xmmword ptr [rbx+70h]
0x18000ef89  add     rbx, rdx
0x18000ef8c  movups  xmmword ptr [rcx+60h], xmm0
0x18000ef90  movups  xmmword ptr [rcx+70h], xmm1
0x18000ef94  add     rcx, rdx
0x18000ef97  sub     rax, 1
0x18000ef9b  jnz     short loc_18000EF53
0x18000ef9d  mov     eax, [rbx+10h]
0x18000efa0  movups  xmm0, xmmword ptr [rbx]
0x18000efa3  movups  xmmword ptr [rcx], xmm0
0x18000efa6  mov     [rcx+10h], eax
0x18000efa9  lea     rcx, __ImageBase
0x18000efb0  movsxd  rax, cs:MyPlatform
0x18000efb7  mov     [rbp+590h+var_5F8], r11
0x18000efbb  movzx   eax, ds:rva word_180047CE4[rcx+rax*8]
0x18000efc3  mov     [rbp+590h+var_4DC], eax
0x18000efc9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000efcd  mov     rbx, rax
0x18000efd0  inc     rbx
0x18000efd3  cmp     [r15+rbx*2], r11w
0x18000efd8  jnz     short loc_18000EFD0
0x18000efda  test    ebx, ebx
0x18000efdc  jz      loc_18000F08D
0x18000efe2  mov     r12, rax
0x18000efe5  inc     r12
0x18000efe8  cmp     [r13+r12*2+0], r11w
0x18000efee  jnz     short loc_18000EFE5
0x18000eff0  test    r12d, r12d
0x18000eff3  jz      loc_18000F088
0x18000eff9  mov     r15, rax
0x18000effc  inc     r15
0x18000efff  cmp     [r14+r15*2], r11w
0x18000f004  jnz     short loc_18000EFFC
0x18000f006  test    r15d, r15d
0x18000f009  jz      short loc_18000F083
0x18000f00b  lea     eax, [r15+r12]
0x18000f00f  mov     ecx, 40h ; '@'; uFlags
0x18000f014  add     eax, ebx
0x18000f016  lea     edx, ds:8[rax*2]; uBytes
0x18000f01d  call    cs:__imp_LocalAlloc
0x18000f023  mov     [rbp+590h+var_5F8], rax
0x18000f027  mov     rcx, rax; unsigned __int16 *
0x18000f02a  test    rax, rax
0x18000f02d  jz      loc_18000F14C
0x18000f033  mov     r8, [rsp+690h+var_628]; unsigned __int16 *
0x18000f038  lea     eax, [rbx+1]
0x18000f03b  movsxd  rdx, eax; unsigned __int64
0x18000f03e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f043  mov     rcx, [rbp+590h+var_5F8]
0x18000f047  lea     eax, [r12+1]
0x18000f04c  add     rcx, 2
0x18000f050  movsxd  rbx, ebx
0x18000f053  movsxd  rdx, eax; unsigned __int64
0x18000f056  mov     r8, r13; unsigned __int16 *
0x18000f059  lea     rcx, [rcx+rbx*2]; unsigned __int16 *
0x18000f05d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f062  mov     rax, [rbp+590h+var_5F8]
0x18000f066  lea     r11d, [r15+1]
0x18000f06a  add     rax, 4
0x18000f06e  movsxd  rcx, r12d
0x18000f071  add     rcx, rbx
0x18000f074  movsxd  rdx, r11d; unsigned __int64
0x18000f077  mov     r8, r14; unsigned __int16 *
0x18000f07a  lea     rcx, [rax+rcx*2]; unsigned __int16 *
0x18000f07e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f083  mov     r15, [rsp+690h+var_628]
0x18000f088  mov     r12, [rsp+690h+var_620]
0x18000f08d  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000f094  jz      short loc_18000F0B2
0x18000f096  mov     [rsp+690h+var_668], rsi
0x18000f09b  lea     rdx, DocPerf_Setup_DownloadDriverFromWindowsUpdate_Start
0x18000f0a2  mov     r9, r13
0x18000f0a5  mov     qword ptr [rsp+690h+dwFlags], r15
0x18000f0aa  mov     r8, r14
0x18000f0ad  call    McTemplateU0zzzz_EventWriteTransfer
0x18000f0b2  mov     rcx, cs:gpCodeDownLoadInfo
0x18000f0b9  lea     rdx, [rsp+690h+var_618]
0x18000f0be  mov     [rsp+690h+var_668], rdx
0x18000f0c3  lea     r9, [rbp+590h+Str]
0x18000f0ca  lea     r8, [rbp+590h+var_610]
0x18000f0ce  mov     [rsp+690h+dwFlags], 104h
0x18000f0d6  mov     rdx, r12
0x18000f0d9  mov     rax, [rcx+18h]
0x18000f0dd  mov     rcx, [rcx+8]
0x18000f0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0e6  xor     r12d, r12d
0x18000f0e9  test    eax, eax
0x18000f0eb  jnz     loc_18000F1A7
0x18000f0f1  mov     r15d, r12d
0x18000f0f4  call    GetFailureLastError
0x18000f0f9  mov     edi, eax
0x18000f0fb  test    eax, eax
0x18000f0fd  jle     short loc_18000F107
0x18000f0ff  movzx   eax, di
0x18000f102  or      eax, 80070000h
0x18000f107  mov     [rsp+690h+var_638], eax; unsigned int
0x18000f10b  lea     r8, aDownloadFailed; "Download failed"
0x18000f112  mov     [rsp+690h+var_640], edi; unsigned int
0x18000f116  lea     rdx, aInstallprinter_0; "InstallPrinterDriverFromTheWeb"
0x18000f11d  mov     [rsp+690h+var_648], r12; unsigned __int16 *
0x18000f122  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000f129  mov     [rsp+690h+var_650], r12d; int
0x18000f12e  mov     r9, r14; unsigned __int16 *
0x18000f131  mov     [rsp+690h+var_658], r12; unsigned __int16 *
0x18000f136  mov     [rsp+690h+var_660], r12; unsigned __int16 *
0x18000f13b  mov     [rsp+690h+var_668], r12; unsigned __int16 *
0x18000f140  mov     qword ptr [rsp+690h+dwFlags], r12; unsigned __int16 *
0x18000f145  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000f14a  jmp     short loc_18000F1AD
0x18000f14c  mov     [rsp+690h+var_638], 80070008h; unsigned int
0x18000f154  lea     r8, aNotEnoughMemor_1; "Not enough memory (2)"
0x18000f15b  xor     r12d, r12d
0x18000f15e  lea     rdx, aInstallprinter_0; "InstallPrinterDriverFromTheWeb"
0x18000f165  mov     eax, 8
0x18000f16a  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18000f171  mov     [rsp+690h+var_640], eax; unsigned int
0x18000f175  mov     r9, r14; unsigned __int16 *
0x18000f178  mov     [rsp+690h+var_648], r12; unsigned __int16 *
0x18000f17d  mov     edi, eax
0x18000f17f  mov     [rsp+690h+var_650], r12d; int
0x18000f184  mov     [rsp+690h+var_658], r12; unsigned __int16 *
0x18000f189  mov     [rsp+690h+var_660], r12; unsigned __int16 *
0x18000f18e  mov     [rsp+690h+var_668], r12; unsigned __int16 *
0x18000f193  mov     qword ptr [rsp+690h+dwFlags], r12; unsigned __int16 *
0x18000f198  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18000f19d  mov     r15, [rsp+690h+var_628]
0x18000f1a2  jmp     loc_18000F5D8
0x18000f1a7  mov     r15d, 1
0x18000f1ad  test    cs:Microsoft_Windows_DocumentsEnableBits, 2
0x18000f1b4  jz      short loc_18000F1D7
0x18000f1b6  mov     rax, [rsp+690h+var_628]
0x18000f1bb  lea     rdx, DocPerf_Setup_DownloadDriverFromWindowsUpdate_Stop
0x18000f1c2  mov     [rsp+690h+var_668], rsi
0x18000f1c7  mov     r9, r13
0x18000f1ca  mov     r8, r14
0x18000f1cd  mov     qword ptr [rsp+690h+dwFlags], rax
0x18000f1d2  call    McTemplateU0zzzz_EventWriteTransfer
0x18000f1d7  test    edi, edi
0x18000f1d9  jnz     loc_18000F598
0x18000f1df  or      rdx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x18000f1e3  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18000f1ea  call    cs:__imp_SetupDiCreateDeviceInfoList
0x18000f1f0  mov     rbx, rax
0x18000f1f3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000f1f7  jnz     short loc_18000F260
0x18000f1f9  call    GetFailureLastError
0x18000f1fe  mov     edi, eax
0x18000f200  test    eax, eax
0x18000f202  jg      short loc_18000F208
0x18000f204  mov     ecx, eax
0x18000f206  jmp     short loc_18000F211
0x18000f208  movzx   ecx, di
0x18000f20b  or      ecx, 80070000h
0x18000f211  mov     [rsp+690h+var_638], ecx; unsigned int
0x18000f215  lea     r9, [rbp+590h+Str]; unsigned __int16 *
0x18000f21c  mov     [rsp+690h+var_640], edi; unsigned int
0x18000f220  lea     r8, aCreateprinterd; "CreatePrinterDeviceInfoList failed"
0x18000f227  mov     [rsp+690h+var_648], r12; unsigned __int16 *
0x18000f22c  lea     rdx, aInstallprinter_0; "InstallPrinterDriverFromTheWeb"
  ... truncated ...
```
