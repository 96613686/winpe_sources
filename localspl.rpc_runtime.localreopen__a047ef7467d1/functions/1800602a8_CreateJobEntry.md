# CreateJobEntry

- ea: `0x1800602a8`
- end: `0x180060be7`
- name: `CreateJobEntry`
- size: `2367`
- prototype: `__int64 __usercall@<rax>(struct _SPOOL *@<rcx>, int, unsigned int, __int64)`
- caller_count: `3`
- callee_count: `35`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180065080`
- `0x18006557c`
- `0x180067c44`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x18000ee90`
- `0x18000ef18`
- `0x180010cf0`
- `0x18001ed18`
- `0x1800237b0`
- `0x18002a824`
- `0x18002e530`
- `0x1800306e4`
- `0x18003e984`
- `0x18003ea2c`
- `0x180040674`
- `0x180043aa4`
- `0x180043adc`
- `0x180046650`
- `0x180046a5c`
- `0x180047330`
- `0x18004dbcc`
- `0x18004e5a4`
- `0x180054638`
- `0x18005e4b8`
- `0x18005f8f0`
- `0x1800601c4`
- `0x1800602a8`
- `0x180061d80`
- `0x1800626e8`
- `0x180065e24`
- `0x180065ec4`
- `0x180074218`
- `0x180092288`
- `0x180097a3c`
- `0x1800dd5d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800603b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800604fc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800603b6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800604fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180060b5d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060b54`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060417`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180060b54`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180060abb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180060abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060ac9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180060ac9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800608f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800608f0`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006075b`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18006075b`
- `SPOOLSS!DllFreeSplMem` at `0x1800608e3`
- `SPOOLSS!DllFreeSplMem` at `0x1800608e3`
- `SPOOLSS!AllocSplStr` at `0x180060561`
- `SPOOLSS!AllocSplStr` at `0x18006071d`
- `SPOOLSS!AllocSplStr` at `0x1800607ba`
- `SPOOLSS!AllocSplStr` at `0x1800607d5`
- `SPOOLSS!AllocSplStr` at `0x180060818`
- `SPOOLSS!AllocSplStr` at `0x180060845`
- `SPOOLSS!AllocSplStr` at `0x180060561`
- `SPOOLSS!AllocSplStr` at `0x18006071d`
- `SPOOLSS!AllocSplStr` at `0x1800607ba`
- `SPOOLSS!AllocSplStr` at `0x1800607d5`
- `SPOOLSS!AllocSplStr` at `0x180060818`
- `SPOOLSS!AllocSplStr` at `0x180060845`
- `SPOOLSS!bGetDevModePerUser` at `0x1800608ab`
- `SPOOLSS!bGetDevModePerUser` at `0x1800608ab`
- `SspiCli!GetUserNameExW` at `0x18006070b`
- `SspiCli!GetUserNameExW` at `0x18006079b`
- `SspiCli!GetUserNameExW` at `0x18006070b`
- `SspiCli!GetUserNameExW` at `0x18006079b`

## string_xrefs

- `0x180060401`: `CreateJobEntry`
- `0x180060427`: `CreateJobEntry`
- `0x180060514`: `CreateJobEntry`
- `0x1800605be`: `CreateJobEntry`
- `0x180060b2b`: `CreateJobEntry`
- `0x180060b43`: `CreateJobEntry`
- `0x180060b6d`: `CreateJobEntry`
- `0x1800605b7`: `Failing because the driver must be updated.`
- `0x180060b66`: `Failed to create new job entry.  Error %d`
- `0x180060b8c`: `CreateJobEntry`

## pseudocode

```c
INIJOB *__fastcall CreateJobEntry(
        struct _SPOOL *a1,
        __int64 a2,
        const wchar_t **a3,
        unsigned int a4,
        int a5,
        unsigned int a6,
        __int64 a7)
{
  INIJOB *v9; // rdi
  __int64 v11; // rcx
  __int64 v12; // rax
  DWORD v13; // ecx
  __int64 v14; // rax
  int v15; // r14d
  _WORD *v16; // rbx
  __int64 v17; // rcx
  __int64 v18; // rcx
  INIJOB *v19; // rax
  __int64 v20; // r15
  __int64 v21; // rcx
  const wchar_t *v22; // rcx
  const unsigned __int16 *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rcx
  const wchar_t *v26; // rbx
  __int64 v27; // rax
  unsigned int v28; // ebx
  int v29; // ecx
  __int64 v30; // rax
  __int64 v31; // rcx
  int v32; // eax
  struct INIPRINTPROC *XpsPrintProcessor; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int64 v36; // rax
  BOOLEAN UserName; // bl
  __int64 v38; // rax
  __int64 v39; // rax
  void *DocumentSecurityDescriptor; // rax
  const wchar_t *v41; // rcx
  __int64 v42; // rax
  const wchar_t *v43; // rcx
  __int64 v44; // rax
  void *v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // r8
  int v49; // ecx
  __int64 v50; // rax
  int v51; // r15d
  BOOL v52; // r14d
  int v53; // r12d
  const unsigned __int16 *v54; // r9
  _DWORD *v55; // rbx
  HANDLE Thread; // rax
  __int64 v57; // rax
  const unsigned __int16 *v58; // rcx
  DWORD LastError; // eax
  __int64 v61; // rbx
  struct _INIPRINTER *v62; // rcx
  unsigned int v63; // edx
  __int64 v64; // rax
  ULONG nSize; // [rsp+30h] [rbp-2E8h] BYREF
  DWORD ThreadId[2]; // [rsp+38h] [rbp-2E0h] BYREF
  void *v67; // [rsp+40h] [rbp-2D8h] BYREF
  _DWORD RpcCallAttributes[2]; // [rsp+50h] [rbp-2C8h] BYREF
  char v69[56]; // [rsp+58h] [rbp-2C0h] BYREF
  int v70; // [rsp+90h] [rbp-288h]
  WCHAR NameBuffer[264]; // [rsp+C0h] [rbp-258h] BYREF

  *(_QWORD *)ThreadId = a7;
  nSize = 260;
  v9 = 0;
  v67 = 0;
  if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
  {
    McTemplateU0q_EtwEventWriteTransfer(a1, DocPerf_PrintDocument_Start, a4);
    if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
      McTemplateU0q_EtwEventWriteTransfer(v11, DocPerf_SpoolDocument_Start, a4);
  }
  if ( (unsigned __int8)IsSystemCurrentlyUpgrading() || dwSPUpgradeFlag )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "CreateJobEntry",
      L"job ID %u cannot be printed as the driver is getting upgraded with dwSPUpgradeFlag=%d",
      a4,
      (unsigned int)dwSPUpgradeFlag);
    v13 = 2001;
    goto LABEL_123;
  }
  v12 = *((_QWORD *)a1 + 8);
  if ( (*(_DWORD *)(v12 + 136) & 0x40000010) != 0 )
  {
    v13 = 1905;
LABEL_123:
    SetLastError(v13);
    goto LABEL_124;
  }
  if ( a5 )
  {
    if ( *(_QWORD *)(*(_QWORD *)(v12 + 280) + 216LL) )
    {
      v14 = *((_QWORD *)a1 + 21);
      v15 = *(_DWORD *)(v14 + 224);
      v16 = *(_WORD **)(v14 + 216);
      if ( v15 )
      {
        while ( *v16 )
        {
          v17 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL);
          if ( !v17 )
            goto LABEL_51;
          if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)(v17 + 24), v16) )
          {
            SetLastError(0x41u);
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "CreateJobEntry",
              L"Failing call because driver %ws is not allowed for remote printing.",
              v16);
            goto LABEL_124;
          }
          v18 = -1;
          do
            ++v18;
          while ( v16[v18] );
          v16 += v18 + 1;
          v15 += -1 - v18;
          if ( !v15 )
            break;
        }
      }
    }
  }
  v19 = (INIJOB *)operator new(0x288u);
  v9 = INIJOB::INIJOB(v19);
  if ( !v9 )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CreateJobEntry", L"Failed to allocate memory for IniJob");
    goto LABEL_124;
  }
  *((_DWORD *)v9 + 104) = *((_DWORD *)a1 + 71);
  v20 = *((_QWORD *)a1 + 6);
  if ( !v20 )
    v20 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 56LL);
  if ( (a6 & 0x20000000) != 0
    && (v21 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL)) != 0
    && (*(_BYTE *)(v21 + 200) & 2) != 0 )
  {
    v22 = L"XPS_PASS";
  }
  else if ( a3 && (v23 = a3[2]) != 0 )
  {
    v24 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL);
    if ( v24 && *(_DWORD *)(v24 + 236) < 4u && IsXPS2GDI(v23) )
    {
      v22 = L"XPS2GDI";
    }
    else
    {
      v25 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL);
      if ( v25
        && *(_DWORD *)(v25 + 236) == 4
        && (unsigned int)(*((_DWORD *)a1 + 62) - 6000) <= 0x6A3
        && !(unsigned int)_o__wcsicmp(L"XPS_PASS", a3[2]) )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo(
          "CreateJobEntry",
          L"XPS_PASS job received from downlevel client (build=%d) for a v4 queue. Forcing to RAW.",
          *((unsigned int *)a1 + 62));
        v22 = L"RAW";
      }
      else
      {
        v22 = a3[2];
      }
    }
  }
  else
  {
    v26 = (const wchar_t *)*((_QWORD *)a1 + 5);
    if ( !v26 )
      v26 = *(const wchar_t **)(*((_QWORD *)a1 + 8) + 64LL);
    if ( (a6 & 0x100) != 0 && !(unsigned int)ValidRawDatatype(v26) )
      goto LABEL_42;
    v22 = v26;
  }
  v27 = AllocSplStr(v22);
  *((_QWORD *)v9 + 16) = v27;
  if ( !v27 )
    goto LABEL_124;
  v28 = a6 | 0x20000;
  v29 = *(_DWORD *)(*((_QWORD *)a1 + 21) + 168LL);
  if ( (v29 & 0x4000000) == 0 )
    v28 = a6;
  if ( (v29 & 0x1000000) != 0 && !*(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL)
    || (v30 = *((_QWORD *)a1 + 8), (*(_BYTE *)(v30 + 140) & 1) != 0) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceWarning("CreateJobEntry", L"Failing because the driver must be updated.");
LABEL_51:
    v13 = 3019;
    goto LABEL_123;
  }
  v31 = *(_QWORD *)(v30 + 88);
  if ( !v31 || (*(_BYTE *)(v31 + 200) & 2) == 0 || IsXPS2GDI(v9) )
  {
    *((_QWORD *)v9 + 14) = FindDatatype(v20, *((_QWORD *)v9 + 16));
    goto LABEL_66;
  }
  v32 = SelectXpsPrintProcessor(*(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL));
  if ( v32 )
  {
    if ( v32 != 1 )
      goto LABEL_62;
    XpsPrintProcessor = g_pHybridXpsIniPrintProc;
    if ( !g_pHybridXpsIniPrintProc )
    {
      XpsPrintProcessor = (struct INIPRINTPROC *)LoadXpsPrintProcessor(1);
      g_pHybridXpsIniPrintProc = XpsPrintProcessor;
    }
  }
  else
  {
    XpsPrintProcessor = g_pXpsIniPrintProc;
    if ( !g_pXpsIniPrintProc )
    {
      XpsPrintProcessor = (struct INIPRINTPROC *)LoadXpsPrintProcessor(0);
      g_pXpsIniPrintProc = XpsPrintProcessor;
    }
  }
  *((_QWORD *)v9 + 14) = XpsPrintProcessor;
LABEL_62:
  v34 = *((_QWORD *)v9 + 14);
  if ( !v34 )
    goto LABEL_124;
  if ( !(unsigned int)CheckDataTypes(v34, *((_QWORD *)v9 + 16)) )
  {
LABEL_42:
    v13 = 1804;
    goto LABEL_123;
  }
LABEL_66:
  SafeIncrementReference((unsigned int *)(*((_QWORD *)v9 + 14) + 16LL));
  *((_QWORD *)v9 + 3) = 1;
  if ( a5 )
    v28 |= 0x1000u;
  *((_QWORD *)v9 + 11) = *((_QWORD *)a1 + 8);
  *((_DWORD *)v9 + 10) = a4;
  INIJOB::SetJobStatusFlags(v9, v28);
  v36 = *((_QWORD *)v9 + 11);
  if ( v36 )
    *((_QWORD *)v9 + 80) = *(_QWORD *)(v36 + 224);
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 8) + 152LL) & 0x8000) != 0 )
    INIJOB::SetJobStatusFlags(v9, 0x8000u);
  LeaveSplSem(v35);
  if ( GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    *((_QWORD *)v9 + 69) = AllocSplStr(NameBuffer);
  if ( IsXPS2GDI(a3[2]) )
  {
    memset_0(v69, 0, 0x68u);
    RpcCallAttributes[0] = 2;
    RpcCallAttributes[1] = 16;
    if ( !RpcServerInqCallAttributesW(0, RpcCallAttributes) )
      *((_DWORD *)v9 + 140) = v70;
  }
  if ( (unsigned int)IsDefenderDeviceControlEnabled() )
    *((_DWORD *)v9 + 144) = GetDefenderProcessId(a1);
  UserName = GetUserNameExW((EXTENDED_NAME_FORMAT)65538, NameBuffer, &nSize);
  EnterSplSem(0);
  if ( !UserName )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "CreateJobEntry",
      L"Failed to get user name for job entry.  Error %d",
      LastError);
    goto LABEL_124;
  }
  v38 = AllocSplStr(NameBuffer);
  *((_QWORD *)v9 + 7) = v38;
  if ( !v38 )
    goto LABEL_124;
  v39 = AllocSplStr(NameBuffer);
  *((_QWORD *)v9 + 6) = v39;
  if ( !v39 )
    goto LABEL_124;
  DocumentSecurityDescriptor = CreateDocumentSecurityDescriptor(*(PSECURITY_DESCRIPTOR *)(*((_QWORD *)a1 + 8) + 192LL));
  *((_QWORD *)v9 + 33) = DocumentSecurityDescriptor;
  if ( !DocumentSecurityDescriptor )
    goto LABEL_124;
  v41 = *a3;
  if ( !*a3 )
    v41 = L"No Document Name";
  v42 = AllocSplStr(v41);
  *((_QWORD *)v9 + 9) = v42;
  if ( !v42 || !GetSid((__int64)v9) )
    goto LABEL_124;
  v43 = a3[1];
  if ( v43 )
  {
    v44 = AllocSplStr(v43);
    *((_QWORD *)v9 + 10) = v44;
    if ( !v44
      || (unsigned int)IsGoingToFile(a3[1], *((_QWORD *)a1 + 21))
      && (INIJOB::SetJobStatusFlags(v9, 0x40000u), !SetOutputFileProperty(v9, a3[1])) )
    {
LABEL_124:
      v61 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning("CreateJobEntry", L"Failed to create new job entry.  Error %d", v61);
      if ( a1 )
        v62 = (struct _INIPRINTER *)*((_QWORD *)a1 + 8);
      else
        v62 = 0;
      LocalSpoolerTelemetry::LogPrintQError(v62, L"CreateJobEntry", 5748, v61);
      if ( v9 )
      {
        v64 = *((_QWORD *)v9 + 12);
        if ( v64 )
        {
          if ( *(_DWORD *)(v64 + 16) )
            SafeDecrementReference((unsigned int *)(v64 + 16));
        }
        INIJOB::`scalar deleting destructor'(v9, v63);
      }
      return 0;
    }
  }
  else
  {
    *((_QWORD *)v9 + 10) = 0;
  }
  v45 = (void *)*((_QWORD *)a1 + 7);
  if ( v45
    || (unsigned int)bGetDevModePerUser(0, *(_QWORD *)(*((_QWORD *)a1 + 8) + 24LL), &v67) && (v45 = v67) != 0
    || (v45 = *(void **)(*((_QWORD *)a1 + 8) + 104LL)) != 0 )
  {
    v46 = AllocDevMode(v45);
    *((_QWORD *)v9 + 13) = v46;
    if ( !v46 )
      goto LABEL_124;
    DllFreeSplMem(v67);
  }
  GetSystemTime((LPSYSTEMTIME)v9 + 9);
  ++*(_DWORD *)(*((_QWORD *)a1 + 8) + 156LL);
  ++*(_DWORD *)(*((_QWORD *)a1 + 8) + 216LL);
  v47 = *(_QWORD *)(*((_QWORD *)a1 + 8) + 88LL);
  *((_QWORD *)v9 + 12) = v47;
  if ( v47 )
    SafeIncrementReference((unsigned int *)(v47 + 16));
  v48 = *(_QWORD *)ThreadId;
  *((_QWORD *)v9 + 31) = 0;
  *((_QWORD *)v9 + 17) = 0;
  if ( !(unsigned int)bAddMachineName(a1, v9, v48) )
    goto LABEL_124;
  *((_QWORD *)v9 + 24) = 0;
  *((_QWORD *)v9 + 34) = 0;
  *((_QWORD *)v9 + 22) = 0;
  *((_QWORD *)v9 + 41) = 0;
  v49 = *(_DWORD *)(*((_QWORD *)a1 + 8) + 116LL);
  if ( !v49 )
    v49 = 1;
  *((_DWORD *)v9 + 11) = v49;
  *((_DWORD *)v9 + 41) = *(_DWORD *)(*((_QWORD *)a1 + 8) + 120LL);
  *((_DWORD *)v9 + 42) = *(_DWORD *)(*((_QWORD *)a1 + 8) + 124LL);
  *((_QWORD *)v9 + 37) = 0;
  *((_QWORD *)v9 + 28) = 0;
  *((_QWORD *)v9 + 27) = 0;
  *((_QWORD *)v9 + 23) = -1;
  *(_QWORD *)((char *)v9 + 364) = 0;
  *(_QWORD *)((char *)v9 + 372) = 0;
  *((_QWORD *)v9 + 35) = 0;
  *((_DWORD *)v9 + 72) = 0;
  *((_QWORD *)v9 + 44) = 0;
  *(_QWORD *)((char *)v9 + 340) = 0;
  *((_DWORD *)v9 + 90) = 0;
  *((_DWORD *)v9 + 84) = 0;
  *((_DWORD *)v9 + 108) = 0;
  *((_DWORD *)v9 + 114) = *((_DWORD *)a1 + 62);
  v50 = *((_QWORD *)v9 + 12);
  v51 = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 8) + 280LL) + 168LL) & 0x4000000;
  v52 = v51 != 0;
  if ( !v50 || (v53 = 1, (*(_DWORD *)(v50 + 200) & 0x1000) == 0) )
    v53 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetImpl'::`2'::impl)
    || *(_DWORD *)(*((_QWORD *)a1 + 8) + 552LL) )
  {
    v55 = operator new(0x10u);
    v55[3] = 0;
    ThreadId[0] = 0;
    *(_QWORD *)v55 = v9;
    v55[2] = v52;
    SafeIncrementReference((unsigned int *)v9 + 6);
    Thread = CreateThread(0, 0x8000u, TelemetryRetrieveAppInfoThread, v55, 0, ThreadId);
    if ( Thread )
    {
      CloseHandle(Thread);
    }
    else if ( *(_QWORD *)v55 )
    {
      SafeDecrementReference((unsigned int *)(*(_QWORD *)v55 + 24LL));
    }
  }
  else
  {
    LocalSpoolerTelemetry::LogJobStarted(v9, v52, 0, 0, 0, 0);
  }
  if ( !v53 && !a5 )
  {
    v57 = *((_QWORD *)v9 + 11);
    if ( v51 )
      v58 = *(const unsigned __int16 **)(v57 + 80);
    else
      v58 = *(const unsigned __int16 **)(v57 + 24);
    UpdateMRUPrinterIfApplicable(v58, *((const unsigned __int16 **)v9 + 51), 0, v54);
  }
  return v9;
}

```

## disassembly

```asm
0x1800602a8  push    rbx
0x1800602aa  push    rsi
0x1800602ab  push    rdi
0x1800602ac  push    r12
0x1800602ae  push    r13
0x1800602b0  push    r14
0x1800602b2  push    r15
0x1800602b4  sub     rsp, 2E0h
0x1800602bb  mov     rax, cs:__security_cookie
0x1800602c2  xor     rax, rsp
0x1800602c5  mov     [rsp+318h+var_48], rax
0x1800602cd  mov     rax, [rsp+318h+arg_30]
0x1800602d5  mov     r13d, r9d
0x1800602d8  mov     qword ptr [rsp+318h+ThreadId], rax
0x1800602dd  mov     r12, r8
0x1800602e0  xor     eax, eax
0x1800602e2  mov     [rsp+318h+nSize], 104h
0x1800602ea  mov     edi, eax
0x1800602ec  mov     [rsp+318h+var_2D8], rax
0x1800602f1  mov     eax, cs:Microsoft_Windows_DocumentsEnableBits
0x1800602f7  mov     rsi, rcx
0x1800602fa  lea     ebx, [rdi+1]
0x1800602fd  test    bl, al
0x1800602ff  jz      short loc_180060329
0x180060301  mov     r8d, r9d
0x180060304  lea     rdx, DocPerf_PrintDocument_Start
0x18006030b  call    McTemplateU0q_EtwEventWriteTransfer
0x180060310  mov     eax, cs:Microsoft_Windows_DocumentsEnableBits
0x180060316  test    bl, al
0x180060318  jz      short loc_180060329
0x18006031a  mov     r8d, r13d
0x18006031d  lea     rdx, DocPerf_SpoolDocument_Start
0x180060324  call    McTemplateU0q_EtwEventWriteTransfer
0x180060329  call    IsSystemCurrentlyUpgrading
0x18006032e  mov     r9d, cs:dwSPUpgradeFlag
0x180060335  xor     ebx, ebx
0x180060337  test    al, al
0x180060339  jnz     loc_180060B39
0x18006033f  test    r9d, r9d
0x180060342  jnz     loc_180060B39
0x180060348  mov     rax, [rsi+40h]
0x18006034c  test    dword ptr [rax+88h], 40000010h
0x180060356  jz      short loc_180060362
0x180060358  mov     ecx, 771h
0x18006035d  jmp     loc_180060B54
0x180060362  cmp     [rsp+318h+arg_20], ebx
0x180060369  jz      short loc_1800603E0
0x18006036b  mov     rax, [rax+118h]
0x180060372  cmp     [rax+0D8h], rbx
0x180060379  jz      short loc_1800603E0
0x18006037b  mov     rax, [rsi+0A8h]
0x180060382  xor     r15d, r15d
0x180060385  mov     r14d, [rax+0E0h]
0x18006038c  mov     rbx, [rax+0D8h]
0x180060393  test    r14d, r14d
0x180060396  jz      short loc_1800603E0
0x180060398  cmp     [rbx], r15w
0x18006039c  jz      short loc_1800603E0
0x18006039e  mov     rax, [rsi+40h]
0x1800603a2  mov     rcx, [rax+58h]
0x1800603a6  test    rcx, rcx
0x1800603a9  jz      loc_1800605CA
0x1800603af  mov     rcx, [rcx+18h]
0x1800603b3  mov     rdx, rbx
0x1800603b6  call    cs:__imp__o__wcsicmp
0x1800603bc  test    eax, eax
0x1800603be  jz      short loc_180060412
0x1800603c0  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800603c4  inc     rcx
0x1800603c7  cmp     [rbx+rcx*2], r15w
0x1800603cc  jnz     short loc_1800603C4
0x1800603ce  or      eax, 0FFFFFFFFh
0x1800603d1  lea     rbx, [rbx+rcx*2]
0x1800603d5  sub     eax, ecx
0x1800603d7  lea     rbx, [rbx+2]
0x1800603db  add     r14d, eax
0x1800603de  jnz     short loc_180060398
0x1800603e0  mov     ecx, 288h; Size
0x1800603e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800603ea  mov     rcx, rax; this
0x1800603ed  call    ??0INIJOB@@QEAA@XZ; INIJOB::INIJOB(void)
0x1800603f2  mov     rdi, rax
0x1800603f5  test    rax, rax
0x1800603f8  jnz     short loc_180060438
0x1800603fa  lea     rdx, aFailedToAlloca_8; "Failed to allocate memory for IniJob"
0x180060401  lea     rcx, aCreatejobentry_0; "CreateJobEntry"
0x180060408  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18006040d  jmp     loc_180060B5A
0x180060412  mov     ecx, 41h ; 'A'; dwErrCode
0x180060417  call    cs:__imp_SetLastError
0x18006041d  mov     r8, rbx
0x180060420  lea     rdx, aFailingCallBec; "Failing call because driver %ws is not "...
0x180060427  lea     rcx, aCreatejobentry_0; "CreateJobEntry"
0x18006042e  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180060433  jmp     loc_180060B5A
0x180060438  mov     eax, [rsi+11Ch]
0x18006043e  mov     [rdi+1A0h], eax
0x180060444  mov     r15, [rsi+30h]
0x180060448  test    r15, r15
0x18006044b  jnz     short loc_180060455
0x18006044d  mov     rax, [rsi+40h]
0x180060451  mov     r15, [rax+38h]
0x180060455  mov     r14d, [rsp+318h+arg_28]
0x18006045d  bt      r14d, 1Dh
0x180060462  jnb     short loc_180060486
0x180060464  mov     rax, [rsi+40h]
0x180060468  mov     rcx, [rax+58h]
0x18006046c  test    rcx, rcx
0x18006046f  jz      short loc_180060486
0x180060471  test    byte ptr [rcx+0C8h], 2
0x180060478  jz      short loc_180060486
0x18006047a  lea     rcx, aXpsPass; "XPS_PASS"
0x180060481  jmp     loc_180060561
0x180060486  test    r12, r12
0x180060489  jz      loc_180060530
0x18006048f  mov     rcx, [r12+10h]; unsigned __int16 *
0x180060494  test    rcx, rcx
0x180060497  jz      loc_180060530
0x18006049d  mov     rax, [rsi+40h]
0x1800604a1  mov     rdx, [rax+58h]
0x1800604a5  test    rdx, rdx
0x1800604a8  jz      short loc_1800604C8
0x1800604aa  cmp     dword ptr [rdx+0ECh], 4
0x1800604b1  jnb     short loc_1800604C8
0x1800604b3  call    ?IsXPS2GDI@@YA_NPEBG@Z; IsXPS2GDI(ushort const *)
0x1800604b8  test    al, al
0x1800604ba  jz      short loc_1800604C8
0x1800604bc  lea     rcx, aXps2gdi; "XPS2GDI"
0x1800604c3  jmp     loc_180060561
0x1800604c8  mov     rax, [rsi+40h]
0x1800604cc  mov     rcx, [rax+58h]
0x1800604d0  test    rcx, rcx
0x1800604d3  jz      short loc_180060529
0x1800604d5  cmp     dword ptr [rcx+0ECh], 4
0x1800604dc  jnz     short loc_180060529
0x1800604de  mov     eax, [rsi+0F8h]
0x1800604e4  sub     eax, 1770h
0x1800604e9  cmp     eax, 6A3h
0x1800604ee  ja      short loc_180060529
0x1800604f0  mov     rdx, [r12+10h]
0x1800604f5  lea     rcx, aXpsPass; "XPS_PASS"
0x1800604fc  call    cs:__imp__o__wcsicmp
0x180060502  test    eax, eax
0x180060504  jnz     short loc_180060529
0x180060506  mov     r8d, [rsi+0F8h]
0x18006050d  lea     rdx, aXpsPassJobRece; "XPS_PASS job received from downlevel cl"...
0x180060514  lea     rcx, aCreatejobentry_0; "CreateJobEntry"
0x18006051b  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180060520  lea     rcx, aRaw; "RAW"
0x180060527  jmp     short loc_180060561
0x180060529  mov     rcx, [r12+10h]
0x18006052e  jmp     short loc_180060561
0x180060530  mov     rbx, [rsi+28h]
0x180060534  test    rbx, rbx
0x180060537  jnz     short loc_180060541
0x180060539  mov     rax, [rsi+40h]
0x18006053d  mov     rbx, [rax+40h]
0x180060541  bt      r14d, 8
0x180060546  jnb     short loc_18006055E
0x180060548  mov     rcx, rbx
0x18006054b  call    ValidRawDatatype
0x180060550  test    eax, eax
0x180060552  jnz     short loc_18006055E
0x180060554  mov     ecx, 70Ch
0x180060559  jmp     loc_180060B54
0x18006055e  mov     rcx, rbx
0x180060561  call    cs:__imp_AllocSplStr
0x180060567  mov     [rdi+80h], rax
0x18006056e  test    rax, rax
0x180060571  jz      loc_180060B5A
0x180060577  mov     rax, [rsi+0A8h]
0x18006057e  mov     ebx, r14d
0x180060581  bts     ebx, 11h
0x180060585  mov     ecx, [rax+0A8h]
0x18006058b  bt      ecx, 1Ah
0x18006058f  cmovnb  ebx, r14d
0x180060593  bt      ecx, 18h
0x180060597  jnb     short loc_1800605A4
0x180060599  mov     rax, [rsi+40h]
0x18006059d  cmp     qword ptr [rax+58h], 0
0x1800605a2  jz      short loc_1800605B7
0x1800605a4  mov     rax, [rsi+40h]
0x1800605a8  mov     r14d, 1
0x1800605ae  test    [rax+8Ch], r14b
0x1800605b5  jz      short loc_1800605D4
0x1800605b7  lea     rdx, aFailingBecause_0; "Failing because the driver must be upda"...
0x1800605be  lea     rcx, aCreatejobentry_0; "CreateJobEntry"
0x1800605c5  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800605ca  mov     ecx, 0BCBh
0x1800605cf  jmp     loc_180060B54
0x1800605d4  mov     rcx, [rax+58h]
0x1800605d8  test    rcx, rcx
0x1800605db  jz      loc_180060670
0x1800605e1  test    byte ptr [rcx+0C8h], 2
0x1800605e8  jz      loc_180060670
0x1800605ee  mov     rcx, rdi; struct INIJOB *
0x1800605f1  call    ?IsXPS2GDI@@YA_NPEAVINIJOB@@@Z; IsXPS2GDI(INIJOB *)
0x1800605f6  test    al, al
0x1800605f8  jnz     short loc_180060670
0x1800605fa  mov     rcx, [rsi+40h]
0x1800605fe  mov     rcx, [rcx+58h]
0x180060602  call    ?SelectXpsPrintProcessor@@YA?AW4XpsPrintProcessorType@@PEAU_INIDRIVER@@@Z; SelectXpsPrintProcessor(_INIDRIVER *)
0x180060607  xor     r15d, r15d
0x18006060a  test    eax, eax
0x18006060c  jnz     short loc_18006062A
0x18006060e  mov     rax, cs:?g_pXpsIniPrintProc@@3PEAVINIPRINTPROC@@EA; INIPRINTPROC * g_pXpsIniPrintProc
0x180060615  test    rax, rax
0x180060618  jnz     short loc_18006064A
0x18006061a  xor     ecx, ecx
0x18006061c  call    ?LoadXpsPrintProcessor@@YAPEAVINIPRINTPROC@@W4XpsPrintProcessorType@@@Z; LoadXpsPrintProcessor(XpsPrintProcessorType)
0x180060621  mov     cs:?g_pXpsIniPrintProc@@3PEAVINIPRINTPROC@@EA, rax; INIPRINTPROC * g_pXpsIniPrintProc
0x180060628  jmp     short loc_18006064A
0x18006062a  cmp     eax, r14d
0x18006062d  jnz     short loc_18006064E
0x18006062f  mov     rax, cs:?g_pHybridXpsIniPrintProc@@3PEAVINIPRINTPROC@@EA; INIPRINTPROC * g_pHybridXpsIniPrintProc
0x180060636  test    rax, rax
0x180060639  jnz     short loc_18006064A
0x18006063b  mov     ecx, r14d
0x18006063e  call    ?LoadXpsPrintProcessor@@YAPEAVINIPRINTPROC@@W4XpsPrintProcessorType@@@Z; LoadXpsPrintProcessor(XpsPrintProcessorType)
0x180060643  mov     cs:?g_pHybridXpsIniPrintProc@@3PEAVINIPRINTPROC@@EA, rax; INIPRINTPROC * g_pHybridXpsIniPrintProc
0x18006064a  mov     [rdi+70h], rax
0x18006064e  mov     rcx, [rdi+70h]
0x180060652  test    rcx, rcx
0x180060655  jz      loc_180060B5A
0x18006065b  mov     rdx, [rdi+80h]
0x180060662  call    CheckDataTypes
0x180060667  test    eax, eax
0x180060669  jnz     short loc_180060686
0x18006066b  jmp     loc_180060554
0x180060670  mov     rdx, [rdi+80h]
0x180060677  mov     rcx, r15
0x18006067a  call    FindDatatype
0x18006067f  mov     [rdi+70h], rax
0x180060683  xor     r15d, r15d
0x180060686  mov     rcx, [rdi+70h]
0x18006068a  add     rcx, 10h; unsigned int *
0x18006068e  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060693  mov     [rdi+18h], r14
0x180060697  cmp     [rsp+318h+arg_20], r15d
0x18006069f  jz      short loc_1800606A5
0x1800606a1  bts     ebx, 0Ch
0x1800606a5  mov     rax, [rsi+40h]
0x1800606a9  mov     edx, ebx; unsigned int
0x1800606ab  mov     rcx, rdi; this
0x1800606ae  mov     [rdi+58h], rax
0x1800606b2  mov     [rdi+28h], r13d
0x1800606b6  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x1800606bb  mov     rax, [rdi+58h]
0x1800606bf  xor     r13d, r13d
0x1800606c2  test    rax, rax
0x1800606c5  jz      short loc_1800606D5
0x1800606c7  mov     rax, [rax+0E0h]
0x1800606ce  mov     [rdi+280h], rax
0x1800606d5  mov     rax, [rsi+40h]
0x1800606d9  test    dword ptr [rax+98h], 8000h
0x1800606e3  jz      short loc_1800606F2
0x1800606e5  mov     edx, 8000h; unsigned int
0x1800606ea  mov     rcx, rdi; this
0x1800606ed  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x1800606f2  call    LeaveSplSem
0x1800606f7  mov     ebx, 2
0x1800606fc  lea     r8, [rsp+318h+nSize]; nSize
0x180060701  mov     ecx, ebx; NameFormat
0x180060703  lea     rdx, [rsp+318h+NameBuffer]; lpNameBuffer
0x18006070b  call    cs:__imp_GetUserNameExW
0x180060711  test    al, al
0x180060713  jz      short loc_18006072A
0x180060715  lea     rcx, [rsp+318h+NameBuffer]
0x18006071d  call    cs:__imp_AllocSplStr
0x180060723  mov     [rdi+228h], rax
0x18006072a  mov     rcx, [r12+10h]; unsigned __int16 *
0x18006072f  call    ?IsXPS2GDI@@YA_NPEBG@Z; IsXPS2GDI(ushort const *)
0x180060734  test    al, al
0x180060736  jz      short loc_180060772
0x180060738  xor     edx, edx; Val
0x18006073a  lea     rcx, [rsp+318h+var_2C0]; void *
0x18006073f  lea     r8d, [rdx+68h]; Size
0x180060743  call    memset_0
0x180060748  lea     rdx, [rsp+318h+RpcCallAttributes]; RpcCallAttributes
0x18006074d  mov     [rsp+318h+RpcCallAttributes], ebx
0x180060751  xor     ecx, ecx; ClientBinding
0x180060753  mov     [rsp+318h+var_2C4], 10h
0x18006075b  call    cs:__imp_RpcServerInqCallAttributesW
0x180060761  test    eax, eax
0x180060763  jnz     short loc_180060772
0x180060765  mov     eax, [rsp+318h+var_288]
0x18006076c  mov     [rdi+230h], eax
0x180060772  call    ?IsDefenderDeviceControlEnabled@@YAHXZ; IsDefenderDeviceControlEnabled(void)
0x180060777  test    eax, eax
0x180060779  jz      short loc_180060789
0x18006077b  mov     rcx, rsi; struct _SPOOL *
0x18006077e  call    ?GetDefenderProcessId@@YAKPEAU_SPOOL@@@Z; GetDefenderProcessId(_SPOOL *)
0x180060783  mov     [rdi+240h], eax
0x180060789  lea     r8, [rsp+318h+nSize]; nSize
0x18006078e  mov     ecx, 10002h; NameFormat
0x180060793  lea     rdx, [rsp+318h+NameBuffer]; lpNameBuffer
0x18006079b  call    cs:__imp_GetUserNameExW
0x1800607a1  xor     ecx, ecx
0x1800607a3  mov     bl, al
0x1800607a5  call    EnterSplSem
  ... truncated ...
```
