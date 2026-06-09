# InstallAllInfSections

- ea: `0x18001f958`
- end: `0x1800201ed`
- name: `InstallAllInfSections`
- size: `2197`
- prototype: `__int64 __usercall@<rax>(struct _PSETUP_LOCAL_DATA *@<rcx>, PCWSTR, char, HINF InfHandle, PCWSTR SectionName, __int64, __int64, __int64)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, installer_update`

## callers

- `0x180009d64`
- `0x18000db80`
- `0x18000f698`
- `0x180022dec`

## callees

- `0x18000d57c`
- `0x18000d624`
- `0x180012424`
- `0x180019908`
- `0x18001f958`
- `0x180020b60`
- `0x180034bec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001faeb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbbe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800201be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fd45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200e6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fd45`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800200e6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc85`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001fc85`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001fc6c`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001fcae`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001fc6c`
- `SETUPAPI!SetupGetStringFieldW` at `0x18001fcae`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x18001fad9`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x18001feed`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x18001fad9`
- `SETUPAPI!SetupInstallFilesFromInfSectionW` at `0x18001feed`
- `SETUPAPI!SetupGetFieldCount` at `0x18001fc3b`
- `SETUPAPI!SetupGetFieldCount` at `0x18001fc3b`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001fc29`
- `SETUPAPI!SetupFindFirstLineW` at `0x18001fc29`
- `SETUPAPI!SetupCloseInfFile` at `0x18001fd38`
- `SETUPAPI!SetupCloseInfFile` at `0x18001fe23`
- `SETUPAPI!SetupCloseInfFile` at `0x18001fd38`
- `SETUPAPI!SetupCloseInfFile` at `0x18001fe23`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18001fcf0`
- `SETUPAPI!SetupOpenAppendInfFileW` at `0x18001fcf0`

## string_xrefs

- `0x18001fbfc`: `InstallFilesFromNeedsSections`
- `0x18001fdcb`: `InstallFilesFromNeedsSections`
- `0x18001ff17`: `Error installing files from included inf: %d`
- `0x180020123`: `Invalid Argument: pLocalData=%p, CopyQueue=%p, pszInstallSection=%ws, hInf=%p`
- `0x18001f9d7`: `InstallAllInfSections`
- `0x18002010c`: `InstallAllInfSections`
- `0x18001fa8f`: `InstallAllInfSections`
- `0x18001fdf9`: `InstallAllInfSections`
- `0x180020085`: `InstallAllInfSections`
- `0x1800201ad`: `InstallAllInfSections`
- `0x18001f9e2`: `Installing from %ws on %ws from %ws with install section %ws on platform %ws`
- `0x18001faf1`: `Error populating copy queue: %d`
- `0x18001fb29`: `For install section`
- `0x18001fb30`: `SetupInstallFilesFromInfSection failed`
- `0x18001fb50`: `%ws is not package-aware, installing files from needs sections`
- `0x18001fb70`: `Installing needed files from non-native ntprint.inf`
- `0x18001fbc4`: `Error installing files from needs sections: %d`
- `0x18001fcbf`: `Found included inf %ws, attempting to open`
- `0x18001fcf9`: `Installing files from included inf %ws`
- `0x18001fd8c`: `Error installing files from included inf %ws: %d`
- `0x18001ff79`: `SetupInstallFilesFromInfSection failed (Core section in additional info)`
- `0x1800200f8`: `Successfully installed all files from %ws.`
- `0x1800201c4`: `Error installing files from INF: %d`

## pseudocode

```c
__int64 __fastcall InstallAllInfSections(
        struct _PSETUP_LOCAL_DATA *a1,
        unsigned int a2,
        __int64 a3,
        char *a4,
        PCWSTR SourceRootPath,
        char a6,
        HINF InfHandle,
        PCWSTR SectionName,
        __int64 a9,
        unsigned int *a10,
        __int64 a11)
{
  unsigned int v11; // r12d
  __int64 v13; // rdi
  signed int LastError; // edi
  DWORD v16; // eax
  unsigned int v17; // ecx
  int v18; // edx
  const unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r8
  const unsigned __int16 *v21; // r9
  DWORD v22; // eax
  __int64 v23; // r8
  DWORD v24; // eax
  DWORD v25; // r12d
  DWORD v26; // r13d
  WCHAR *v27; // rdi
  void *v28; // rax
  void *v29; // r13
  int v30; // ecx
  const unsigned __int16 *v31; // rax
  signed int v32; // r15d
  DWORD v33; // eax
  unsigned int v34; // ecx
  int v35; // edx
  const unsigned __int16 *v36; // rax
  unsigned int v37; // r12d
  unsigned __int64 v38; // r13
  __int64 v39; // rax
  signed int v40; // edi
  DWORD v41; // eax
  unsigned int v42; // ecx
  int v43; // r8d
  const unsigned __int16 *v44; // rdx
  signed int v45; // edi
  DWORD v46; // eax
  unsigned int v47; // ecx
  int v48; // r8d
  const unsigned __int16 *v49; // rdx
  signed int v50; // edi
  unsigned int v51; // ecx
  int v52; // edx
  const unsigned __int16 *v53; // rax
  int *v54; // rax
  const unsigned __int16 *v55; // rcx
  int v56; // r8d
  const unsigned __int16 *v57; // rax
  const unsigned __int16 *v58; // rdx
  DWORD v59; // eax
  DWORD RequiredSize[2]; // [rsp+68h] [rbp-31h] BYREF
  DWORD FieldCount; // [rsp+70h] [rbp-29h]
  __int64 v63; // [rsp+78h] [rbp-21h]
  struct _INFCONTEXT Context; // [rsp+80h] [rbp-19h] BYREF

  v11 = 0;
  v13 = (int)a2;
  if ( !a1 || (unsigned __int64)(a4 - 1) > 0xFFFFFFFFFFFFFFFDuLL || !SectionName || InfHandle == (HINF)-1LL )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InstallAllInfSections",
      L"Invalid Argument: pLocalData=%p, CopyQueue=%p, pszInstallSection=%ws, hInf=%p",
      a1);
    v54 = (int *)((char *)a1 + 172);
    if ( a1 )
    {
      if ( *v54 )
        v55 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
      else
        v55 = 0;
      v56 = *v54;
    }
    else
    {
      v56 = 0;
      v55 = 0;
    }
    if ( a1 )
    {
      v57 = *(const unsigned __int16 **)a1;
      v58 = (const unsigned __int16 *)*((_QWORD *)a1 + 1);
    }
    else
    {
      v57 = 0;
      v58 = 0;
    }
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InstallAllInfSections",
      0,
      0,
      v57,
      v58,
      SectionName,
      (const unsigned __int16 *)PlatformEnv[v13],
      v56,
      v55,
      0x57u,
      0x80070057);
    goto LABEL_99;
  }
  v63 = (int)a2;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "InstallAllInfSections",
    L"Installing from %ws on %ws from %ws with install section %ws on platform %ws",
    *(_QWORD *)a1,
    a3,
    SourceRootPath,
    SectionName,
    PlatformEnv[a2]);
  if ( !(unsigned int)SetTargetDirectories(a1, a6) )
  {
    LastError = GetLastError();
    v16 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError("InstallAllInfSections", L"Error Setting target directories: %d", v16);
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    else
      v17 = LastError;
    v18 = *((_DWORD *)a1 + 43);
    if ( v18 )
      v19 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
    else
      v19 = 0;
    v20 = L"SetTargetDirectories failed";
LABEL_13:
    v21 = 0;
LABEL_14:
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InstallAllInfSections",
      v20,
      v21,
      *(const unsigned __int16 **)a1,
      *((const unsigned __int16 **)a1 + 1),
      SectionName,
      (const unsigned __int16 *)PlatformEnv[v63],
      v18,
      v19,
      LastError,
      v17);
    goto LABEL_15;
  }
  if ( !SetupInstallFilesFromInfSectionW(InfHandle, 0, a4, SectionName, SourceRootPath, 0x20u) )
  {
    LastError = GetLastError();
    v22 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceInfo("InstallAllInfSections", L"Error populating copy queue: %d", v22);
    if ( LastError > 0 )
      v17 = (unsigned __int16)LastError | 0x80070000;
    else
      v17 = LastError;
    v18 = *((_DWORD *)a1 + 43);
    if ( v18 )
      v19 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
    else
      v19 = 0;
    v21 = L"For install section";
    v20 = L"SetupInstallFilesFromInfSection failed";
    goto LABEL_14;
  }
  v23 = *(_QWORD *)a1;
  if ( *((_DWORD *)a1 + 43) )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InstallAllInfSections",
      L"%ws is package-aware, ignoring include/needs and using package-aware keywords",
      v23);
    if ( !a11 || !*(_DWORD *)(a11 + 16) )
      goto LABEL_44;
    v37 = 0;
    while ( 1 )
    {
      v38 = (unsigned __int64)v37 << 9;
      v39 = *(unsigned __int16 *)(*(_QWORD *)(a11 + 24) + v38 + 510);
      FieldCount = v39;
      if ( (unsigned int)v39 >= *a10 )
        break;
      *(_QWORD *)RequiredSize = v39;
      if ( *(_QWORD *)(*((_QWORD *)a10 + 1) + 8LL * (unsigned int)v39) == -1 )
        break;
      if ( !(unsigned int)SetTargetDirectories(a1, a6) )
      {
        v45 = GetLastError();
        v46 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError(
          "InstallAllInfSections",
          L"Error setting target directories: %d",
          v46);
        if ( v45 > 0 )
          v47 = (unsigned __int16)v45 | 0x80070000;
        else
          v47 = v45;
        v48 = *((_DWORD *)a1 + 43);
        if ( v48 )
          v49 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
        else
          v49 = 0;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"InstallAllInfSections",
          L"SetTargetDirectories failed (core section in additional info)",
          (const unsigned __int16 *)(v38 + *(_QWORD *)(a11 + 24)),
          *(const unsigned __int16 **)a1,
          *((const unsigned __int16 **)a1 + 1),
          SectionName,
          (const unsigned __int16 *)PlatformEnv[v63],
          v48,
          v49,
          v45,
          v47);
        goto LABEL_15;
      }
      if ( !SetupInstallFilesFromInfSectionW(
              *(HINF *)(*((_QWORD *)a10 + 1) + 8LL * *(_QWORD *)RequiredSize),
              0,
              a4,
              (PCWSTR)(v38 + *(_QWORD *)(a11 + 24)),
              0,
              0x20u) )
      {
        v40 = GetLastError();
        v41 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "InstallAllInfSections",
          L"Error installing files from included inf: %d",
          v41);
        if ( v40 > 0 )
          v42 = (unsigned __int16)v40 | 0x80070000;
        else
          v42 = v40;
        v43 = *((_DWORD *)a1 + 43);
        if ( v43 )
          v44 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
        else
          v44 = 0;
        SplLogPrinterSetupCoreDriverEvent(
          &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
          L"InstallAllInfSections",
          L"SetupInstallFilesFromInfSection failed (Core section in additional info)",
          (const unsigned __int16 *)(v38 + *(_QWORD *)(a11 + 24)),
          *(const unsigned __int16 **)a1,
          *((const unsigned __int16 **)a1 + 1),
          SectionName,
          (const unsigned __int16 *)PlatformEnv[v63],
          v43,
          v44,
          v40,
          v42);
        goto LABEL_15;
      }
      if ( ++v37 >= *(_DWORD *)(a11 + 16) )
        goto LABEL_44;
    }
    v50 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "InstallAllInfSections",
      L"Core section index out of bounds: %d >= %d",
      FieldCount,
      *a10);
    if ( v50 > 0 )
      v51 = (unsigned __int16)v50 | 0x80070000;
    else
      v51 = v50;
    v52 = *((_DWORD *)a1 + 43);
    if ( v52 )
      v53 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
    else
      v53 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
      L"InstallAllInfSections",
      L"Core section(s) out of bounds",
      0,
      *(const unsigned __int16 **)a1,
      *((const unsigned __int16 **)a1 + 1),
      SectionName,
      (const unsigned __int16 *)PlatformEnv[v63],
      v52,
      v53,
      v50,
      v51);
LABEL_15:
    v11 = 0;
    goto LABEL_99;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "InstallAllInfSections",
    L"%ws is not package-aware, installing files from needs sections",
    v23);
  if ( (unsigned __int64)(a9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo(
      "InstallAllInfSections",
      L"Installing needed files from non-native ntprint.inf");
    if ( !(unsigned int)InstallFilesFromNeedsSections(a1, a2, a3, a4) )
    {
      LastError = GetLastError();
      v24 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError(
        "InstallAllInfSections",
        L"Error installing files from needs sections: %d",
        v24);
      if ( LastError > 0 )
        v17 = (unsigned __int16)LastError | 0x80070000;
      else
        v17 = LastError;
      v18 = *((_DWORD *)a1 + 43);
      if ( v18 )
        v19 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
      else
        v19 = 0;
      v20 = L"InstallFilesFromNeedsSections";
      goto LABEL_13;
    }
LABEL_44:
    v30 = *((_DWORD *)a1 + 43);
    if ( v30 )
      v31 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
    else
      v31 = 0;
    SplLogPrinterSetupCoreDriverEvent(
      &SETUP_INSTALL_PRINTER_DRIVER_SUCCEEDED,
      L"InstallAllInfSections",
      0,
      0,
      *(const unsigned __int16 **)a1,
      *((const unsigned __int16 **)a1 + 1),
      SectionName,
      (const unsigned __int16 *)PlatformEnv[v63],
      v30,
      v31,
      0,
      0);
    v11 = 1;
    goto LABEL_87;
  }
  RequiredSize[0] = 0;
  memset(&Context, 0, sizeof(Context));
  if ( !SetupFindFirstLineW(InfHandle, SectionName, L"Include", &Context) )
    goto LABEL_44;
  v25 = 1;
  FieldCount = SetupGetFieldCount(&Context);
  v26 = FieldCount;
  if ( !FieldCount )
    goto LABEL_44;
  while ( 1 )
  {
    if ( !SetupGetStringFieldW(&Context, v25, 0, 0, RequiredSize) )
      goto LABEL_43;
    v27 = (WCHAR *)LocalAlloc(0x40u, 2 * RequiredSize[0]);
    if ( !v27 )
      goto LABEL_43;
    if ( SetupGetStringFieldW(&Context, v25, v27, RequiredSize[0], RequiredSize) )
      break;
LABEL_42:
    LocalFree(v27);
LABEL_43:
    if ( ++v25 > v26 )
      goto LABEL_44;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "InstallAllInfSections",
    L"Found included inf %ws, attempting to open",
    v27);
  v28 = (void *)OpenPrinterInfFile(v27);
  v29 = v28;
  if ( v28 == (void *)-1LL )
  {
    v11 = 0;
    goto LABEL_86;
  }
  SetupOpenAppendInfFileW(0, v28, 0);
  ClassInstallerTelemetry::WriteDbgTraceInfo("InstallAllInfSections", L"Installing files from included inf %ws", v27);
  if ( (unsigned int)InstallFilesFromNeedsSections(a1, a2, a3, a4) )
  {
    SetupCloseInfFile(v29);
    v26 = FieldCount;
    goto LABEL_42;
  }
  v32 = GetLastError();
  v33 = GetLastError();
  ClassInstallerTelemetry::WriteDbgTraceError(
    "InstallAllInfSections",
    L"Error installing files from included inf %ws: %d",
    v27,
    v33);
  if ( v32 > 0 )
    v34 = (unsigned __int16)v32 | 0x80070000;
  else
    v34 = v32;
  v35 = *((_DWORD *)a1 + 43);
  if ( v35 )
    v36 = (const unsigned __int16 *)*((_QWORD *)a1 + 28);
  else
    v36 = 0;
  SplLogPrinterSetupCoreDriverEvent(
    &SETUP_INSTALL_PRINTER_DRIVER_FAILED,
    L"InstallAllInfSections",
    L"InstallFilesFromNeedsSections",
    0,
    *(const unsigned __int16 **)a1,
    *((const unsigned __int16 **)a1 + 1),
    SectionName,
    (const unsigned __int16 *)PlatformEnv[v63],
    v35,
    v36,
    v32,
    v34);
  SetupCloseInfFile(v29);
  v11 = 0;
LABEL_86:
  LocalFree(v27);
LABEL_87:
  if ( !v11 )
  {
LABEL_99:
    v59 = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError("InstallAllInfSections", L"Error installing files from INF: %d", v59);
    return v11;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "InstallAllInfSections",
    L"Successfully installed all files from %ws.",
    *(_QWORD *)a1);
  return v11;
}

```

## disassembly

```asm
0x18001f958  mov     rax, rsp
0x18001f95b  mov     [rax+20h], r9
0x18001f95f  mov     [rax+18h], r8
0x18001f963  mov     [rax+10h], edx
0x18001f966  push    rbp
0x18001f967  push    rbx
0x18001f968  push    rsi
0x18001f969  push    rdi
0x18001f96a  push    r12
0x18001f96c  push    r13
0x18001f96e  push    r14
0x18001f970  push    r15
0x18001f972  lea     rbp, [rax-47h]
0x18001f976  sub     rsp, 98h
0x18001f97d  mov     r14, [rbp+3Fh+SectionName]
0x18001f984  xor     r12d, r12d
0x18001f987  mov     r15, [rbp+3Fh+InfHandle]
0x18001f98b  mov     r13, r9
0x18001f98e  movsxd  rdi, edx
0x18001f991  mov     rbx, rcx
0x18001f994  mov     [rbp+3Fh+arg_0], r12d
0x18001f998  test    rcx, rcx
0x18001f99b  jz      loc_18002010C
0x18001f9a1  lea     rax, [r9-1]
0x18001f9a5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001f9a9  ja      loc_18002010C
0x18001f9af  test    r14, r14
0x18001f9b2  jz      loc_18002010C
0x18001f9b8  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18001f9bc  jz      loc_18002010C
0x18001f9c2  mov     r9, r8
0x18001f9c5  mov     [rbp+3Fh+var_60], rdi
0x18001f9c9  mov     r8, [rcx]
0x18001f9cc  lea     r12, PlatformEnv
0x18001f9d3  mov     rax, [r12+rdi*8]
0x18001f9d7  lea     rsi, aInstallallinfs; "InstallAllInfSections"
0x18001f9de  mov     rdi, [rbp+3Fh+arg_20]
0x18001f9e2  lea     rdx, aInstallingFrom; "Installing from %ws on %ws from %ws wit"...
0x18001f9e9  mov     [rsp+0D0h+var_A0], rax
0x18001f9ee  mov     rcx, rsi; char *
0x18001f9f1  mov     qword ptr [rsp+0D0h+CopyFlags], r14
0x18001f9f6  mov     [rsp+0D0h+SourceRootPath], rdi
0x18001f9fb  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fa00  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18001fa03  mov     r9, r15
0x18001fa06  mov     r8, [rbp+3Fh+arg_10]
0x18001fa0a  mov     rcx, rbx; struct _PSETUP_LOCAL_DATA *
0x18001fa0d  mov     edx, [rbp+3Fh+arg_8]
0x18001fa10  mov     dword ptr [rsp+0D0h+SourceRootPath], eax; char
0x18001fa14  call    SetTargetDirectories
0x18001fa19  test    eax, eax
0x18001fa1b  jnz     loc_18001FAC1
0x18001fa21  call    cs:__imp_GetLastError
0x18001fa27  mov     edi, eax
0x18001fa29  call    cs:__imp_GetLastError
0x18001fa2f  lea     rdx, aErrorSettingTa_0; "Error Setting target directories: %d"
0x18001fa36  mov     rcx, rsi; char *
0x18001fa39  mov     r8d, eax
0x18001fa3c  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001fa41  test    edi, edi
0x18001fa43  jg      short loc_18001FA49
0x18001fa45  mov     ecx, edi
0x18001fa47  jmp     short loc_18001FA52
0x18001fa49  movzx   ecx, di
0x18001fa4c  or      ecx, 80070000h
0x18001fa52  mov     edx, [rbx+0ACh]
0x18001fa58  test    edx, edx
0x18001fa5a  jz      short loc_18001FA65
0x18001fa5c  mov     rax, [rbx+0E0h]
0x18001fa63  jmp     short loc_18001FA67
0x18001fa65  xor     eax, eax
0x18001fa67  lea     r8, aSettargetdirec_0; "SetTargetDirectories failed"
0x18001fa6e  xor     r9d, r9d; unsigned __int16 *
0x18001fa71  mov     [rsp+58h], ecx; unsigned int
0x18001fa75  mov     [rsp+0D0h+var_80], edi; unsigned int
0x18001fa79  mov     [rsp+0D0h+var_88], rax; unsigned __int16 *
0x18001fa7e  mov     rax, [rbp+3Fh+var_60]
0x18001fa82  mov     [rsp+0D0h+var_90], edx; int
0x18001fa86  mov     rax, [r12+rax*8]
0x18001fa8a  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x18001fa8f  lea     rdx, aInstallallinfs_0; "InstallAllInfSections"
0x18001fa96  mov     rax, [rbx+8]
0x18001fa9a  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18001faa1  mov     [rsp+0D0h+var_A0], r14; unsigned __int16 *
0x18001faa6  mov     qword ptr [rsp+0D0h+CopyFlags], rax; unsigned __int16 *
0x18001faab  mov     rax, [rbx]
0x18001faae  mov     [rsp+0D0h+SourceRootPath], rax; unsigned __int16 *
0x18001fab3  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001fab8  mov     r12d, [rbp+3Fh+arg_0]
0x18001fabc  jmp     loc_1800201BE
0x18001fac1  mov     [rsp+0D0h+CopyFlags], 20h ; ' '; CopyFlags
0x18001fac9  mov     r9, r14; SectionName
0x18001facc  mov     r8, r13; FileQueue
0x18001facf  mov     [rsp+0D0h+SourceRootPath], rdi; SourceRootPath
0x18001fad4  xor     edx, edx; LayoutInfHandle
0x18001fad6  mov     rcx, r15; InfHandle
0x18001fad9  call    cs:__imp_SetupInstallFilesFromInfSectionW
0x18001fadf  test    eax, eax
0x18001fae1  jnz     short loc_18001FB3C
0x18001fae3  call    cs:__imp_GetLastError
0x18001fae9  mov     edi, eax
0x18001faeb  call    cs:__imp_GetLastError
0x18001faf1  lea     rdx, aErrorPopulatin; "Error populating copy queue: %d"
0x18001faf8  mov     rcx, rsi; char *
0x18001fafb  mov     r8d, eax
0x18001fafe  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fb03  test    edi, edi
0x18001fb05  jg      short loc_18001FB0B
0x18001fb07  mov     ecx, edi
0x18001fb09  jmp     short loc_18001FB14
0x18001fb0b  movzx   ecx, di
0x18001fb0e  or      ecx, 80070000h
0x18001fb14  mov     edx, [rbx+0ACh]
0x18001fb1a  test    edx, edx
0x18001fb1c  jz      short loc_18001FB27
0x18001fb1e  mov     rax, [rbx+0E0h]
0x18001fb25  jmp     short loc_18001FB29
0x18001fb27  xor     eax, eax
0x18001fb29  lea     r9, aForInstallSect; "For install section"
0x18001fb30  lea     r8, aSetupinstallfi_0; "SetupInstallFilesFromInfSection failed"
0x18001fb37  jmp     loc_18001FA71
0x18001fb3c  mov     r8, [rbx]
0x18001fb3f  xor     edi, edi
0x18001fb41  mov     rcx, rsi; char *
0x18001fb44  cmp     [rbx+0ACh], edi
0x18001fb4a  jnz     loc_18001FE31
0x18001fb50  lea     rdx, aWsIsNotPackage; "%ws is not package-aware, installing fi"...
0x18001fb57  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fb5c  mov     rax, [rbp+3Fh+arg_40]
0x18001fb63  dec     rax
0x18001fb66  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001fb6a  ja      loc_18001FC08
0x18001fb70  lea     rdx, aInstallingNeed; "Installing needed files from non-native"...
0x18001fb77  mov     rcx, rsi; char *
0x18001fb7a  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fb7f  mov     rax, [rbp+3Fh+arg_40]
0x18001fb86  mov     r9, r13
0x18001fb89  mov     r8, [rbp+3Fh+arg_10]
0x18001fb8d  mov     rcx, rbx
0x18001fb90  mov     edx, [rbp+3Fh+arg_8]
0x18001fb93  mov     qword ptr [rsp+0D0h+var_90], rax
0x18001fb98  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18001fb9b  mov     [rsp+0D0h+var_98], r14
0x18001fba0  mov     [rsp+0D0h+var_A0], r15
0x18001fba5  mov     [rsp+0D0h+CopyFlags], eax
0x18001fba9  call    ?InstallFilesFromNeedsSections@@YAHPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEBGPEAX2K323@Z; InstallFilesFromNeedsSections(_PSETUP_LOCAL_DATA *,PLATFORM,ushort const *,void *,ushort const *,ulong,void *,ushort const *,void *)
0x18001fbae  test    eax, eax
0x18001fbb0  jnz     loc_18001FD60
0x18001fbb6  call    cs:__imp_GetLastError
0x18001fbbc  mov     edi, eax
0x18001fbbe  call    cs:__imp_GetLastError
0x18001fbc4  lea     rdx, aErrorInstallin_1; "Error installing files from needs secti"...
0x18001fbcb  mov     rcx, rsi; char *
0x18001fbce  mov     r8d, eax
0x18001fbd1  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001fbd6  test    edi, edi
0x18001fbd8  jg      short loc_18001FBDE
0x18001fbda  mov     ecx, edi
0x18001fbdc  jmp     short loc_18001FBE7
0x18001fbde  movzx   ecx, di
0x18001fbe1  or      ecx, 80070000h
0x18001fbe7  mov     edx, [rbx+0ACh]
0x18001fbed  test    edx, edx
0x18001fbef  jz      short loc_18001FBFA
0x18001fbf1  mov     rax, [rbx+0E0h]
0x18001fbf8  jmp     short loc_18001FBFC
0x18001fbfa  xor     eax, eax
0x18001fbfc  lea     r8, aInstallfilesfr; "InstallFilesFromNeedsSections"
0x18001fc03  jmp     loc_18001FA6E
0x18001fc08  xor     eax, eax
0x18001fc0a  lea     r9, [rbp+3Fh+Context]; Context
0x18001fc0e  xorps   xmm0, xmm0
0x18001fc11  mov     qword ptr [rbp+3Fh+Context.Section], rax
0x18001fc15  lea     r8, aInclude; "Include"
0x18001fc1c  mov     [rbp+3Fh+RequiredSize], eax
0x18001fc1f  mov     rdx, r14; Section
0x18001fc22  mov     rcx, r15; InfHandle
0x18001fc25  movups  xmmword ptr [rbp+3Fh+Context.Inf], xmm0
0x18001fc29  call    cs:__imp_SetupFindFirstLineW
0x18001fc2f  test    eax, eax
0x18001fc31  jz      loc_18001FD60
0x18001fc37  lea     rcx, [rbp+3Fh+Context]; Context
0x18001fc3b  call    cs:__imp_SetupGetFieldCount
0x18001fc41  mov     r12d, 1
0x18001fc47  mov     [rbp+3Fh+var_68], eax
0x18001fc4a  mov     r13d, eax
0x18001fc4d  cmp     eax, r12d
0x18001fc50  jb      loc_18001FD59
0x18001fc56  lea     rax, [rbp+3Fh+RequiredSize]
0x18001fc5a  xor     r9d, r9d; ReturnBufferSize
0x18001fc5d  xor     r8d, r8d; ReturnBuffer
0x18001fc60  mov     [rsp+0D0h+SourceRootPath], rax; RequiredSize
0x18001fc65  mov     edx, r12d; FieldIndex
0x18001fc68  lea     rcx, [rbp+3Fh+Context]; Context
0x18001fc6c  call    cs:__imp_SetupGetStringFieldW
0x18001fc72  test    eax, eax
0x18001fc74  jz      loc_18001FD4D
0x18001fc7a  mov     eax, [rbp+3Fh+RequiredSize]
0x18001fc7d  mov     ecx, 40h ; '@'; uFlags
0x18001fc82  lea     edx, [rax+rax]; uBytes
0x18001fc85  call    cs:__imp_LocalAlloc
0x18001fc8b  mov     rdi, rax
0x18001fc8e  test    rax, rax
0x18001fc91  jz      loc_18001FD4D
0x18001fc97  mov     r9d, [rbp+3Fh+RequiredSize]; ReturnBufferSize
0x18001fc9b  lea     rax, [rbp+3Fh+RequiredSize]
0x18001fc9f  mov     r8, rdi; ReturnBuffer
0x18001fca2  mov     [rsp+0D0h+SourceRootPath], rax; RequiredSize
0x18001fca7  mov     edx, r12d; FieldIndex
0x18001fcaa  lea     rcx, [rbp+3Fh+Context]; Context
0x18001fcae  call    cs:__imp_SetupGetStringFieldW
0x18001fcb4  test    eax, eax
0x18001fcb6  jz      loc_18001FD42
0x18001fcbc  mov     r8, rdi
0x18001fcbf  lea     rdx, aFoundIncludedI; "Found included inf %ws, attempting to o"...
0x18001fcc6  mov     rcx, rsi; char *
0x18001fcc9  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fcce  mov     edx, 1
0x18001fcd3  mov     rcx, rdi; unsigned __int16 *
0x18001fcd6  call    OpenPrinterInfFile
0x18001fcdb  mov     r13, rax
0x18001fcde  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001fce2  jz      loc_1800200DF
0x18001fce8  xor     r8d, r8d; ErrorLine
0x18001fceb  mov     rdx, rax; InfHandle
0x18001fcee  xor     ecx, ecx; FileName
0x18001fcf0  call    cs:__imp_SetupOpenAppendInfFileW
0x18001fcf6  mov     r8, rdi
0x18001fcf9  lea     rdx, aInstallingFile_0; "Installing files from included inf %ws"
0x18001fd00  mov     rcx, rsi; char *
0x18001fd03  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001fd08  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18001fd0b  mov     rcx, rbx
0x18001fd0e  mov     r9, [rbp+3Fh+FileQueue]
0x18001fd12  mov     r8, [rbp+3Fh+arg_10]
0x18001fd16  mov     edx, [rbp+3Fh+arg_8]
0x18001fd19  mov     qword ptr [rsp+0D0h+var_90], r13
0x18001fd1e  mov     [rsp+0D0h+var_98], r14
0x18001fd23  mov     [rsp+0D0h+var_A0], r15
0x18001fd28  mov     [rsp+0D0h+CopyFlags], eax
0x18001fd2c  call    ?InstallFilesFromNeedsSections@@YAHPEAU_PSETUP_LOCAL_DATA@@W4PLATFORM@@PEBGPEAX2K323@Z; InstallFilesFromNeedsSections(_PSETUP_LOCAL_DATA *,PLATFORM,ushort const *,void *,ushort const *,ulong,void *,ushort const *,void *)
0x18001fd31  test    eax, eax
0x18001fd33  jz      short loc_18001FD7A
0x18001fd35  mov     rcx, r13; InfHandle
0x18001fd38  call    cs:__imp_SetupCloseInfFile
0x18001fd3e  mov     r13d, [rbp+3Fh+var_68]
0x18001fd42  mov     rcx, rdi; hMem
0x18001fd45  call    cs:__imp_LocalFree
0x18001fd4b  xor     edi, edi
0x18001fd4d  inc     r12d
0x18001fd50  cmp     r12d, r13d
0x18001fd53  jbe     loc_18001FC56
0x18001fd59  lea     r12, PlatformEnv
0x18001fd60  mov     ecx, [rbx+0ACh]
0x18001fd66  test    ecx, ecx
0x18001fd68  jz      loc_18002007B
0x18001fd6e  mov     rax, [rbx+0E0h]
0x18001fd75  jmp     loc_18002007D
0x18001fd7a  call    cs:__imp_GetLastError
0x18001fd80  mov     r15d, eax
0x18001fd83  call    cs:__imp_GetLastError
0x18001fd89  mov     r8, rdi
0x18001fd8c  lea     rdx, aErrorInstallin_3; "Error installing files from included in"...
0x18001fd93  mov     r9d, eax
0x18001fd96  mov     rcx, rsi; char *
0x18001fd99  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001fd9e  test    r15d, r15d
0x18001fda1  jg      short loc_18001FDA8
0x18001fda3  mov     ecx, r15d
0x18001fda6  jmp     short loc_18001FDB2
0x18001fda8  movzx   ecx, r15w
0x18001fdac  or      ecx, 80070000h
0x18001fdb2  mov     edx, [rbx+0ACh]
0x18001fdb8  test    edx, edx
0x18001fdba  jz      short loc_18001FDC5
0x18001fdbc  mov     rax, [rbx+0E0h]
0x18001fdc3  jmp     short loc_18001FDC7
0x18001fdc5  xor     eax, eax
0x18001fdc7  mov     [rsp+58h], ecx; unsigned int
0x18001fdcb  lea     r8, aInstallfilesfr; "InstallFilesFromNeedsSections"
0x18001fdd2  mov     [rsp+0D0h+var_80], r15d; unsigned int
0x18001fdd7  lea     rcx, SETUP_INSTALL_PRINTER_DRIVER_FAILED; struct _EVENT_DESCRIPTOR *
0x18001fdde  mov     [rsp+0D0h+var_88], rax; unsigned __int16 *
0x18001fde3  xor     r9d, r9d; unsigned __int16 *
0x18001fde6  mov     rax, [rbp+3Fh+var_60]
0x18001fdea  mov     [rsp+0D0h+var_90], edx; int
0x18001fdee  lea     rdx, PlatformEnv
0x18001fdf5  mov     rax, [rdx+rax*8]
0x18001fdf9  lea     rdx, aInstallallinfs_0; "InstallAllInfSections"
0x18001fe00  mov     [rsp+0D0h+var_98], rax; unsigned __int16 *
0x18001fe05  mov     rax, [rbx+8]
0x18001fe09  mov     [rsp+0D0h+var_A0], r14; unsigned __int16 *
0x18001fe0e  mov     qword ptr [rsp+0D0h+CopyFlags], rax; unsigned __int16 *
0x18001fe13  mov     rax, [rbx]
0x18001fe16  mov     [rsp+0D0h+SourceRootPath], rax; unsigned __int16 *
0x18001fe1b  call    ?SplLogPrinterSetupCoreDriverEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111111H1KK@Z; SplLogPrinterSetupCoreDriverEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ulong,ulong)
0x18001fe20  mov     rcx, r13; InfHandle
0x18001fe23  call    cs:__imp_SetupCloseInfFile
0x18001fe29  xor     r12d, r12d
0x18001fe2c  jmp     loc_1800200E3
  ... truncated ...
```
