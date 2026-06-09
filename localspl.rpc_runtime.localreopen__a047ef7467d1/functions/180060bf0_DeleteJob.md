# DeleteJob

- ea: `0x180060bf0`
- end: `0x1800617b5`
- name: `DeleteJob`
- size: `3013`
- prototype: `__int64 __fastcall(INIJOB *this)`
- caller_count: `7`
- callee_count: `36`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x18002a550`
- `0x1800559a0`
- `0x18005d178`
- `0x1800632bc`
- `0x180065080`
- `0x180067628`
- `0x180088860`

## callees

- `0x180008520`
- `0x180008560`
- `0x1800086e0`
- `0x180008730`
- `0x180008cb8`
- `0x180009630`
- `0x18000d0d8`
- `0x18001fb10`
- `0x1800227a4`
- `0x1800237b0`
- `0x1800237d8`
- `0x180023804`
- `0x18002abf8`
- `0x18002c8d8`
- `0x18002e530`
- `0x180032fd4`
- `0x180034e08`
- `0x180038d84`
- `0x180038fec`
- `0x18003e984`
- `0x18003ea2c`
- `0x180042b3c`
- `0x1800435b0`
- `0x180043aa4`
- `0x180043d30`
- `0x180046650`
- `0x180054638`
- `0x180060204`
- `0x180060bf0`
- `0x1800619a8`
- `0x180074cf0`
- `0x1800750e4`
- `0x1800cca90`
- `0x1800ccbd8`
- `0x1800d7464`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800614c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180061582`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800614c4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180061582`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e7f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180060e7f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f1f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180060f1f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060d21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061773`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180060d21`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180061773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006137a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006169d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006137a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006169d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800610e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800610e3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006167e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18006167e`
- `SPOOLSS!DllFreeSplStr` at `0x180060c9d`
- `SPOOLSS!DllFreeSplStr` at `0x180060c9d`
- `SPOOLSS!DllFreeSplMem` at `0x18006154c`
- `SPOOLSS!DllFreeSplMem` at `0x180061555`
- `SPOOLSS!DllFreeSplMem` at `0x18006154c`
- `SPOOLSS!DllFreeSplMem` at `0x180061555`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006121d`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006121d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180061440`
- `SPOOLSS!ImpersonatePrinterClient` at `0x180061440`

## string_xrefs

- `0x180060eb9`: `DeleteJob`
- `0x180060ee6`: `DeleteJob`
- `0x18006127f`: `DeleteJob`
- `0x18006131d`: `DeleteJob`
- `0x180061394`: `DeleteJob`
- `0x180061431`: `DeleteJob`
- `0x180061608`: `DeleteJob`
- `0x1800616b3`: `DeleteJob`
- `0x180061784`: `DeleteJob`
- `0x180061276`: `Failed to delete shadow file %ws.  Error %d`
- `0x1800616aa`: `Failed to delete shadow file %ws.  Error %d`
- `0x18006138d`: `Failed to delete spool file %ws.  Error %d`

## pseudocode

```c
__int64 __fastcall DeleteJob(INIJOB *this, int a2)
{
  __int64 v2; // r13
  INIJOB *v3; // rdi
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 *v6; // rbx
  void *v7; // rcx
  int v8; // ecx
  __int64 IniKey; // rbx
  __int64 v10; // rcx
  __int64 v11; // rsi
  char v12; // r12
  struct INIPRINTPROC *IniPrintProc; // rsi
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // rcx
  sandbox::PrintProcessorAdapter *v17; // rcx
  void *v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // r14d
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rbx
  void *v26; // rax
  int FileCreationInfo; // eax
  unsigned int v28; // ecx
  _QWORD *v29; // rcx
  __int64 v30; // rax
  unsigned __int64 v31; // r15
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rbx
  int v35; // ebx
  int v36; // esi
  unsigned int v37; // edx
  __int64 v38; // rcx
  int v39; // edi
  HANDLE v40; // rax
  bool v41; // cf
  char *v42; // rsi
  void *v43; // r14
  __int64 v44; // rbx
  struct SplLogType *v45; // rax
  __int64 v46; // r10
  __int64 v47; // rbx
  struct SplLogType *v48; // rax
  __int64 Job; // rax
  __int64 v50; // rcx
  unsigned int v51; // r9d
  __int64 i; // rdi
  _QWORD **v53; // rdx
  _QWORD *v54; // rcx
  _QWORD *v55; // rbx
  __int64 v56; // rcx
  int v57; // eax
  const struct _EVENT_DESCRIPTOR *v58; // rcx
  unsigned int v59; // ebx
  void *v60; // rcx
  __int64 v61; // rcx
  BOOL v62; // ebx
  __int64 LastError; // rbx
  struct SplLogType *v64; // rax
  int v66; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v67; // [rsp+44h] [rbp-BCh] BYREF
  int v68; // [rsp+48h] [rbp-B8h]
  void *v69; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-A8h]
  int v71; // [rsp+60h] [rbp-A0h]
  int v72; // [rsp+64h] [rbp-9Ch]
  unsigned int v73; // [rsp+68h] [rbp-98h]
  int v74; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v75; // [rsp+70h] [rbp-90h]
  const wchar_t *v76; // [rsp+78h] [rbp-88h] BYREF
  __int64 v77; // [rsp+80h] [rbp-80h]
  int v78; // [rsp+88h] [rbp-78h]
  int v79; // [rsp+90h] [rbp-70h] BYREF
  __int64 v80; // [rsp+98h] [rbp-68h]
  int v81; // [rsp+A0h] [rbp-60h]
  int v82; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v83; // [rsp+B0h] [rbp-50h]
  int v84; // [rsp+B8h] [rbp-48h]
  const wchar_t *v85; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v86; // [rsp+C8h] [rbp-38h]
  int v87; // [rsp+D0h] [rbp-30h]
  _BYTE v88[24]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR FileName[264]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v90[264]; // [rsp+300h] [rbp+200h] BYREF

  v2 = *((_QWORD *)this + 11);
  v72 = a2;
  v3 = this;
  v74 = 0;
  v69 = 0;
  v4 = *(_QWORD *)(v2 + 280);
  v70 = v4;
  v71 = 0;
  v67 = 0;
  v68 = 0;
  if ( v2 && SafeIncrementReference((unsigned int *)(v2 + 16)) > *(_DWORD *)(v2 + 248) )
    *(_DWORD *)(v2 + 248) = *(_DWORD *)(v2 + 16);
  while ( 1 )
  {
    v66 = *((_DWORD *)v3 + 8);
    if ( (v66 & 0x800) != 0 )
      break;
    v5 = *((_QWORD *)v3 + 24);
    v73 = *((_DWORD *)v3 + 76);
    if ( v5 )
    {
      DllFreeSplStr(v5);
      *((_QWORD *)v3 + 24) = 0;
      v6 = NVJobStatusAndString;
    }
    else
    {
      v6 = &NVJobStatus;
    }
    SetPortErrorEvent(*((_QWORD *)v3 + 31));
    if ( *((_DWORD *)v3 + 9) )
    {
      _m_prefetchw((char *)v3 + 36);
      INIJOB::CheckJobStatusChange(
        v3,
        _InterlockedAnd((volatile signed __int32 *)v3 + 9, 0xFFFFFFFB),
        *((_DWORD *)v3 + 9) & 0xFFFFFFFB);
    }
    if ( (*((_BYTE *)v3 + 32) & 0x20) == 0 )
    {
      INIJOB::SetJobStatusFlags(v3, 0x20u);
      SeekPrinterSetEvent(v3, 0, 1);
      v7 = (void *)*((_QWORD *)v3 + 29);
      if ( v7 )
        SetEvent(v7);
      SetPrinterChange(*((_QWORD *)v3 + 11), (_DWORD)v3, (_DWORD)v6, 512, v4);
      v8 = *((_DWORD *)v3 + 8);
      if ( (v8 & 0x401) == 1 || (v8 & 0x4200) == 0x4200 )
      {
        IniKey = *((_QWORD *)v3 + 31);
        if ( IniKey || (IniKey = FindIniKey(*(_QWORD *)(v4 + 64), *((_QWORD *)v3 + 68), v4 + 33160)) != 0 )
        {
          SafeIncrementReference((unsigned int *)(IniKey + 16));
          SafeIncrementReference((unsigned int *)v3 + 6);
          v11 = *(_QWORD *)(IniKey + 96);
          v12 = 0;
          if ( v11 && *(_QWORD *)(v11 + 416) && *(_DWORD *)(*(_QWORD *)(v2 + 88) + 236LL) > 3u )
          {
            v12 = 1;
            LeaveSplSem(v10);
            (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(v11 + 416))(
              *(_QWORD *)(v11 + 56),
              *(_QWORD *)(IniKey + 24),
              *((unsigned int *)v3 + 10));
            EnterSplSem(0);
          }
          SafeDecrementReference((unsigned int *)v3 + 6);
          if ( *(_DWORD *)(IniKey + 16) )
            SafeDecrementReference((unsigned int *)(IniKey + 16));
          if ( v12 )
            break;
        }
      }
      if ( (*((_BYTE *)v3 + 32) & 1) != 0 )
      {
        IniPrintProc = INIJOB::GetIniPrintProc(v3);
        if ( IniPrintProc )
        {
          SafeIncrementReference((unsigned int *)v3 + 6);
          v14 = *((_QWORD *)v3 + 31);
          if ( v14 && (*(_BYTE *)(v14 + 216) & 1) == 0 )
          {
            SafeIncrementReference((unsigned int *)(v14 + 16));
            SafeIncrementReference((unsigned int *)IniPrintProc + 4);
            ++*((_DWORD *)IniPrintProc + 32);
            LeaveSplSem(v15);
            EnterCriticalSection((LPCRITICAL_SECTION)IniPrintProc + 2);
            EnterSplSem(0);
            *(_DWORD *)(v14 + 216) |= 1u;
            if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl'::`2'::impl) )
            {
              if ( *((_QWORD *)v3 + 15) )
              {
                LocalSpoolerTelemetry::WriteDbgTraceInfo(
                  "DeleteJob",
                  L"Sending JOB_CONTROL_CANCEL to print processor '%ws' for job %u",
                  *((_QWORD *)IniPrintProc + 3),
                  *((unsigned int *)v3 + 10));
                LeaveSplSem(v16);
                v18 = (void *)*((_QWORD *)v3 + 15);
                goto LABEL_33;
              }
            }
            else if ( *(_QWORD *)(v14 + 40) )
            {
              LocalSpoolerTelemetry::WriteDbgTraceInfo(
                "DeleteJob",
                L"Sending JOB_CONTROL_CANCEL to print processor '%ws' for job %u",
                *((_QWORD *)IniPrintProc + 3),
                *((unsigned int *)v3 + 10));
              LeaveSplSem(v19);
              v18 = *(void **)(v14 + 40);
LABEL_33:
              sandbox::PrintProcessorAdapter::ControlPrintProcessor(v17, v18, 3u);
              EnterSplSem(0);
            }
            *(_DWORD *)(v14 + 216) &= ~1u;
            *(_DWORD *)(v14 + 216) |= 6u;
            LeaveCriticalSection((LPCRITICAL_SECTION)IniPrintProc + 2);
            SafeDecrementReference((unsigned int *)IniPrintProc + 4);
            --*((_DWORD *)IniPrintProc + 32);
            if ( *(_DWORD *)(v14 + 16) )
              SafeDecrementReference((unsigned int *)(v14 + 16));
          }
          SafeDecrementReference((unsigned int *)v3 + 6);
        }
      }
    }
    if ( *((_QWORD *)v3 + 49) == -1 )
      GetFullNameFromId(*((_QWORD *)v3 + 11), *((_DWORD *)v3 + 10), 0, (unsigned int)FileName, 260, 0);
    if ( *((_DWORD *)v3 + 6) )
    {
      if ( (*(_DWORD *)(v70 + 168) & 0x1000) == 0 )
      {
        v60 = (void *)*((_QWORD *)v3 + 49);
        if ( v60 == (void *)-1LL )
        {
          INIJOB::SetJobStatusFlags(v3, 0x40000000u);
          SafeIncrementReference((unsigned int *)v3 + 6);
          LeaveSplSem(v61);
          v62 = DeleteFileW(FileName);
          EnterSplSem(0);
          SafeDecrementReference((unsigned int *)v3 + 6);
          if ( !v62 )
          {
            LastError = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceWarning(
              "DeleteJob",
              L"Failed to delete shadow file %ws.  Error %d",
              FileName,
              LastError);
            LODWORD(v85) = 104;
            v86 = 4;
            v76 = L"-";
            v87 = 0;
            v82 = LastError;
            v83 = 4;
            v84 = 0;
            v79 = 0;
            v80 = 4;
            v81 = 0;
            v77 = 4;
            v78 = 1;
            v64 = SplLogType::SplLogType((SplLogType *)v88, FileName);
            SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v64, &v76, &v79, &v82, &v85, 0);
            INIJOB::ClearJobStatusFlags(v3, 0x40000000u);
          }
        }
        else
        {
          FinishedWriting(v60, 0);
          INIJOB::SetJobStatusFlags(v3, 0x40000000u);
        }
      }
      break;
    }
    if ( (*((_BYTE *)v3 + 32) & 0x40) != 0 )
    {
      v59 = 0;
      goto LABEL_125;
    }
    v20 = *((_QWORD *)v3 + 11);
    v21 = v66 & 0x100;
    v66 = v21;
    if ( *(INIJOB **)(v20 + 176) == v3 )
      *(_QWORD *)(v20 + 176) = *((_QWORD *)v3 + 1);
    v22 = *((_QWORD *)v3 + 11);
    if ( *(INIJOB **)(v22 + 184) == v3 )
      *(_QWORD *)(v22 + 184) = *((_QWORD *)v3 + 2);
    v23 = *((_QWORD *)v3 + 2);
    if ( v23 )
      *(_QWORD *)(v23 + 8) = *((_QWORD *)v3 + 1);
    v24 = *((_QWORD *)v3 + 1);
    if ( v24 )
      *(_QWORD *)(v24 + 16) = *((_QWORD *)v3 + 2);
    if ( (*((_DWORD *)v3 + 8) & 0x400) == 0 || *((_DWORD *)v3 + 109) == 63 )
    {
      SafeIncrementReference((unsigned int *)v3 + 6);
      v25 = *(_QWORD *)(*((_QWORD *)v3 + 11) + 24LL);
      GetSpoolerNumericPolicy(L"ShowJobTitleInEventLogs");
      LogJobInfo((struct _EVENT_DESCRIPTOR *)&MSG_DOCUMENT_DELETED, v25, 0);
      SafeDecrementReference((unsigned int *)v3 + 6);
      v21 = v66;
    }
    v26 = (void *)*((_QWORD *)v3 + 49);
    if ( v26 == (void *)-1LL )
    {
      GetFullNameFromId(*((_QWORD *)v3 + 11), *((_DWORD *)v3 + 10), 1, (unsigned int)v90, 260, 0);
      v26 = v69;
    }
    else
    {
      v69 = (void *)*((_QWORD *)v3 + 49);
    }
    FileCreationInfo = GetFileCreationInfo(v26, &v67);
    v28 = v67;
    if ( FileCreationInfo )
      v28 = 7;
    v75 = v28;
    v67 = v28;
    v29 = (_QWORD *)*((_QWORD *)v3 + 31);
    if ( v29 )
    {
      v29 = (_QWORD *)v29[25];
      if ( v29 )
      {
        CloseHandle(v29);
        *(_QWORD *)(*((_QWORD *)v3 + 31) + 200LL) = 0;
      }
    }
    v30 = *((_QWORD *)v3 + 11);
    v31 = *((unsigned int *)v3 + 10);
    if ( *(_DWORD *)(v30 + 156) == 1 && (*(_BYTE *)(v30 + 136) & 0x10) != 0 )
    {
      if ( v2 && SafeIncrementReference((unsigned int *)(v2 + 16)) > *(_DWORD *)(v2 + 248) )
        *(_DWORD *)(v2 + 248) = *(_DWORD *)(v2 + 16);
      LeaveSplSem(v29);
      PrinterDriverEvent((struct _INIPRINTER *)v2);
      EnterSplSem(0);
      if ( v2 && *(_DWORD *)(v2 + 16) )
        SafeDecrementReference((unsigned int *)(v2 + 16));
    }
    if ( !*((_DWORD *)v3 + 76) || !IsXPS2GDI(v3) )
      --*(_DWORD *)(*((_QWORD *)v3 + 11) + 156LL);
    v32 = *((_QWORD *)v3 + 12);
    if ( v32 && *(_DWORD *)(v32 + 16) )
      SafeDecrementReference((unsigned int *)(v32 + 16));
    v33 = *((_QWORD *)v3 + 14);
    if ( v33 )
      SafeDecrementReference((unsigned int *)(v33 + 16));
    if ( v72 == 1 )
    {
      INIJOB::SetJobStatusFlags(v3, 0x1000000u);
      v34 = v70;
      SetPrinterChange(*((_QWORD *)v3 + 11), (_DWORD)v3, (unsigned int)NVDeletedJob, 1026, v70);
    }
    else
    {
      v34 = v70;
    }
    v35 = *(_DWORD *)(v34 + 168);
    DeletePrinterCheck(*((_INIPRINTER **)v3 + 11));
    v36 = *((_DWORD *)v3 + 8);
    INIJOB::`scalar deleting destructor'(v3, v37);
    if ( v21 || (v35 & 0x1000) != 0 )
      goto LABEL_102;
    v39 = 0;
    LeaveSplSem(v38);
    v40 = RevertToPrinterSelf();
    v41 = (v36 & 0x40000000) != 0;
    v42 = (char *)v69;
    v43 = v40;
    if ( !v41 )
    {
      if ( (char *)v69 - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      {
        v66 = 1;
        if ( !(unsigned int)SafeDeleteFileByHandle(FileName, &v66) )
        {
          v44 = GetLastError();
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "DeleteJob",
            L"Failed to delete shadow file %ws.  Error %d",
            FileName,
            v44);
          LODWORD(v76) = 104;
          v77 = 4;
          v78 = 0;
          v85 = L"-";
          v79 = v44;
          v80 = 4;
          v81 = 0;
          v82 = 0;
          v83 = 4;
          v84 = 0;
          v86 = 4;
          v87 = 1;
          v45 = SplLogType::SplLogType((SplLogType *)v88, FileName);
          SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v45, &v85, &v82, &v79, &v76, v46);
          if ( !v66 )
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "DeleteJob",
              L"Deletion failed. Invalid SHD file %ws. Error %d",
              FileName,
              (unsigned int)v44);
        }
      }
      else
      {
        FinishedWriting(v69, 0);
      }
    }
    if ( (unsigned __int64)(v42 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v66 = 1;
      if ( !(unsigned int)SafeDeleteFileByHandle(v90, &v66) )
      {
        v39 = 1;
        v47 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "DeleteJob",
          L"Failed to delete spool file %ws.  Error %d",
          v90,
          v47);
        LODWORD(v85) = 104;
        v86 = 4;
        v76 = L"-";
        v87 = 0;
        v82 = v47;
        v83 = 4;
        v84 = 0;
        v79 = 0;
        v80 = 4;
        v81 = 0;
        v77 = 4;
        v78 = 1;
        v48 = SplLogType::SplLogType((SplLogType *)v88, v90);
        SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v48, &v76, &v79, &v82, &v85, 0);
        if ( !v66 )
          LocalSpoolerTelemetry::WriteDbgTraceError(
            "DeleteJob",
            L"Deletion failed. Invalid SPL file %ws. Error %d",
            v90,
            (unsigned int)v47);
      }
    }
    else
    {
      FinishedWriting(v42, 1);
      FinishedReading(v42);
      ReleasePoolHandle(&v69);
      v68 = 1;
    }
    ImpersonatePrinterClient(v43);
    EnterSplSem(0);
    if ( !v39 )
    {
LABEL_102:
      v4 = v70;
      *(_DWORD *)(**(_QWORD **)(v70 + 264) + 4 * (v31 >> 5)) &= ~(1 << v31);
      for ( i = *(_QWORD *)(v2 + 200); i; i = *(_QWORD *)(i + 8) )
      {
        if ( (*(_BYTE *)(i + 160) & 0x10) == 0 )
        {
          v53 = (_QWORD **)(i + 272);
          v54 = *(_QWORD **)(i + 272);
          if ( v54 )
          {
            while ( *((_DWORD *)v54 + 4) != (_DWORD)v31 || (*((_BYTE *)v54 + 20) & 2) != 0 )
            {
              v53 = (_QWORD **)v54;
              v54 = (_QWORD *)*v54;
              if ( !v54 )
                goto LABEL_110;
            }
            v55 = *v53;
            *v53 = (_QWORD *)**v53;
            DllFreeSplMem(v55[1]);
            DllFreeSplMem(v55);
          }
        }
LABEL_110:
        ;
      }
    }
    else
    {
      v4 = v70;
    }
    if ( !v73 )
      break;
    Job = FindJob(v2, v73, &v74);
    v3 = (INIJOB *)Job;
    if ( !Job )
    {
      LocalSpoolerTelemetry::WriteDbgTraceWarning("DeleteJob", L"NextJobId %d not found", MEMORY[0x130]);
      break;
    }
    SafeDecrementReference((unsigned int *)(Job + 24));
    if ( *((_DWORD *)v3 + 6) )
      v3 = 0;
    if ( !v3 )
      break;
    SafeIncrementReference((unsigned int *)v3 + 6);
    v50 = *((_QWORD *)v3 + 16);
    if ( !v50 || (unsigned int)_o__wcsnicmp(v50, L"TEXT", 4) )
    {
      v56 = *((_QWORD *)v3 + 16);
      if ( !v56 || (v57 = _o__wcsnicmp(v56, L"NT EMF", 6), v51 = 2, v57) )
        v51 = 1;
    }
    else
    {
      v51 = 3;
    }
    v58 = (const struct _EVENT_DESCRIPTOR *)v75;
    LOWORD(v58) = v75 & 1;
    SplLogDeleteJobDiagEvent(
      v58,
      v31,
      *((_DWORD *)v3 + 44),
      v51,
      *((_DWORD *)v3 + 68),
      *((_DWORD *)v3 + 91),
      (_WORD)v58 + ((v75 >> 1) & 1) + ((v75 >> 2) & 1),
      *((_DWORD *)v3 + 45));
    SafeDecrementReference((unsigned int *)v3 + 6);
  }
  v59 = 1;
LABEL_125:
  if ( v2 && *(_DWORD *)(v2 + 16) )
    SafeDecrementReference((unsigned int *)(v2 + 16));
  DeletePrinterCheck((_INIPRINTER *)v2);
  if ( v68 )
    SetEvent(SchedulerSignal);
  if ( !v59 )
    LocalSpoolerTelemetry::WriteDbgTraceError("DeleteJob", L"Deleting job failed.");
  return v59;
}

```

## disassembly

```asm
0x180060bf0  push    rbp
0x180060bf2  push    rbx
0x180060bf3  push    rsi
0x180060bf4  push    rdi
0x180060bf5  push    r12
0x180060bf7  push    r13
0x180060bf9  push    r14
0x180060bfb  push    r15
0x180060bfd  lea     rbp, [rsp-428h]
0x180060c05  sub     rsp, 528h
0x180060c0c  mov     rax, cs:__security_cookie
0x180060c13  xor     rax, rsp
0x180060c16  mov     [rbp+460h+var_50], rax
0x180060c1d  mov     r13, [rcx+58h]
0x180060c21  xor     r14d, r14d
0x180060c24  mov     [rsp+560h+var_4FC], edx
0x180060c28  mov     rdi, rcx
0x180060c2b  mov     [rsp+560h+var_4F4], r14d
0x180060c30  mov     [rsp+560h+var_510], r14
0x180060c35  mov     rsi, [r13+118h]
0x180060c3c  lea     r12d, [r14+1]
0x180060c40  mov     [rsp+560h+var_508], rsi
0x180060c45  mov     [rsp+560h+var_500], r14d
0x180060c4a  mov     [rsp+560h+var_51C], r14d
0x180060c4f  mov     [rsp+560h+var_518], r14d
0x180060c54  test    r13, r13
0x180060c57  jz      short loc_180060C76
0x180060c59  lea     rcx, [r13+10h]; unsigned int *
0x180060c5d  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060c62  cmp     eax, [r13+0F8h]
0x180060c69  jbe     short loc_180060C76
0x180060c6b  mov     eax, [r13+10h]
0x180060c6f  mov     [r13+0F8h], eax
0x180060c76  mov     eax, [rdi+20h]
0x180060c79  mov     [rsp+560h+var_520], eax
0x180060c7d  bt      eax, 0Bh
0x180060c81  jb      loc_180061745
0x180060c87  mov     rcx, [rdi+0C0h]
0x180060c8e  mov     eax, [rdi+130h]
0x180060c94  mov     [rsp+560h+var_4F8], eax
0x180060c98  test    rcx, rcx
0x180060c9b  jz      short loc_180060CB3
0x180060c9d  call    cs:__imp_DllFreeSplStr
0x180060ca3  mov     [rdi+0C0h], r14
0x180060caa  lea     rbx, NVJobStatusAndString
0x180060cb1  jmp     short loc_180060CBA
0x180060cb3  lea     rbx, NVJobStatus
0x180060cba  mov     rcx, [rdi+0F8h]
0x180060cc1  call    SetPortErrorEvent
0x180060cc6  cmp     [rdi+24h], r14d
0x180060cca  jz      short loc_180060CF1
0x180060ccc  prefetchw byte ptr [rdi+24h]
0x180060cd0  mov     eax, [rdi+24h]
0x180060cd3  mov     ecx, eax
0x180060cd5  and     ecx, 0FFFFFFFBh
0x180060cd8  lock cmpxchg [rdi+24h], ecx
0x180060cdd  jnz     short loc_180060CD3
0x180060cdf  mov     r8d, [rdi+24h]
0x180060ce3  mov     edx, eax; unsigned int
0x180060ce5  and     r8d, 0FFFFFFFBh; unsigned int
0x180060ce9  mov     rcx, rdi; this
0x180060cec  call    ?CheckJobStatusChange@INIJOB@@AEAAXKK@Z; INIJOB::CheckJobStatusChange(ulong,ulong)
0x180060cf1  test    byte ptr [rdi+20h], 20h
0x180060cf5  jnz     loc_180060F52
0x180060cfb  mov     edx, 20h ; ' '; unsigned int
0x180060d00  mov     rcx, rdi; this
0x180060d03  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180060d08  mov     r8d, r12d
0x180060d0b  xor     edx, edx
0x180060d0d  mov     rcx, rdi
0x180060d10  call    SeekPrinterSetEvent
0x180060d15  mov     rcx, [rdi+0E8h]; hEvent
0x180060d1c  test    rcx, rcx
0x180060d1f  jz      short loc_180060D27
0x180060d21  call    cs:__imp_SetEvent
0x180060d27  mov     rcx, [rdi+58h]
0x180060d2b  mov     r9d, 200h
0x180060d31  mov     r8, rbx
0x180060d34  mov     qword ptr [rsp+560h+var_540], rsi
0x180060d39  mov     rdx, rdi
0x180060d3c  call    SetPrinterChange
0x180060d41  mov     ecx, [rdi+20h]
0x180060d44  mov     eax, ecx
0x180060d46  and     eax, 401h
0x180060d4b  cmp     eax, r12d
0x180060d4e  jz      short loc_180060D62
0x180060d50  and     ecx, 4200h
0x180060d56  cmp     ecx, 4200h
0x180060d5c  jnz     loc_180060E17
0x180060d62  mov     rbx, [rdi+0F8h]
0x180060d69  test    rbx, rbx
0x180060d6c  jnz     short loc_180060D91
0x180060d6e  mov     rdx, [rdi+220h]
0x180060d75  lea     r8, [rsi+8188h]
0x180060d7c  mov     rcx, [rsi+40h]
0x180060d80  call    FindIniKey
0x180060d85  mov     rbx, rax
0x180060d88  test    rax, rax
0x180060d8b  jz      loc_180060E17
0x180060d91  lea     r14, [rbx+10h]
0x180060d95  mov     rcx, r14; unsigned int *
0x180060d98  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060d9d  lea     rcx, [rdi+18h]; unsigned int *
0x180060da1  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060da6  mov     rsi, [rbx+60h]
0x180060daa  xor     r12b, r12b
0x180060dad  test    rsi, rsi
0x180060db0  jz      short loc_180060DF0
0x180060db2  cmp     qword ptr [rsi+1A0h], 0
0x180060dba  jz      short loc_180060DF0
0x180060dbc  mov     rax, [r13+58h]
0x180060dc0  cmp     dword ptr [rax+0ECh], 3
0x180060dc7  jbe     short loc_180060DF0
0x180060dc9  mov     r12b, 1
0x180060dcc  call    LeaveSplSem
0x180060dd1  mov     r8d, [rdi+28h]
0x180060dd5  mov     rdx, [rbx+18h]
0x180060dd9  mov     rcx, [rsi+38h]
0x180060ddd  mov     rax, [rsi+1A0h]
0x180060de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060de9  xor     ecx, ecx
0x180060deb  call    EnterSplSem
0x180060df0  lea     rcx, [rdi+18h]; unsigned int *
0x180060df4  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180060df9  cmp     dword ptr [r14], 0
0x180060dfd  jz      short loc_180060E07
0x180060dff  mov     rcx, r14; unsigned int *
0x180060e02  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180060e07  xor     r14d, r14d
0x180060e0a  test    r12b, r12b
0x180060e0d  jnz     loc_180061745
0x180060e13  lea     r12d, [r14+1]
0x180060e17  test    [rdi+20h], r12b
0x180060e1b  jz      loc_180060F52
0x180060e21  mov     rcx, rdi; this
0x180060e24  call    ?GetIniPrintProc@INIJOB@@QEAAPEAVINIPRINTPROC@@XZ; INIJOB::GetIniPrintProc(void)
0x180060e29  mov     rsi, rax
0x180060e2c  test    rax, rax
0x180060e2f  jz      loc_180060F52
0x180060e35  lea     rcx, [rdi+18h]; unsigned int *
0x180060e39  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060e3e  mov     rbx, [rdi+0F8h]
0x180060e45  test    rbx, rbx
0x180060e48  jz      loc_180060F49
0x180060e4e  test    [rbx+0D8h], r12b
0x180060e55  jnz     loc_180060F49
0x180060e5b  lea     r14, [rbx+10h]
0x180060e5f  mov     rcx, r14; unsigned int *
0x180060e62  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060e67  lea     rcx, [rsi+10h]; unsigned int *
0x180060e6b  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180060e70  inc     dword ptr [rsi+80h]
0x180060e76  call    LeaveSplSem
0x180060e7b  lea     rcx, [rsi+50h]; lpCriticalSection
0x180060e7f  call    cs:__imp_EnterCriticalSection
0x180060e85  xor     ecx, ecx
0x180060e87  call    EnterSplSem
0x180060e8c  or      dword ptr [rbx+0D8h], 1
0x180060e93  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race> `wil::Feature<__WilFeatureTraits_Feature_Spooler_hProc_Race>::GetImpl(void)'::`2'::impl
0x180060e9a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Spooler_hProc_Race@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Spooler_hProc_Race>::__private_IsEnabled(void)
0x180060e9f  test    al, al
0x180060ea1  jz      short loc_180060ED0
0x180060ea3  cmp     qword ptr [rdi+78h], 0
0x180060ea8  jz      short loc_180060F0D
0x180060eaa  mov     r9d, [rdi+28h]
0x180060eae  lea     rdx, aSendingJobCont; "Sending JOB_CONTROL_CANCEL to print pro"...
0x180060eb5  mov     r8, [rsi+18h]
0x180060eb9  lea     rcx, aDeletejob; "DeleteJob"
0x180060ec0  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180060ec5  call    LeaveSplSem
0x180060eca  mov     rdx, [rdi+78h]
0x180060ece  jmp     short loc_180060EFB
0x180060ed0  cmp     qword ptr [rbx+28h], 0
0x180060ed5  jz      short loc_180060F0D
0x180060ed7  mov     r9d, [rdi+28h]
0x180060edb  lea     rdx, aSendingJobCont; "Sending JOB_CONTROL_CANCEL to print pro"...
0x180060ee2  mov     r8, [rsi+18h]
0x180060ee6  lea     rcx, aDeletejob; "DeleteJob"
0x180060eed  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180060ef2  call    LeaveSplSem
0x180060ef7  mov     rdx, [rbx+28h]; void *
0x180060efb  mov     r8d, 3; unsigned int
0x180060f01  call    ?ControlPrintProcessor@PrintProcessorAdapter@sandbox@@QEAAHPEAXK@Z; sandbox::PrintProcessorAdapter::ControlPrintProcessor(void *,ulong)
0x180060f06  xor     ecx, ecx
0x180060f08  call    EnterSplSem
0x180060f0d  and     dword ptr [rbx+0D8h], 0FFFFFFFEh
0x180060f14  lea     rcx, [rsi+50h]; lpCriticalSection
0x180060f18  or      dword ptr [rbx+0D8h], 6
0x180060f1f  call    cs:__imp_LeaveCriticalSection
0x180060f25  lea     rcx, [rsi+10h]; unsigned int *
0x180060f29  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180060f2e  dec     dword ptr [rsi+80h]
0x180060f34  cmp     dword ptr [r14], 0
0x180060f38  jz      short loc_180060F42
0x180060f3a  mov     rcx, r14; unsigned int *
0x180060f3d  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180060f42  xor     r14d, r14d
0x180060f45  lea     r12d, [r14+1]
0x180060f49  lea     rcx, [rdi+18h]; unsigned int *
0x180060f4d  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180060f52  cmp     qword ptr [rdi+188h], 0FFFFFFFFFFFFFFFFh
0x180060f5a  jnz     short loc_180060F7D
0x180060f5c  mov     edx, [rdi+28h]
0x180060f5f  lea     r9, [rbp+460h+FileName]
0x180060f63  mov     rcx, [rdi+58h]
0x180060f67  xor     r8d, r8d
0x180060f6a  mov     [rsp+560h+var_538], r14d
0x180060f6f  mov     qword ptr [rsp+560h+var_540], 104h
0x180060f78  call    GetFullNameFromId
0x180060f7d  lea     rsi, [rdi+18h]
0x180060f81  cmp     [rsi], r14d
0x180060f84  jnz     loc_180061621
0x180060f8a  test    byte ptr [rdi+20h], 40h
0x180060f8e  jnz     loc_180061619
0x180060f94  mov     r14d, [rsp+560h+var_520]
0x180060f99  mov     rcx, [rdi+58h]
0x180060f9d  and     r14d, 100h
0x180060fa4  mov     [rsp+560h+var_520], r14d
0x180060fa9  cmp     [rcx+0B0h], rdi
0x180060fb0  jnz     short loc_180060FBD
0x180060fb2  mov     rax, [rdi+8]
0x180060fb6  mov     [rcx+0B0h], rax
0x180060fbd  mov     rcx, [rdi+58h]
0x180060fc1  cmp     [rcx+0B8h], rdi
0x180060fc8  jnz     short loc_180060FD5
0x180060fca  mov     rax, [rdi+10h]
0x180060fce  mov     [rcx+0B8h], rax
0x180060fd5  mov     rcx, [rdi+10h]
0x180060fd9  xor     ebx, ebx
0x180060fdb  test    rcx, rcx
0x180060fde  jz      short loc_180060FE8
0x180060fe0  mov     rax, [rdi+8]
0x180060fe4  mov     [rcx+8], rax
0x180060fe8  mov     rcx, [rdi+8]
0x180060fec  test    rcx, rcx
0x180060fef  jz      short loc_180060FF9
0x180060ff1  mov     rax, [rdi+10h]
0x180060ff5  mov     [rcx+10h], rax
0x180060ff9  test    dword ptr [rdi+20h], 400h
0x180061000  jz      short loc_18006100B
0x180061002  cmp     dword ptr [rdi+1B4h], 3Fh ; '?'
0x180061009  jnz     short loc_18006106C
0x18006100b  mov     rcx, rsi; unsigned int *
0x18006100e  call    ?SafeIncrementReference@@YAKPEAK@Z; SafeIncrementReference(ulong *)
0x180061013  mov     r10, [rdi+58h]
0x180061017  lea     rcx, aShowjobtitlein; "ShowJobTitleInEventLogs"
0x18006101e  mov     r14, [rdi+38h]
0x180061022  xor     edx, edx
0x180061024  mov     rbx, [r10+18h]
0x180061028  call    GetSpoolerNumericPolicy
0x18006102d  test    eax, eax
0x18006102f  jz      short loc_180061037
0x180061031  mov     r8, [rdi+48h]
0x180061035  jmp     short loc_18006103E
0x180061037  mov     r8, cs:g_pszGenericDoc
0x18006103e  mov     edx, [rdi+28h]
0x180061041  lea     rcx, MSG_DOCUMENT_DELETED; struct _EVENT_DESCRIPTOR *
0x180061048  mov     [rsp+560h+var_538], 0; int
0x180061050  mov     r9, r14
0x180061053  mov     qword ptr [rsp+560h+var_540], rbx; __int64
0x180061058  call    LogJobInfo
0x18006105d  mov     rcx, rsi; unsigned int *
0x180061060  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180061065  mov     r14d, [rsp+560h+var_520]
0x18006106a  xor     ebx, ebx
0x18006106c  mov     rax, [rdi+188h]
0x180061073  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180061077  jz      short loc_180061080
0x180061079  mov     [rsp+560h+var_510], rax
0x18006107e  jmp     short loc_1800610A8
0x180061080  mov     edx, [rdi+28h]
0x180061083  lea     r9, [rbp+460h+var_260]
0x18006108a  mov     rcx, [rdi+58h]
0x18006108e  mov     r8d, r12d
0x180061091  mov     [rsp+560h+var_538], ebx
0x180061095  mov     qword ptr [rsp+560h+var_540], 104h
0x18006109e  call    GetFullNameFromId
0x1800610a3  mov     rax, [rsp+560h+var_510]
0x1800610a8  lea     rdx, [rsp+560h+var_51C]; unsigned int *
0x1800610ad  mov     rcx, rax; void *
0x1800610b0  call    ?GetFileCreationInfo@@YAJPEAXPEAK@Z; GetFileCreationInfo(void *,ulong *)
0x1800610b5  mov     ecx, [rsp+560h+var_51C]
0x1800610b9  test    eax, eax
0x1800610bb  mov     edx, 7
0x1800610c0  cmovnz  ecx, edx
0x1800610c3  mov     [rsp+560h+var_4F0], ecx
0x1800610c7  mov     [rsp+560h+var_51C], ecx
0x1800610cb  mov     rcx, [rdi+0F8h]
0x1800610d2  test    rcx, rcx
0x1800610d5  jz      short loc_1800610F7
0x1800610d7  mov     rcx, [rcx+0C8h]; hObject
0x1800610de  test    rcx, rcx
0x1800610e1  jz      short loc_1800610F7
0x1800610e3  call    cs:__imp_CloseHandle
0x1800610e9  mov     rax, [rdi+0F8h]
0x1800610f0  mov     [rax+0C8h], rbx
0x1800610f7  mov     rax, [rdi+58h]
0x1800610fb  mov     r15d, [rdi+28h]
0x1800610ff  cmp     [rax+9Ch], r12d
0x180061106  jnz     short loc_180061165
  ... truncated ...
```
