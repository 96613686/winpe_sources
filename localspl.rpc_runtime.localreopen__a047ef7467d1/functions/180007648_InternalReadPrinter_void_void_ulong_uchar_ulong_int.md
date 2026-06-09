# InternalReadPrinter(void *,void *,ulong,uchar * *,ulong *,int)

- ea: `0x180007648`
- end: `0x180007e8d`
- name: `?InternalReadPrinter@@YAHPEAX0KPEAPEAEPEAKH@Z`
- size: `2117`
- prototype: `__int64 __usercall@<rax>(struct _SPOOL *@<rcx>, void *pBuf@<rdx>, unsigned int@<r8d>, unsigned __int8 **@<r9>, LPDWORD lpNumberOfBytesRead, int)`
- caller_count: `2`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006ba4`
- `0x180067260`

## callees

- `0x1800051f0`
- `0x18000710c`
- `0x180007648`
- `0x180008520`
- `0x180008560`
- `0x180008cb8`
- `0x18000bdb0`
- `0x1800227a4`
- `0x1800237b0`
- `0x180024368`
- `0x18002abf8`
- `0x180044484`
- `0x1800619a8`
- `0x1800653f0`
- `0x18006549c`
- `0x1800cd7b4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800079ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007b99`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800079ee`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180007b99`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800079d7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007b82`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800079d7`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180007b82`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007bd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007be3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e7f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800078dc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007bd1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007be3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007c07`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007e7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a64`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000790b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000797c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007b44`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000790b`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18000797c`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007b44`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800077f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007e1e`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800077f4`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180007e1e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180007827`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800079a2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180007827`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800079a2`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007748`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180007748`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180007754`
- `api-ms-win-security-base-l1-1-0!AreAllAccessesGranted` at `0x180007754`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b12`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007d3e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007b12`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180007d3e`
- `SPOOLSS!ReallocSplStr` at `0x180007a87`
- `SPOOLSS!ReallocSplStr` at `0x180007a87`
- `SPOOLSS!ReadPrinter` at `0x180007e6d`
- `SPOOLSS!ReadPrinter` at `0x180007e6d`

## string_xrefs

- `0x180007bee`: `InternalReadPrinter: JOB_PENDING_DELETION`
- `0x180007c12`: `InternalReadPrinter: SPOOL_STATUS_CANCELLED`
- `0x180007d1c`: `InternalReadPrinter: JOB_PENDING_DELETION #2`

## pseudocode

```c
__int64 __fastcall InternalReadPrinter(
        struct _SPOOL *a1,
        void *pBuf,
        DWORD a3,
        unsigned __int8 **a4,
        LPDWORD lpNumberOfBytesRead,
        int a6)
{
  LPDWORD v6; // rsi
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned int v13; // r14d
  signed __int32 v14; // eax
  LARGE_INTEGER v15; // rcx
  __int64 v16; // rax
  unsigned int File; // ebx
  union _LARGE_INTEGER *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rcx
  DWORD v22; // ecx
  __int64 v23; // rbx
  unsigned __int64 v24; // rax
  __int64 v25; // rbx
  union _LARGE_INTEGER v26; // rax
  __int64 v27; // rcx
  void *v28; // rbx
  __int64 v29; // rcx
  __int64 v30; // rcx
  int v31; // ebx
  __int64 v32; // rsi
  unsigned __int64 v33; // rax
  void *v34; // rbx
  __int64 v35; // rcx
  __int64 v36; // rax
  const struct _tlgProvider_t *v37; // rax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rax
  __int64 v41; // rcx
  const struct _tlgProvider_t *v42; // rax
  __int64 i; // rcx
  __int64 v44; // r8
  __int64 v45; // rcx
  __int64 OpenedMonitor; // rax
  __int64 v48; // r10
  LARGE_INTEGER PerformanceCount; // [rsp+30h] [rbp-40h] BYREF
  union _LARGE_INTEGER NewFilePointer; // [rsp+38h] [rbp-38h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+40h] [rbp-30h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-28h] BYREF
  __int64 v53; // [rsp+50h] [rbp-20h] BYREF
  int v54; // [rsp+58h] [rbp-18h]
  unsigned __int8 **v55; // [rsp+60h] [rbp-10h]
  LPDWORD v56; // [rsp+68h] [rbp-8h]

  v6 = lpNumberOfBytesRead;
  v53 = 0;
  v54 = 0;
  v55 = a4;
  v56 = lpNumberOfBytesRead;
  FileSize.QuadPart = 0;
  NewFilePointer.QuadPart = 0;
  PerformanceCount.LowPart = 0;
  if ( (unsigned __int64)a1 - 1 > 0xFFFFFFFFFFFFFFFDuLL
    || *((char *)a1 + 112) < 0
    || *(_DWORD *)a1 != 17997
    || (*((_DWORD *)a1 + 22) & 0x110) != 0
    || **((_DWORD **)a1 + 21) != 1230196812
    || (*((_BYTE *)a1 + 88) & 1) != 0 && **((_DWORD **)a1 + 8) != 18769 )
  {
    v22 = 6;
LABEL_36:
    SetLastError(v22);
    return 0;
  }
  if ( (*((_BYTE *)a1 + 112) & 4) != 0 )
  {
    SetLastError(0x3Fu);
    v37 = LocalSpoolerTelemetry::Provider();
    v38 = L"InternalReadPrinter: SPOOL_STATUS_CANCELLED";
    goto LABEL_66;
  }
  if ( lpNumberOfBytesRead )
    *lpNumberOfBytesRead = 0;
  if ( a6 && (*((_DWORD *)a1 + 22) & 0xA) != 2 )
  {
    v22 = 50;
    goto LABEL_36;
  }
  if ( (*((_BYTE *)a1 + 88) & 2) == 0 )
  {
    if ( (*((_BYTE *)a1 + 88) & 4) != 0 )
    {
      v44 = *((_QWORD *)a1 + 10);
      if ( v44 && !(unsigned int)ValidateObjectAccess(2, 131104, v44, 0, *((_QWORD *)a1 + 21), 1) )
      {
LABEL_93:
        v22 = 5;
        goto LABEL_36;
      }
      v45 = *((_QWORD *)a1 + 9);
      if ( (*(_DWORD *)(v45 + 48) & 0x10000) != 0 )
        return ReadFile(*((HANDLE *)a1 + 27), pBuf, a3, lpNumberOfBytesRead, 0);
      if ( (*(_DWORD *)(v45 + 48) & 0x8000) == 0 )
        return ReadPrinter(*((HANDLE *)a1 + 13), pBuf, a3, lpNumberOfBytesRead);
      GetMonitorHandle();
      OpenedMonitor = GetOpenedMonitor();
      if ( OpenedMonitor && v48 )
        return (unsigned int)(*(__int64 (__fastcall **)(__int64, void *, _QWORD, LPDWORD))(OpenedMonitor + 136))(
                               v48,
                               pBuf,
                               a3,
                               lpNumberOfBytesRead);
    }
    SetLastError(6u);
    return 0;
  }
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 10) + 32LL) & 0x820) != 0 )
  {
    SetLastError(0x3Fu);
    v37 = LocalSpoolerTelemetry::Provider();
    v38 = L"InternalReadPrinter: JOB_PENDING_DELETION";
LABEL_66:
    SplTraceErrorPrintCancelled(v37, v38);
    return 0;
  }
  if ( (*((_BYTE *)a1 + 88) & 8) != 0 )
  {
    *lpNumberOfBytesRead = ReadFromPrinter(a1, (unsigned __int8 *)pBuf, a3);
    return 1;
  }
  v10 = *((_QWORD *)a1 + 21);
  AccessMask = 131104;
  if ( (*(_BYTE *)(v10 + 168) & 0x20) != 0 )
  {
    MapGenericMask(&AccessMask, &GenericMapping);
    if ( !AreAllAccessesGranted(*((_DWORD *)a1 + 29), AccessMask) )
      goto LABEL_93;
  }
  EnterSplSem(0);
  while ( 1 )
  {
    v11 = *((_QWORD *)a1 + 10);
    v12 = v11;
    if ( !*(_QWORD *)(v11 + 224) )
      break;
    if ( (*(_BYTE *)(v11 + 32) & 0x40) == 0 )
      break;
    SetFilePointerEx(*((HANDLE *)a1 + 27), LARGE_INTEGER_ZERO, &NewFilePointer, 1u);
    v12 = *((_QWORD *)a1 + 10);
    if ( NewFilePointer.QuadPart < *(_QWORD *)(v12 + 328) )
      break;
    GetFileSizeEx(*((HANDLE *)a1 + 27), &FileSize);
    v25 = *((_QWORD *)a1 + 10);
    v26 = FileSize;
    v27 = *(_QWORD *)(v25 + 176);
    if ( v27 == FileSize.QuadPart )
    {
      if ( (*(_DWORD *)(v25 + 32) & 0x800820) != 0 )
      {
        SetLastError(0x3Fu);
        v42 = LocalSpoolerTelemetry::Provider();
        SplTraceErrorPrintCancelled(v42, L"InternalReadPrinter: JOB_PENDING_DELETION #2");
        goto LABEL_81;
      }
      v28 = *(void **)(v25 + 224);
      ResetEvent(v28);
      LeaveSplSem(v29);
      LODWORD(v28) = WaitForSingleObjectEx(v28, dwFastPrintWaitTimeout, 0);
      EnterSplSem(0);
      if ( (_DWORD)v28 == 258 )
      {
        INIJOB::SetJobStatusFlags(*((INIJOB **)a1 + 10), 0x400000u);
        SeekPrinterSetEvent(*((_QWORD *)a1 + 10), 0, 1);
        v30 = *(_QWORD *)(*((_QWORD *)a1 + 10) + 248LL);
        if ( !v30 || AssignFreeJobToFreePort(v30, &PerformanceCount, 0) )
        {
          INIJOB::SetJobStatusFlags(*((INIJOB **)a1 + 10), 0x800000u);
          CloseHandle(*(HANDLE *)(*((_QWORD *)a1 + 10) + 224LL));
          *(_QWORD *)(*((_QWORD *)a1 + 10) + 224LL) = 0;
          ReallocSplStr(*((_QWORD *)a1 + 10) + 192LL, szFastPrintTimeout);
          SetPrinterChange(
            *(_QWORD *)(*((_QWORD *)a1 + 10) + 88LL),
            *((_QWORD *)a1 + 10),
            (unsigned int)NVJobStatusAndString,
            512,
            *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 88LL) + 280LL));
          v31 = dwFastPrintWaitTimeout;
          v32 = *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 10) + 88LL) + 24LL);
          GetSpoolerNumericPolicy(L"ShowJobTitleInEventLogs");
          LogJobInfo((struct _EVENT_DESCRIPTOR *)&MSG_DOCUMENT_TIMEOUT, v32, v31);
          SetLastError(0x79u);
LABEL_81:
          LeaveSplSem(v41);
          return 0;
        }
      }
    }
    else
    {
      v39 = *(_QWORD *)(v25 + 328);
      if ( (*(_DWORD *)(v25 + 32) & 0x80000) != 0 )
      {
        *(_QWORD *)(v25 + 328) = v27;
      }
      else
      {
        if ( (*(_DWORD *)(v25 + 32) & 0x8000000) != 0 )
          goto LABEL_76;
        *(union _LARGE_INTEGER *)(v25 + 328) = FileSize;
      }
      v26 = FileSize;
LABEL_76:
      *(union _LARGE_INTEGER *)(*((_QWORD *)a1 + 10) + 176LL) = v26;
      v40 = *((_QWORD *)a1 + 10);
      if ( v39 != *(_QWORD *)(v40 + 328) )
      {
        if ( *(_DWORD *)&gSendAllNotificationsForJobs || (++*(_DWORD *)(v40 + 452), (*(_BYTE *)(v40 + 452) & 0xF) == 0) )
          SetPrinterChange(
            *((_QWORD *)a1 + 8),
            *((_QWORD *)a1 + 10),
            (unsigned int)NVSpoolJob,
            2048,
            *((_QWORD *)a1 + 21));
      }
    }
  }
  v13 = a3;
  _m_prefetchw((const void *)(v12 + 32));
  v14 = _InterlockedAnd((volatile signed __int32 *)(v12 + 32), 0xFF3FFFFF);
  v15.QuadPart = *(_DWORD *)(v12 + 32) & 0xFF3FFFFF;
  if ( v14 != v15.LowPart )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 616));
    if ( (v15.LowPart & 1) != 0 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v15 = PerformanceCount;
      _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 624), PerformanceCount.QuadPart, 0);
    }
    else if ( (v15.LowPart & 0x400) != 0 )
    {
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v15 = PerformanceCount;
      _InterlockedCompareExchange64((volatile signed __int64 *)(v12 + 632), PerformanceCount.QuadPart, 0);
    }
  }
  v16 = *((_QWORD *)a1 + 10);
  if ( *(_QWORD *)(v16 + 224) && (*(_BYTE *)(v16 + 32) & 0x40) != 0 )
  {
    SetFilePointerEx(*((HANDLE *)a1 + 27), LARGE_INTEGER_ZERO, &NewFilePointer, 1u);
    v23 = *((_QWORD *)a1 + 10);
    if ( (unsigned __int64)*(unsigned int *)&dwFastPrintSlowDownThreshold >= *(_QWORD *)(v23 + 176)
                                                                           - NewFilePointer.QuadPart )
    {
      v34 = *(void **)(v23 + 224);
      v13 = 1;
      ResetEvent(v34);
      LeaveSplSem(v35);
      WaitForSingleObjectEx(v34, dwFastPrintThrottleTimeout, 0);
      EnterSplSem(0);
    }
    else
    {
      v24 = *(_QWORD *)(v23 + 176) - NewFilePointer.QuadPart - *(unsigned int *)&dwFastPrintSlowDownThreshold;
      v15.QuadPart = HIDWORD(v24);
      if ( HIDWORD(v24) )
        LODWORD(v24) = -1;
      if ( a3 > (unsigned int)v24 )
        v13 = v24;
    }
  }
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 10) + 32LL) & 0x40) != 0 )
  {
    SetFilePointerEx(*((HANDLE *)a1 + 27), LARGE_INTEGER_ZERO, &NewFilePointer, 1u);
    v33 = *(_QWORD *)(*((_QWORD *)a1 + 10) + 328LL) - NewFilePointer.QuadPart;
    v15.QuadPart = HIDWORD(v33);
    if ( HIDWORD(v33) )
      LODWORD(v33) = -1;
    if ( v13 > (unsigned int)v33 )
      v13 = v33;
  }
  ((void (__fastcall *)(_QWORD))LeaveSplSem)((LARGE_INTEGER)v15.QuadPart);
  if ( a6 )
  {
    if ( a3 == v13 )
    {
      File = SetMappingPointer(a1, v55, v13);
      if ( File )
        *lpNumberOfBytesRead = v13;
    }
    else
    {
      File = 0;
    }
  }
  else
  {
    File = ReadFile(*((HANDLE *)a1 + 27), pBuf, v13, lpNumberOfBytesRead, 0);
  }
  if ( (*(_BYTE *)(*((_QWORD *)a1 + 10) + 32LL) & 1) != 0 && *lpNumberOfBytesRead )
  {
    GetFileSizeEx(*((HANDLE *)a1 + 27), &FileSize);
    if ( __OFSUB__(
           *(_QWORD *)(*((_QWORD *)a1 + 10) + 296LL) + *lpNumberOfBytesRead,
           *(_QWORD *)(*((_QWORD *)a1 + 10) + 296LL))
      || *(_QWORD *)(*((_QWORD *)a1 + 10) + 296LL) + *lpNumberOfBytesRead == *(_QWORD *)(*((_QWORD *)a1 + 10) + 296LL) )
    {
      SetLastError(0x216u);
      File = 0;
    }
    else
    {
      EnterSplSem(0);
      v19 = (union _LARGE_INTEGER *)*((_QWORD *)a1 + 10);
      v54 = dword_18013DE50;
      v53 = NVWriteJob;
      if ( v19[22].QuadPart < FileSize.QuadPart )
      {
        v19[22] = FileSize;
        for ( i = 0; i != 3; ++i )
          *((_DWORD *)&v53 + i) |= *((_DWORD *)NVSpoolJob + i);
        v6 = v56;
      }
      *(_QWORD *)(*((_QWORD *)a1 + 10) + 296LL) += *v6;
    }
    v20 = *((_QWORD *)a1 + 10);
    v21 = *(_QWORD *)(v20 + 176);
    if ( *(_QWORD *)(v20 + 296) > v21 )
      *(_QWORD *)(v20 + 296) = v21;
    if ( *(_DWORD *)&gSendAllNotificationsForJobs
      || (v36 = *((_QWORD *)a1 + 10), ++*(_DWORD *)(v36 + 452), (*(_BYTE *)(v36 + 452) & 0xF) == 0) )
    {
      SetPrinterChange(*((_QWORD *)a1 + 8), *((_QWORD *)a1 + 10), (unsigned int)&v53, 2048, *((_QWORD *)a1 + 21));
    }
    LeaveSplSem(v21);
  }
  return File;
}

```

## disassembly

```asm
0x180007648  push    rbp
0x18000764a  push    rbx
0x18000764b  push    rsi
0x18000764c  push    rdi
0x18000764d  push    r12
0x18000764f  push    r14
0x180007651  push    r15
0x180007653  mov     rbp, rsp
0x180007656  sub     rsp, 70h
0x18000765a  mov     rsi, [rbp+lpNumberOfBytesRead]
0x18000765e  xor     eax, eax
0x180007660  xor     r14d, r14d
0x180007663  mov     [rbp+var_20], rax
0x180007667  mov     [rbp+var_18], eax
0x18000766a  mov     r15d, r8d
0x18000766d  lea     rax, [rcx-1]
0x180007671  mov     [rbp+var_10], r9
0x180007675  mov     [rbp+var_8], rsi
0x180007679  mov     r12, rdx
0x18000767c  mov     qword ptr [rbp+FileSize], r14
0x180007680  mov     rdi, rcx
0x180007683  mov     qword ptr [rbp+NewFilePointer], r14
0x180007687  mov     dword ptr [rbp+PerformanceCount], r14d
0x18000768b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000768f  ja      loc_1800078D7
0x180007695  test    byte ptr [rcx+70h], 80h
0x180007699  jnz     loc_1800078D7
0x18000769f  cmp     dword ptr [rcx], 464Dh
0x1800076a5  jnz     loc_1800078D7
0x1800076ab  test    dword ptr [rcx+58h], 110h
0x1800076b2  jnz     loc_1800078D7
0x1800076b8  mov     rax, [rcx+0A8h]
0x1800076bf  cmp     dword ptr [rax], 4953504Ch
0x1800076c5  jnz     loc_1800078D7
0x1800076cb  test    byte ptr [rcx+58h], 1
0x1800076cf  jz      short loc_1800076E1
0x1800076d1  mov     rax, [rcx+40h]
0x1800076d5  cmp     dword ptr [rax], 4951h
0x1800076db  jnz     loc_1800078D7
0x1800076e1  test    byte ptr [rcx+70h], 4
0x1800076e5  jnz     loc_180007C02
0x1800076eb  test    rsi, rsi
0x1800076ee  jz      short loc_1800076F3
0x1800076f0  mov     [rsi], r14d
0x1800076f3  mov     ecx, 2
0x1800076f8  cmp     [rbp+arg_28], r14d
0x1800076fc  jnz     loc_180007C1B
0x180007702  test    [rdi+58h], cl
0x180007705  jz      loc_180007DBA
0x18000770b  mov     rax, [rdi+50h]
0x18000770f  test    dword ptr [rax+20h], 820h
0x180007716  jnz     loc_180007BDE
0x18000771c  test    byte ptr [rdi+58h], 8
0x180007720  jnz     loc_180007C32
0x180007726  mov     rax, [rdi+0A8h]
0x18000772d  mov     [rbp+AccessMask], 20020h
0x180007734  test    byte ptr [rax+0A8h], 20h
0x18000773b  jz      short loc_180007762
0x18000773d  lea     rdx, GenericMapping; GenericMapping
0x180007744  lea     rcx, [rbp+AccessMask]; AccessMask
0x180007748  call    cs:__imp_MapGenericMask
0x18000774e  mov     edx, [rbp+AccessMask]; DesiredAccess
0x180007751  mov     ecx, [rdi+74h]; GrantedAccess
0x180007754  call    cs:__imp_AreAllAccessesGranted
0x18000775a  test    eax, eax
0x18000775c  jz      loc_180007DF2
0x180007762  xor     ecx, ecx
0x180007764  call    EnterSplSem
0x180007769  mov     rax, [rdi+50h]
0x18000776d  mov     rbx, rax
0x180007770  cmp     [rax+0E0h], r14
0x180007777  jnz     loc_18000795A
0x18000777d  mov     r14d, r15d
0x180007780  prefetchw byte ptr [rbx+20h]
0x180007784  mov     eax, [rbx+20h]
0x180007787  mov     ecx, eax
0x180007789  and     ecx, 0FF3FFFFFh
0x18000778f  lock cmpxchg [rbx+20h], ecx
0x180007794  jnz     short loc_180007787
0x180007796  mov     ecx, [rbx+20h]
0x180007799  and     ecx, 0FF3FFFFFh
0x18000779f  cmp     eax, ecx
0x1800077a1  jnz     loc_180007AEC
0x1800077a7  mov     rax, [rdi+50h]
0x1800077ab  mov     ebx, 0FFFFFFFFh
0x1800077b0  cmp     qword ptr [rax+0E0h], 0
0x1800077b8  jnz     loc_1800078E9
0x1800077be  mov     rax, [rdi+50h]
0x1800077c2  test    byte ptr [rax+20h], 40h
0x1800077c6  jnz     loc_180007B2C
0x1800077cc  call    LeaveSplSem
0x1800077d1  cmp     [rbp+arg_28], 0
0x1800077d5  jnz     loc_180007D58
0x1800077db  mov     rcx, [rdi+0D8h]; hFile
0x1800077e2  mov     r9, rsi; lpNumberOfBytesRead
0x1800077e5  mov     r8d, r14d; nNumberOfBytesToRead
0x1800077e8  mov     [rsp+70h+lpOverlapped], 0; lpOverlapped
0x1800077f1  mov     rdx, r12; lpBuffer
0x1800077f4  call    cs:__imp_ReadFile
0x1800077fa  mov     ebx, eax
0x1800077fc  mov     rax, [rdi+50h]
0x180007800  test    byte ptr [rax+20h], 1
0x180007804  jnz     short loc_180007817
0x180007806  mov     eax, ebx
0x180007808  add     rsp, 70h
0x18000780c  pop     r15
0x18000780e  pop     r14
0x180007810  pop     r12
0x180007812  pop     rdi
0x180007813  pop     rsi
0x180007814  pop     rbx
0x180007815  pop     rbp
0x180007816  retn
0x180007817  cmp     dword ptr [rsi], 0
0x18000781a  jz      short loc_180007806
0x18000781c  mov     rcx, [rdi+0D8h]; hFile
0x180007823  lea     rdx, [rbp+FileSize]; lpFileSize
0x180007827  call    cs:__imp_GetFileSizeEx
0x18000782d  mov     rax, [rdi+50h]
0x180007831  mov     rcx, [rax+128h]
0x180007838  mov     eax, [rsi]
0x18000783a  add     rax, rcx
0x18000783d  cmp     rax, rcx
0x180007840  jle     loc_180007BCC
0x180007846  xor     ecx, ecx
0x180007848  call    EnterSplSem
0x18000784d  mov     eax, cs:dword_18013DE50
0x180007853  mov     rcx, [rdi+50h]
0x180007857  movsd   xmm0, cs:NVWriteJob
0x18000785f  mov     [rbp+var_18], eax
0x180007862  mov     rax, qword ptr [rbp+FileSize]
0x180007866  movsd   [rbp+var_20], xmm0
0x18000786b  cmp     [rcx+0B0h], rax
0x180007872  jl      loc_180007D85
0x180007878  mov     rcx, [rdi+50h]
0x18000787c  mov     eax, [rsi]
0x18000787e  add     [rcx+128h], rax
0x180007885  mov     rax, [rdi+50h]
0x180007889  mov     rcx, [rax+0B0h]
0x180007890  cmp     [rax+128h], rcx
0x180007897  jg      loc_180007DAE
0x18000789d  cmp     cs:gSendAllNotificationsForJobs, 0
0x1800078a4  jz      loc_180007BB0
0x1800078aa  mov     rax, [rdi+0A8h]
0x1800078b1  lea     r8, [rbp+var_20]
0x1800078b5  mov     rdx, [rdi+50h]
0x1800078b9  mov     r9d, 800h
0x1800078bf  mov     rcx, [rdi+40h]
0x1800078c3  mov     [rsp+70h+lpOverlapped], rax
0x1800078c8  call    SetPrinterChange
0x1800078cd  call    LeaveSplSem
0x1800078d2  jmp     loc_180007806
0x1800078d7  mov     ecx, 6; dwErrCode
0x1800078dc  call    cs:__imp_SetLastError
0x1800078e2  xor     eax, eax
0x1800078e4  jmp     loc_180007808
0x1800078e9  test    byte ptr [rax+20h], 40h
0x1800078ed  jz      loc_1800077BE
0x1800078f3  mov     rdx, qword ptr cs:?LARGE_INTEGER_ZERO@@3T_LARGE_INTEGER@@A; liDistanceToMove
0x1800078fa  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x1800078fe  mov     rcx, [rdi+0D8h]; hFile
0x180007905  mov     r9d, 1; dwMoveMethod
0x18000790b  call    cs:__imp_SetFilePointerEx
0x180007911  mov     rbx, [rdi+50h]
0x180007915  mov     edx, cs:dwFastPrintSlowDownThreshold
0x18000791b  mov     rax, [rbx+0B0h]
0x180007922  sub     rax, qword ptr [rbp+NewFilePointer]
0x180007926  mov     rcx, rax
0x180007929  sar     rcx, 20h
0x18000792d  test    ecx, ecx
0x18000792f  jnz     short loc_180007939
0x180007931  cmp     edx, eax
0x180007933  jnb     loc_180007B72
0x180007939  sub     rax, rdx
0x18000793c  mov     ebx, 0FFFFFFFFh
0x180007941  mov     rcx, rax
0x180007944  shr     rcx, 20h
0x180007948  test    ecx, ecx
0x18000794a  cmovnz  rax, rbx
0x18000794e  cmp     r15d, eax
0x180007951  cmova   r14d, eax
0x180007955  jmp     loc_1800077BE
0x18000795a  test    byte ptr [rax+20h], 40h
0x18000795e  jz      loc_18000777D
0x180007964  mov     rdx, qword ptr cs:?LARGE_INTEGER_ZERO@@3T_LARGE_INTEGER@@A; liDistanceToMove
0x18000796b  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x18000796f  mov     rcx, [rdi+0D8h]; hFile
0x180007976  mov     r9d, 1; dwMoveMethod
0x18000797c  call    cs:__imp_SetFilePointerEx
0x180007982  mov     rbx, [rdi+50h]
0x180007986  mov     rax, [rbx+148h]
0x18000798d  cmp     qword ptr [rbp+NewFilePointer], rax
0x180007991  jl      loc_18000777D
0x180007997  mov     rcx, [rdi+0D8h]; hFile
0x18000799e  lea     rdx, [rbp+FileSize]; lpFileSize
0x1800079a2  call    cs:__imp_GetFileSizeEx
0x1800079a8  mov     rbx, [rdi+50h]
0x1800079ac  mov     rax, qword ptr [rbp+FileSize]
0x1800079b0  mov     rcx, [rbx+0B0h]
0x1800079b7  cmp     rcx, rax
0x1800079ba  jnz     loc_180007C46
0x1800079c0  test    dword ptr [rbx+20h], 800820h
0x1800079c7  jnz     loc_180007D09
0x1800079cd  mov     rbx, [rbx+0E0h]
0x1800079d4  mov     rcx, rbx; hEvent
0x1800079d7  call    cs:__imp_ResetEvent
0x1800079dd  call    LeaveSplSem
0x1800079e2  mov     edx, cs:dwFastPrintWaitTimeout; dwMilliseconds
0x1800079e8  xor     r8d, r8d; bAlertable
0x1800079eb  mov     rcx, rbx; hHandle
0x1800079ee  call    cs:__imp_WaitForSingleObjectEx
0x1800079f4  xor     ecx, ecx
0x1800079f6  mov     ebx, eax
0x1800079f8  call    EnterSplSem
0x1800079fd  cmp     ebx, 102h
0x180007a03  jnz     loc_180007769
0x180007a09  mov     rcx, [rdi+50h]; this
0x180007a0d  mov     edx, 400000h; unsigned int
0x180007a12  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180007a17  mov     rcx, [rdi+50h]
0x180007a1b  xor     edx, edx
0x180007a1d  lea     r8d, [rdx+1]
0x180007a21  call    SeekPrinterSetEvent
0x180007a26  mov     rax, [rdi+50h]
0x180007a2a  mov     rcx, [rax+0F8h]
0x180007a31  test    rcx, rcx
0x180007a34  jz      short loc_180007A4B
0x180007a36  xor     r8d, r8d
0x180007a39  lea     rdx, [rbp+PerformanceCount]
0x180007a3d  call    AssignFreeJobToFreePort
0x180007a42  test    rax, rax
0x180007a45  jz      loc_180007769
0x180007a4b  mov     rcx, [rdi+50h]; this
0x180007a4f  mov     edx, 800000h; unsigned int
0x180007a54  call    ?SetJobStatusFlags@INIJOB@@QEAAXK@Z; INIJOB::SetJobStatusFlags(ulong)
0x180007a59  mov     rcx, [rdi+50h]
0x180007a5d  mov     rcx, [rcx+0E0h]; hObject
0x180007a64  call    cs:__imp_CloseHandle
0x180007a6a  mov     rax, [rdi+50h]
0x180007a6e  mov     [rax+0E0h], r14
0x180007a75  mov     rcx, [rdi+50h]
0x180007a79  mov     rdx, cs:szFastPrintTimeout
0x180007a80  add     rcx, 0C0h
0x180007a87  call    cs:__imp_ReallocSplStr
0x180007a8d  mov     rdx, [rdi+50h]
0x180007a91  lea     r8, NVJobStatusAndString
0x180007a98  mov     r9d, 200h
0x180007a9e  mov     rcx, [rdx+58h]
0x180007aa2  mov     rax, [rcx+118h]
0x180007aa9  mov     [rsp+70h+lpOverlapped], rax
0x180007aae  call    SetPrinterChange
0x180007ab3  mov     rcx, [rdi+50h]
0x180007ab7  xor     edx, edx
0x180007ab9  mov     ebx, cs:dwFastPrintWaitTimeout
0x180007abf  mov     rax, [rcx+58h]
0x180007ac3  mov     r14, [rcx+38h]
0x180007ac7  lea     rcx, aShowjobtitlein; "ShowJobTitleInEventLogs"
0x180007ace  mov     rsi, [rax+18h]
0x180007ad2  call    GetSpoolerNumericPolicy
0x180007ad7  test    eax, eax
0x180007ad9  jz      loc_180007CD6
0x180007adf  mov     rax, [rdi+50h]
0x180007ae3  mov     r8, [rax+48h]
0x180007ae7  jmp     loc_180007CDD
0x180007aec  lock inc dword ptr [rbx+268h]
0x180007af3  test    cl, 1
0x180007af6  jnz     loc_180007D32
0x180007afc  bt      ecx, 0Ah
0x180007b00  jnb     loc_1800077A7
0x180007b06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180007b0a  mov     qword ptr [rbp+PerformanceCount], 0
0x180007b12  call    cs:__imp_QueryPerformanceCounter
0x180007b18  mov     rcx, qword ptr [rbp+PerformanceCount]
0x180007b1c  xor     eax, eax
0x180007b1e  lock cmpxchg [rbx+278h], rcx
0x180007b27  jmp     loc_1800077A7
0x180007b2c  mov     rdx, qword ptr cs:?LARGE_INTEGER_ZERO@@3T_LARGE_INTEGER@@A; liDistanceToMove
0x180007b33  lea     r8, [rbp+NewFilePointer]; lpNewFilePointer
0x180007b37  mov     rcx, [rdi+0D8h]; hFile
0x180007b3e  mov     r9d, 1; dwMoveMethod
0x180007b44  call    cs:__imp_SetFilePointerEx
0x180007b4a  mov     rax, [rdi+50h]
0x180007b4e  mov     rax, [rax+148h]
0x180007b55  sub     rax, qword ptr [rbp+NewFilePointer]
0x180007b59  mov     rcx, rax
0x180007b5c  shr     rcx, 20h
0x180007b60  test    ecx, ecx
0x180007b62  cmovnz  rax, rbx
0x180007b66  cmp     r14d, eax
0x180007b69  cmova   r14d, eax
0x180007b6d  jmp     loc_1800077CC
0x180007b72  mov     rbx, [rbx+0E0h]
0x180007b79  mov     r14d, 1
0x180007b7f  mov     rcx, rbx; hEvent
0x180007b82  call    cs:__imp_ResetEvent
0x180007b88  call    LeaveSplSem
0x180007b8d  mov     edx, cs:dwFastPrintThrottleTimeout; dwMilliseconds
0x180007b93  xor     r8d, r8d; bAlertable
0x180007b96  mov     rcx, rbx; hHandle
0x180007b99  call    cs:__imp_WaitForSingleObjectEx
  ... truncated ...
```
