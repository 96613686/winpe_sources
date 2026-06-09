# FindLatestCoreDrivers

- ea: `0x18001c978`
- end: `0x18001d133`
- name: `FindLatestCoreDrivers`
- size: `1979`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001785c`
- `0x18001a914`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d21c`
- `0x18000d57c`
- `0x18000d624`
- `0x1800162c8`
- `0x180018d18`
- `0x18001b320`
- `0x18001c978`
- `0x180020330`
- `0x180026c04`
- `0x180026ed4`
- `0x1800272bc`
- `0x180034bec`
- `0x180036664`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d0fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d0fc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ccfb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ce50`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ccfb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001ce50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb5e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb5e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ca5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ca5b`
- `KERNEL32!lstrcmpiW` at `0x18001cc69`
- `KERNEL32!lstrcmpiW` at `0x18001cc69`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001cc3b`
- `SETUPAPI!SetupDiEnumDriverInfoW` at `0x18001cc3b`

## string_xrefs

- `0x18001cad3`: `StringCbCopy failed (source string in additional info)`
- `0x18001cce4`: `Found a compatible core driver for %ws in %ws`
- `0x18001cd68`: `StringCbCopy(2) failed (source - driver store inf path - in additional info)`
- `0x18001cdbe`: `The compatible core driver is the same or above the required version.`
- `0x18001ce28`: `The compatible core driver is older than the required inbox core driver version.`
- `0x18001ce39`: `Found another compatible core driver for %ws in %ws`
- `0x18001cec1`: `StringCbCopy(3) failed (source - driver store inf path - in additional info)`
- `0x18001cf3a`: `StringCbCopy(4) failed (source - driver store inf path - in additional info)`
- `0x18001cfdc`: `Couldn't find a compatible core driver %ws.`

## pseudocode

```c
_BOOL8 __fastcall FindLatestCoreDrivers(
        unsigned __int16 *a1,
        int a2,
        FILETIME a3,
        DWORDLONG a4,
        const WCHAR *a5,
        _QWORD *a6,
        unsigned int *a7)
{
  unsigned int v8; // r12d
  unsigned __int16 *i; // rcx
  __int64 v10; // rax
  __int64 v11; // r8
  signed int LastErrorAsHResult; // ebx
  unsigned int j; // edx
  __int64 v14; // rax
  const unsigned __int16 *v15; // rdi
  unsigned int v16; // esi
  signed int v17; // eax
  __int64 v18; // r11
  __int64 v19; // rax
  HDEVINFO v20; // rsi
  DWORD v21; // eax
  unsigned int m; // esi
  __int64 v23; // rdi
  int v24; // edx
  LONG v25; // esi
  DWORDLONG DriverVersion; // rcx
  FILETIME DriverDate; // rax
  signed int v28; // eax
  LONG v29; // eax
  const unsigned __int16 *v30; // r8
  __int64 v31; // rax
  unsigned int k; // edx
  __int64 v33; // rdi
  DWORD v34; // eax
  HDEVINFO DeviceInfoSet; // [rsp+68h] [rbp-98h] BYREF
  int v38; // [rsp+70h] [rbp-90h]
  _DWORD v39[3]; // [rsp+74h] [rbp-8Ch] BYREF
  PCWSTR Section; // [rsp+80h] [rbp-80h]
  FILETIME FileTime1; // [rsp+88h] [rbp-78h] BYREF
  DWORDLONG v42; // [rsp+90h] [rbp-70h]
  unsigned int *v43; // [rsp+98h] [rbp-68h]
  _QWORD *v44; // [rsp+A0h] [rbp-60h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ReturnBuffer[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  v42 = a4;
  FileTime1 = a3;
  Section = a5;
  v44 = a6;
  v43 = a7;
  DeviceInfoSet = (HDEVINFO)-1LL;
  if ( !a1 || !*a1 || !a7 || !a6 )
  {
    LastErrorAsHResult = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "FindLatestCoreDrivers",
      L"Invalid Argument: pszzCoreDriverDependencies=%ws, pdwDependencyCount=%d, ppCoreDriverDependencies=%p",
      a1,
      *a7,
      a6);
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"FindLatestCoreDrivers",
      L"Invalid argument(s)",
      0,
      0,
      0,
      0,
      (const unsigned __int16 *)PlatformEnv[a2],
      1,
      a1,
      0x57u,
      0x80070057);
    goto LABEL_72;
  }
  v8 = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo("FindLatestCoreDrivers", L"Finding latest required core drivers");
  *a6 = 0;
  *a7 = 0;
  for ( i = a1; *i; i += v10 + 1 )
  {
    v10 = -1;
    do
      ++v10;
    while ( i[v10] );
    ++v8;
  }
  *(_QWORD *)&v39[1] = LocalAlloc(0x40u, 624 * v8);
  v11 = *(_QWORD *)&v39[1];
  if ( !*(_QWORD *)&v39[1] )
  {
    LastErrorAsHResult = -2147024882;
LABEL_72:
    v34 = StatusFromHResult((unsigned int)LastErrorAsHResult);
    SetLastError(v34);
    return LastErrorAsHResult >= 0;
  }
  for ( j = 0; j < v8; *(_DWORD *)(624 * v14 + v11 + 616) = 0 )
    v14 = j++;
  v15 = a1;
  v16 = 0;
  while ( v16 < v8 )
  {
    v17 = StringCbCopyW((unsigned __int16 *)(v11 + 624LL * v16), 0x50u, v15);
    LastErrorAsHResult = v17;
    if ( v17 < 0 )
      SplLogPrinterSetupCoreDriverEvent(
        &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
        L"FindLatestCoreDrivers",
        L"StringCbCopy failed (source string in additional info)",
        v15,
        0,
        0,
        0,
        *(const unsigned __int16 **)(v18 + 8LL * a2),
        1,
        a1,
        (unsigned __int16)v17,
        v17);
    ++v16;
    v19 = -1;
    do
      ++v19;
    while ( v15[v19] );
    v11 = *(_QWORD *)&v39[1];
    v15 += v19 + 1;
    if ( LastErrorAsHResult < 0 )
      goto LABEL_20;
  }
  LastErrorAsHResult = CreateAndBuildDriverList((unsigned int)a2, &DeviceInfoSet, v11);
  if ( LastErrorAsHResult >= 0 )
  {
    memset_0(&DriverInfoData.DriverType, 0, 0x61Cu);
    v38 = 0;
    memset_0(ReturnBuffer, 0, 0x208u);
    v20 = DeviceInfoSet;
    v21 = 0;
    DriverInfoData.cbSize = 1568;
    while ( 1 )
    {
      if ( !SetupDiEnumDriverInfoW(v20, 0, 1u, v21, &DriverInfoData) )
      {
        v31 = *(_QWORD *)&v39[1];
        for ( k = 0; k < v8; ++k )
        {
          v31 = *(_QWORD *)&v39[1];
          v33 = *(_QWORD *)&v39[1] + 624LL * k;
          if ( !*(_DWORD *)(v33 + 616) )
          {
            LastErrorAsHResult = -2147021880;
            ClassInstallerTelemetry::WriteDbgTraceError(
              "FindLatestCoreDrivers",
              L"Couldn't find a compatible core driver %ws.",
              *(_QWORD *)&v39[1] + 624LL * k);
            SplLogPrinterSetupCoreDriverEvent(
              &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
              L"FindLatestCoreDrivers",
              L"Unable to find core dependency (see additional info for driver GUID)",
              (const unsigned __int16 *)v33,
              0,
              0,
              0,
              (const unsigned __int16 *)PlatformEnv[a2],
              1,
              a1,
              0xBC8u,
              0x80070BC8);
            goto LABEL_21;
          }
        }
        *v43 = v8;
        *v44 = v31;
        goto LABEL_22;
      }
      for ( m = 0; ; ++m )
      {
        if ( m >= v8 )
          goto LABEL_43;
        v23 = *(_QWORD *)&v39[1] + 624LL * m;
        if ( !lstrcmpiW((LPCWSTR)v23, DriverInfoData.Description) )
          break;
      }
      v20 = DeviceInfoSet;
      v39[0] = 0;
      if ( (unsigned int)GetDriverStorePathFromDeviceInfo(
                           (int)DeviceInfoSet,
                           v24,
                           (int)&DriverInfoData,
                           a2,
                           (__int64)v39,
                           ReturnBuffer)
        || (LastErrorAsHResult = GetLastErrorAsHResult(), LastErrorAsHResult >= 0) )
      {
        if ( v39[0] )
          break;
      }
LABEL_44:
      v21 = v38 + 1;
      DriverInfoData.cbSize = 1568;
      ++v38;
      if ( LastErrorAsHResult < 0 )
        goto LABEL_21;
    }
    if ( !*(_DWORD *)(v23 + 616) )
    {
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "FindLatestCoreDrivers",
        L"Found a compatible core driver for %ws in %ws",
        v23,
        ReturnBuffer);
      v25 = CompareFileTime(&FileTime1, &DriverInfoData.DriverDate);
      if ( Section )
      {
        if ( (unsigned int)VerifyLegacyNeedsDependencies(Section, ReturnBuffer) )
          goto LABEL_39;
LABEL_50:
        ClassInstallerTelemetry::WriteDbgTraceWarning(
          "FindLatestCoreDrivers",
          L"The compatible core driver is older than the required inbox core driver version.");
LABEL_43:
        v20 = DeviceInfoSet;
        goto LABEL_44;
      }
      if ( !(unsigned int)IsInboxCorePrinterDriver((LPCWSTR)v23) || v25 == -1 )
      {
LABEL_39:
        DriverVersion = DriverInfoData.DriverVersion;
      }
      else
      {
        if ( v25 )
          goto LABEL_50;
        DriverVersion = DriverInfoData.DriverVersion;
        if ( DriverInfoData.DriverVersion < v42 )
          goto LABEL_50;
      }
      DriverDate = DriverInfoData.DriverDate;
      *(_QWORD *)(v23 + 88) = DriverVersion;
      *(FILETIME *)(v23 + 80) = DriverDate;
      v28 = StringCbCopyW((unsigned __int16 *)(v23 + 96), 0x208u, ReturnBuffer);
      LastErrorAsHResult = v28;
      if ( v28 < 0 )
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"FindLatestCoreDrivers",
          L"StringCbCopy(2) failed (source - driver store inf path - in additional info)",
          ReturnBuffer,
          0,
          0,
          0,
          (const unsigned __int16 *)PlatformEnv[a2],
          1,
          a1,
          (unsigned __int16)v28,
          v28);
      *(_DWORD *)(v23 + 616) = 1;
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "FindLatestCoreDrivers",
        L"The compatible core driver is the same or above the required version.");
      goto LABEL_43;
    }
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "FindLatestCoreDrivers",
      L"Found another compatible core driver for %ws in %ws",
      v23,
      ReturnBuffer);
    v29 = CompareFileTime((const FILETIME *)(v23 + 80), &DriverInfoData.DriverDate);
    if ( v29 == -1 )
    {
      if ( Section && !(unsigned int)VerifyLegacyNeedsDependencies(Section, ReturnBuffer) )
        goto LABEL_64;
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "FindLatestCoreDrivers",
        L"The new core driver has a newer date than the previous best core driver");
      *(FILETIME *)(v23 + 80) = DriverInfoData.DriverDate;
      *(_QWORD *)(v23 + 88) = DriverInfoData.DriverVersion;
      LastErrorAsHResult = StringCbCopyW((unsigned __int16 *)(v23 + 96), 0x208u, ReturnBuffer);
      if ( LastErrorAsHResult >= 0 )
        goto LABEL_63;
      v30 = L"StringCbCopy(3) failed (source - driver store inf path - in additional info)";
    }
    else
    {
      if ( v29
        || DriverInfoData.DriverVersion <= *(_QWORD *)(v23 + 88)
        || Section && !(unsigned int)VerifyLegacyNeedsDependencies(Section, ReturnBuffer) )
      {
LABEL_64:
        ClassInstallerTelemetry::WriteDbgTraceWarning(
          "FindLatestCoreDrivers",
          L"This core driver is older than the previous best found core driver");
        goto LABEL_43;
      }
      ClassInstallerTelemetry::WriteDbgTraceInfo(
        "FindLatestCoreDrivers",
        L"The new core driver has the same date and newer version than the previous best core driver");
      *(_QWORD *)(v23 + 88) = DriverInfoData.DriverVersion;
      LastErrorAsHResult = StringCbCopyW((unsigned __int16 *)(v23 + 96), 0x208u, ReturnBuffer);
      if ( LastErrorAsHResult >= 0 )
        goto LABEL_63;
      v30 = L"StringCbCopy(4) failed (source - driver store inf path - in additional info)";
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"FindLatestCoreDrivers",
      v30,
      ReturnBuffer,
      0,
      0,
      0,
      (const unsigned __int16 *)PlatformEnv[a2],
      1,
      a1,
      (unsigned __int16)LastErrorAsHResult,
      LastErrorAsHResult);
LABEL_63:
    v20 = DeviceInfoSet;
    goto LABEL_44;
  }
LABEL_20:
  v20 = DeviceInfoSet;
LABEL_21:
  LocalFree(*(HLOCAL *)&v39[1]);
LABEL_22:
  if ( v20 != (HDEVINFO)-1LL )
    DestroyOnlyPrinterDeviceInfoList(v20);
  if ( LastErrorAsHResult < 0 )
    goto LABEL_72;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "FindLatestCoreDrivers",
    L"Successfully found all required core printer drivers.");
  SplLogPrinterSetupCoreDriverEvent(
    &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
    L"FindLatestCoreDrivers",
    0,
    0,
    0,
    0,
    0,
    (const unsigned __int16 *)PlatformEnv[a2],
    1,
    a1,
    0,
    0);
  return LastErrorAsHResult >= 0;
}

```

## disassembly

```asm
0x18001c978  mov     [rsp-8+arg_18], rbx
0x18001c97d  push    rbp
0x18001c97e  push    rsi
0x18001c97f  push    rdi
0x18001c980  push    r12
0x18001c982  push    r13
0x18001c984  push    r14
0x18001c986  push    r15
0x18001c988  lea     rbp, [rsp-7F0h]
0x18001c990  sub     rsp, 8F0h
0x18001c997  mov     rax, cs:__security_cookie
0x18001c99e  xor     rax, rsp
0x18001c9a1  mov     [rbp+820h+var_40], rax
0x18001c9a8  mov     rax, [rbp+820h+arg_20]
0x18001c9af  xor     ebx, ebx
0x18001c9b1  mov     rdi, [rbp+820h+arg_28]
0x18001c9b8  mov     r15, rcx
0x18001c9bb  mov     rsi, [rbp+820h+arg_30]
0x18001c9c2  mov     [rbp+820h+var_890], r9
0x18001c9c6  mov     [rsp+920h+var_8C0], edx
0x18001c9ca  mov     qword ptr [rbp+820h+FileTime1.dwLowDateTime], r8
0x18001c9ce  mov     [rbp+820h+Section], rax
0x18001c9d2  mov     [rbp+820h+var_880], rdi
0x18001c9d6  mov     [rbp+820h+var_888], rsi
0x18001c9da  mov     [rsp+920h+DeviceInfoSet], 0FFFFFFFFFFFFFFFFh
0x18001c9e3  test    rcx, rcx
0x18001c9e6  jz      loc_18001D070
0x18001c9ec  cmp     [rcx], bx
0x18001c9ef  jz      loc_18001D070
0x18001c9f5  test    rsi, rsi
0x18001c9f8  jz      loc_18001D070
0x18001c9fe  test    rdi, rdi
0x18001ca01  jz      loc_18001D070
0x18001ca07  lea     r13, aFindlatestcore_1; "FindLatestCoreDrivers"
0x18001ca0e  mov     r12d, ebx
0x18001ca11  mov     rcx, r13; char *
0x18001ca14  lea     rdx, aFindingLatestR; "Finding latest required core drivers"
0x18001ca1b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001ca20  mov     [rdi], rbx
0x18001ca23  lea     r14d, [rbx+1]
0x18001ca27  mov     [rsi], ebx
0x18001ca29  mov     rcx, r15
0x18001ca2c  cmp     [r15], bx
0x18001ca30  jz      short loc_18001CA4F
0x18001ca32  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ca36  inc     rax
0x18001ca39  cmp     [rcx+rax*2], bx
0x18001ca3d  jnz     short loc_18001CA36
0x18001ca3f  lea     rcx, [rcx+rax*2]
0x18001ca43  add     r12d, r14d
0x18001ca46  add     rcx, 2
0x18001ca4a  cmp     [rcx], bx
0x18001ca4d  jnz     short loc_18001CA32
0x18001ca4f  imul    edx, r12d, 270h; uBytes
0x18001ca56  mov     ecx, 40h ; '@'; uFlags
0x18001ca5b  call    cs:__imp_LocalAlloc
0x18001ca61  mov     qword ptr [rsp+920h+var_8AC+4], rax
0x18001ca66  mov     r8, rax
0x18001ca69  test    rax, rax
0x18001ca6c  jnz     short loc_18001CA78
0x18001ca6e  mov     ebx, 8007000Eh
0x18001ca73  jmp     loc_18001D0F3
0x18001ca78  mov     edx, ebx
0x18001ca7a  test    r12d, r12d
0x18001ca7d  jz      short loc_18001CA98
0x18001ca7f  mov     eax, edx
0x18001ca81  add     edx, r14d
0x18001ca84  imul    rcx, rax, 270h
0x18001ca8b  mov     [rcx+r8+268h], ebx
0x18001ca93  cmp     edx, r12d
0x18001ca96  jb      short loc_18001CA7F
0x18001ca98  mov     rdi, r15
0x18001ca9b  lea     r11, PlatformEnv
0x18001caa2  mov     esi, ebx
0x18001caa4  cmp     esi, r12d
0x18001caa7  jnb     loc_18001CBD6
0x18001caad  mov     eax, esi
0x18001caaf  mov     edx, 50h ; 'P'; unsigned __int64
0x18001cab4  imul    rcx, rax, 270h
0x18001cabb  add     rcx, r8; unsigned __int16 *
0x18001cabe  mov     r8, rdi; unsigned __int16 *
0x18001cac1  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cac6  xor     edx, edx
0x18001cac8  mov     ebx, eax
0x18001caca  test    eax, eax
0x18001cacc  jns     short loc_18001CB26
0x18001cace  movsxd  rcx, [rsp+920h+var_8C0]
0x18001cad3  lea     r8, aStringcbcopyFa; "StringCbCopy failed (source string in a"...
0x18001cada  mov     [rsp+920h+var_8C8], ebx; unsigned int
0x18001cade  mov     r9, rdi; unsigned __int16 *
0x18001cae1  movzx   eax, bx
0x18001cae4  mov     [rsp+920h+var_8D0], eax; unsigned int
0x18001cae8  mov     rax, [r11+rcx*8]
0x18001caec  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18001caf3  mov     [rsp+920h+var_8D8], r15; unsigned __int16 *
0x18001caf8  mov     [rsp+920h+var_8E0], r14d; int
0x18001cafd  mov     [rsp+920h+var_8E8], rax; unsigned __int16 *
0x18001cb02  mov     [rsp+920h+var_8F0], rdx; unsigned __int16 *
0x18001cb07  mov     [rsp+920h+ReturnBuffer], rdx; unsigned __int16 *
0x18001cb0c  mov     [rsp+920h+DriverInfoData], rdx; unsigned __int16 *
0x18001cb11  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x18001cb18  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001cb1d  lea     r11, PlatformEnv
0x18001cb24  xor     edx, edx
0x18001cb26  add     esi, r14d
0x18001cb29  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cb2d  inc     rax
0x18001cb30  cmp     [rdi+rax*2], dx
0x18001cb34  jnz     short loc_18001CB2D
0x18001cb36  mov     r8, qword ptr [rsp+920h+var_8AC+4]
0x18001cb3b  lea     rdi, [rdi+rax*2]
0x18001cb3f  add     rdi, 2
0x18001cb43  test    ebx, ebx
0x18001cb45  jns     loc_18001CAA4
0x18001cb4b  xor     edi, edi
0x18001cb4d  mov     rsi, [rsp+920h+DeviceInfoSet]
0x18001cb52  lea     r12, PlatformEnv
0x18001cb59  mov     rcx, qword ptr [rsp+920h+var_8AC+4]; hMem
0x18001cb5e  call    cs:__imp_LocalFree
0x18001cb64  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18001cb68  jz      short loc_18001CB72
0x18001cb6a  mov     rcx, rsi
0x18001cb6d  call    DestroyOnlyPrinterDeviceInfoList
0x18001cb72  test    ebx, ebx
0x18001cb74  js      loc_18001D0F3
0x18001cb7a  lea     rdx, aSuccessfullyFo; "Successfully found all required core pr"...
0x18001cb81  mov     rcx, r13; char *
0x18001cb84  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001cb89  movsxd  rax, [rsp+920h+var_8C0]
0x18001cb8e  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x18001cb95  mov     [rsp+920h+var_8C8], edi; unsigned int
0x18001cb99  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED; struct _EVENT_DESCRIPTOR *
0x18001cba0  mov     [rsp+920h+var_8D0], edi; unsigned int
0x18001cba4  xor     r9d, r9d; unsigned __int16 *
0x18001cba7  mov     [rsp+920h+var_8D8], r15; unsigned __int16 *
0x18001cbac  xor     r8d, r8d; unsigned __int16 *
0x18001cbaf  mov     rax, [r12+rax*8]
0x18001cbb3  mov     [rsp+920h+var_8E0], r14d; int
0x18001cbb8  mov     [rsp+920h+var_8E8], rax; unsigned __int16 *
0x18001cbbd  mov     [rsp+920h+var_8F0], rdi; unsigned __int16 *
0x18001cbc2  mov     [rsp+920h+ReturnBuffer], rdi; unsigned __int16 *
0x18001cbc7  mov     [rsp+920h+DriverInfoData], rdi; unsigned __int16 *
0x18001cbcc  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001cbd1  jmp     loc_18001D102
0x18001cbd6  mov     ecx, [rsp+920h+var_8C0]
0x18001cbda  lea     rdx, [rsp+920h+DeviceInfoSet]
0x18001cbdf  call    CreateAndBuildDriverList
0x18001cbe4  xor     edi, edi
0x18001cbe6  mov     ebx, eax
0x18001cbe8  test    eax, eax
0x18001cbea  js      loc_18001CB4D
0x18001cbf0  xor     edx, edx; Val
0x18001cbf2  lea     rcx, [rbp+820h+var_870.DriverType]; void *
0x18001cbf6  mov     r8d, 61Ch; Size
0x18001cbfc  call    memset_0
0x18001cc01  xor     edx, edx; Val
0x18001cc03  mov     [rsp+920h+var_8B0], edi
0x18001cc07  mov     r8d, 208h; Size
0x18001cc0d  lea     rcx, [rbp+820h+var_250]; void *
0x18001cc14  call    memset_0
0x18001cc19  mov     rsi, [rsp+920h+DeviceInfoSet]
0x18001cc1e  mov     eax, edi
0x18001cc20  mov     [rbp+820h+var_870.cbSize], 620h
0x18001cc27  lea     rcx, [rbp+820h+var_870]
0x18001cc2b  mov     r9d, eax; MemberIndex
0x18001cc2e  mov     [rsp+920h+DriverInfoData], rcx; DriverInfoData
0x18001cc33  mov     r8d, r14d; DriverType
0x18001cc36  mov     rcx, rsi; DeviceInfoSet
0x18001cc39  xor     edx, edx; DeviceInfoData
0x18001cc3b  call    cs:__imp_SetupDiEnumDriverInfoW
0x18001cc41  test    eax, eax
0x18001cc43  jz      loc_18001CFAA
0x18001cc49  mov     esi, edi
0x18001cc4b  cmp     esi, r12d
0x18001cc4e  jnb     loc_18001CDD4
0x18001cc54  mov     eax, esi
0x18001cc56  lea     rdx, [rbp+820h+var_870.Description]; lpString2
0x18001cc5a  imul    rdi, rax, 270h
0x18001cc61  add     rdi, qword ptr [rsp+920h+var_8AC+4]
0x18001cc66  mov     rcx, rdi; lpString1
0x18001cc69  call    cs:__imp_lstrcmpiW
0x18001cc6f  test    eax, eax
0x18001cc71  jz      short loc_18001CC78
0x18001cc73  add     esi, r14d
0x18001cc76  jmp     short loc_18001CC4B
0x18001cc78  mov     rsi, [rsp+920h+DeviceInfoSet]
0x18001cc7d  lea     rax, [rbp+820h+var_250]
0x18001cc84  mov     r9d, [rsp+920h+var_8C0]; int
0x18001cc89  lea     r8, [rbp+820h+var_870]; int
0x18001cc8d  mov     [rsp+920h+ReturnBuffer], rax; ReturnBuffer
0x18001cc92  mov     rcx, rsi; int
0x18001cc95  lea     rax, [rsp+920h+var_8AC]
0x18001cc9a  mov     dword ptr [rsp+920h+var_8AC], 0
0x18001cca2  mov     [rsp+920h+DriverInfoData], rax; __int64
0x18001cca7  call    GetDriverStorePathFromDeviceInfo
0x18001ccac  test    eax, eax
0x18001ccae  jnz     short loc_18001CCBF
0x18001ccb0  call    GetLastErrorAsHResult
0x18001ccb5  mov     ebx, eax
0x18001ccb7  test    eax, eax
0x18001ccb9  js      loc_18001CDD9
0x18001ccbf  cmp     dword ptr [rsp+920h+var_8AC], 0
0x18001ccc4  jz      loc_18001CDD9
0x18001ccca  cmp     dword ptr [rdi+268h], 0
0x18001ccd1  lea     r9, [rbp+820h+var_250]
0x18001ccd8  mov     r8, rdi
0x18001ccdb  mov     rcx, r13; char *
0x18001ccde  jnz     loc_18001CE39
0x18001cce4  lea     rdx, aFoundACompatib_0; "Found a compatible core driver for %ws "...
0x18001cceb  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001ccf0  lea     rdx, [rbp+820h+var_870.DriverDate]; lpFileTime2
0x18001ccf7  lea     rcx, [rbp+820h+FileTime1]; lpFileTime1
0x18001ccfb  call    cs:__imp_CompareFileTime
0x18001cd01  mov     esi, eax
0x18001cd03  mov     rax, [rbp+820h+Section]
0x18001cd07  test    rax, rax
0x18001cd0a  jz      loc_18001CDFA
0x18001cd10  lea     rdx, [rbp+820h+var_250]; unsigned __int16 *
0x18001cd17  mov     rcx, rax; Section
0x18001cd1a  call    ?VerifyLegacyNeedsDependencies@@YAHPEBG0@Z; VerifyLegacyNeedsDependencies(ushort const *,ushort const *)
0x18001cd1f  test    eax, eax
0x18001cd21  jz      loc_18001CE28
0x18001cd27  mov     rcx, [rbp+820h+var_870.DriverVersion]
0x18001cd2e  mov     rax, qword ptr [rbp+820h+var_870.DriverDate.dwLowDateTime]
0x18001cd35  lea     r8, [rbp+820h+var_250]; unsigned __int16 *
0x18001cd3c  mov     [rdi+58h], rcx
0x18001cd40  mov     edx, 208h; unsigned __int64
0x18001cd45  lea     rcx, [rdi+60h]; unsigned __int16 *
0x18001cd49  mov     [rdi+50h], rax
0x18001cd4d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cd52  mov     ebx, eax
0x18001cd54  test    eax, eax
0x18001cd56  jns     short loc_18001CDBE
0x18001cd58  movsxd  rcx, [rsp+920h+var_8C0]
0x18001cd5d  lea     r9, [rbp+820h+var_250]; unsigned __int16 *
0x18001cd64  mov     [rsp+920h+var_8C8], ebx; unsigned int
0x18001cd68  lea     r8, aStringcbcopy2F; "StringCbCopy(2) failed (source - driver"...
0x18001cd6f  movzx   eax, bx
0x18001cd72  lea     rdx, aFindlatestcore_0; "FindLatestCoreDrivers"
0x18001cd79  mov     [rsp+920h+var_8D0], eax; unsigned int
0x18001cd7d  lea     rax, PlatformEnv
0x18001cd84  mov     rax, [rax+rcx*8]
0x18001cd88  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18001cd8f  mov     [rsp+920h+var_8D8], r15; unsigned __int16 *
0x18001cd94  mov     [rsp+920h+var_8E0], r14d; int
0x18001cd99  mov     [rsp+920h+var_8E8], rax; unsigned __int16 *
0x18001cd9e  mov     [rsp+920h+var_8F0], 0; unsigned __int16 *
0x18001cda7  mov     [rsp+920h+ReturnBuffer], 0; unsigned __int16 *
0x18001cdb0  mov     [rsp+920h+DriverInfoData], 0; unsigned __int16 *
0x18001cdb9  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001cdbe  lea     rdx, aTheCompatibleC_0; "The compatible core driver is the same "...
0x18001cdc5  mov     [rdi+268h], r14d
0x18001cdcc  mov     rcx, r13; char *
0x18001cdcf  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001cdd4  mov     rsi, [rsp+920h+DeviceInfoSet]
0x18001cdd9  xor     edi, edi
0x18001cddb  mov     eax, [rsp+920h+var_8B0]
0x18001cddf  add     eax, r14d
0x18001cde2  mov     [rbp+820h+var_870.cbSize], 620h
0x18001cde9  mov     [rsp+920h+var_8B0], eax
0x18001cded  test    ebx, ebx
0x18001cdef  jns     loc_18001CC27
0x18001cdf5  jmp     loc_18001CB52
0x18001cdfa  mov     rcx, rdi; lpString1
0x18001cdfd  call    IsInboxCorePrinterDriver
0x18001ce02  test    eax, eax
0x18001ce04  jz      loc_18001CD27
0x18001ce0a  cmp     esi, 0FFFFFFFFh
0x18001ce0d  jz      loc_18001CD27
0x18001ce13  test    esi, esi
0x18001ce15  jnz     short loc_18001CE28
0x18001ce17  mov     rcx, [rbp+820h+var_870.DriverVersion]
0x18001ce1e  cmp     rcx, [rbp+820h+var_890]
0x18001ce22  jnb     loc_18001CD2E
0x18001ce28  lea     rdx, aTheCompatibleC; "The compatible core driver is older tha"...
0x18001ce2f  mov     rcx, r13; char *
0x18001ce32  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001ce37  jmp     short loc_18001CDD4
0x18001ce39  lea     rdx, aFoundAnotherCo; "Found another compatible core driver fo"...
0x18001ce40  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001ce45  lea     rdx, [rbp+820h+var_870.DriverDate]; lpFileTime2
0x18001ce4c  lea     rcx, [rdi+50h]; lpFileTime1
0x18001ce50  call    cs:__imp_CompareFileTime
0x18001ce56  cmp     eax, 0FFFFFFFFh
0x18001ce59  jnz     short loc_18001CECA
0x18001ce5b  mov     rax, [rbp+820h+Section]
0x18001ce5f  test    rax, rax
0x18001ce62  jz      short loc_18001CE7B
0x18001ce64  lea     rdx, [rbp+820h+var_250]; unsigned __int16 *
0x18001ce6b  mov     rcx, rax; Section
0x18001ce6e  call    ?VerifyLegacyNeedsDependencies@@YAHPEBG0@Z; VerifyLegacyNeedsDependencies(ushort const *,ushort const *)
0x18001ce73  test    eax, eax
0x18001ce75  jz      loc_18001CF9E
0x18001ce7b  lea     rdx, aTheNewCoreDriv_0; "The new core driver has a newer date th"...
0x18001ce82  mov     rcx, r13; char *
0x18001ce85  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001ce8a  mov     rax, qword ptr [rbp+820h+var_870.DriverDate.dwLowDateTime]
0x18001ce91  lea     rcx, [rdi+60h]; unsigned __int16 *
0x18001ce95  mov     [rdi+50h], rax
0x18001ce99  lea     r8, [rbp+820h+var_250]; unsigned __int16 *
  ... truncated ...
```
