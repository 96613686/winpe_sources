# AsyncEventsThread

- ea: `0x1800890b0`
- end: `0x180089a0d`
- name: `AsyncEventsThread`
- size: `2397`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800755b8`
- `0x1800890b0`
- `0x18008aa50`
- `0x18008f50c`
- `0x18008f954`
- `0x180090714`
- `0x180092a92`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18008972e`
- `KERNEL32!DeleteCriticalSection` at `0x18008972e`
- `KERNEL32!DeviceIoControl` at `0x180089162`
- `KERNEL32!DeviceIoControl` at `0x18008944c`
- `KERNEL32!DeviceIoControl` at `0x180089162`
- `KERNEL32!DeviceIoControl` at `0x18008944c`
- `KERNEL32!Sleep` at `0x180089337`
- `KERNEL32!Sleep` at `0x1800894e8`
- `KERNEL32!Sleep` at `0x180089337`
- `KERNEL32!Sleep` at `0x1800894e8`
- `KERNEL32!GetProcessHeap` at `0x18008973a`
- `KERNEL32!GetProcessHeap` at `0x18008973a`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180089229`
- `KERNEL32!GetQueuedCompletionStatus` at `0x180089229`
- `KERNEL32!GetLastError` at `0x180089177`
- `KERNEL32!GetLastError` at `0x1800892b2`
- `KERNEL32!GetLastError` at `0x180089461`
- `KERNEL32!GetLastError` at `0x180089177`
- `KERNEL32!GetLastError` at `0x1800892b2`
- `KERNEL32!GetLastError` at `0x180089461`
- `KERNEL32!LeaveCriticalSection` at `0x18008971f`
- `KERNEL32!LeaveCriticalSection` at `0x18008975c`
- `KERNEL32!LeaveCriticalSection` at `0x18008971f`
- `KERNEL32!LeaveCriticalSection` at `0x18008975c`
- `KERNEL32!EnterCriticalSection` at `0x18008970a`
- `KERNEL32!EnterCriticalSection` at `0x18008970a`
- `KERNEL32!HeapFree` at `0x18008974e`
- `KERNEL32!HeapFree` at `0x18008974e`
- `rtutils!TracePrintfA` at `0x1800891e9`
- `rtutils!TracePrintfA` at `0x1800892a1`
- `rtutils!TracePrintfA` at `0x180089326`
- `rtutils!TracePrintfA` at `0x180089399`
- `rtutils!TracePrintfA` at `0x1800894d7`
- `rtutils!TracePrintfA` at `0x180089555`
- `rtutils!TracePrintfA` at `0x1800895b8`
- `rtutils!TracePrintfA` at `0x180089649`
- `rtutils!TracePrintfA` at `0x1800896d5`
- `rtutils!TracePrintfA` at `0x1800897cb`
- `rtutils!TracePrintfA` at `0x18008987c`
- `rtutils!TracePrintfA` at `0x1800898f3`
- `rtutils!TracePrintfA` at `0x18008997f`
- `rtutils!TracePrintfA` at `0x1800899f2`
- `rtutils!TracePrintfA` at `0x1800891e9`
- `rtutils!TracePrintfA` at `0x1800892a1`
- `rtutils!TracePrintfA` at `0x180089326`
- `rtutils!TracePrintfA` at `0x180089399`
- `rtutils!TracePrintfA` at `0x1800894d7`
- `rtutils!TracePrintfA` at `0x180089555`
- `rtutils!TracePrintfA` at `0x1800895b8`
- `rtutils!TracePrintfA` at `0x180089649`
- `rtutils!TracePrintfA` at `0x1800896d5`
- `rtutils!TracePrintfA` at `0x1800897cb`
- `rtutils!TracePrintfA` at `0x18008987c`
- `rtutils!TracePrintfA` at `0x1800898f3`
- `rtutils!TracePrintfA` at `0x18008997f`
- `rtutils!TracePrintfA` at `0x1800899f2`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180089a00`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180089a00`

## string_xrefs

- `0x1800891a4`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x180089960`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x1800891e2`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x180089273`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x180089978`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x1800892e1`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x18008929a`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x1800899aa`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x18008931f`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x180089372`: `AsyncEventsThread: Got a line event`
- `0x1800899eb`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x180089492`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x180089392`: `AsyncEventsThread: Got a line event`
- `0x180089526`: `AsyncEventsThread: Got a completed request`
- `0x1800894d0`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x180089589`: `AsyncEventsThread: Got a bogus request`
- `0x18008954e`: `AsyncEventsThread: Got a completed request`
- `0x1800895fd`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x1800895b1`: `AsyncEventsThread: Got a bogus request`
- `0x18008968d`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x180089642`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x1800897a0`: `AsyncEventsThread: Report back the saved call state`
- `0x1800896cb`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x1800897f5`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x1800897c4`: `AsyncEventsThread: Report back the saved call state`
- `0x1800898ba`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180089857`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x1800898ec`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`

## pseudocode

```c
void __fastcall __noreturn AsyncEventsThread(PVOID Parameter)
{
  LPVOID v1; // rdx
  HANDLE v2; // rcx
  DWORD LastError; // eax
  LPOVERLAPPED v4; // rbx
  DWORD v5; // eax
  LPVOID v6; // r9
  unsigned int v7; // edi
  __int64 v8; // rax
  struct _EVENT_RECORD *v9; // rbx
  HANDLE v10; // rcx
  DWORD v11; // eax
  __int64 v12; // rdx
  DWORD v13; // ecx
  const wchar_t *v14; // r8
  __int64 hEvent_low; // rsi
  unsigned int v16; // eax
  __int64 v17; // rdi
  void (__fastcall *InternalHigh)(LPOVERLAPPED, _QWORD, _OWORD *); // rax
  bool v19; // zf
  struct _RTL_CRITICAL_SECTION *v20; // rcx
  HANDLE ProcessHeap; // rax
  const void *v22; // rdi
  unsigned int Lock; // eax
  __int64 v24; // rbx
  __int64 v25; // rdx
  const wchar_t *v26; // r8
  __int64 lpOutBuffer; // [rsp+28h] [rbp-E0h]
  DWORD BytesReturned[2]; // [rsp+48h] [rbp-C0h] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+50h] [rbp-B8h] BYREF
  LPOVERLAPPED v30; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int64 CompletionKey; // [rsp+60h] [rbp-A8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD v33[3]; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v35[2044]; // [rsp+BCh] [rbp-4Ch] BYREF

  memset(&Overlapped, 0, sizeof(Overlapped));
  BytesReturned[0] = 0;
  v34 = 0;
  memset_0(v35, 0, sizeof(v35));
  v1 = g_pAsyncEventsThreadInfo;
  **((_DWORD **)g_pAsyncEventsThreadInfo + 1) = *((_DWORD *)g_pAsyncEventsThreadInfo + 4) - 12;
  v2 = g_hDriverAsync;
  *(_DWORD *)(*((_QWORD *)v1 + 1) + 4LL) = 0;
  if ( !DeviceIoControl(
          v2,
          0x8FFF23D0,
          *((LPVOID *)v1 + 1),
          0xCu,
          *((LPVOID *)v1 + 1),
          *((_DWORD *)v1 + 4),
          BytesReturned,
          &Overlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)",
            LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v34);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)", LastError);
      }
    }
  }
  while ( 1 )
  {
    while ( 1 )
    {
      v30 = 0;
      while ( 1 )
      {
        while ( 1 )
        {
          NumberOfBytesTransferred[0] = 0;
          CompletionKey = 0;
          if ( GetQueuedCompletionStatus(
                 g_hAsyncIoCompletionPort,
                 NumberOfBytesTransferred,
                 &CompletionKey,
                 &v30,
                 0xFFFFFFFF) )
          {
            break;
          }
          v5 = GetLastError();
          if ( v5 == 6 )
          {
            if ( gIsndpspEtwTracingAvailable )
            {
              if ( (_QWORD)xmmword_1800D0BE0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(
                  &v34,
                  L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread",
                  6);
                v25 = xmmword_1800D0BE0;
                v26 = (const wchar_t *)&v34;
LABEL_100:
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v25, v26);
              }
            }
            else if ( dwTraceId != -1 )
            {
              TracePrintfA(dwTraceId, "AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread", 6);
            }
LABEL_103:
            ExitThread(0);
          }
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second",
                v5);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800D0BE0,
                &v34);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(
              dwTraceId,
              "AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second",
              v5);
          }
          Sleep(1u);
        }
        v4 = v30;
        if ( &g_OverlappedTerminate == v30 )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            v25 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
            if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
            {
              v26 = L"AsyncEventsThread: Got exit message from CleanupNdproxyIoControl";
              goto LABEL_100;
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "AsyncEventsThread: Got exit message from CleanupNdproxyIoControl");
          }
          goto LABEL_103;
        }
        if ( v30 )
          break;
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              *((_QWORD *)&xmmword_1800D0BE0 + 1),
              L"AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!");
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!");
        }
      }
      if ( v30 != &Overlapped )
        break;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800D0BE0 + 1),
            L"AsyncEventsThread: Got a line event");
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "AsyncEventsThread: Got a line event");
      }
      v6 = g_pAsyncEventsThreadInfo;
      v7 = 0;
      v8 = *((_QWORD *)g_pAsyncEventsThreadInfo + 1);
      v9 = (struct _EVENT_RECORD *)(v8 + 8);
      if ( *(unsigned int *)(v8 + 4) / 0x30uLL )
      {
        do
        {
          if ( v9 )
          {
            ProcessEvent(v9);
            v6 = g_pAsyncEventsThreadInfo;
            v9 = (struct _EVENT_RECORD *)((char *)v9 + 48);
          }
          ++v7;
        }
        while ( v7 < *(unsigned int *)(*((_QWORD *)v6 + 1) + 4LL) / 0x30uLL );
      }
      Overlapped.hEvent = 0;
      **((_DWORD **)v6 + 1) = *((_DWORD *)v6 + 4) - 11;
      v10 = g_hDriverAsync;
      *(_DWORD *)(*((_QWORD *)v6 + 1) + 4LL) = 0;
      if ( !DeviceIoControl(
              v10,
              0x8FFF23D0,
              *((LPVOID *)v6 + 1),
              0xCu,
              *((LPVOID *)v6 + 1),
              *((_DWORD *)v6 + 4),
              BytesReturned,
              &Overlapped) )
      {
        v11 = GetLastError();
        if ( v11 != 997 )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)",
                v11);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800D0BE0,
                &v34);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(
              dwTraceId,
              "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)",
              v11);
          }
          Sleep(1u);
        }
      }
    }
    memset(v33, 0, 40);
    if ( !gIsndpspEtwTracingAvailable )
      break;
    v12 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
    if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800D0BE0 + 1),
        L"AsyncEventsThread: Got a completed request");
      goto LABEL_48;
    }
    v13 = dwTraceId;
LABEL_50:
    if ( LODWORD(v4[1].Internal) == 1095915339 )
    {
      hEvent_low = LODWORD(v4[4].hEvent);
      v16 = TranslateDriverResult(HIDWORD(v4[4].Internal));
      v17 = v16;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v34) = 0;
          LODWORD(lpOutBuffer) = v16;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)",
            v4,
            (unsigned int)hEvent_low,
            lpOutBuffer);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v34);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)",
          v4,
          hEvent_low,
          v16);
      }
      *(_QWORD *)&v33[0] = 0;
      InternalHigh = (void (__fastcall *)(LPOVERLAPPED, _QWORD, _OWORD *))v4[1].InternalHigh;
      if ( InternalHigh )
        InternalHigh(v4, (unsigned int)v17, v33);
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)",
            (unsigned int)hEvent_low,
            (unsigned int)v17);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v34);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(
          dwTraceId,
          "AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)",
          hEvent_low,
          v17);
      }
      ((void (__fastcall *)(_QWORD, __int64, _QWORD, __int64, __int64, _QWORD))g_pfnCallback)(
        0,
        12,
        0,
        hEvent_low,
        v17,
        0);
      EnterCriticalSection((LPCRITICAL_SECTION)&v4[1].16);
      v19 = LODWORD(v4[2].hEvent)-- == 1;
      v20 = (struct _RTL_CRITICAL_SECTION *)&v4[1].16;
      if ( v19 )
      {
        LeaveCriticalSection(v20);
        DeleteCriticalSection((LPCRITICAL_SECTION)&v4[1].16);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v4);
      }
      else
      {
        LeaveCriticalSection(v20);
      }
      v22 = *(const void **)&v33[0];
      if ( *(_QWORD *)&v33[0] )
      {
        *(_QWORD *)NumberOfBytesTransferred = 0;
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( !*((_QWORD *)&xmmword_1800D0BE0 + 1) )
            goto LABEL_79;
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800D0BE0 + 1),
            L"AsyncEventsThread: Report back the saved call state");
        }
        else
        {
          if ( dwTraceId == -1 )
            goto LABEL_85;
          TracePrintfA(dwTraceId, "AsyncEventsThread: Report back the saved call state");
        }
        v22 = *(const void **)&v33[0];
LABEL_79:
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v34) = 0;
            FormatRRASErrorString(
              &v34,
              L"AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
              v22,
              *((_QWORD *)&v33[0] + 1),
              v33[1],
              *(_QWORD *)&v33[2]);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v34);
LABEL_84:
            LODWORD(v22) = v33[0];
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(
            dwTraceId,
            "AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
            v22,
            *((const void **)&v33[0] + 1),
            *(const void **)&v33[1],
            *((const void **)&v33[1] + 1),
            *(const void **)&v33[2]);
          goto LABEL_84;
        }
LABEL_85:
        Lock = GetLineObjWithReadLock((unsigned int)v22, NumberOfBytesTransferred);
        if ( Lock )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800D0BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(&v34, L"AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)", Lock);
              v12 = xmmword_1800D0BE0;
              v14 = (const wchar_t *)&v34;
LABEL_54:
              ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v12, v14);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)", Lock);
          }
        }
        else
        {
          v24 = *(_QWORD *)(*(_QWORD *)NumberOfBytesTransferred + 32LL);
          ReleaseObjReadLock((unsigned int)v22);
          ((void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _QWORD, _QWORD))g_pfnCallback)(
            *((_QWORD *)&v33[0] + 1),
            2,
            v24,
            *(_QWORD *)&v33[1],
            *((_QWORD *)&v33[1] + 1),
            *(_QWORD *)&v33[2]);
        }
      }
    }
    else if ( gIsndpspEtwTracingAvailable )
    {
      if ( v12 )
      {
        v14 = L"AsyncEventsThread: Got a bogus request";
        goto LABEL_54;
      }
    }
    else if ( v13 != -1 )
    {
      TracePrintfA(v13, "AsyncEventsThread: Got a bogus request");
    }
  }
  v13 = dwTraceId;
  if ( dwTraceId != -1 )
  {
    TracePrintfA(dwTraceId, "AsyncEventsThread: Got a completed request");
LABEL_48:
    v13 = dwTraceId;
  }
  v12 = *((_QWORD *)&xmmword_1800D0BE0 + 1);
  goto LABEL_50;
}

```

## disassembly

```asm
0x1800890b0  mov     rax, rsp
0x1800890b3  mov     [rax+8], rbx
0x1800890b7  mov     [rax+10h], rsi
0x1800890bb  mov     [rax+18h], rdi
0x1800890bf  push    rbp
0x1800890c0  push    r14
0x1800890c2  push    r15
0x1800890c4  lea     rbp, [rax-7D8h]
0x1800890cb  sub     rsp, 8C0h
0x1800890d2  mov     rax, cs:__security_cookie
0x1800890d9  xor     rax, rsp
0x1800890dc  mov     [rbp+7D0h+var_20], rax
0x1800890e3  xor     r14d, r14d
0x1800890e6  lea     rcx, [rbp+7D0h+var_81C]; void *
0x1800890ea  xorps   xmm0, xmm0
0x1800890ed  mov     [rsp+8D0h+Overlapped.Internal], r14
0x1800890f2  xor     edx, edx; Val
0x1800890f4  mov     [rsp+8D0h+BytesReturned], r14d
0x1800890f9  mov     r8d, 7FCh; Size
0x1800890ff  mov     [rbp+7D0h+var_820], r14d
0x180089103  movdqu  xmmword ptr [rsp+8D0h+Overlapped.InternalHigh], xmm0
0x180089109  call    memset_0
0x18008910e  mov     rdx, cs:g_pAsyncEventsThreadInfo
0x180089115  lea     r9d, [r14+0Ch]; nInBufferSize
0x180089119  mov     [rsp+8D0h+Overlapped.hEvent], r14
0x18008911e  mov     ecx, [rdx+10h]
0x180089121  mov     rax, [rdx+8]
0x180089125  sub     ecx, 0Ch
0x180089128  mov     [rax], ecx
0x18008912a  mov     rax, [rdx+8]
0x18008912e  mov     rcx, cs:g_hDriverAsync; hDevice
0x180089135  mov     [rax+4], r14d
0x180089139  lea     rax, [rsp+8D0h+Overlapped]
0x18008913e  mov     r8, [rdx+8]; lpInBuffer
0x180089142  mov     [rsp+8D0h+lpOverlapped], rax; lpOverlapped
0x180089147  lea     rax, [rsp+8D0h+BytesReturned]
0x18008914c  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x180089151  mov     eax, [rdx+10h]
0x180089154  mov     edx, 8FFF23D0h; dwIoControlCode
0x180089159  mov     dword ptr [rsp+8D0h+lpOutBuffer+8], eax; nOutBufferSize
0x18008915d  mov     qword ptr [rsp+8D0h+lpOutBuffer], r8; lpOutBuffer
0x180089162  call    cs:__imp_DeviceIoControl
0x180089169  nop     dword ptr [rax+rax+00h]
0x18008916e  or      r15d, 0FFFFFFFFh
0x180089172  cmp     eax, 1
0x180089175  jz      short loc_1800891F5
0x180089177  call    cs:__imp_GetLastError
0x18008917e  nop     dword ptr [rax+rax+00h]
0x180089183  cmp     eax, 3E5h
0x180089188  jz      short loc_1800891F5
0x18008918a  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180089191  jz      short loc_1800891D4
0x180089193  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x18008919a  jz      short loc_1800891F5
0x18008919c  mov     r8d, eax
0x18008919f  mov     word ptr [rbp+7D0h+var_820], r14w
0x1800891a4  lea     rdx, aAsynceventsthr_20; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x1800891ab  lea     rcx, [rbp+7D0h+var_820]
0x1800891af  call    FormatRRASErrorString
0x1800891b4  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x1800891bb  lea     r8, [rbp+7D0h+var_820]
0x1800891bf  mov     rcx, cs:gNdpspEtwContext
0x1800891c6  mov     rax, cs:gNdpspTemplateFunc
0x1800891cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800891d2  jmp     short loc_1800891F5
0x1800891d4  mov     ecx, cs:dwTraceId; dwTraceID
0x1800891da  cmp     ecx, r15d
0x1800891dd  jz      short loc_1800891F5
0x1800891df  mov     r8d, eax
0x1800891e2  lea     rdx, aAsynceventsthr_3; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x1800891e9  call    cs:__imp_TracePrintfA
0x1800891f0  nop     dword ptr [rax+rax+00h]
0x1800891f5  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800891ff  mov     [rsp+8D0h+var_880], r14
0x180089204  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x18008920b  lea     r9, [rsp+8D0h+var_880]; lpOverlapped
0x180089210  lea     r8, [rsp+8D0h+CompletionKey]; lpCompletionKey
0x180089215  mov     [rsp+8D0h+NumberOfBytesTransferred], r14d
0x18008921a  lea     rdx, [rsp+8D0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18008921f  mov     [rsp+8D0h+CompletionKey], r14
0x180089224  mov     dword ptr [rsp+8D0h+lpOutBuffer], r15d; dwMilliseconds
0x180089229  call    cs:__imp_GetQueuedCompletionStatus
0x180089230  nop     dword ptr [rax+rax+00h]
0x180089235  test    eax, eax
0x180089237  jz      short loc_1800892B2
0x180089239  mov     rbx, [rsp+8D0h+var_880]
0x18008923e  lea     rax, g_OverlappedTerminate
0x180089245  cmp     rax, rbx
0x180089248  jz      loc_180089947
0x18008924e  test    rbx, rbx
0x180089251  jnz     loc_180089348
0x180089257  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008925e  jz      short loc_18008928B
0x180089260  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180089267  test    rdx, rdx
0x18008926a  jz      short loc_180089204
0x18008926c  mov     rcx, cs:gNdpspEtwContext
0x180089273  lea     r8, aAsynceventsthr_14; "AsyncEventsThread: GetQueuedCompletionS"...
0x18008927a  mov     rax, cs:gNdpspTemplateFunc
0x180089281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089286  jmp     loc_180089204
0x18008928b  mov     ecx, cs:dwTraceId; dwTraceID
0x180089291  cmp     ecx, r15d
0x180089294  jz      loc_180089204
0x18008929a  lea     rdx, aAsynceventsthr_22; "AsyncEventsThread: GetQueuedCompletionS"...
0x1800892a1  call    cs:__imp_TracePrintfA
0x1800892a8  nop     dword ptr [rax+rax+00h]
0x1800892ad  jmp     loc_180089204
0x1800892b2  call    cs:__imp_GetLastError
0x1800892b9  nop     dword ptr [rax+rax+00h]
0x1800892be  cmp     eax, 6
0x1800892c1  jz      loc_18008998D
0x1800892c7  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800892ce  jz      short loc_180089311
0x1800892d0  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x1800892d7  jz      short loc_180089332
0x1800892d9  mov     r8d, eax
0x1800892dc  mov     word ptr [rbp+7D0h+var_820], r14w
0x1800892e1  lea     rdx, aAsynceventsthr_19; "AsyncEventsThread: GetQueuedCompletionS"...
0x1800892e8  lea     rcx, [rbp+7D0h+var_820]
0x1800892ec  call    FormatRRASErrorString
0x1800892f1  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x1800892f8  lea     r8, [rbp+7D0h+var_820]
0x1800892fc  mov     rcx, cs:gNdpspEtwContext
0x180089303  mov     rax, cs:gNdpspTemplateFunc
0x18008930a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008930f  jmp     short loc_180089332
0x180089311  mov     ecx, cs:dwTraceId; dwTraceID
0x180089317  cmp     ecx, r15d
0x18008931a  jz      short loc_180089332
0x18008931c  mov     r8d, eax
0x18008931f  lea     rdx, aAsynceventsthr_0; "AsyncEventsThread: GetQueuedCompletionS"...
0x180089326  call    cs:__imp_TracePrintfA
0x18008932d  nop     dword ptr [rax+rax+00h]
0x180089332  mov     ecx, 1; dwMilliseconds
0x180089337  call    cs:__imp_Sleep
0x18008933e  nop     dword ptr [rax+rax+00h]
0x180089343  jmp     loc_180089204
0x180089348  lea     rax, [rsp+8D0h+Overlapped]
0x18008934d  cmp     rbx, rax
0x180089350  jnz     loc_1800894F9
0x180089356  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008935d  jz      short loc_180089387
0x18008935f  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x180089366  test    rdx, rdx
0x180089369  jz      short loc_1800893A5
0x18008936b  mov     rcx, cs:gNdpspEtwContext
0x180089372  lea     r8, aAsynceventsthr_25; "AsyncEventsThread: Got a line event"
0x180089379  mov     rax, cs:gNdpspTemplateFunc
0x180089380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089385  jmp     short loc_1800893A5
0x180089387  mov     ecx, cs:dwTraceId; dwTraceID
0x18008938d  cmp     ecx, r15d
0x180089390  jz      short loc_1800893A5
0x180089392  lea     rdx, aAsynceventsthr_11; "AsyncEventsThread: Got a line event"
0x180089399  call    cs:__imp_TracePrintfA
0x1800893a0  nop     dword ptr [rax+rax+00h]
0x1800893a5  mov     r9, cs:g_pAsyncEventsThreadInfo
0x1800893ac  mov     edi, r14d
0x1800893af  mov     rax, [r9+8]
0x1800893b3  mov     ecx, [rax+4]
0x1800893b6  lea     rbx, [rax+8]
0x1800893ba  mov     rax, rsi
0x1800893bd  mul     rcx
0x1800893c0  shr     rdx, 5
0x1800893c4  test    rdx, rdx
0x1800893c7  jz      short loc_1800893FB
0x1800893c9  test    rbx, rbx
0x1800893cc  jz      short loc_1800893E1
0x1800893ce  mov     rcx, rbx; eventRecord
0x1800893d1  call    ProcessEvent
0x1800893d6  mov     r9, cs:g_pAsyncEventsThreadInfo
0x1800893dd  add     rbx, 30h ; '0'
0x1800893e1  mov     rax, [r9+8]
0x1800893e5  inc     edi
0x1800893e7  mov     ecx, [rax+4]
0x1800893ea  mov     rax, rsi
0x1800893ed  mul     rcx
0x1800893f0  mov     eax, edi
0x1800893f2  shr     rdx, 5
0x1800893f6  cmp     rax, rdx
0x1800893f9  jb      short loc_1800893C9
0x1800893fb  mov     [rsp+8D0h+Overlapped.hEvent], r14
0x180089400  mov     edx, 8FFF23D0h; dwIoControlCode
0x180089405  mov     ecx, [r9+10h]
0x180089409  mov     rax, [r9+8]
0x18008940d  sub     ecx, 0Bh
0x180089410  mov     [rax], ecx
0x180089412  mov     rax, [r9+8]
0x180089416  mov     rcx, cs:g_hDriverAsync; hDevice
0x18008941d  mov     [rax+4], r14d
0x180089421  lea     rax, [rsp+8D0h+Overlapped]
0x180089426  mov     r8, [r9+8]; lpInBuffer
0x18008942a  mov     [rsp+8D0h+lpOverlapped], rax; lpOverlapped
0x18008942f  lea     rax, [rsp+8D0h+BytesReturned]
0x180089434  mov     [rsp+8D0h+lpBytesReturned], rax; lpBytesReturned
0x180089439  mov     eax, [r9+10h]
0x18008943d  mov     r9d, 0Ch; nInBufferSize
0x180089443  mov     dword ptr [rsp+8D0h+lpOutBuffer+8], eax; nOutBufferSize
0x180089447  mov     qword ptr [rsp+8D0h+lpOutBuffer], r8; lpOutBuffer
0x18008944c  call    cs:__imp_DeviceIoControl
0x180089453  nop     dword ptr [rax+rax+00h]
0x180089458  cmp     eax, 1
0x18008945b  jz      loc_1800891FF
0x180089461  call    cs:__imp_GetLastError
0x180089468  nop     dword ptr [rax+rax+00h]
0x18008946d  cmp     eax, 3E5h
0x180089472  jz      loc_1800891FF
0x180089478  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008947f  jz      short loc_1800894C2
0x180089481  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x180089488  jz      short loc_1800894E3
0x18008948a  mov     r8d, eax
0x18008948d  mov     word ptr [rbp+7D0h+var_820], r14w
0x180089492  lea     rdx, aAsynceventsthr_21; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180089499  lea     rcx, [rbp+7D0h+var_820]
0x18008949d  call    FormatRRASErrorString
0x1800894a2  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x1800894a9  lea     r8, [rbp+7D0h+var_820]
0x1800894ad  mov     rcx, cs:gNdpspEtwContext
0x1800894b4  mov     rax, cs:gNdpspTemplateFunc
0x1800894bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800894c0  jmp     short loc_1800894E3
0x1800894c2  mov     ecx, cs:dwTraceId; dwTraceID
0x1800894c8  cmp     ecx, r15d
0x1800894cb  jz      short loc_1800894E3
0x1800894cd  mov     r8d, eax
0x1800894d0  lea     rdx, aAsynceventsthr_1; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x1800894d7  call    cs:__imp_TracePrintfA
0x1800894de  nop     dword ptr [rax+rax+00h]
0x1800894e3  mov     ecx, 1; dwMilliseconds
0x1800894e8  call    cs:__imp_Sleep
0x1800894ef  nop     dword ptr [rax+rax+00h]
0x1800894f4  jmp     loc_1800891FF
0x1800894f9  xor     eax, eax
0x1800894fb  xorps   xmm0, xmm0
0x1800894fe  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180089505  movups  [rbp+7D0h+var_850], xmm0
0x180089509  mov     qword ptr [rbp+7D0h+var_840+10h], rax
0x18008950d  movups  xmmword ptr [rbp+7D0h+var_840], xmm0
0x180089511  jz      short loc_180089543
0x180089513  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008951a  test    rdx, rdx
0x18008951d  jz      short loc_18008953B
0x18008951f  mov     rcx, cs:gNdpspEtwContext
0x180089526  lea     r8, aAsynceventsthr_18; "AsyncEventsThread: Got a completed requ"...
0x18008952d  mov     rax, cs:gNdpspTemplateFunc
0x180089534  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180089539  jmp     short loc_180089561
0x18008953b  mov     ecx, cs:dwTraceId
0x180089541  jmp     short loc_18008956E
0x180089543  mov     ecx, cs:dwTraceId; dwTraceID
0x180089549  cmp     ecx, r15d
0x18008954c  jz      short loc_180089567
0x18008954e  lea     rdx, aAsynceventsthr_13; "AsyncEventsThread: Got a completed requ"...
0x180089555  call    cs:__imp_TracePrintfA
0x18008955c  nop     dword ptr [rax+rax+00h]
0x180089561  mov     ecx, cs:dwTraceId; dwTraceID
0x180089567  mov     rdx, qword ptr cs:xmmword_1800D0BE0+8
0x18008956e  cmp     dword ptr [rbx+20h], 4152574Bh
0x180089575  jz      short loc_1800895C9
0x180089577  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008957e  jz      short loc_1800895A8
0x180089580  test    rdx, rdx
0x180089583  jz      loc_1800891FF
0x180089589  lea     r8, aAsynceventsthr_12; "AsyncEventsThread: Got a bogus request"
0x180089590  mov     rcx, cs:gNdpspEtwContext
0x180089597  mov     rax, cs:gNdpspTemplateFunc
0x18008959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800895a3  jmp     loc_1800891FF
0x1800895a8  cmp     ecx, r15d
0x1800895ab  jz      loc_1800891FF
0x1800895b1  lea     rdx, aAsynceventsthr_24; "AsyncEventsThread: Got a bogus request"
0x1800895b8  call    cs:__imp_TracePrintfA
0x1800895bf  nop     dword ptr [rax+rax+00h]
0x1800895c4  jmp     loc_1800891FF
0x1800895c9  mov     ecx, [rbx+84h]
0x1800895cf  mov     esi, [rbx+98h]
0x1800895d5  call    TranslateDriverResult
0x1800895da  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800895e1  mov     edi, eax
0x1800895e3  jz      short loc_18008962D
0x1800895e5  cmp     qword ptr cs:xmmword_1800D0BE0, r14
0x1800895ec  jz      short loc_180089655
0x1800895ee  mov     r9d, esi
0x1800895f1  mov     word ptr [rbp+7D0h+var_820], r14w
0x1800895f6  mov     r8, rbx
0x1800895f9  mov     dword ptr [rsp+8D0h+lpOutBuffer], edi
0x1800895fd  lea     rdx, aAsynceventsthr_15; "AsyncEventsThread: Request (%p) with re"...
0x180089604  lea     rcx, [rbp+7D0h+var_820]
0x180089608  call    FormatRRASErrorString
0x18008960d  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x180089614  lea     r8, [rbp+7D0h+var_820]
0x180089618  mov     rcx, cs:gNdpspEtwContext
0x18008961f  mov     rax, cs:gNdpspTemplateFunc
0x180089626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008962b  jmp     short loc_180089655
0x18008962d  mov     ecx, cs:dwTraceId; dwTraceID
0x180089633  cmp     ecx, r15d
0x180089636  jz      short loc_180089655
  ... truncated ...
```
