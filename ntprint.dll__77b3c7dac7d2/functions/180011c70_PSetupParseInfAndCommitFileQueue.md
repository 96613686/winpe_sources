# PSetupParseInfAndCommitFileQueue

- ea: `0x180011c70`
- end: `0x18001233d`
- name: `PSetupParseInfAndCommitFileQueue`
- size: `1741`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000c408`
- `0x18000d57c`
- `0x18000d624`
- `0x180011c70`
- `0x18001c5c0`
- `0x18001e264`
- `0x1800264c8`
- `0x180026820`
- `0x180027700`
- `0x180027750`
- `0x1800284d0`
- `0x1800288a0`
- `0x1800340b4`
- `0x180034bec`
- `0x180034f60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001208a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001208a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001219a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011d6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011dcb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011de7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ebc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011f07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011fc8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001219a`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180012243`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x180012243`
- `SETUPAPI!SetupOpenFileQueue` at `0x180011d4c`
- `SETUPAPI!SetupOpenFileQueue` at `0x180011d4c`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180011e35`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x180011e35`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18001223a`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18001223a`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180012269`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180012269`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18001220c`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x18001220c`
- `SETUPAPI!SetupCloseFileQueue` at `0x18001225b`
- `SETUPAPI!SetupCloseFileQueue` at `0x18001225b`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180011db1`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x180011db1`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x180011d46`
- `SETUPAPI!SetupSetNonInteractiveMode` at `0x180011d46`

## string_xrefs

- `0x180011d74`: `SetupOpenFileQueue failed`
- `0x1800120ee`: `PSetupInstallPrinterDriver`
- `0x180011e6f`: `CreatePrinterDeviceInfoList failed`
- `0x180011ff7`: `PSetupBuildDriversFromPath failed`
- `0x180011d7f`: `ParseInfAndCommitFileQueue`
- `0x180011dfc`: `ParseInfAndCommitFileQueue`
- `0x180011e7a`: `ParseInfAndCommitFileQueue`
- `0x1800121ca`: `ParseInfAndCommitFileQueue`
- `0x180012291`: `ParseInfAndCommitFileQueue`
- `0x180011cf3`: `PSetupParseInfAndCommitFileQueue`
- `0x180011d37`: `PSetupParseInfAndCommitFileQueue`
- `0x180011ddb`: `PSetupParseInfAndCommitFileQueue`
- `0x180011e59`: `PSetupParseInfAndCommitFileQueue`
- `0x180011f37`: `PSetupParseInfAndCommitFileQueue`
- `0x18001227e`: `PSetupParseInfAndCommitFileQueue`
- `0x1800122d8`: `PSetupParseInfAndCommitFileQueue`
- `0x1800122f6`: `PSetupParseInfAndCommitFileQueue`
- `0x18001230c`: `PSetupParseInfAndCommitFileQueue`
- `0x180011d0b`: `Parsing INF and committing files for %ws(%ws) on %ws with environment %ws and flags %d`
- `0x180011f30`: `No INF path was specified, searching through all installed drivers`
- `0x1800120d7`: `Cannot install non-native v4 driver`
- `0x180012277`: `Successfully committed driver files`
- `0x180012305`: `Error committing driver files: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall PSetupParseInfAndCommitFileQueue(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const WCHAR *a4,
        int a5,
        __int64 *a6)
{
  const wchar_t *v9; // rax
  signed int PlatformFromEnvironmentString; // ebx
  __int64 v11; // rsi
  NCoreLibrary *v12; // rcx
  DWORD LastError; // eax
  NCoreLibrary *v14; // rcx
  void *v15; // r15
  DWORD v16; // eax
  DWORD v17; // eax
  NCoreLibrary *v18; // rcx
  HDEVINFO DeviceInfoList; // r15
  int LastErrorAsFailHR; // eax
  DWORD v21; // eax
  NCoreLibrary *v22; // rcx
  DWORD v23; // eax
  NCoreLibrary *v24; // rcx
  DWORD v25; // eax
  const wchar_t *v26; // rax
  NCoreLibrary *v27; // rcx
  NCoreLibrary *v28; // rcx
  DWORD v29; // eax
  DWORD v30; // eax
  NCoreLibrary *v31; // rcx
  int v32; // edx
  const unsigned __int16 *v33; // rcx
  bool v34; // cf
  int v35; // eax
  DWORD v36; // eax
  unsigned __int16 *v39; // [rsp+68h] [rbp-98h]
  const unsigned __int16 *v40; // [rsp+70h] [rbp-90h]
  PVOID inited; // [rsp+78h] [rbp-88h]
  HSPFILEQ QueueHandle; // [rsp+80h] [rbp-80h]
  _QWORD v43[5]; // [rsp+90h] [rbp-70h] BYREF
  int v44; // [rsp+B8h] [rbp-48h]
  int v45; // [rsp+BCh] [rbp-44h]
  unsigned __int16 *v46; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v47; // [rsp+C8h] [rbp-38h]
  const WCHAR *v48; // [rsp+D0h] [rbp-30h]
  __int64 v49; // [rsp+D8h] [rbp-28h]
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+E0h] [rbp-20h] BYREF

  if ( !a3 || !a4 || !a6 )
  {
    PlatformFromEnvironmentString = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError("PSetupParseInfAndCommitFileQueue", L"Arguments are invalid:");
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupParseInfAndCommitFileQueue",
      L"pszDriverName = %ws, pszEnvironment = %ws, ppLocalData = %p",
      a3,
      a4,
      a6);
LABEL_65:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupParseInfAndCommitFileQueue",
      L"Error committing driver files: hr: 0x%x",
      (unsigned int)PlatformFromEnvironmentString);
    return (unsigned int)PlatformFromEnvironmentString;
  }
  v9 = a1;
  if ( !a1 )
    v9 = L"NULL";
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "PSetupParseInfAndCommitFileQueue",
    L"Parsing INF and committing files for %ws(%ws) on %ws with environment %ws and flags %d",
    a3,
    a2,
    v9,
    a4,
    a5);
  PlatformFromEnvironmentString = GetPlatformFromEnvironmentString(a4);
  if ( PlatformFromEnvironmentString < 0 )
    goto LABEL_65;
  v11 = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo("PSetupParseInfAndCommitFileQueue", L"Disabling SetupAPI UI");
  SetupSetNonInteractiveMode(1);
  QueueHandle = SetupOpenFileQueue();
  if ( QueueHandle == (HSPFILEQ)-1LL )
  {
    PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v12);
    LastError = GetLastError();
    SplLogPrinterSetupEvent(
      &SETUP_PARSEINF_FAILED,
      L"ParseInfAndCommitFileQueue",
      L"SetupOpenFileQueue failed",
      0,
      a2,
      a3,
      0,
      a4,
      LastError,
      PlatformFromEnvironmentString);
    if ( PlatformFromEnvironmentString < 0 )
      goto LABEL_65;
  }
  inited = SetupInitDefaultQueueCallback(HWND_MESSAGE|0x2LL);
  v15 = inited;
  if ( inited
    || (PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v14),
        v16 = GetLastError(),
        ClassInstallerTelemetry::WriteDbgTraceError(
          "PSetupParseInfAndCommitFileQueue",
          L"Initializing callback failed: %d",
          v16),
        v17 = GetLastError(),
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"SetupInitDefaultQueueCallback failed",
          0,
          a2,
          a3,
          0,
          a4,
          v17,
          PlatformFromEnvironmentString),
        PlatformFromEnvironmentString >= 0) )
  {
    DeviceInfoList = SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, HWND_MESSAGE|0x2LL);
    if ( DeviceInfoList == (HDEVINFO)-1LL )
    {
      LastErrorAsFailHR = NCoreLibrary::GetLastErrorAsFailHR(v18);
      PlatformFromEnvironmentString = LastErrorAsFailHR;
      if ( LastErrorAsFailHR < 0 )
      {
        ClassInstallerTelemetry::WriteDbgTraceError(
          "PSetupParseInfAndCommitFileQueue",
          L"Error creating device info list: hr: 0x%x",
          (unsigned int)LastErrorAsFailHR);
        v21 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"CreatePrinterDeviceInfoList failed",
          0,
          a2,
          a3,
          0,
          a4,
          v21,
          PlatformFromEnvironmentString);
LABEL_57:
        v15 = inited;
        goto LABEL_58;
      }
    }
    if ( !(unsigned int)AllowExcludedDrivers(DeviceInfoList) )
    {
      PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v22);
      if ( PlatformFromEnvironmentString < 0 )
      {
        v23 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"AllowExcludedDrivers failed",
          0,
          a2,
          a3,
          0,
          a4,
          v23,
          PlatformFromEnvironmentString);
        goto LABEL_51;
      }
    }
    if ( !(unsigned int)SetAltPlatform(DeviceInfoList, 0, 0) )
    {
      PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v24);
      if ( PlatformFromEnvironmentString < 0 )
      {
        v25 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"SetAltPlatform failed",
          0,
          a2,
          a3,
          0,
          a4,
          v25,
          PlatformFromEnvironmentString);
        goto LABEL_51;
      }
    }
    if ( a2 )
    {
      if ( (unsigned int)PSetupBuildDriversFromPath(DeviceInfoList, a2) )
      {
        PlatformFromEnvironmentString = 0;
      }
      else
      {
        PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v27);
        if ( PlatformFromEnvironmentString < 0 )
        {
          v26 = L"PSetupBuildDriversFromPath failed";
          v40 = a2;
          goto LABEL_32;
        }
      }
    }
    else
    {
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "PSetupParseInfAndCommitFileQueue",
        L"No INF path was specified, searching through all installed drivers");
      PlatformFromEnvironmentString = PSetupBuildDriverList(DeviceInfoList);
      if ( PlatformFromEnvironmentString < 0 )
      {
        v26 = L"PSetupBuildDriverList failed";
        v40 = 0;
LABEL_32:
        v39 = (unsigned __int16 *)v26;
        v30 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          v39,
          0,
          v40,
          a3,
          0,
          a4,
          v30,
          PlatformFromEnvironmentString);
        goto LABEL_51;
      }
    }
    if ( !(unsigned int)PreSelectDriverEx((int)DeviceInfoList, 0, a3, 1, a5 & 0x4000000) )
      PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v28);
    if ( PlatformFromEnvironmentString < 0 )
    {
      if ( (a5 & 0x4000000) == 0 )
      {
        v29 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"PreSelectDriverEx failed",
          0,
          a2,
          a3,
          0,
          a4,
          v29,
          PlatformFromEnvironmentString);
      }
      goto LABEL_51;
    }
    v11 = BuildInternalData((int)DeviceInfoList, 0);
    if ( v11 )
    {
      PlatformFromEnvironmentString = 0;
    }
    else
    {
      PlatformFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHR(v31);
      if ( PlatformFromEnvironmentString < 0 )
      {
        v36 = GetLastError();
        SplLogPrinterSetupEvent(
          &SETUP_PARSEINF_FAILED,
          L"ParseInfAndCommitFileQueue",
          L"BuildInternalData failed",
          0,
          a2,
          a3,
          0,
          a4,
          v36,
          PlatformFromEnvironmentString);
LABEL_51:
        if ( DeviceInfoList != (HDEVINFO)-1LL )
        {
          if ( MyPlatform != 1 )
          {
            memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
            DeviceInstallParams.cbSize = 584;
            if ( SetupDiGetDeviceInstallParamsW(DeviceInfoList, 0, &DeviceInstallParams) )
            {
              if ( DeviceInstallParams.FileQueue == QueueHandle )
              {
                DeviceInstallParams.FlagsEx &= ~0x10000000u;
                DeviceInstallParams.Flags &= ~8u;
                DeviceInstallParams.FileQueue = (HSPFILEQ)-1LL;
                SetupDiSetDeviceInstallParamsW(DeviceInfoList, 0, &DeviceInstallParams);
              }
            }
          }
          SetupDiDestroyDeviceInfoList(DeviceInfoList);
        }
        goto LABEL_57;
      }
    }
    *(_DWORD *)(v11 + 164) |= 8u;
    *(_QWORD *)(v11 + 280) = a4;
    if ( *(_DWORD *)(v11 + 96) >= 4u && (unsigned int)_o__wcsicmp(a4, L"Windows x64") )
    {
      v32 = *(_DWORD *)(v11 + 172);
      PlatformFromEnvironmentString = -2147024846;
      if ( v32 )
        v33 = *(const unsigned __int16 **)(v11 + 224);
      else
        v33 = 0;
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"PSetupInstallPrinterDriver",
        L"Cannot install non-native v4 driver",
        a1,
        *(const unsigned __int16 **)v11,
        a3,
        *(const unsigned __int16 **)(v11 + 184),
        off_1800551A8,
        v32,
        v33,
        0x70Du,
        0x80070032);
    }
    if ( PlatformFromEnvironmentString < 0 )
      goto LABEL_48;
    v34 = *(_DWORD *)(v11 + 96) < 4u;
    v43[1] = QueueHandle;
    v43[2] = inited;
    v43[3] = a1;
    v45 = a5;
    v49 = 0;
    v43[0] = DeviceInfoList;
    v43[4] = v11;
    v44 = 1;
    v46 = a2;
    v47 = a3;
    v48 = a4;
    v35 = v34
        ? LegacyParseInfAndCommitFileQueue((struct _SETUP_CONTEXT *)v43)
        : InstallV4Driver((struct _SETUP_CONTEXT *)v43);
    PlatformFromEnvironmentString = v35;
    if ( v35 < 0 )
    {
LABEL_48:
      if ( v11 )
        DestroyLocalData((HLOCAL)v11);
    }
    else
    {
      *a6 = v11;
    }
    goto LABEL_51;
  }
LABEL_58:
  if ( QueueHandle != (HSPFILEQ)-1LL )
    SetupCloseFileQueue(QueueHandle);
  if ( v15 )
    SetupTermDefaultQueueCallback(v15);
  if ( PlatformFromEnvironmentString < 0 )
    goto LABEL_65;
  ClassInstallerTelemetry::WriteDbgTraceInfo("PSetupParseInfAndCommitFileQueue", L"Successfully committed driver files");
  SplLogPrinterSetupEvent(
    &SETUP_PARSEINF_SUCCEEDED,
    L"ParseInfAndCommitFileQueue",
    0,
    0,
    a2,
    a3,
    *(const unsigned __int16 **)(v11 + 184),
    a4,
    0,
    PlatformFromEnvironmentString);
  return (unsigned int)PlatformFromEnvironmentString;
}

```

## disassembly

```asm
0x180011c70  push    rbp
0x180011c72  push    rbx
0x180011c73  push    rsi
0x180011c74  push    rdi
0x180011c75  push    r12
0x180011c77  push    r13
0x180011c79  push    r14
0x180011c7b  push    r15
0x180011c7d  lea     rbp, [rsp-248h]
0x180011c85  sub     rsp, 348h
0x180011c8c  mov     rax, cs:__security_cookie
0x180011c93  xor     rax, rsp
0x180011c96  mov     [rbp+280h+var_50], rax
0x180011c9d  mov     rsi, [rbp+280h+arg_28]
0x180011ca4  mov     r15d, 1
0x180011caa  mov     [rbp+280h+var_2F8], rsi
0x180011cae  mov     rdi, r9
0x180011cb1  mov     [rsp+380h+var_320], r15d
0x180011cb6  mov     r14, r8
0x180011cb9  mov     [rsp+380h+var_318], rcx
0x180011cbe  mov     r12, rdx
0x180011cc1  test    r8, r8
0x180011cc4  jz      loc_1800122CC
0x180011cca  test    r9, r9
0x180011ccd  jz      loc_1800122CC
0x180011cd3  test    rsi, rsi
0x180011cd6  jz      loc_1800122CC
0x180011cdc  mov     rax, rcx
0x180011cdf  lea     rdx, aNull; "NULL"
0x180011ce6  test    rcx, rcx
0x180011ce9  mov     ecx, [rbp+280h+arg_20]
0x180011cef  mov     dword ptr [rsp+380h+var_350], ecx
0x180011cf3  lea     rcx, aPsetupparseinf_0; "PSetupParseInfAndCommitFileQueue"
0x180011cfa  cmovz   rax, rdx
0x180011cfe  mov     [rsp+380h+var_358], r9
0x180011d03  mov     r9, r12
0x180011d06  mov     [rsp+380h+AlternateDefaultCatalogFile], rax
0x180011d0b  lea     rdx, aParsingInfAndC; "Parsing INF and committing files for %w"...
0x180011d12  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011d17  lea     rdx, [rsp+380h+var_320]
0x180011d1c  mov     rcx, rdi; lpString1
0x180011d1f  call    GetPlatformFromEnvironmentString
0x180011d24  mov     ebx, eax
0x180011d26  test    eax, eax
0x180011d28  js      loc_180012302
0x180011d2e  lea     rdx, aDisablingSetup; "Disabling SetupAPI UI"
0x180011d35  xor     esi, esi
0x180011d37  lea     rcx, aPsetupparseinf_0; "PSetupParseInfAndCommitFileQueue"
0x180011d3e  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011d43  mov     ecx, r15d; NonInteractiveFlag
0x180011d46  call    cs:__imp_SetupSetNonInteractiveMode
0x180011d4c  call    cs:__imp_SetupOpenFileQueue
0x180011d52  mov     [rbp+280h+QueueHandle], rax
0x180011d56  lea     r13, SETUP_PARSEINF_FAILED
0x180011d5d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011d61  jnz     short loc_180011DAD
0x180011d63  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011d68  mov     ebx, eax
0x180011d6a  call    cs:__imp_GetLastError
0x180011d70  mov     dword ptr [rsp+380h+var_338], ebx; unsigned int
0x180011d74  lea     r8, aSetupopenfileq; "SetupOpenFileQueue failed"
0x180011d7b  mov     [rsp+380h+var_340], eax; unsigned int
0x180011d7f  lea     rdx, aParseinfandcom; "ParseInfAndCommitFileQueue"
0x180011d86  mov     [rsp+380h+var_348], rdi; unsigned __int16 *
0x180011d8b  xor     r9d, r9d; unsigned __int16 *
0x180011d8e  mov     [rsp+380h+var_350], rsi; unsigned __int16 *
0x180011d93  mov     rcx, r13; struct _EVENT_DESCRIPTOR *
0x180011d96  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x180011d9b  mov     [rsp+380h+AlternateDefaultCatalogFile], r12; unsigned __int16 *
0x180011da0  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180011da5  test    ebx, ebx
0x180011da7  js      loc_180012302
0x180011dad  or      rcx, 0FFFFFFFFFFFFFFFFh; OwnerWindow
0x180011db1  call    cs:__imp_SetupInitDefaultQueueCallback
0x180011db7  mov     [rsp+380h+var_308], rax
0x180011dbc  mov     r15, rax
0x180011dbf  test    rax, rax
0x180011dc2  jnz     short loc_180011E2A
0x180011dc4  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011dc9  mov     ebx, eax
0x180011dcb  call    cs:__imp_GetLastError
0x180011dd1  mov     r8d, eax
0x180011dd4  lea     rdx, aInitializingCa; "Initializing callback failed: %d"
0x180011ddb  lea     rcx, aPsetupparseinf_0; "PSetupParseInfAndCommitFileQueue"
0x180011de2  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180011de7  call    cs:__imp_GetLastError
0x180011ded  mov     dword ptr [rsp+380h+var_338], ebx; unsigned int
0x180011df1  lea     r8, aSetupinitdefau; "SetupInitDefaultQueueCallback failed"
0x180011df8  mov     [rsp+380h+var_340], eax; unsigned int
0x180011dfc  lea     rdx, aParseinfandcom; "ParseInfAndCommitFileQueue"
0x180011e03  mov     [rsp+380h+var_348], rdi; unsigned __int16 *
0x180011e08  xor     r9d, r9d; unsigned __int16 *
0x180011e0b  mov     [rsp+380h+var_350], rsi; unsigned __int16 *
0x180011e10  mov     rcx, r13; struct _EVENT_DESCRIPTOR *
0x180011e13  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x180011e18  mov     [rsp+380h+AlternateDefaultCatalogFile], r12; unsigned __int16 *
0x180011e1d  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180011e22  test    ebx, ebx
0x180011e24  js      loc_18001224E
0x180011e2a  or      rdx, 0FFFFFFFFFFFFFFFFh; hwndParent
0x180011e2e  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x180011e35  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180011e3b  mov     r15, rax
0x180011e3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180011e42  jnz     short loc_180011EA5
0x180011e44  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011e49  mov     ebx, eax
0x180011e4b  test    eax, eax
0x180011e4d  jns     short loc_180011EA5
0x180011e4f  mov     r8d, eax
0x180011e52  lea     rdx, aErrorCreatingD; "Error creating device info list: hr: 0x"...
0x180011e59  lea     rcx, aPsetupparseinf_0; "PSetupParseInfAndCommitFileQueue"
0x180011e60  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180011e65  call    cs:__imp_GetLastError
0x180011e6b  mov     dword ptr [rsp+380h+var_338], ebx; unsigned int
0x180011e6f  lea     r8, aCreateprinterd; "CreatePrinterDeviceInfoList failed"
0x180011e76  mov     [rsp+380h+var_340], eax; unsigned int
0x180011e7a  lea     rdx, aParseinfandcom; "ParseInfAndCommitFileQueue"
0x180011e81  mov     [rsp+380h+var_348], rdi; unsigned __int16 *
0x180011e86  xor     r9d, r9d; unsigned __int16 *
0x180011e89  mov     [rsp+380h+var_350], rsi; unsigned __int16 *
0x180011e8e  mov     rcx, r13; struct _EVENT_DESCRIPTOR *
0x180011e91  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x180011e96  mov     [rsp+380h+AlternateDefaultCatalogFile], r12; unsigned __int16 *
0x180011e9b  call    ?SplLogPrinterSetupEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111KK@Z; SplLogPrinterSetupEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x180011ea0  jmp     loc_180012249
0x180011ea5  mov     rcx, r15; DeviceInfoSet
0x180011ea8  call    AllowExcludedDrivers
0x180011ead  test    eax, eax
0x180011eaf  jnz     short loc_180011EE0
0x180011eb1  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011eb6  mov     ebx, eax
0x180011eb8  test    eax, eax
0x180011eba  jns     short loc_180011EE0
0x180011ebc  call    cs:__imp_GetLastError
0x180011ec2  mov     dword ptr [rsp+380h+var_338], ebx
0x180011ec6  lea     r8, aAllowexcludedd; "AllowExcludedDrivers failed"
0x180011ecd  mov     [rsp+380h+var_340], eax
0x180011ed1  mov     [rsp+380h+var_348], rdi
0x180011ed6  mov     [rsp+380h+var_350], rsi
0x180011edb  jmp     loc_1800121BD
0x180011ee0  mov     r9, [rbp+280h+QueueHandle]
0x180011ee4  xor     edx, edx; lpString1
0x180011ee6  mov     r8d, [rsp+380h+var_320]
0x180011eeb  mov     rcx, r15; DeviceInfoSet
0x180011eee  mov     [rsp+380h+AlternateDefaultCatalogFile], rsi; AlternateDefaultCatalogFile
0x180011ef3  call    SetAltPlatform
0x180011ef8  test    eax, eax
0x180011efa  jnz     short loc_180011F2B
0x180011efc  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011f01  mov     ebx, eax
0x180011f03  test    eax, eax
0x180011f05  jns     short loc_180011F2B
0x180011f07  call    cs:__imp_GetLastError
0x180011f0d  mov     dword ptr [rsp+380h+var_338], ebx
0x180011f11  lea     r8, aSetaltplatform_0; "SetAltPlatform failed"
0x180011f18  mov     [rsp+380h+var_340], eax
0x180011f1c  mov     [rsp+380h+var_348], rdi
0x180011f21  mov     [rsp+380h+var_350], rsi
0x180011f26  jmp     loc_1800121BD
0x180011f2b  test    r12, r12
0x180011f2e  jnz     short loc_180011F62
0x180011f30  lea     rdx, aNoInfPathWasSp; "No INF path was specified, searching th"...
0x180011f37  lea     rcx, aPsetupparseinf_0; "PSetupParseInfAndCommitFileQueue"
0x180011f3e  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180011f43  mov     rcx, r15; DeviceInfoSet
0x180011f46  call    PSetupBuildDriverList
0x180011f4b  mov     ebx, eax
0x180011f4d  test    eax, eax
0x180011f4f  jns     short loc_180011F79
0x180011f51  lea     rax, aPsetupbuilddri_4; "PSetupBuildDriverList failed"
0x180011f58  mov     [rsp+380h+var_310], rsi
0x180011f5d  jmp     loc_180012003
0x180011f62  mov     r8d, 1
0x180011f68  mov     rdx, r12; unsigned __int16 *
0x180011f6b  mov     rcx, r15; DeviceInfoSet
0x180011f6e  call    PSetupBuildDriversFromPath
0x180011f73  test    eax, eax
0x180011f75  jz      short loc_180011FEC
0x180011f77  xor     ebx, ebx
0x180011f79  mov     eax, [rbp+280h+arg_20]
0x180011f7f  xor     r9d, r9d
0x180011f82  and     eax, 4000000h
0x180011f87  mov     r8, r14; LPCWSTR
0x180011f8a  mov     dword ptr [rsp+380h+var_358], eax; int
0x180011f8e  test    r12, r12
0x180011f91  mov     dword ptr [rsp+380h+var_310], eax
0x180011f95  mov     rcx, r15; int
0x180011f98  mov     eax, [rsp+380h+var_320]
0x180011f9c  setz    r9b
0x180011fa0  xor     edx, edx; lpString1
0x180011fa2  mov     dword ptr [rsp+380h+AlternateDefaultCatalogFile], eax; int
0x180011fa6  call    PreSelectDriverEx
0x180011fab  test    eax, eax
0x180011fad  jnz     short loc_180011FB6
0x180011faf  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011fb4  mov     ebx, eax
0x180011fb6  test    ebx, ebx
0x180011fb8  jns     loc_18001203E
0x180011fbe  cmp     dword ptr [rsp+380h+var_310], esi
0x180011fc2  jnz     loc_1800121D9
0x180011fc8  call    cs:__imp_GetLastError
0x180011fce  mov     dword ptr [rsp+380h+var_338], ebx
0x180011fd2  lea     r8, aPreselectdrive_0; "PreSelectDriverEx failed"
0x180011fd9  mov     [rsp+380h+var_340], eax
0x180011fdd  mov     [rsp+380h+var_348], rdi
0x180011fe2  mov     [rsp+380h+var_350], rsi
0x180011fe7  jmp     loc_1800121BD
0x180011fec  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180011ff1  mov     ebx, eax
0x180011ff3  test    eax, eax
0x180011ff5  jns     short loc_180011F79
0x180011ff7  lea     rax, aPsetupbuilddri_1; "PSetupBuildDriversFromPath failed"
0x180011ffe  mov     [rsp+380h+var_310], r12
0x180012003  mov     [rsp+380h+var_318], rax
0x180012008  call    cs:__imp_GetLastError
0x18001200e  mov     rcx, [rsp+380h+var_310]
0x180012013  mov     r8, [rsp+380h+var_318]
0x180012018  mov     dword ptr [rsp+380h+var_338], ebx
0x18001201c  mov     [rsp+380h+var_340], eax
0x180012020  xor     eax, eax
0x180012022  mov     [rsp+380h+var_348], rdi
0x180012027  mov     r9d, eax
0x18001202a  mov     [rsp+380h+var_350], rax
0x18001202f  mov     [rsp+380h+var_358], r14
0x180012034  mov     [rsp+380h+AlternateDefaultCatalogFile], rcx
0x180012039  jmp     loc_1800121CA
0x18001203e  mov     r8d, [rsp+380h+var_320]
0x180012043  xor     edx, edx; int
0x180012045  mov     rcx, r15; int
0x180012048  call    BuildInternalData
0x18001204d  mov     rsi, rax
0x180012050  test    rax, rax
0x180012053  jz      short loc_180012059
0x180012055  xor     ebx, ebx
0x180012057  jmp     short loc_180012068
0x180012059  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x18001205e  mov     ebx, eax
0x180012060  test    eax, eax
0x180012062  js      loc_18001219A
0x180012068  or      dword ptr [rsi+0A4h], 8
0x18001206f  mov     [rsi+118h], rdi
0x180012076  cmp     dword ptr [rsi+60h], 4
0x18001207a  jb      loc_18001211A
0x180012080  lea     rdx, aWindowsX64_0; "Windows x64"
0x180012087  mov     rcx, rdi
0x18001208a  call    cs:__imp__o__wcsicmp
0x180012090  test    eax, eax
0x180012092  jz      loc_18001211A
0x180012098  mov     edx, [rsi+0ACh]
0x18001209e  mov     ebx, 80070032h
0x1800120a3  test    edx, edx
0x1800120a5  jz      short loc_1800120B0
0x1800120a7  mov     rcx, [rsi+0E0h]
0x1800120ae  jmp     short loc_1800120B2
0x1800120b0  xor     ecx, ecx
0x1800120b2  movsxd  r13, [rsp+380h+var_320]
0x1800120b7  lea     r8, PlatformEnv
0x1800120be  mov     r9, [rsp+380h+var_318]; unsigned __int16 *
0x1800120c3  mov     [rsp+380h+var_328], 80070032h; unsigned int
0x1800120cb  mov     [rsp+380h+var_330], 70Dh; unsigned int
0x1800120d3  mov     rax, [r8+r13*8]
0x1800120d7  lea     r8, aCannotInstallN; "Cannot install non-native v4 driver"
0x1800120de  mov     [rsp+380h+var_338], rcx; unsigned __int16 *
0x1800120e3  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x1800120ea  mov     [rsp+380h+var_340], edx; int
0x1800120ee  lea     rdx, aPsetupinstallp_0; "PSetupInstallPrinterDriver"
0x1800120f5  mov     [rsp+380h+var_348], rax; unsigned __int16 *
0x1800120fa  mov     rax, [rsi+0B8h]
0x180012101  mov     [rsp+380h+var_350], rax; unsigned __int16 *
0x180012106  mov     rax, [rsi]
0x180012109  mov     [rsp+380h+var_358], r14; unsigned __int16 *
0x18001210e  mov     [rsp+380h+AlternateDefaultCatalogFile], rax; unsigned __int16 *
0x180012113  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x180012118  jmp     short loc_18001211F
0x18001211a  mov     r13d, [rsp+380h+var_320]
0x18001211f  test    ebx, ebx
0x180012121  js      short loc_18001218B
0x180012123  cmp     dword ptr [rsi+60h], 4
0x180012127  lea     rcx, [rbp+280h+var_2F0]; struct _SETUP_CONTEXT *
0x18001212b  mov     rax, [rbp+280h+QueueHandle]
0x18001212f  mov     [rbp+280h+var_2E8], rax
0x180012133  mov     rax, [rsp+380h+var_308]
0x180012138  mov     [rbp+280h+var_2E0], rax
0x18001213c  mov     rax, [rsp+380h+var_318]
0x180012141  mov     [rbp+280h+var_2D8], rax
0x180012145  mov     eax, [rbp+280h+arg_20]
0x18001214b  mov     [rbp+280h+var_2C4], eax
0x18001214e  mov     [rbp+280h+var_2A8], 0
0x180012156  mov     [rbp+280h+var_2F0], r15
0x18001215a  mov     [rbp+280h+var_2D0], rsi
0x18001215e  mov     [rbp+280h+var_2C8], r13d
0x180012162  mov     [rbp+280h+var_2C0], r12
0x180012166  mov     [rbp+280h+var_2B8], r14
0x18001216a  mov     [rbp+280h+var_2B0], rdi
0x18001216e  jnb     short loc_180012177
0x180012170  call    ?LegacyParseInfAndCommitFileQueue@@YAJPEAU_SETUP_CONTEXT@@@Z; LegacyParseInfAndCommitFileQueue(_SETUP_CONTEXT *)
0x180012175  jmp     short loc_18001217C
0x180012177  call    InstallV4Driver
0x18001217c  mov     ebx, eax
  ... truncated ...
```
