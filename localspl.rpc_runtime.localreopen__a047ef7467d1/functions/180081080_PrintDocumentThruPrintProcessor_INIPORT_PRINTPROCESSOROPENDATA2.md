# PrintDocumentThruPrintProcessor(_INIPORT *,PRINTPROCESSOROPENDATA2 *)

- ea: `0x180081080`
- end: `0x180081eaf`
- name: `?PrintDocumentThruPrintProcessor@@YAXPEAU_INIPORT@@PEAUPRINTPROCESSOROPENDATA2@@@Z`
- size: `3631`
- prototype: `void(struct _INIPORT *, struct PRINTPROCESSOROPENDATA2 *)`
- caller_count: `1`
- callee_count: `41`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180088860`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180008cb8`
- `0x18000bb60`
- `0x18000edc4`
- `0x180011ed0`
- `0x18001fb10`
- `0x1800237b0`
- `0x1800237d8`
- `0x18002c8d8`
- `0x180031e10`
- `0x1800349c4`
- `0x18003a888`
- `0x18003d1f8`
- `0x18003e984`
- `0x18003ea2c`
- `0x180041b0c`
- `0x180043adc`
- `0x180044484`
- `0x18004486c`
- `0x180046650`
- `0x180047330`
- `0x180054638`
- `0x180060204`
- `0x180061dd8`
- `0x180072ff8`
- `0x1800747e4`
- `0x180081080`
- `0x180088304`
- `0x180097778`
- `0x1800c5aa4`
- `0x1800c7a84`
- `0x1800cc910`
- `0x1800ccbd8`
- `0x1800cd620`
- `0x1800cd7b4`
- `0x1800d7418`
- `0x1800d75dc`
- `0x1800d8a90`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x18008119e`
- `ntdll!NtSetInformationThread` at `0x18008188d`
- `ntdll!NtSetInformationThread` at `0x180081d82`
- `ntdll!NtSetInformationThread` at `0x18008119e`
- `ntdll!NtSetInformationThread` at `0x18008188d`
- `ntdll!NtSetInformationThread` at `0x180081d82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081aae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180081aae`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081b4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180081b4e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180081a60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180081a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800814c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008160b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081264`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800812f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800814c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008160b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081adc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081ae6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081b15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081b1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180081d55`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081d0e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180081d0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081d33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180081d33`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180081256`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180081256`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800812ee`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800812ee`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081d4b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180081d4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081550`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180081550`
- `SPOOLSS!SetPrinterDataW` at `0x1800818d6`
- `SPOOLSS!SetPrinterDataW` at `0x1800818d6`
- `SPOOLSS!ClosePrinter` at `0x18008171d`
- `SPOOLSS!ClosePrinter` at `0x180081983`
- `SPOOLSS!ClosePrinter` at `0x18008171d`
- `SPOOLSS!ClosePrinter` at `0x180081983`
- `SPOOLSS!OpenPrinter2W` at `0x1800816c4`
- `SPOOLSS!OpenPrinter2W` at `0x1800818ac`
- `SPOOLSS!OpenPrinter2W` at `0x1800816c4`
- `SPOOLSS!OpenPrinter2W` at `0x1800818ac`
- `SPOOLSS!AllocSplStr` at `0x180081462`
- `SPOOLSS!AllocSplStr` at `0x180081926`
- `SPOOLSS!AllocSplStr` at `0x180081462`
- `SPOOLSS!AllocSplStr` at `0x180081926`
- `SPOOLSS!GetPrinterDataW` at `0x180081705`
- `SPOOLSS!GetPrinterDataW` at `0x180081705`

## string_xrefs

- `0x180081124`: `User does not have access to the target file. Failing job with ERROR_ACCESS_DENIED!`
- `0x180081277`: `SetCurrentSid or ImpersonateSelf failed! Error %d`
- `0x18008116d`: `Windows Protected Print is enabled. Impersonating the user.`
- `0x180081301`: `Failed to get the appContainer info from GetTokenInformation. Defaulting the IsAppContainer to FALSE. Error %d`
- `0x18008148a`: `Printing job %u through print processor '%ws', datatype='%ws', pOpenData->pPrinterName='%ws'`
- `0x1800814dc`: `Failed to open print processor %ws. Error %d`
- `0x1800816fa`: `ForceClientSideRendering`
- `0x1800819b6`: `CSR job has already been retried, printer='%ws', JobID=%u, datatype='%ws', status=%u, significant error=%d`
- `0x180081d21`: `PrintDocumentThruPrintProcessor: Cannot reset the thread token. Error %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PrintDocumentThruPrintProcessor(struct _INIPORT *a1, const unsigned __int16 **a2)
{
  __int64 v4; // rdi
  unsigned int v5; // r12d
  struct INIPRINTPROC *IniPrintProc; // r14
  int v7; // r13d
  int *v8; // r8
  int v9; // eax
  int v10; // r14d
  HANDLE v11; // rbx
  unsigned int IsRemoteGuest; // ebx
  __int64 v13; // rcx
  __int64 LastError; // rbx
  DWORD v15; // eax
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // r10
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v21; // rax
  unsigned __int16 *v22; // r12
  unsigned int v23; // ebx
  char IsEnabled; // al
  sandbox::PrintProcessorAdapter *v25; // rcx
  void *v26; // rax
  DWORD v27; // ebx
  void *v28; // rax
  __int64 v29; // r13
  unsigned __int16 *v30; // rbx
  __int64 v31; // rcx
  int v32; // r12d
  struct sandbox::ProcessorDataHandle *v33; // rdx
  struct _RTL_CRITICAL_SECTION *v34; // rbx
  DWORD v35; // ebx
  int v36; // r14d
  __int64 v37; // rcx
  const struct _tlgProvider_t *v38; // rax
  __int64 v39; // r8
  int v40; // r14d
  DWORD v41; // ecx
  struct SplLogType *v42; // rax
  __int64 v43; // r10
  __int64 v44; // r11
  _DWORD *v45; // rcx
  _DWORD *v46; // r9
  const unsigned __int16 *v47; // rdx
  struct SplLogType *v48; // rax
  __int64 v49; // r10
  __int64 v50; // r11
  const wchar_t *v51; // rcx
  __int64 v52; // rcx
  void *v53; // rcx
  __int64 v54; // rcx
  sandbox::PrintProcessorAdapter *v55; // rcx
  DWORD v56; // eax
  DWORD v57; // eax
  __int64 v58; // rax
  const struct _EVENT_DESCRIPTOR *v59; // rcx
  __int16 v60; // r14
  __int16 v61; // bx
  __int16 v62; // r11
  __int16 v63; // r8
  __int16 v64; // r10
  __int16 v65; // dx
  unsigned int v66; // r9d
  __int64 v67; // rbx
  HANDLE v68; // r14
  unsigned __int64 v69; // rcx
  __int64 v70; // r10
  __int64 v71; // rdx
  HANDLE v72; // r13
  DWORD v73; // eax
  DWORD v74; // eax
  SplLogType *v75; // rax
  __int64 v76; // r10
  unsigned int *v77; // rcx
  PDWORD ReturnLength; // [rsp+20h] [rbp-E0h]
  LPDWORD pcbNeeded; // [rsp+28h] [rbp-D8h]
  LPDWORD pcbNeededa; // [rsp+28h] [rbp-D8h]
  void *TokenInformation; // [rsp+50h] [rbp-B0h] BYREF
  __int64 ThreadInformation; // [rsp+58h] [rbp-A8h] BYREF
  int v83; // [rsp+60h] [rbp-A0h]
  unsigned int v84[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _PRINTER_OPTIONSW pData; // [rsp+70h] [rbp-90h] BYREF
  DWORD pType[2]; // [rsp+78h] [rbp-88h] BYREF
  int v87; // [rsp+80h] [rbp-80h]
  DWORD v88[2]; // [rsp+88h] [rbp-78h] BYREF
  HANDLE phPrinter; // [rsp+90h] [rbp-70h] BYREF
  HANDLE TokenHandle; // [rsp+98h] [rbp-68h] BYREF
  int v91; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v92; // [rsp+A8h] [rbp-58h]
  int v93; // [rsp+B0h] [rbp-50h]
  DWORD v94; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v95; // [rsp+C0h] [rbp-40h]
  int v96; // [rsp+C8h] [rbp-38h]
  struct INIPRINTPROC *v97; // [rsp+D0h] [rbp-30h]
  _BYTE v98[24]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v99[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v100[800]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v101[264]; // [rsp+750h] [rbp+650h] BYREF

  *(_QWORD *)pType = a1;
  v4 = *((_QWORD *)a1 + 9);
  memset_0(v100, 0, 0x63Eu);
  v5 = 0;
  pData.cbSize = 0;
  v84[0] = 0;
  TokenInformation = 0;
  v87 = 0;
  TokenHandle = 0;
  IniPrintProc = INIJOB::GetIniPrintProc((INIJOB *)v4);
  v97 = IniPrintProc;
  if ( (*(_DWORD *)(v4 + 32) & 0x40000) != 0
    && !*(_BYTE *)(v4 + 536)
    && !CanUserAccessTargetFile(*((LPCWSTR *)a1 + 3), *(void **)(v4 + 256)) )
  {
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "PrintDocumentThruPrintProcessor",
      L"User does not have access to the target file. Failing job with ERROR_ACCESS_DENIED!");
    LogPrintProcError(5u);
LABEL_5:
    v7 = 1;
    goto LABEL_132;
  }
  if ( !(unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    if ( !(unsigned int)IsSpecialDriver(*(_QWORD *)(v4 + 96), IniPrintProc) )
    {
      IsRemoteGuest = PrincipalIsRemoteGuest(*(HANDLE *)(v4 + 256), (int *)v84);
      if ( IsRemoteGuest )
        goto LABEL_21;
      if ( !v84[0] )
      {
        v13 = *(_QWORD *)(v4 + 256);
        if ( (unsigned __int64)(v13 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        {
          v87 = 0;
          ThreadInformation = v13;
          goto LABEL_8;
        }
      }
    }
    v87 = 1;
    if ( ImpersonateSelf(SecurityImpersonation) )
      goto LABEL_9;
    IsRemoteGuest = GetLastError();
    if ( !IsRemoteGuest )
      goto LABEL_9;
LABEL_21:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "PrintDocumentThruPrintProcessor",
      L"SetCurrentSid or ImpersonateSelf failed! Error %d",
      IsRemoteGuest);
    LogPrintProcError(IsRemoteGuest);
    goto LABEL_5;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "PrintDocumentThruPrintProcessor",
    L"Windows Protected Print is enabled. Impersonating the user.");
  ThreadInformation = *(_QWORD *)(v4 + 256);
LABEL_8:
  NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
LABEL_9:
  v9 = NSecurityLibrary::ElevateIntegrityLevelIfLow((NSecurityLibrary *)&TokenHandle, &TokenInformation, v8);
  v10 = (int)TokenInformation;
  if ( v9 )
    goto LABEL_23;
  if ( !(_DWORD)TokenInformation )
    goto LABEL_33;
  if ( !(unsigned int)IsWindowsProtectedPrintEnabled() )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "PrintDocumentThruPrintProcessor",
      L"ElevateIntegrityLevelIfLow failed! Error %d",
      LastError);
    LogPrintProcError(LastError);
    goto LABEL_23;
  }
  if ( (unsigned __int16)GetPipelineLaunchTokenForLowILPrinting(&TokenHandle) )
  {
LABEL_23:
    v11 = TokenHandle;
    goto LABEL_24;
  }
  *(_BYTE *)(v4 + 565) = 1;
  v11 = TokenHandle;
  *(_QWORD *)(v4 + 568) = TokenHandle;
  v5 = 1;
LABEL_24:
  if ( !v10 || v5 )
  {
    v5 = 0;
  }
  else
  {
    v5 = 0;
    LODWORD(TokenInformation) = 0;
    v88[0] = 0;
    if ( GetTokenInformation(v11, TokenIsAppContainer, &TokenInformation, 4u, v88) )
    {
      v16 = (int)TokenInformation;
    }
    else
    {
      v15 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "PrintDocumentThruPrintProcessor",
        L"Failed to get the appContainer info from GetTokenInformation. Defaulting the IsAppContainer to FALSE. Error %d",
        v15);
      v16 = 0;
    }
    if ( !v16 || !g_bBypassSecurityCheckForAppContainerPrinting )
    {
      *(_BYTE *)(v4 + 565) = 1;
      *(_QWORD *)(v4 + 568) = v11;
    }
  }
LABEL_33:
  ThreadInformation = NVJobStatus;
  v83 = dword_18013E040;
  v17 = *(_QWORD *)(v4 + 88);
  v18 = *(_QWORD *)(*(_QWORD *)(v17 + 280) + 24LL);
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( *(_WORD *)(v18 + 2 * v20) );
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)(*(_QWORD *)(*(_QWORD *)pType + 24LL) + 2 * v21) );
  if ( (unsigned __int64)(unsigned int)v20 + v21 + 20 > 0x31F )
    goto LABEL_5;
  do
    ++v19;
  while ( *(_WORD *)(*(_QWORD *)(v17 + 24) + 2 * v19) );
  if ( (unsigned __int64)(unsigned int)v20 + v19 + 20 > 0x31F )
    goto LABEL_5;
  StrNCatBuff(v100, 799, v18, L"\\");
  v22 = &v100[(unsigned int)(v20 + 1)];
  StringCchPrintfW(v22, 799LL - (unsigned int)(v20 + 1), L"%ws, Port", *(_QWORD *)(*(_QWORD *)pType + 24LL), 0);
  v23 = 0;
  if ( IsXPS2GDI(a2[1]) && g_hWinSta0 )
    v23 = *(_DWORD *)(v4 + 416);
  if ( IsXPS2GDI(a2[1]) && *(_DWORD *)(v4 + 560) && !a2[2] )
  {
    StringCchPrintfW(v101, 0x104u, L"%d");
    a2[2] = (const unsigned __int16 *)AllocSplStr(v101);
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "PrintDocumentThruPrintProcessor",
    L"Printing job %u through print processor '%ws', datatype='%ws', pOpenData->pPrinterName='%ws'",
    *(unsigned int *)(v4 + 40),
    *((_QWORD *)v97 + 3),
    a2[1],
    a2[6]);
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl);
  v25 = (sandbox::PrintProcessorAdapter *)*((_QWORD *)v97 + 9);
  if ( IsEnabled )
  {
    v26 = sandbox::PrintProcessorAdapter::OpenPrintProcessor(v25, v100, (struct PRINTPROCESSOROPENDATA2 *)a2, v23);
    *(_QWORD *)(v4 + 120) = v26;
    if ( !v26 )
    {
LABEL_49:
      v27 = GetLastError();
      HIDWORD(TokenInformation) = v27;
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "PrintDocumentThruPrintProcessor",
        L"Failed to open print processor %ws. Error %d",
        v100,
        v27);
      LogPrintProcError(v27);
      v7 = 1;
      v5 = 0;
      goto LABEL_132;
    }
    v29 = *(_QWORD *)pType;
  }
  else
  {
    v28 = sandbox::PrintProcessorAdapter::OpenPrintProcessor(v25, v100, (struct PRINTPROCESSOROPENDATA2 *)a2, v23);
    v29 = *(_QWORD *)pType;
    *(_QWORD *)(*(_QWORD *)pType + 40LL) = v28;
    if ( !v28 )
      goto LABEL_49;
  }
  LODWORD(TokenInformation) = 0;
  v30 = v100;
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 88) + 280LL) + 168LL) & 0x4000000) != 0 )
    v30 = v22;
  EnterSplSem(0);
  INIJOB::SetJobStatusFlags((INIJOB *)v4, 1u);
  *(_DWORD *)(v4 + 160) = GetTickCount();
  HIDWORD(ThreadInformation) |= 4u;
  SetPrinterChange(
    *(_QWORD *)(v4 + 88),
    v4,
    (unsigned int)&ThreadInformation,
    512,
    *(_QWORD *)(*(_QWORD *)(v4 + 88) + 280LL));
  v31 = *(_QWORD *)(*(_QWORD *)(v4 + 88) + 88LL);
  if ( !v31 || (v32 = 1, (*(_BYTE *)(v31 + 200) & 2) == 0) )
    v32 = 0;
  LeaveSplSem(v31);
  LODWORD(ReturnLength) = *(_DWORD *)(v4 + 40);
  StringCchPrintfW(v30, 799 - (v30 - v100), L"%ws, Job %d", *(_QWORD *)(*(_QWORD *)(v4 + 88) + 24LL), ReturnLength);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl) )
    v33 = *(struct sandbox::ProcessorDataHandle **)(v4 + 120);
  else
    v33 = *(struct sandbox::ProcessorDataHandle **)(v29 + 40);
  v34 = (struct _RTL_CRITICAL_SECTION *)v97;
  if ( !(unsigned int)sandbox::PrintProcessorAdapter::PrintDocumentOnPrintProcessor(
                        *((sandbox::PrintProcessorAdapter **)v97 + 9),
                        v33,
                        v100) )
  {
    v35 = GetLastError();
    HIDWORD(TokenInformation) = v35;
    EnterSplSem(1);
    v36 = *(_DWORD *)(v4 + 32);
    LeaveSplSem(v37);
    if ( v35 == 63 )
    {
LABEL_67:
      *(_DWORD *)(v4 + 436) = 63;
      v38 = LocalSpoolerTelemetry::Provider();
      SplTraceErrorPrintCancelled(v38, L"port.c error fallback.");
LABEL_68:
      v5 = 0;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl) )
        v39 = *(_QWORD *)(v4 + 120);
      else
        v39 = *(_QWORD *)(v29 + 40);
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "PrintDocumentThruPrintProcessor",
        L"PrintDocumentThruPrintProcessor failed - Print hProc %p Error %d",
        v39,
        v35);
      EnterSplSem(1);
      v53 = *(void **)(v4 + 232);
      if ( v53 )
        SetEvent(v53);
      pData.cbSize = 1;
      LeaveSplSem(v53);
      v34 = (struct _RTL_CRITICAL_SECTION *)v97;
      goto LABEL_102;
    }
    if ( (v36 & 0x20000) != 0 && v36 < 0 && (v36 & 0x24) == 0x20 )
    {
      v35 = 63;
      goto LABEL_67;
    }
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "PrintDocumentThruPrintProcessor",
      L"Failed to print document on print processor %ws. Error %d",
      v100,
      v35);
    v40 = 0;
    phPrinter = 0;
    ThreadInformation = 0x200000008LL;
    if ( OpenPrinter2W(*(LPCWSTR *)(v4 + 440), &phPrinter, 0, (PPRINTER_OPTIONSW)&ThreadInformation) )
    {
      pData.cbSize = 0;
      pType[0] = 4;
      v88[0] = 0;
      if ( !GetPrinterDataW(phPrinter, (LPWSTR)L"ForceClientSideRendering", pType, (LPBYTE)&pData, 4u, v88) )
        LOBYTE(v40) = pData.cbSize != 0;
      ClosePrinter(phPrinter);
    }
    if ( v35 == 3003 )
    {
      v41 = *(_DWORD *)(v4 + 436);
      if ( v41 != 63 )
        LogPrintProcError(v41);
      goto LABEL_96;
    }
    if ( v35 )
    {
      if ( v35 == 3020 )
      {
LABEL_96:
        CheckGdiQuotaCondition();
        goto LABEL_68;
      }
      *(_DWORD *)(v4 + 436) = v35;
      LogPrintProcError(v35);
      if ( v40 )
      {
        v94 = *(_DWORD *)(v4 + 436);
        v95 = 4;
        v96 = 0;
        v91 = v32;
        v92 = 4;
        v93 = 0;
        SplLogType::SplLogType((SplLogType *)v99, *(const unsigned __int16 **)(v4 + 440));
        v42 = SplLogType::SplLogType((SplLogType *)v98, v100);
        v45 = &v94;
        v46 = &v91;
        goto LABEL_95;
      }
    }
    else
    {
      *(_DWORD *)(v4 + 436) = 1;
      LogPrintProcError(0);
      if ( v40 )
      {
        v91 = *(_DWORD *)(v4 + 436);
        v92 = 4;
        v93 = 0;
        v94 = v32;
        v95 = 4;
        v96 = 0;
        SplLogType::SplLogType((SplLogType *)v98, *(const unsigned __int16 **)(v4 + 440));
        v42 = SplLogType::SplLogType((SplLogType *)v99, v100);
        v45 = &v91;
        v46 = &v94;
LABEL_95:
        SplLogEvent2(&SPOOLER_CSR_FAILED_DONT_REVERT_TO_SSR, v42, v43, v46, v45, v44);
        goto LABEL_96;
      }
    }
    if ( *(_BYTE *)(v4 + 537) )
    {
      LODWORD(pcbNeeded) = *(_DWORD *)(v4 + 32);
      LocalSpoolerTelemetry::WriteDbgTraceError(
        "PrintDocumentThruPrintProcessor",
        L"CSR job has already been retried, printer='%ws', JobID=%u, datatype='%ws', status=%u, significant error=%d",
        *(_QWORD *)(v4 + 440),
        *(unsigned int *)(v4 + 40),
        *(_QWORD *)(v4 + 128),
        pcbNeeded,
        *(_DWORD *)(v4 + 436));
    }
    else
    {
      *(_QWORD *)v88 = 0;
      pData.cbSize = 8;
      pData.dwFlags = 4;
      pType[0] = 1;
      v47 = *(const unsigned __int16 **)(v4 + 440);
      if ( v47 )
      {
        if ( !v84[0] )
        {
          v94 = v35;
          v95 = 4;
          v96 = 0;
          v91 = v32;
          v92 = 4;
          v93 = 0;
          SplLogType::SplLogType((SplLogType *)v99, v47);
          v48 = SplLogType::SplLogType((SplLogType *)v98, v100);
          SplLogEvent2(&SPOOLER_CSR_FAILED_REVERT_TO_SSR, v48, v49, &v91, &v94, v50);
          *(_QWORD *)v84 = *(_QWORD *)(v4 + 256);
          NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, v84, 8u);
          v35 = 0;
          if ( OpenPrinter2W(*(LPCWSTR *)(v4 + 440), (LPHANDLE)v88, 0, &pData) )
          {
            if ( !SetPrinterDataW(*(HANDLE *)v88, (LPWSTR)L"EmfDespoolingSetting", 4u, (LPBYTE)pType, 4u) )
            {
              INIJOB::ClearJobStatusFlags((INIJOB *)v4, 0x20u);
              INIJOB::SetJobStatusFlags((INIJOB *)v4, 0x10000u);
              EnterSplSem(0);
              *(_QWORD *)(v4 + 424) = *(_QWORD *)(v4 + 128);
              v51 = L"XPS_PASS_RAW";
              if ( !v32 )
                v51 = L"RAW";
              v52 = AllocSplStr(v51);
              *(_QWORD *)(v4 + 128) = v52;
              if ( v52 )
              {
                *(_BYTE *)(v4 + 537) = 1;
                LODWORD(pcbNeededa) = *(_DWORD *)(v4 + 32);
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "PrintDocumentThruPrintProcessor",
                  L"Retrying CSR job in SSR mode, printer='%ws', JobID=%u, datatype='%ws', status=%u, significant error=%d",
                  *(_QWORD *)(v4 + 440),
                  *(unsigned int *)(v4 + 40),
                  v52,
                  pcbNeededa,
                  *(_DWORD *)(v4 + 436));
                RestartJob((INIJOB *)v4);
              }
              LeaveSplSem(v52);
            }
            ClosePrinter(*(HANDLE *)v88);
          }
        }
      }
    }
    goto LABEL_96;
  }
  v5 = 0;
LABEL_102:
  EnterSplSem(0);
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl);
  INIJOB::ClearJobStatusFlags((INIJOB *)v4, 1u);
  LeaveSplSem(v54);
  if ( (*(_DWORD *)(v4 + 32) & 0x10000000) == 0 )
  {
    EnterCriticalSection(v34 + 2);
    INIJOB::SetJobStatusFlags((INIJOB *)v4, 0x10000000u);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl) )
    {
      if ( !sandbox::PrintProcessorAdapter::ClosePrintProcessor(v55, *(void **)(v4 + 120)) )
      {
        HIDWORD(TokenInformation) = GetLastError();
        v56 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "PrintDocumentThruPrintProcessor",
          L"Failed to close print proc.  hProc %p.  Error %d",
          *(_QWORD *)(v4 + 120),
          v56);
      }
      *(_QWORD *)(v4 + 120) = 0;
    }
    else
    {
      if ( !sandbox::PrintProcessorAdapter::ClosePrintProcessor(v55, *(void **)(v29 + 40)) )
      {
        HIDWORD(TokenInformation) = GetLastError();
        v57 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "PrintDocumentThruPrintProcessor",
          L"Failed to close print proc.  hProc %p.  Error %d",
          *(_QWORD *)(v29 + 40),
          v57);
      }
      *(_QWORD *)(v29 + 40) = 0;
    }
    INIJOB::ClearJobStatusFlags((INIJOB *)v4, 0x10000000u);
    LeaveCriticalSection(v34 + 2);
    v58 = *(_QWORD *)(v4 + 104);
    if ( v58 )
    {
      v59 = (const struct _EVENT_DESCRIPTOR *)*(unsigned int *)(v58 + 72);
      v60 = ((unsigned __int16)v59 & 0x4000) != 0 ? *(_WORD *)(v58 + 98) : 0;
      v61 = ((unsigned __int16)v59 & 0x100) != 0 ? *(_WORD *)(v58 + 86) : 0;
      v62 = ((unsigned __int16)v59 & 0x400) != 0 ? *(_WORD *)(v58 + 90) : 0;
      if ( ((unsigned __int16)v59 & 0x2000) != 0 )
      {
        v63 = *(_WORD *)(v58 + 90);
        v64 = *(_WORD *)(v58 + 96);
      }
      else
      {
        v63 = 0;
        v64 = 0;
      }
      v65 = ((unsigned __int16)v59 & 0x800) != 0 ? *(_WORD *)(v58 + 92) : 0;
      v66 = ((unsigned int)v59 & 0x800000) != 0 ? *(_DWORD *)(v58 + 188) : 0;
      SplLogRenderJobDiagEvent(v59, *(_DWORD *)(v4 + 40), *(_DWORD *)(v4 + 176), v66, v65, v63, v64, v62, v61, v60);
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v4 + 88) + 280LL) + 168LL) & 0x4000000) != 0 )
        ProcessBranchOfficeLogEntry(2, v4, 0);
    }
  }
  v7 = (int)TokenInformation;
LABEL_132:
  v67 = 0;
  v68 = 0;
  phPrinter = 0;
  v84[0] = 0;
  if ( v7 || pData.cbSize )
  {
    if ( HIDWORD(TokenInformation) != 63 )
    {
      EnterSplSem(0);
      v67 = *(_QWORD *)(v4 + 88);
      if ( v67 && SafeIncrementReference((unsigned int *)(v67 + 16)) > *(_DWORD *)(v67 + 248) )
        *(_DWORD *)(v67 + 248) = *(_DWORD *)(v67 + 16);
      ++*(_DWORD *)(v67 + 276);
      v69 = *(unsigned int *)(v67 + 216);
      if ( (unsigned int)v69 > 0xA )
      {
        v69 = (unsigned int)(v69 - *(_DWORD *)(*(_QWORD *)(v4 + 88) + 276LL));
        if ( (unsigned int)v69 < 0xA )
        {
          v70 = *(_QWORD *)(v67 + 88);
          if ( (*(_BYTE *)(v70 + 200) & 4) == 0 )
          {
            v71 = *(_QWORD *)(*(_QWORD *)(v67 + 280) + 368LL);
            v69 = v71 + 128;
            if ( *(_QWORD *)(v71 + 204) == 0x100000001LL )
            {
              sandbox::SandboxManagerUtil::AddDriverToSandboxExclusionList(
                (sandbox::SandboxManagerUtil *)v69,
                *(const unsigned __int16 **)(v70 + 24),
                (unsigned __int16 **)&phPrinter,
                v84);
              v68 = phPrinter;
              v5 = v84[0];
            }
          }
        }
      }
      LeaveSplSem(v69);
    }
    DiscardJobFromPortThread((INIJOB *)v4);
  }
  v72 = TokenHandle;
  if ( TokenHandle )
  {
    if ( !SetThreadToken(0, TokenHandle) )
    {
      v73 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "PrintDocumentThruPrintProcessor",
        L"PrintDocumentThruPrintProcessor: Cannot reset the thread token. Error %d",
        v73);
    }
    CloseHandle(v72);
    *(_QWORD *)(v4 + 568) = 0;
  }
  if ( v87 )
  {
    if ( !RevertToSelf() )
    {
      v74 = GetLastError();
      ForceProcessShutdown(0x68u, v74);
    }
  }
  else
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
  if ( v67 )
  {
    EnterSplSem(0);
    if ( v68
      && !(unsigned int)SetPrinterDataServer(*(_QWORD *)(v67 + 280), L"PrintDriverIsolationGroups", 1, v68, 2 * v5) )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "PrintDocumentThruPrintProcessor",
        L"There were %u print job failures out of %u jobs sent to printer %ws using driver %ws. The driver isolation setti"
         "ng was changed to in-proc. New isolation list %ws",
        *(unsigned int *)(v67 + 276),
        *(unsigned int *)(v67 + 216),
        *(_QWORD *)(v67 + 24),
        *(_QWORD *)(*(_QWORD *)(v67 + 88) + 24LL),
        v68);
      SplLogType::SplLogType((SplLogType *)v99, *(const unsigned __int16 **)(*(_QWORD *)(v67 + 88) + 24LL));
      v75 = SplLogType::SplLogType((SplLogType *)v98, *(const unsigned __int16 **)(v67 + 24));
      v94 = *(_DWORD *)(v67 + 216);
      v95 = 4;
      v96 = 0;
      v91 = *(_DWORD *)(v67 + 276);
      v92 = 4;
      v93 = 0;
      SplLogEvent2(&FORCED_DRIVER_ISOLATION_DISABLED, (struct SplLogType *)&v91, &v94, v75, v76, 0);
    }
    v77 = (unsigned int *)(v67 + 16);
    if ( *(_DWORD *)(v67 + 16) )
      SafeDecrementReference(v77);
    LeaveSplSem(v77);
  }
  NCoreLibrary::TGenericSP<unsigned short,NCoreLibrary::TAutoPtrArray<unsigned short>,unsigned short *,0,unsigned short const *>::Reset(&phPrinter);
}

```

## disassembly

```asm
0x180081080  mov     [rsp-8+arg_10], rbx
0x180081085  push    rbp
0x180081086  push    rsi
0x180081087  push    rdi
0x180081088  push    r12
0x18008108a  push    r13
0x18008108c  push    r14
0x18008108e  push    r15
0x180081090  lea     rbp, [rsp-870h]
0x180081098  sub     rsp, 970h
0x18008109f  mov     rax, cs:__security_cookie
0x1800810a6  xor     rax, rsp
0x1800810a9  mov     [rbp+8A0h+var_40], rax
0x1800810b0  mov     r13, rdx
0x1800810b3  mov     rbx, rcx
0x1800810b6  mov     qword ptr [rsp+9A0h+pType], rcx
0x1800810bb  mov     rdi, [rcx+48h]
0x1800810bf  xor     edx, edx; Val
0x1800810c1  mov     r8d, 63Eh; Size
0x1800810c7  lea     rcx, [rbp+8A0h+var_890]; void *
0x1800810cb  call    memset_0
0x1800810d0  xor     r12d, r12d
0x1800810d3  mov     dword ptr [rsp+9A0h+pData], r12d
0x1800810d8  mov     [rsp+9A0h+var_938], r12d
0x1800810dd  mov     [rsp+9A0h+TokenInformation], r12d
0x1800810e2  mov     [rbp+8A0h+var_920], r12d
0x1800810e6  mov     [rbp+8A0h+TokenHandle], r12
0x1800810ea  mov     [rsp+9A0h+var_94C], r12d
0x1800810ef  mov     rcx, rdi; this
0x1800810f2  call    ?GetIniPrintProc@INIJOB@@QEAAPEAVINIPRINTPROC@@XZ; INIJOB::GetIniPrintProc(void)
0x1800810f7  mov     r14, rax
0x1800810fa  mov     [rbp+8A0h+var_8D0], rax
0x1800810fe  test    dword ptr [rdi+20h], 40000h
0x180081105  jz      short loc_180081154
0x180081107  cmp     [rdi+218h], r12b
0x18008110e  jnz     short loc_180081154
0x180081110  mov     rdx, [rdi+100h]; void *
0x180081117  mov     rcx, [rbx+18h]; lpFileName
0x18008111b  call    ?CanUserAccessTargetFile@@YA_NPEBGPEAX@Z; CanUserAccessTargetFile(ushort const *,void *)
0x180081120  test    al, al
0x180081122  jnz     short loc_180081154
0x180081124  lea     rdx, aUserDoesNotHav; "User does not have access to the target"...
0x18008112b  lea     r15, aPrintdocumentt_1; "PrintDocumentThruPrintProcessor"
0x180081132  mov     rcx, r15; char *
0x180081135  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18008113a  mov     rdx, rdi
0x18008113d  lea     ecx, [r12+5]; dwMessageId
0x180081142  call    LogPrintProcError
0x180081147  lea     esi, [r12+1]
0x18008114c  mov     r13d, esi
0x18008114f  jmp     loc_180081C30
0x180081154  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x180081159  lea     r15, aPrintdocumentt_1; "PrintDocumentThruPrintProcessor"
0x180081160  mov     esi, 1
0x180081165  test    eax, eax
0x180081167  jz      loc_180081201
0x18008116d  lea     rdx, aWindowsProtect; "Windows Protected Print is enabled. Imp"...
0x180081174  mov     rcx, r15; char *
0x180081177  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18008117c  mov     rax, [rdi+100h]
0x180081183  mov     [rsp+9A0h+ThreadInformation], rax
0x180081188  mov     r9d, 8; ThreadInformationLength
0x18008118e  lea     r8, [rsp+9A0h+ThreadInformation]; ThreadInformation
0x180081193  lea     edx, [r9-3]; ThreadInformationClass
0x180081197  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x18008119e  call    cs:__imp_NtSetInformationThread
0x1800811a4  lea     rdx, [rsp+9A0h+TokenInformation]; void **
0x1800811a9  lea     rcx, [rbp+8A0h+TokenHandle]; this
0x1800811ad  call    ?ElevateIntegrityLevelIfLow@NSecurityLibrary@@YAHPEAPEAXPEAH@Z; NSecurityLibrary::ElevateIntegrityLevelIfLow(void * *,int *)
0x1800811b2  mov     r14d, [rsp+9A0h+TokenInformation]
0x1800811b7  test    eax, eax
0x1800811b9  jnz     loc_1800812B9
0x1800811bf  test    r14d, r14d
0x1800811c2  jz      loc_180081339
0x1800811c8  call    ?IsWindowsProtectedPrintEnabled@@YAHXZ; IsWindowsProtectedPrintEnabled(void)
0x1800811cd  test    eax, eax
0x1800811cf  jz      loc_180081295
0x1800811d5  lea     rcx, [rbp+8A0h+TokenHandle]; void **
0x1800811d9  call    ?GetPipelineLaunchTokenForLowILPrinting@@YAJPEAPEAX@Z; GetPipelineLaunchTokenForLowILPrinting(void * *)
0x1800811de  test    ax, ax
0x1800811e1  jnz     loc_1800812B9
0x1800811e7  mov     [rdi+235h], sil
0x1800811ee  mov     rbx, [rbp+8A0h+TokenHandle]
0x1800811f2  mov     [rdi+238h], rbx
0x1800811f9  mov     r12d, esi
0x1800811fc  jmp     loc_1800812BD
0x180081201  mov     rdx, r14
0x180081204  mov     rcx, [rdi+60h]
0x180081208  call    IsSpecialDriver
0x18008120d  test    eax, eax
0x18008120f  jnz     short loc_18008124E
0x180081211  lea     rdx, [rsp+9A0h+var_938]; int *
0x180081216  mov     rcx, [rdi+100h]; TokenHandle
0x18008121d  call    ?PrincipalIsRemoteGuest@@YAKPEAXPEAH@Z; PrincipalIsRemoteGuest(void *,int *)
0x180081222  mov     ebx, eax
0x180081224  test    eax, eax
0x180081226  jnz     short loc_180081274
0x180081228  cmp     [rsp+9A0h+var_938], r12d
0x18008122d  jnz     short loc_18008124E
0x18008122f  mov     rcx, [rdi+100h]
0x180081236  lea     rax, [rcx-1]
0x18008123a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18008123e  ja      short loc_18008124E
0x180081240  mov     [rbp+8A0h+var_920], r12d
0x180081244  mov     [rsp+9A0h+ThreadInformation], rcx
0x180081249  jmp     loc_180081188
0x18008124e  mov     [rbp+8A0h+var_920], esi
0x180081251  mov     ecx, 2; ImpersonationLevel
0x180081256  call    cs:__imp_ImpersonateSelf
0x18008125c  test    eax, eax
0x18008125e  jnz     loc_1800811A4
0x180081264  call    cs:__imp_GetLastError
0x18008126a  mov     ebx, eax
0x18008126c  test    eax, eax
0x18008126e  jz      loc_1800811A4
0x180081274  mov     r8d, ebx
0x180081277  lea     rdx, aSetcurrentsidO; "SetCurrentSid or ImpersonateSelf failed"...
0x18008127e  mov     rcx, r15; char *
0x180081281  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180081286  mov     rdx, rdi
0x180081289  mov     ecx, ebx; dwMessageId
0x18008128b  call    LogPrintProcError
0x180081290  jmp     loc_18008114C
0x180081295  call    cs:__imp_GetLastError
0x18008129b  mov     ebx, eax
0x18008129d  mov     r8d, eax
0x1800812a0  lea     rdx, aElevateintegri; "ElevateIntegrityLevelIfLow failed! Erro"...
0x1800812a7  mov     rcx, r15; char *
0x1800812aa  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800812af  mov     rdx, rdi
0x1800812b2  mov     ecx, ebx; dwMessageId
0x1800812b4  call    LogPrintProcError
0x1800812b9  mov     rbx, [rbp+8A0h+TokenHandle]
0x1800812bd  test    r14d, r14d
0x1800812c0  jz      short loc_180081336
0x1800812c2  test    r12d, r12d
0x1800812c5  jnz     short loc_180081336
0x1800812c7  xor     r12d, r12d
0x1800812ca  mov     [rsp+9A0h+TokenInformation], r12d
0x1800812cf  mov     [rbp+8A0h+var_918], r12d
0x1800812d3  lea     rax, [rbp+8A0h+var_918]
0x1800812d7  mov     [rsp+9A0h+ReturnLength], rax; ReturnLength
0x1800812dc  lea     r9d, [r12+4]; TokenInformationLength
0x1800812e1  lea     r8, [rsp+9A0h+TokenInformation]; TokenInformation
0x1800812e6  lea     edx, [r12+1Dh]; TokenInformationClass
0x1800812eb  mov     rcx, rbx; TokenHandle
0x1800812ee  call    cs:__imp_GetTokenInformation
0x1800812f4  test    eax, eax
0x1800812f6  jnz     short loc_180081315
0x1800812f8  call    cs:__imp_GetLastError
0x1800812fe  mov     r8d, eax
0x180081301  lea     rdx, aFailedToGetThe_2; "Failed to get the appContainer info fro"...
0x180081308  mov     rcx, r15; char *
0x18008130b  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180081310  mov     eax, r12d
0x180081313  jmp     short loc_180081319
0x180081315  mov     eax, [rsp+9A0h+TokenInformation]
0x180081319  test    eax, eax
0x18008131b  jz      short loc_180081326
0x18008131d  cmp     cs:g_bBypassSecurityCheckForAppContainerPrinting, r12d
0x180081324  jnz     short loc_180081339
0x180081326  mov     [rdi+235h], sil
0x18008132d  mov     [rdi+238h], rbx
0x180081334  jmp     short loc_180081339
0x180081336  xor     r12d, r12d
0x180081339  movsd   xmm0, cs:NVJobStatus
0x180081341  movsd   [rsp+9A0h+ThreadInformation], xmm0
0x180081347  mov     eax, cs:dword_18013E040
0x18008134d  mov     [rsp+9A0h+var_940], eax
0x180081351  mov     rdx, [rdi+58h]
0x180081355  mov     rax, [rdx+118h]
0x18008135c  mov     r10, [rax+18h]
0x180081360  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180081364  mov     rbx, rcx
0x180081367  inc     rbx
0x18008136a  cmp     [r10+rbx*2], r12w
0x18008136f  jnz     short loc_180081367
0x180081371  mov     r8d, ebx
0x180081374  mov     r9, qword ptr [rsp+9A0h+pType]
0x180081379  mov     r9, [r9+18h]
0x18008137d  mov     rax, rcx
0x180081380  inc     rax
0x180081383  cmp     [r9+rax*2], r12w
0x180081388  jnz     short loc_180081380
0x18008138a  add     rax, 14h
0x18008138e  add     rax, r8
0x180081391  mov     r14d, 31Fh
0x180081397  cmp     rax, r14
0x18008139a  ja      loc_18008114C
0x1800813a0  mov     rax, [rdx+18h]
0x1800813a4  inc     rcx
0x1800813a7  cmp     [rax+rcx*2], r12w
0x1800813ac  jnz     short loc_1800813A4
0x1800813ae  lea     rax, [rcx+14h]
0x1800813b2  add     rax, r8
0x1800813b5  cmp     rax, r14
0x1800813b8  ja      loc_18008114C
0x1800813be  mov     [rsp+9A0h+ReturnLength], r12
0x1800813c3  lea     r9, SubBlock; "\\"
0x1800813ca  mov     r8, r10
0x1800813cd  mov     edx, r14d
0x1800813d0  lea     rcx, [rbp+8A0h+var_890]
0x1800813d4  call    StrNCatBuff
0x1800813d9  lea     eax, [rbx+1]
0x1800813dc  mov     ecx, eax
0x1800813de  lea     r12, [rbp+8A0h+var_890]
0x1800813e2  lea     r12, [r12+rax*2]
0x1800813e6  mov     rdx, r14
0x1800813e9  sub     rdx, rcx; unsigned __int64
0x1800813ec  mov     rax, qword ptr [rsp+9A0h+pType]
0x1800813f1  mov     r9, [rax+18h]
0x1800813f5  lea     r8, aWsPort; "%ws, Port"
0x1800813fc  mov     rcx, r12; unsigned __int16 *
0x1800813ff  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180081404  xor     ebx, ebx
0x180081406  mov     rcx, [r13+8]; unsigned __int16 *
0x18008140a  call    ?IsXPS2GDI@@YA_NPEBG@Z; IsXPS2GDI(ushort const *)
0x18008140f  test    al, al
0x180081411  jz      short loc_180081422
0x180081413  cmp     cs:g_hWinSta0, rbx
0x18008141a  jz      short loc_180081422
0x18008141c  mov     ebx, [rdi+1A0h]
0x180081422  mov     rcx, [r13+8]; unsigned __int16 *
0x180081426  call    ?IsXPS2GDI@@YA_NPEBG@Z; IsXPS2GDI(ushort const *)
0x18008142b  xor     ecx, ecx
0x18008142d  test    al, al
0x18008142f  jz      short loc_18008146C
0x180081431  mov     r9d, [rdi+230h]
0x180081438  test    r9d, r9d
0x18008143b  jz      short loc_18008146C
0x18008143d  cmp     [r13+10h], rcx
0x180081441  jnz     short loc_18008146C
0x180081443  lea     r8, aD; "%d"
0x18008144a  mov     edx, 104h; unsigned __int64
0x18008144f  lea     rcx, [rbp+8A0h+var_250]; unsigned __int16 *
0x180081456  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18008145b  lea     rcx, [rbp+8A0h+var_250]
0x180081462  call    cs:__imp_AllocSplStr
0x180081468  mov     [r13+10h], rax
0x18008146c  mov     rax, [r13+30h]
0x180081470  mov     [rsp+9A0h+pcbNeeded], rax
0x180081475  mov     rax, [r13+8]
0x180081479  mov     [rsp+9A0h+ReturnLength], rax
0x18008147e  mov     rax, [rbp+8A0h+var_8D0]
0x180081482  mov     r9, [rax+18h]
0x180081486  mov     r8d, [rdi+28h]
0x18008148a  lea     rdx, aPrintingJobUTh; "Printing job %u through print processor"...
0x180081491  mov     rcx, r15; char *
0x180081494  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180081499  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race> `wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl(void)'::`2'::impl
0x1800814a0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(void)
0x1800814a5  mov     rcx, [rbp+8A0h+var_8D0]
0x1800814a9  mov     rcx, [rcx+48h]; this
0x1800814ad  mov     r9d, ebx; unsigned int
0x1800814b0  mov     r8, r13; struct PRINTPROCESSOROPENDATA2 *
0x1800814b3  lea     rdx, [rbp+8A0h+var_890]; unsigned __int16 *
0x1800814b7  test    al, al
0x1800814b9  jz      short loc_180081500
0x1800814bb  call    ?OpenPrintProcessor@PrintProcessorAdapter@sandbox@@QEAAPEAXPEBGPEAUPRINTPROCESSOROPENDATA2@@K@Z; sandbox::PrintProcessorAdapter::OpenPrintProcessor(ushort const *,PRINTPROCESSOROPENDATA2 *,ulong)
0x1800814c0  mov     [rdi+78h], rax
0x1800814c4  test    rax, rax
0x1800814c7  jnz     short loc_180081515
0x1800814c9  call    cs:__imp_GetLastError
0x1800814cf  mov     ebx, eax
0x1800814d1  mov     [rsp+9A0h+var_94C], eax
0x1800814d5  mov     r9d, eax
0x1800814d8  lea     r8, [rbp+8A0h+var_890]
0x1800814dc  lea     rdx, aFailedToOpenPr_2; "Failed to open print processor %ws. Err"...
0x1800814e3  mov     rcx, r15; char *
0x1800814e6  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800814eb  mov     rdx, rdi
0x1800814ee  mov     ecx, ebx; dwMessageId
0x1800814f0  call    LogPrintProcError
0x1800814f5  mov     r13d, esi
0x1800814f8  xor     r12d, r12d
0x1800814fb  jmp     loc_180081C30
0x180081500  call    ?OpenPrintProcessor@PrintProcessorAdapter@sandbox@@QEAAPEAXPEBGPEAUPRINTPROCESSOROPENDATA2@@K@Z; sandbox::PrintProcessorAdapter::OpenPrintProcessor(ushort const *,PRINTPROCESSOROPENDATA2 *,ulong)
0x180081505  mov     r13, qword ptr [rsp+9A0h+pType]
0x18008150a  mov     [r13+28h], rax
0x18008150e  test    rax, rax
0x180081511  jnz     short loc_18008151A
0x180081513  jmp     short loc_1800814C9
0x180081515  mov     r13, qword ptr [rsp+9A0h+pType]
0x18008151a  mov     [rsp+9A0h+TokenInformation], 0
0x180081522  mov     rax, [rdi+58h]
0x180081526  mov     rcx, [rax+118h]
0x18008152d  test    dword ptr [rcx+0A8h], 4000000h
0x180081537  lea     rbx, [rbp+8A0h+var_890]
0x18008153b  cmovnz  rbx, r12
0x18008153f  xor     ecx, ecx
0x180081541  call    EnterSplSem
0x180081546  mov     edx, esi; unsigned int
0x180081548  mov     rcx, rdi; this
0x18008154b  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180081550  call    cs:__imp_GetTickCount
0x180081556  mov     [rdi+0A0h], eax
0x18008155c  or      dword ptr [rsp+9A0h+ThreadInformation+4], 4
0x180081561  mov     rcx, [rdi+58h]
0x180081565  mov     rax, [rcx+118h]
0x18008156c  mov     [rsp+9A0h+ReturnLength], rax
  ... truncated ...
```
