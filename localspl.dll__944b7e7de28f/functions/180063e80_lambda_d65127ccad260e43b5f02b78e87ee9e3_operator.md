# _lambda_d65127ccad260e43b5f02b78e87ee9e3_::operator()

- ea: `0x180063e80`
- end: `0x1800647d6`
- name: `_lambda_d65127ccad260e43b5f02b78e87ee9e3_::operator()`
- size: `2390`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, installer_update`

## callers

- `0x180062d98`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x18000bdb0`
- `0x18000ee90`
- `0x1800237b0`
- `0x180024368`
- `0x18002abf8`
- `0x180038fec`
- `0x18003e984`
- `0x18003ea2c`
- `0x1800430b8`
- `0x180043aa4`
- `0x180044484`
- `0x180054638`
- `0x180062280`
- `0x180062b9c`
- `0x180063e80`
- `0x180065adc`
- `0x180065dd4`
- `0x1800cd7b4`
- `0x1800dae5c`
- `0x1800dc638`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800641af`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800641af`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064498`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800644aa`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180064498`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800644aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063ff7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180063ff7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006413f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006470e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064742`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006413f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006470e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180064742`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064629`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064643`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064653`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064674`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800647a4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064030`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064619`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064629`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064643`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064653`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180064674`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800647a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800641f1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006437e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800641f1`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18006437e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18006439b`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18006439b`
- `SPOOLSS!WritePrinter` at `0x1800641fd`
- `SPOOLSS!WritePrinter` at `0x1800641fd`

## string_xrefs

- `0x180063f3c`: `SplWritePrinter: SPOOL_STATUS_CANCELLED`
- `0x180064766`: `SplWritePrinter: JOB_PENDING_DELETION`
- `0x180064778`: `WritePrinter failed with error %d`
- `0x180063f5b`: `SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()`
- `0x18006477f`: `SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()`
- `0x18006403e`: `SplWritePrinter: JOB_PENDING_DELETION #2`
- `0x1800645e8`: `Deleted job %u on %ws because printer is offline`
- `0x1800645f9`: `Failed to delete job %u on %ws because printer is offline`
- `0x180064661`: `SplWritePrinter: JOB_PENDING_DELETION #3`
- `0x180064717`: `WritePrinter failed for handle %p. Error %d`

## pseudocode

```c
int __fastcall lambda_d65127ccad260e43b5f02b78e87ee9e3_::operator()(__int64 **a1)
{
  __int64 *v1; // rax
  __int64 v3; // rdi
  char **v4; // rax
  char *v5; // r14
  __int64 *v6; // rax
  _BYTE *v7; // r12
  DWORD v8; // r15d
  __int64 v9; // rax
  const struct _tlgProvider_t *v10; // rax
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rbx
  __int64 v13; // rcx
  unsigned int *v14; // rcx
  __int64 v15; // rcx
  DWORD v16; // r14d
  __int64 v17; // rbx
  __int64 v18; // rbx
  const struct _tlgProvider_t *v19; // rax
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 OpenedMonitor; // rax
  __int64 v23; // r10
  unsigned int *v24; // r8
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  DWORD v29; // r8d
  BOOL v30; // eax
  DWORD v31; // ecx
  DWORD v32; // eax
  __int64 v33; // r8
  __int64 v34; // rcx
  __int64 v35; // rax
  __int64 v36; // r14
  __int64 v37; // rcx
  BOOL *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 Job; // rax
  __int64 v42; // rbx
  __int64 v43; // rbx
  __int64 v44; // rcx
  int v45; // edx
  int v46; // eax
  __int64 v47; // r9
  __int64 v48; // r8
  const struct _tlgProvider_t *v49; // rax
  unsigned int v50; // r8d
  __int64 v51; // rax
  unsigned __int64 v52; // rdx
  PrintDAM *v53; // rcx
  DWORD LastError; // eax
  __int64 *v55; // rax
  const char *v56; // r9
  __int64 v57; // rcx
  const char *v58; // r9
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-28h]
  __int64 v61; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+40h]
  DWORD NumberOfBytesWritten; // [rsp+90h] [rbp+48h] BYREF
  int v64; // [rsp+98h] [rbp+50h] BYREF
  LPCVOID lpBuffer; // [rsp+A0h] [rbp+58h]
  union _LARGE_INTEGER FileSize; // [rsp+A8h] [rbp+60h] BYREF

  v1 = *a1;
  v64 = 0;
  v3 = *v1;
  v4 = (char **)a1[1];
  NumberOfBytesWritten = 0;
  v5 = *v4;
  FileSize = LARGE_INTEGER_ZERO;
  v6 = a1[2];
  lpBuffer = v5;
  *(_DWORD *)*v6 = 0;
  EnterSplSem(0);
  v7 = (_BYTE *)(v3 + 112);
  if ( !(unsigned int)ValidateSpoolHandle(v3, 16) )
    goto LABEL_2;
  if ( (*v7 & 1) == 0 || (*v7 & 0x10) != 0 )
  {
    v8 = 3003;
    goto LABEL_133;
  }
  v9 = *(_QWORD *)(v3 + 80);
  if ( v9
    && (*(_BYTE *)(v3 + 88) & 0xC) == 0
    && (*(_QWORD *)(v9 + 184) == -1 || (*(_DWORD *)(v9 + 32) & 0x8000000) != 0) )
  {
LABEL_2:
    v8 = 6;
    goto LABEL_133;
  }
  if ( (*v7 & 4) != 0 )
  {
    v8 = 63;
    v10 = LocalSpoolerTelemetry::Provider();
    v11 = L"SplWritePrinter: SPOOL_STATUS_CANCELLED";
LABEL_132:
    SplTraceErrorPrintCancelled(v10, v11);
LABEL_133:
    LocalSpoolerTelemetry::WriteDbgTraceWarning(
      "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
      L"WritePrinter failed with error %d",
      v8);
    if ( v8 == 63 && (*(_BYTE *)(v3 + 88) & 4) != 0 )
      *(_DWORD *)v7 |= 0x100u;
    LeaveSplSem(v57);
    SetLastError(v8);
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x928,
      (unsigned int)"printscan\\print\\spooler\\localspl\\spooler.c",
      v58);
  }
  if ( v9 && (*(_BYTE *)(v9 + 32) & 0x20) != 0 )
  {
    v8 = 63;
    v10 = LocalSpoolerTelemetry::Provider();
    v11 = L"SplWritePrinter: JOB_PENDING_DELETION";
    goto LABEL_132;
  }
  LocalSpoolerTelemetry::WriteDbgTraceInfo(
    "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
    L"Printer - %ws",
    *(_QWORD *)(*(_QWORD *)(v3 + 64) + 24LL));
  v12 = *(_QWORD *)(v3 + 72);
  v61 = v12;
  LeaveSplSem(v13);
  v14 = (unsigned int *)a1[3];
  NumberOfBytesWritten = 0;
  if ( *v14 )
  {
    while ( 1 )
    {
      if ( (*(_BYTE *)(v3 + 88) & 4) != 0 )
      {
        EnterSplSem(0);
        if ( *(_DWORD *)(*(_QWORD *)(v3 + 64) + 308LL) > 1u
          && (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 48LL) & 0x20000) != 0
          && *(_QWORD *)(v12 + 200) )
        {
          LeaveSplSem(v15);
          v16 = WaitForSingleObject(*(HANDLE *)(v12 + 200), 1000 * *(_DWORD *)(*(_QWORD *)(v3 + 168) + 284LL));
          EnterSplSem(0);
          v17 = *(_QWORD *)(v3 + 80);
          if ( v17 || (v18 = *(_QWORD *)(v3 + 72)) != 0 && (v17 = *(_QWORD *)(v18 + 72)) != 0 )
          {
            if ( (*(_DWORD *)(v17 + 32) & 0x820) != 0 )
            {
              SetLastError(0x3Fu);
              v19 = LocalSpoolerTelemetry::Provider();
              SplTraceErrorPrintCancelled(v19, L"SplWritePrinter: JOB_PENDING_DELETION #2");
LABEL_24:
              *(_DWORD *)a1[4] = 0;
              goto LABEL_122;
            }
          }
          else
          {
            v17 = 0;
          }
          if ( v16 == 258 )
          {
            INIJOB::SetJobStatusFlags((INIJOB *)v17, 4u);
            SetPrinterChange(
              *(_QWORD *)(v17 + 88),
              v17,
              (unsigned int)&NVJobStatus,
              512,
              *(_QWORD *)(*(_QWORD *)(v17 + 88) + 280LL));
          }
          v12 = v61;
          v5 = (char *)lpBuffer;
        }
        LeaveSplSem(v15);
        v21 = *(_QWORD *)(v3 + 80);
        if ( (*(_DWORD *)(*(_QWORD *)(v3 + 72) + 48LL) & 0x8000) != 0 )
        {
          if ( v21 && *(_DWORD *)(v21 + 580) )
            goto LABEL_67;
          GetMonitorHandle(v12);
          OpenedMonitor = GetOpenedMonitor();
          if ( !OpenedMonitor || !v23 )
          {
            *(_DWORD *)a1[4] = 0;
            SetLastError(6u);
            goto LABEL_121;
          }
          v24 = (unsigned int *)a1[3];
          NumberOfBytesWritten = 0;
          *(_DWORD *)a1[4] = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, DWORD *))(OpenedMonitor + 128))(
                               v23,
                               v5,
                               *v24,
                               &NumberOfBytesWritten);
          if ( NumberOfBytesWritten )
          {
            EnterSplSem(0);
            v25 = *(_QWORD **)(v3 + 64);
            v25[28] += NumberOfBytesWritten;
LABEL_87:
            LeaveSplSem(v25);
            goto LABEL_88;
          }
          if ( !*(_DWORD *)a1[4] )
          {
            if ( GetLastError() == 3003 )
            {
              EnterSplSem(0);
              v27 = *(_QWORD *)(v3 + 80);
              if ( v27 || (v28 = *(_QWORD *)(v3 + 72)) != 0 && (v27 = *(_QWORD *)(v28 + 72)) != 0 )
                *(_DWORD *)(v27 + 240) = 3003;
              LeaveSplSem(v26);
            }
            else if ( gbInConnectedStandby && *(char *)(*(_QWORD *)(v3 + 64) + 320LL) < 0 )
            {
              LODWORD(lpOverlapped) = 5;
              v46 = SplSetJob(v3, *(_DWORD *)(*(_QWORD *)(v3 + 80) + 40LL), 0, 0, lpOverlapped);
              v47 = *(_QWORD *)(*(_QWORD *)(v3 + 64) + 24LL);
              v48 = *(unsigned int *)(*(_QWORD *)(v3 + 80) + 40LL);
              if ( v46 )
                LocalSpoolerTelemetry::WriteDbgTraceWarning(
                  "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
                  L"Deleted job %u on %ws because printer is offline",
                  v48,
                  v47);
              else
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
                  L"Failed to delete job %u on %ws because printer is offline",
                  v48,
                  v47);
              goto LABEL_122;
            }
          }
          if ( *(_DWORD *)a1[4] && *(_DWORD *)&dwWritePrinterSleepTime )
            Sleep(*(DWORD *)&dwWritePrinterSleepTime);
        }
        else
        {
          if ( v21 && *(_DWORD *)(v21 + 580) )
          {
LABEL_67:
            LocalSpoolerTelemetry::WriteDbgTraceInfo(
              "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
              L"Job rejected by Defender Rules: Printer %ws",
              *(_QWORD *)(*(_QWORD *)(v3 + 64) + 24LL));
            NumberOfBytesWritten = *(_DWORD *)a1[3];
            goto LABEL_88;
          }
          v29 = *(_DWORD *)a1[3];
          if ( (*v7 & 0x20) != 0 )
            v30 = WriteFile(*(HANDLE *)(v3 + 192), v5, v29, &NumberOfBytesWritten, 0);
          else
            v30 = WritePrinter(*(HANDLE *)(v3 + 104), v5, v29, &NumberOfBytesWritten);
          *(_DWORD *)a1[4] = v30;
        }
      }
      else if ( (*(_BYTE *)(v3 + 88) & 8) != 0 )
      {
        if ( *(_DWORD *)(*(_QWORD *)(v3 + 80) + 580LL) )
        {
          LocalSpoolerTelemetry::WriteDbgTraceInfo(
            "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
            L"Job rejected by Defender Rules: Printer %ws",
            *(_QWORD *)(*(_QWORD *)(v3 + 64) + 24LL));
          v31 = *(_DWORD *)a1[3];
          NumberOfBytesWritten = v31;
        }
        else
        {
          v32 = WriteToPrinter((struct _SPOOL *)v3, (unsigned __int8 *)v5, *v14);
          v31 = v32;
          NumberOfBytesWritten = v32;
          if ( v32 )
          {
            v33 = *(_QWORD *)(v3 + 80);
            if ( *(_QWORD *)(v33 + 176) > (signed __int64)(*(_QWORD *)(v33 + 176) + v32)
              && !(unsigned int)ValidRawDatatype(*(_QWORD *)(v33 + 128)) )
            {
              SetLastError(0x216u);
              *(_DWORD *)a1[4] = 0;
              goto LABEL_121;
            }
            *(_QWORD *)(*(_QWORD *)(v3 + 80) + 328LL) = *(_QWORD *)(*(_QWORD *)(v3 + 80) + 176LL);
            *(_QWORD *)(*(_QWORD *)(v3 + 80) + 176LL) += NumberOfBytesWritten;
            EnterSplSem(0);
            if ( *(_DWORD *)&gSendAllNotificationsForJobs
              || (v35 = *(_QWORD *)(v3 + 80), ++*(_DWORD *)(v35 + 448), (*(_BYTE *)(v35 + 448) & 3) == 0) )
            {
              SetPrinterChange(
                *(_QWORD *)(v3 + 64),
                *(_QWORD *)(v3 + 80),
                (unsigned int)NVSpoolJob,
                2048,
                *(_QWORD *)(v3 + 168));
            }
            LeaveSplSem(v34);
            v31 = NumberOfBytesWritten;
          }
        }
        *(_DWORD *)a1[4] = v31;
      }
      else
      {
        EnterSplSem(0);
        v36 = *(_QWORD *)(v3 + 80);
        NumberOfBytesWritten = 0;
        LeaveSplSem(v37);
        if ( v36 )
        {
          if ( *(_DWORD *)(*(_QWORD *)(v3 + 80) + 580LL) )
            goto LABEL_67;
          v38 = (BOOL *)a1[4];
          *v38 = WriteFile(*(HANDLE *)(v36 + 184), lpBuffer, *(_DWORD *)a1[3], &NumberOfBytesWritten, 0);
          if ( NumberOfBytesWritten )
          {
            GetFileSizeEx(*(HANDLE *)(v36 + 184), &FileSize);
            EnterSplSem(0);
            if ( FileSize.HighPart && !(unsigned int)ValidRawDatatype(*(_QWORD *)(*(_QWORD *)(v3 + 80) + 128LL)) )
            {
LABEL_108:
              SetLastError(0x216u);
              goto LABEL_24;
            }
            v40 = *(unsigned int *)(v36 + 304);
            *(union _LARGE_INTEGER *)(v36 + 176) = FileSize;
            if ( (_DWORD)v40 )
            {
              Job = FindJob(*(_QWORD *)(v3 + 64), v40, &v64);
              v42 = Job;
              if ( Job )
              {
                if ( *(_QWORD *)(v36 + 176) > *(_QWORD *)(v36 + 176) + *(_QWORD *)(Job + 176)
                  && !(unsigned int)ValidRawDatatype(*(_QWORD *)(v36 + 128)) )
                {
                  goto LABEL_108;
                }
                if ( IsXPS2GDI((struct INIJOB *)v36) )
                  *(_QWORD *)(v36 + 176) = 0;
                *(_QWORD *)(v36 + 176) += *(_QWORD *)(v42 + 176);
              }
            }
            *(_QWORD *)(v36 + 328) = *(_QWORD *)(v36 + 176);
            LeaveSplSem(v39);
            SeekPrinterSetEvent(v36, 0, 0);
            EnterSplSem(0);
            if ( *(_QWORD *)(v36 + 176) - NumberOfBytesWritten < (__int64)*(unsigned int *)&dwFastPrintSlowDownThreshold
              && *(_QWORD *)(v36 + 176) >= (__int64)*(unsigned int *)&dwFastPrintSlowDownThreshold
              && !*(_QWORD *)(v36 + 224) )
            {
              SetEvent(SchedulerSignal);
            }
            v25 = *(_QWORD **)(v36 + 224);
            if ( v25 )
              SetEvent(v25);
            if ( *(_DWORD *)&gSendAllNotificationsForJobs
              || (++*(_DWORD *)(v36 + 448), (*(_BYTE *)(v36 + 448) & 3) == 0) )
            {
              SetPrinterChange(*(_QWORD *)(v3 + 64), v36, (unsigned int)NVSpoolJob, 2048, *(_QWORD *)(v3 + 168));
            }
            goto LABEL_87;
          }
        }
      }
LABEL_88:
      *(_DWORD *)*a1[2] += NumberOfBytesWritten;
      *(_DWORD *)a1[3] -= NumberOfBytesWritten;
      v43 = NumberOfBytesWritten;
      EnterSplSem(0);
      v44 = *(_QWORD *)(v3 + 80);
      if ( v44 || (v44 = *(_QWORD *)(v3 + 72)) != 0 && (v44 = *(_QWORD *)(v44 + 72)) != 0 )
      {
        v45 = *(_DWORD *)(v44 + 32);
        if ( (v45 & 0x820) != 0 )
        {
          if ( (v45 & 0x800) != 0 )
          {
            SetLastError(0xBCCu);
            goto LABEL_111;
          }
          if ( (v45 & 0x20) != 0 || (*(_BYTE *)(v3 + 88) & 4) != 0 )
          {
            SetLastError(0x3Fu);
            v49 = LocalSpoolerTelemetry::Provider();
            SplTraceErrorPrintCancelled(v49, L"SplWritePrinter: JOB_PENDING_DELETION #3");
LABEL_111:
            *(_DWORD *)a1[4] = 0;
            goto LABEL_122;
          }
        }
        if ( *(_DWORD *)a1[4] && (v45 & 0x1C) != 0 )
          ClearJobError(v44);
      }
      LeaveSplSem(v44);
      if ( !*(_DWORD *)a1[4] && *(_DWORD *)a1[3] && !(unsigned int)UpdateJobStatus(v3) )
        goto LABEL_121;
      v14 = (unsigned int *)a1[3];
      v5 = (char *)lpBuffer + v43;
      lpBuffer = (char *)lpBuffer + v43;
      if ( !*v14 )
        break;
      v12 = v61;
    }
  }
  v50 = *(_DWORD *)*a1[2];
  if ( v50 )
  {
    v51 = *(_QWORD *)(v3 + 80);
    if ( v51 )
    {
      if ( *(_DWORD *)(v51 + 584) )
      {
        v52 = *(_QWORD *)(v51 + 592);
        if ( v52 )
          ArchivePrintJobDataWithDefender(
            *(unsigned __int16 **)(*(_QWORD *)(v3 + 64) + 24LL),
            v52,
            v50,
            (const unsigned __int8 *)*a1[1]);
      }
    }
  }
  if ( NumberOfBytesWritten )
  {
    v53 = *(PrintDAM **)(v3 + 320);
    if ( v53 )
      PrintDAM::UpdateTimer(v53);
  }
  *(_DWORD *)a1[4] = 1;
LABEL_121:
  EnterSplSem(0);
LABEL_122:
  if ( !*(_DWORD *)a1[4] && (*(_BYTE *)(v3 + 88) & 4) != 0 )
    *(_DWORD *)(v3 + 112) |= 0x100u;
  LeaveSplSem(v20);
  if ( !*(_DWORD *)a1[4] )
  {
    LastError = GetLastError();
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "SplWritePrinter::<lambda_d65127ccad260e43b5f02b78e87ee9e3>::operator ()",
      L"WritePrinter failed for handle %p. Error %d",
      **a1,
      LastError);
  }
  v55 = a1[4];
  if ( !*(_DWORD *)v55 )
  {
    LODWORD(v55) = GetLastError();
    if ( (_DWORD)v55 != 3020 )
    {
      LODWORD(v55) = GetLastError();
      if ( (_DWORD)v55 != 63 )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xB16,
          (unsigned int)"printscan\\print\\spooler\\localspl\\spooler.c",
          v56);
    }
  }
  return (int)v55;
}

```

## disassembly

```asm
0x180063e80  push    rbp
0x180063e82  push    rbx
0x180063e83  push    rsi
0x180063e84  push    rdi
0x180063e85  push    r12
0x180063e87  push    r13
0x180063e89  push    r14
0x180063e8b  push    r15
0x180063e8d  mov     rbp, rsp
0x180063e90  sub     rsp, 48h
0x180063e94  mov     rax, [rcx]
0x180063e97  xor     r15d, r15d
0x180063e9a  mov     rsi, rcx
0x180063e9d  mov     [rbp+arg_8], r15d
0x180063ea1  mov     rdi, [rax]
0x180063ea4  mov     rax, [rcx+8]
0x180063ea8  mov     [rbp+NumberOfBytesWritten], r15d
0x180063eac  mov     r14, [rax]
0x180063eaf  mov     rax, qword ptr cs:?LARGE_INTEGER_ZERO@@3T_LARGE_INTEGER@@A; _LARGE_INTEGER LARGE_INTEGER_ZERO ...
0x180063eb6  mov     qword ptr [rbp+FileSize], rax
0x180063eba  mov     rax, [rcx+10h]
0x180063ebe  mov     [rbp+lpBuffer], r14
0x180063ec2  mov     rcx, [rax]
0x180063ec5  mov     [rcx], r15d
0x180063ec8  xor     ecx, ecx
0x180063eca  call    EnterSplSem
0x180063ecf  lea     edx, [r15+10h]
0x180063ed3  mov     rcx, rdi
0x180063ed6  lea     r12, [rdi+70h]
0x180063eda  call    ValidateSpoolHandle
0x180063edf  lea     ebx, [r15+3Fh]
0x180063ee3  test    eax, eax
0x180063ee5  jnz     short loc_180063EF2
0x180063ee7  mov     r15d, 6
0x180063eed  jmp     loc_180064775
0x180063ef2  test    byte ptr [r12], 1
0x180063ef7  jnz     short loc_180063F04
0x180063ef9  mov     r15d, 0BBBh
0x180063eff  jmp     loc_180064775
0x180063f04  test    byte ptr [r12], 10h
0x180063f09  jnz     short loc_180063EF9
0x180063f0b  mov     rax, [rdi+50h]
0x180063f0f  test    rax, rax
0x180063f12  jz      short loc_180063F2D
0x180063f14  test    byte ptr [rdi+58h], 0Ch
0x180063f18  jnz     short loc_180063F2D
0x180063f1a  cmp     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFFFh
0x180063f22  jz      short loc_180063EE7
0x180063f24  test    dword ptr [rax+20h], 8000000h
0x180063f2b  jnz     short loc_180063EE7
0x180063f2d  test    byte ptr [r12], 4
0x180063f32  jz      short loc_180063F48
0x180063f34  mov     r15d, ebx
0x180063f37  call    ?Provider@LocalSpoolerTelemetry@@SAPEBU_tlgProvider_t@@XZ; LocalSpoolerTelemetry::Provider(void)
0x180063f3c  lea     rdx, aSplwriteprinte_1; "SplWritePrinter: SPOOL_STATUS_CANCELLED"
0x180063f43  jmp     loc_18006476D
0x180063f48  test    rax, rax
0x180063f4b  jz      short loc_180063F57
0x180063f4d  test    byte ptr [rax+20h], 20h
0x180063f51  jnz     loc_18006475E
0x180063f57  mov     r8, [rdi+40h]
0x180063f5b  lea     r13, aSplwriteprinte_4; "SplWritePrinter::<lambda_d65127ccad260e"...
0x180063f62  lea     rdx, aPrinterWs_0; "Printer - %ws"
0x180063f69  mov     rcx, r13; char *
0x180063f6c  mov     r8, [r8+18h]
0x180063f70  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180063f75  mov     rbx, [rdi+48h]
0x180063f79  mov     [rbp+var_18], rbx
0x180063f7d  call    LeaveSplSem
0x180063f82  mov     rcx, [rsi+18h]
0x180063f86  mov     [rbp+NumberOfBytesWritten], r15d
0x180063f8a  cmp     [rcx], r15d
0x180063f8d  jz      loc_180064683
0x180063f93  mov     r15d, 0BBBh
0x180063f99  test    byte ptr [rdi+58h], 4
0x180063f9d  jz      loc_18006420E
0x180063fa3  xor     ecx, ecx
0x180063fa5  call    EnterSplSem
0x180063faa  mov     rax, [rdi+40h]
0x180063fae  cmp     dword ptr [rax+134h], 1
0x180063fb5  jbe     loc_18006409E
0x180063fbb  mov     rax, [rdi+48h]
0x180063fbf  test    dword ptr [rax+30h], 20000h
0x180063fc6  jz      loc_18006409E
0x180063fcc  cmp     qword ptr [rbx+0C8h], 0
0x180063fd4  jz      loc_18006409E
0x180063fda  call    LeaveSplSem
0x180063fdf  mov     rax, [rdi+0A8h]
0x180063fe6  mov     rcx, [rbx+0C8h]; hHandle
0x180063fed  imul    edx, [rax+11Ch], 3E8h; dwMilliseconds
0x180063ff7  call    cs:__imp_WaitForSingleObject
0x180063ffd  xor     ecx, ecx
0x180063fff  mov     r14d, eax
0x180064002  call    EnterSplSem
0x180064007  mov     rbx, [rdi+50h]
0x18006400b  test    rbx, rbx
0x18006400e  jnz     short loc_180064022
0x180064010  mov     rbx, [rdi+48h]
0x180064014  test    rbx, rbx
0x180064017  jz      short loc_180064059
0x180064019  mov     rbx, [rbx+48h]
0x18006401d  test    rbx, rbx
0x180064020  jz      short loc_180064059
0x180064022  test    dword ptr [rbx+20h], 820h
0x180064029  jz      short loc_18006405B
0x18006402b  mov     ecx, 3Fh ; '?'; dwErrCode
0x180064030  call    cs:__imp_SetLastError
0x180064036  call    ?Provider@LocalSpoolerTelemetry@@SAPEBU_tlgProvider_t@@XZ; LocalSpoolerTelemetry::Provider(void)
0x18006403b  mov     rcx, rax; struct _tlgProvider_t *
0x18006403e  lea     rdx, aSplwriteprinte_5; "SplWritePrinter: JOB_PENDING_DELETION #"...
0x180064045  call    ?SplTraceErrorPrintCancelled@@YAXPEBU_tlgProvider_t@@PEBG@Z; SplTraceErrorPrintCancelled(_tlgProvider_t const *,ushort const *)
0x18006404a  mov     rax, [rsi+20h]
0x18006404e  mov     dword ptr [rax], 0
0x180064054  jmp     loc_1800646EC
0x180064059  xor     ebx, ebx
0x18006405b  cmp     r14d, 102h
0x180064062  jnz     short loc_180064096
0x180064064  mov     edx, 4; unsigned int
0x180064069  mov     rcx, rbx; this
0x18006406c  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180064071  mov     rcx, [rbx+58h]
0x180064075  lea     r8, NVJobStatus
0x18006407c  mov     r9d, 200h
0x180064082  mov     rdx, rbx
0x180064085  mov     rax, [rcx+118h]
0x18006408c  mov     [rsp+48h+lpOverlapped], rax
0x180064091  call    SetPrinterChange
0x180064096  mov     rbx, [rbp+var_18]
0x18006409a  mov     r14, [rbp+lpBuffer]
0x18006409e  call    LeaveSplSem
0x1800640a3  mov     rax, [rdi+48h]
0x1800640a7  mov     rcx, [rdi+50h]
0x1800640ab  test    dword ptr [rax+30h], 8000h
0x1800640b2  jz      loc_1800641BA
0x1800640b8  test    rcx, rcx
0x1800640bb  jz      short loc_1800640CA
0x1800640bd  cmp     dword ptr [rcx+244h], 0
0x1800640c4  jnz     loc_180064336
0x1800640ca  mov     rcx, rbx
0x1800640cd  call    GetMonitorHandle
0x1800640d2  mov     r10, rax
0x1800640d5  call    GetOpenedMonitor
0x1800640da  test    rax, rax
0x1800640dd  jz      loc_18006460A
0x1800640e3  test    r10, r10
0x1800640e6  jz      loc_18006460A
0x1800640ec  mov     r8, [rsi+18h]
0x1800640f0  lea     r9, [rbp+NumberOfBytesWritten]
0x1800640f4  mov     [rbp+NumberOfBytesWritten], 0
0x1800640fb  mov     rdx, r14
0x1800640fe  mov     rax, [rax+80h]
0x180064105  mov     rcx, r10
0x180064108  mov     r8d, [r8]
0x18006410b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064110  mov     rcx, [rsi+20h]
0x180064114  mov     [rcx], eax
0x180064116  cmp     [rbp+NumberOfBytesWritten], 0
0x18006411a  jz      short loc_180064136
0x18006411c  xor     ecx, ecx
0x18006411e  call    EnterSplSem
0x180064123  mov     rcx, [rdi+40h]
0x180064127  mov     eax, [rbp+NumberOfBytesWritten]
0x18006412a  add     [rcx+0E0h], rax
0x180064131  jmp     loc_1800644EF
0x180064136  mov     rax, [rsi+20h]
0x18006413a  cmp     dword ptr [rax], 0
0x18006413d  jnz     short loc_180064194
0x18006413f  call    cs:__imp_GetLastError
0x180064145  cmp     eax, r15d
0x180064148  jnz     short loc_18006417A
0x18006414a  xor     ecx, ecx
0x18006414c  call    EnterSplSem
0x180064151  mov     rax, [rdi+50h]
0x180064155  test    rax, rax
0x180064158  jnz     short loc_18006416C
0x18006415a  mov     rax, [rdi+48h]
0x18006415e  test    rax, rax
0x180064161  jz      short loc_180064173
0x180064163  mov     rax, [rax+48h]
0x180064167  test    rax, rax
0x18006416a  jz      short loc_180064173
0x18006416c  mov     [rax+0F0h], r15d
0x180064173  call    LeaveSplSem
0x180064178  jmp     short loc_180064194
0x18006417a  cmp     cs:?gbInConnectedStandby@@3HA, 0; int gbInConnectedStandby
0x180064181  jz      short loc_180064194
0x180064183  mov     rax, [rdi+40h]
0x180064187  test    byte ptr [rax+140h], 80h
0x18006418e  jnz     loc_1800645B4
0x180064194  mov     rax, [rsi+20h]
0x180064198  cmp     dword ptr [rax], 0
0x18006419b  jz      loc_1800644F4
0x1800641a1  mov     ecx, cs:dwWritePrinterSleepTime; dwMilliseconds
0x1800641a7  test    ecx, ecx
0x1800641a9  jz      loc_1800644F4
0x1800641af  call    cs:__imp_Sleep
0x1800641b5  jmp     loc_1800644F4
0x1800641ba  test    rcx, rcx
0x1800641bd  jz      short loc_1800641CC
0x1800641bf  cmp     dword ptr [rcx+244h], 0
0x1800641c6  jnz     loc_180064336
0x1800641cc  test    byte ptr [r12], 20h
0x1800641d1  lea     r9, [rbp+NumberOfBytesWritten]; pcWritten
0x1800641d5  mov     rax, [rsi+18h]
0x1800641d9  mov     rdx, r14; pBuf
0x1800641dc  mov     r8d, [rax]; cbBuf
0x1800641df  jz      short loc_1800641F9
0x1800641e1  mov     rcx, [rdi+0C0h]; hFile
0x1800641e8  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x1800641f1  call    cs:__imp_WriteFile
0x1800641f7  jmp     short loc_180064203
0x1800641f9  mov     rcx, [rdi+68h]; hPrinter
0x1800641fd  call    cs:__imp_WritePrinter
0x180064203  mov     rcx, [rsi+20h]
0x180064207  mov     [rcx], eax
0x180064209  jmp     loc_1800644F4
0x18006420e  test    byte ptr [rdi+58h], 8
0x180064212  jz      loc_180064309
0x180064218  mov     rax, [rdi+50h]
0x18006421c  cmp     dword ptr [rax+244h], 0
0x180064223  jz      short loc_18006424A
0x180064225  mov     r8, [rdi+40h]
0x180064229  lea     rdx, aJobRejectedByD; "Job rejected by Defender Rules: Printer"...
0x180064230  mov     rcx, r13; char *
0x180064233  mov     r8, [r8+18h]
0x180064237  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006423c  mov     rax, [rsi+18h]
0x180064240  mov     ecx, [rax]
0x180064242  mov     [rbp+NumberOfBytesWritten], ecx
0x180064245  jmp     loc_1800642FE
0x18006424a  mov     r8d, [rcx]; unsigned int
0x18006424d  mov     rdx, r14; unsigned __int8 *
0x180064250  mov     rcx, rdi; struct _SPOOL *
0x180064253  call    ?WriteToPrinter@@YAKPEAU_SPOOL@@PEAEK@Z; WriteToPrinter(_SPOOL *,uchar *,ulong)
0x180064258  mov     ecx, eax
0x18006425a  mov     [rbp+NumberOfBytesWritten], ecx
0x18006425d  test    eax, eax
0x18006425f  jz      loc_1800642FE
0x180064265  mov     r8, [rdi+50h]
0x180064269  mov     rdx, [r8+0B0h]
0x180064270  lea     rax, [rdx+rcx]
0x180064274  cmp     rdx, rax
0x180064277  jle     short loc_18006428D
0x180064279  mov     rcx, [r8+80h]
0x180064280  call    ValidRawDatatype
0x180064285  test    eax, eax
0x180064287  jz      loc_180064624
0x18006428d  mov     rcx, [rdi+50h]
0x180064291  mov     rax, [rcx+0B0h]
0x180064298  mov     [rcx+148h], rax
0x18006429f  mov     rcx, [rdi+50h]
0x1800642a3  mov     eax, [rbp+NumberOfBytesWritten]
0x1800642a6  add     [rcx+0B0h], rax
0x1800642ad  xor     ecx, ecx
0x1800642af  call    EnterSplSem
0x1800642b4  cmp     cs:gSendAllNotificationsForJobs, 0
0x1800642bb  jnz     short loc_1800642D0
0x1800642bd  mov     rax, [rdi+50h]
0x1800642c1  inc     dword ptr [rax+1C0h]
0x1800642c7  test    byte ptr [rax+1C0h], 3
0x1800642ce  jnz     short loc_1800642F6
0x1800642d0  mov     rax, [rdi+0A8h]
0x1800642d7  lea     r8, NVSpoolJob
0x1800642de  mov     rdx, [rdi+50h]
0x1800642e2  mov     r9d, 800h
0x1800642e8  mov     rcx, [rdi+40h]
0x1800642ec  mov     [rsp+48h+lpOverlapped], rax
0x1800642f1  call    SetPrinterChange
0x1800642f6  call    LeaveSplSem
0x1800642fb  mov     ecx, [rbp+NumberOfBytesWritten]
0x1800642fe  mov     rax, [rsi+20h]
0x180064302  mov     [rax], ecx
0x180064304  jmp     loc_1800644F4
0x180064309  xor     ecx, ecx
0x18006430b  call    EnterSplSem
0x180064310  mov     r14, [rdi+50h]
0x180064314  mov     [rbp+NumberOfBytesWritten], 0
0x18006431b  call    LeaveSplSem
0x180064320  test    r14, r14
0x180064323  jz      loc_1800644F4
0x180064329  mov     rax, [rdi+50h]
0x18006432d  cmp     dword ptr [rax+244h], 0
0x180064334  jz      short loc_18006435B
0x180064336  mov     r8, [rdi+40h]
0x18006433a  lea     rdx, aJobRejectedByD; "Job rejected by Defender Rules: Printer"...
0x180064341  mov     rcx, r13; char *
0x180064344  mov     r8, [r8+18h]
0x180064348  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18006434d  mov     rax, [rsi+18h]
0x180064351  mov     ecx, [rax]
0x180064353  mov     [rbp+NumberOfBytesWritten], ecx
0x180064356  jmp     loc_1800644F4
0x18006435b  mov     r8, [rsi+18h]
0x18006435f  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180064363  mov     rdx, [rbp+lpBuffer]; lpBuffer
0x180064367  mov     rcx, [r14+0B8h]; hFile
0x18006436e  mov     rbx, [rsi+20h]
0x180064372  mov     r8d, [r8]; nNumberOfBytesToWrite
0x180064375  mov     [rsp+48h+lpOverlapped], 0; lpOverlapped
0x18006437e  call    cs:__imp_WriteFile
  ... truncated ...
```
