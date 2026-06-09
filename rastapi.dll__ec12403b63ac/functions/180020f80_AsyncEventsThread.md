# AsyncEventsThread

- ea: `0x180020f80`
- end: `0x180021818`
- name: `AsyncEventsThread`
- size: `2200`
- prototype: `void __fastcall __noreturn(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180020f80`
- `0x1800226f0`
- `0x180027a10`
- `0x180027e38`
- `0x180028b5c`
- `0x180029130`
- `0x18002927e`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021157`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021585`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021585`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021593`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021593`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021576`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002159b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021576`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002159b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021567`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180021567`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002157f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002157f`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021028`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800212d9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180021028`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800212d9`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800210dd`
- `api-ms-win-core-io-l1-1-0!GetQueuedCompletionStatus` at `0x1800210dd`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180021811`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180021811`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800211d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021363`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800211d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021363`
- `rtutils!TracePrintfA` at `0x1800210a3`
- `rtutils!TracePrintfA` at `0x18002114c`
- `rtutils!TracePrintfA` at `0x1800211c5`
- `rtutils!TracePrintfA` at `0x18002122c`
- `rtutils!TracePrintfA` at `0x180021358`
- `rtutils!TracePrintfA` at `0x1800213ca`
- `rtutils!TracePrintfA` at `0x180021427`
- `rtutils!TracePrintfA` at `0x1800214b2`
- `rtutils!TracePrintfA` at `0x180021538`
- `rtutils!TracePrintfA` at `0x180021601`
- `rtutils!TracePrintfA` at `0x1800216aa`
- `rtutils!TracePrintfA` at `0x18002171a`
- `rtutils!TracePrintfA` at `0x18002179c`
- `rtutils!TracePrintfA` at `0x180021809`
- `rtutils!TracePrintfA` at `0x1800210a3`
- `rtutils!TracePrintfA` at `0x18002114c`
- `rtutils!TracePrintfA` at `0x1800211c5`
- `rtutils!TracePrintfA` at `0x18002122c`
- `rtutils!TracePrintfA` at `0x180021358`
- `rtutils!TracePrintfA` at `0x1800213ca`
- `rtutils!TracePrintfA` at `0x180021427`
- `rtutils!TracePrintfA` at `0x1800214b2`
- `rtutils!TracePrintfA` at `0x180021538`
- `rtutils!TracePrintfA` at `0x180021601`
- `rtutils!TracePrintfA` at `0x1800216aa`
- `rtutils!TracePrintfA` at `0x18002171a`
- `rtutils!TracePrintfA` at `0x18002179c`
- `rtutils!TracePrintfA` at `0x180021809`

## string_xrefs

- `0x18002105e`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x18002109c`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x180021781`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x180021795`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x180021121`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x180021145`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x180021180`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x1800211be`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x1800217c1`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x180021802`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x180021205`: `AsyncEventsThread: Got a line event`
- `0x180021225`: `AsyncEventsThread: Got a line event`
- `0x180021313`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x180021351`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x18002139b`: `AsyncEventsThread: Got a completed request`
- `0x1800213c3`: `AsyncEventsThread: Got a completed request`
- `0x1800213f8`: `AsyncEventsThread: Got a bogus request`
- `0x180021420`: `AsyncEventsThread: Got a bogus request`
- `0x180021466`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x1800214ab`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x1800214f0`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x18002152e`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x1800215d6`: `AsyncEventsThread: Report back the saved call state`
- `0x1800215fa`: `AsyncEventsThread: Report back the saved call state`
- `0x180021621`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x180021684`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x1800216e1`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180021713`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`

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
  unsigned int v22; // edi
  unsigned int Lock; // eax
  __int64 v24; // rbx
  __int64 v25; // rdx
  const wchar_t *v26; // r8
  __int64 lpOutBuffer; // [rsp+20h] [rbp-E0h]
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  DWORD NumberOfBytesTransferred[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPOVERLAPPED v30; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 CompletionKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _OVERLAPPED Overlapped; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v33[3]; // [rsp+80h] [rbp-80h] BYREF
  int v34; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v35[2044]; // [rsp+B4h] [rbp-4Ch] BYREF

  memset(&Overlapped, 0, sizeof(Overlapped));
  BytesReturned = 0;
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
          &BytesReturned,
          &Overlapped) )
  {
    LastError = GetLastError();
    if ( LastError != 997 )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)",
            LastError);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v34);
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
              if ( qword_18003EC40 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(
                  &v34,
                  L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread",
                  6);
                v25 = qword_18003EC40;
                v26 = (const wchar_t *)&v34;
LABEL_98:
                ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(gNdpspEtwContext, v25, v26);
              }
            }
            else if ( dwTraceId != -1 )
            {
              TracePrintfA(dwTraceId, "AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread", 6);
            }
LABEL_101:
            ExitThread(0);
          }
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second",
                v5);
              ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC40,
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
            v25 = qword_18003EC48;
            if ( qword_18003EC48 )
            {
              v26 = L"AsyncEventsThread: Got exit message from CleanupNdproxyIoControl";
              goto LABEL_98;
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(dwTraceId, "AsyncEventsThread: Got exit message from CleanupNdproxyIoControl");
          }
          goto LABEL_101;
        }
        if ( v30 )
          break;
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC48 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              qword_18003EC48,
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
        if ( qword_18003EC48 )
          ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            qword_18003EC48,
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
              &BytesReturned,
              &Overlapped) )
      {
        v11 = GetLastError();
        if ( v11 != 997 )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)",
                v11);
              ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC40,
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
    v12 = qword_18003EC48;
    if ( qword_18003EC48 )
    {
      ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        qword_18003EC48,
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
        if ( qword_18003EC40 )
        {
          LOWORD(v34) = 0;
          LODWORD(lpOutBuffer) = v16;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)",
            v4,
            (unsigned int)hEvent_low,
            lpOutBuffer);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v34);
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
        if ( qword_18003EC40 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)",
            (unsigned int)hEvent_low,
            (unsigned int)v17);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v34);
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
      if ( *(_QWORD *)&v33[0] )
      {
        *(_QWORD *)NumberOfBytesTransferred = 0;
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC48 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              qword_18003EC48,
              L"AsyncEventsThread: Report back the saved call state");
          goto LABEL_78;
        }
        if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "AsyncEventsThread: Report back the saved call state");
LABEL_78:
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
                v33[0],
                v33[1],
                *(_QWORD *)&v33[2]);
              ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                qword_18003EC40,
                &v34);
            }
          }
          else if ( dwTraceId != -1 )
          {
            TracePrintfA(
              dwTraceId,
              "AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
              *(const void **)&v33[0],
              *((const void **)&v33[0] + 1),
              *(const void **)&v33[1],
              *((const void **)&v33[1] + 1),
              *(const void **)&v33[2]);
          }
        }
        v22 = v33[0];
        Lock = GetLineObjWithReadLock(LODWORD(v33[0]), NumberOfBytesTransferred);
        if ( Lock )
        {
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( qword_18003EC40 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(&v34, L"AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)", Lock);
              v12 = qword_18003EC40;
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
          ReleaseObjReadLock(v22);
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
  v12 = qword_18003EC48;
  goto LABEL_50;
}

```

## disassembly

```asm
0x180020f80  push    rbp
0x180020f82  push    rbx
0x180020f83  push    rsi
0x180020f84  push    rdi
0x180020f85  push    r14
0x180020f87  push    r15
0x180020f89  lea     rbp, [rsp-7C8h]
0x180020f91  sub     rsp, 8C8h
0x180020f98  mov     rax, cs:__security_cookie
0x180020f9f  xor     rax, rsp
0x180020fa2  mov     [rbp+7F0h+var_40], rax
0x180020fa9  xor     r14d, r14d
0x180020fac  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180020fb0  xorps   xmm0, xmm0
0x180020fb3  mov     [rsp+8F0h+Overlapped.Internal], r14
0x180020fb8  xor     edx, edx; Val
0x180020fba  mov     [rsp+8F0h+BytesReturned], r14d
0x180020fbf  mov     r8d, 7FCh; Size
0x180020fc5  mov     [rbp+7F0h+var_840], r14d
0x180020fc9  movdqu  xmmword ptr [rsp+8F0h+Overlapped.InternalHigh], xmm0
0x180020fcf  call    memset_0
0x180020fd4  mov     rdx, cs:g_pAsyncEventsThreadInfo
0x180020fdb  lea     r9d, [r14+0Ch]; nInBufferSize
0x180020fdf  mov     [rsp+8F0h+Overlapped.hEvent], r14
0x180020fe4  mov     ecx, [rdx+10h]
0x180020fe7  mov     rax, [rdx+8]
0x180020feb  sub     ecx, 0Ch
0x180020fee  mov     [rax], ecx
0x180020ff0  mov     rax, [rdx+8]
0x180020ff4  mov     rcx, cs:g_hDriverAsync; hDevice
0x180020ffb  mov     [rax+4], r14d
0x180020fff  lea     rax, [rsp+8F0h+Overlapped]
0x180021004  mov     r8, [rdx+8]; lpInBuffer
0x180021008  mov     [rsp+8F0h+lpOverlapped], rax; lpOverlapped
0x18002100d  lea     rax, [rsp+8F0h+BytesReturned]
0x180021012  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x180021017  mov     eax, [rdx+10h]
0x18002101a  mov     edx, 8FFF23D0h; dwIoControlCode
0x18002101f  mov     dword ptr [rsp+8F0h+lpOutBuffer+8], eax; nOutBufferSize
0x180021023  mov     qword ptr [rsp+8F0h+lpOutBuffer], r8; lpOutBuffer
0x180021028  call    cs:__imp_DeviceIoControl
0x18002102e  or      r15d, 0FFFFFFFFh
0x180021032  cmp     eax, 1
0x180021035  jz      short loc_1800210A9
0x180021037  call    cs:__imp_GetLastError
0x18002103d  cmp     eax, 3E5h
0x180021042  jz      short loc_1800210A9
0x180021044  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18002104b  jz      short loc_18002108E
0x18002104d  cmp     cs:qword_18003EC40, r14
0x180021054  jz      short loc_1800210A9
0x180021056  mov     r8d, eax
0x180021059  mov     word ptr [rbp+7F0h+var_840], r14w
0x18002105e  lea     rdx, aAsynceventsthr_20; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180021065  lea     rcx, [rbp+7F0h+var_840]
0x180021069  call    FormatRRASErrorString
0x18002106e  mov     rdx, cs:qword_18003EC40
0x180021075  lea     r8, [rbp+7F0h+var_840]
0x180021079  mov     rcx, cs:gNdpspEtwContext
0x180021080  mov     rax, cs:gNdpspTemplateFunc
0x180021087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002108c  jmp     short loc_1800210A9
0x18002108e  mov     ecx, cs:dwTraceId; dwTraceID
0x180021094  cmp     ecx, r15d
0x180021097  jz      short loc_1800210A9
0x180021099  mov     r8d, eax
0x18002109c  lea     rdx, aAsynceventsthr_3; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x1800210a3  call    cs:__imp_TracePrintfA
0x1800210a9  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800210b3  mov     [rsp+8F0h+var_8A0], r14
0x1800210b8  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x1800210bf  lea     r9, [rsp+8F0h+var_8A0]; lpOverlapped
0x1800210c4  lea     r8, [rsp+8F0h+CompletionKey]; lpCompletionKey
0x1800210c9  mov     [rsp+8F0h+NumberOfBytesTransferred], r14d
0x1800210ce  lea     rdx, [rsp+8F0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800210d3  mov     [rsp+8F0h+CompletionKey], r14
0x1800210d8  mov     dword ptr [rsp+8F0h+lpOutBuffer], r15d; dwMilliseconds
0x1800210dd  call    cs:__imp_GetQueuedCompletionStatus
0x1800210e3  test    eax, eax
0x1800210e5  jz      short loc_180021157
0x1800210e7  mov     rbx, [rsp+8F0h+var_8A0]
0x1800210ec  lea     rax, g_OverlappedTerminate
0x1800210f3  cmp     rax, rbx
0x1800210f6  jz      loc_180021768
0x1800210fc  test    rbx, rbx
0x1800210ff  jnz     loc_1800211DB
0x180021105  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18002110c  jz      short loc_180021136
0x18002110e  mov     rdx, cs:qword_18003EC48
0x180021115  test    rdx, rdx
0x180021118  jz      short loc_1800210B8
0x18002111a  mov     rcx, cs:gNdpspEtwContext
0x180021121  lea     r8, aAsynceventsthr_14; "AsyncEventsThread: GetQueuedCompletionS"...
0x180021128  mov     rax, cs:gNdpspTemplateFunc
0x18002112f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021134  jmp     short loc_1800210B8
0x180021136  mov     ecx, cs:dwTraceId; dwTraceID
0x18002113c  cmp     ecx, r15d
0x18002113f  jz      loc_1800210B8
0x180021145  lea     rdx, aAsynceventsthr_22; "AsyncEventsThread: GetQueuedCompletionS"...
0x18002114c  call    cs:__imp_TracePrintfA
0x180021152  jmp     loc_1800210B8
0x180021157  call    cs:__imp_GetLastError
0x18002115d  cmp     eax, 6
0x180021160  jz      loc_1800217A4
0x180021166  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18002116d  jz      short loc_1800211B0
0x18002116f  cmp     cs:qword_18003EC40, r14
0x180021176  jz      short loc_1800211CB
0x180021178  mov     r8d, eax
0x18002117b  mov     word ptr [rbp+7F0h+var_840], r14w
0x180021180  lea     rdx, aAsynceventsthr_19; "AsyncEventsThread: GetQueuedCompletionS"...
0x180021187  lea     rcx, [rbp+7F0h+var_840]
0x18002118b  call    FormatRRASErrorString
0x180021190  mov     rdx, cs:qword_18003EC40
0x180021197  lea     r8, [rbp+7F0h+var_840]
0x18002119b  mov     rcx, cs:gNdpspEtwContext
0x1800211a2  mov     rax, cs:gNdpspTemplateFunc
0x1800211a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211ae  jmp     short loc_1800211CB
0x1800211b0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800211b6  cmp     ecx, r15d
0x1800211b9  jz      short loc_1800211CB
0x1800211bb  mov     r8d, eax
0x1800211be  lea     rdx, aAsynceventsthr_0; "AsyncEventsThread: GetQueuedCompletionS"...
0x1800211c5  call    cs:__imp_TracePrintfA
0x1800211cb  mov     ecx, 1; dwMilliseconds
0x1800211d0  call    cs:__imp_Sleep
0x1800211d6  jmp     loc_1800210B8
0x1800211db  lea     rax, [rsp+8F0h+Overlapped]
0x1800211e0  cmp     rbx, rax
0x1800211e3  jnz     loc_18002136E
0x1800211e9  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800211f0  jz      short loc_18002121A
0x1800211f2  mov     rdx, cs:qword_18003EC48
0x1800211f9  test    rdx, rdx
0x1800211fc  jz      short loc_180021232
0x1800211fe  mov     rcx, cs:gNdpspEtwContext
0x180021205  lea     r8, aAsynceventsthr_25; "AsyncEventsThread: Got a line event"
0x18002120c  mov     rax, cs:gNdpspTemplateFunc
0x180021213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021218  jmp     short loc_180021232
0x18002121a  mov     ecx, cs:dwTraceId; dwTraceID
0x180021220  cmp     ecx, r15d
0x180021223  jz      short loc_180021232
0x180021225  lea     rdx, aAsynceventsthr_11; "AsyncEventsThread: Got a line event"
0x18002122c  call    cs:__imp_TracePrintfA
0x180021232  mov     r9, cs:g_pAsyncEventsThreadInfo
0x180021239  mov     edi, r14d
0x18002123c  mov     rax, [r9+8]
0x180021240  mov     ecx, [rax+4]
0x180021243  lea     rbx, [rax+8]
0x180021247  mov     rax, rsi
0x18002124a  mul     rcx
0x18002124d  shr     rdx, 5
0x180021251  test    rdx, rdx
0x180021254  jz      short loc_180021288
0x180021256  test    rbx, rbx
0x180021259  jz      short loc_18002126E
0x18002125b  mov     rcx, rbx; eventRecord
0x18002125e  call    ProcessEvent
0x180021263  mov     r9, cs:g_pAsyncEventsThreadInfo
0x18002126a  add     rbx, 30h ; '0'
0x18002126e  mov     rax, [r9+8]
0x180021272  inc     edi
0x180021274  mov     ecx, [rax+4]
0x180021277  mov     rax, rsi
0x18002127a  mul     rcx
0x18002127d  mov     eax, edi
0x18002127f  shr     rdx, 5
0x180021283  cmp     rax, rdx
0x180021286  jb      short loc_180021256
0x180021288  mov     [rsp+8F0h+Overlapped.hEvent], r14
0x18002128d  mov     edx, 8FFF23D0h; dwIoControlCode
0x180021292  mov     ecx, [r9+10h]
0x180021296  mov     rax, [r9+8]
0x18002129a  sub     ecx, 0Bh
0x18002129d  mov     [rax], ecx
0x18002129f  mov     rax, [r9+8]
0x1800212a3  mov     rcx, cs:g_hDriverAsync; hDevice
0x1800212aa  mov     [rax+4], r14d
0x1800212ae  lea     rax, [rsp+8F0h+Overlapped]
0x1800212b3  mov     r8, [r9+8]; lpInBuffer
0x1800212b7  mov     [rsp+8F0h+lpOverlapped], rax; lpOverlapped
0x1800212bc  lea     rax, [rsp+8F0h+BytesReturned]
0x1800212c1  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x1800212c6  mov     eax, [r9+10h]
0x1800212ca  mov     r9d, 0Ch; nInBufferSize
0x1800212d0  mov     dword ptr [rsp+8F0h+lpOutBuffer+8], eax; nOutBufferSize
0x1800212d4  mov     qword ptr [rsp+8F0h+lpOutBuffer], r8; lpOutBuffer
0x1800212d9  call    cs:__imp_DeviceIoControl
0x1800212df  cmp     eax, 1
0x1800212e2  jz      loc_1800210B3
0x1800212e8  call    cs:__imp_GetLastError
0x1800212ee  cmp     eax, 3E5h
0x1800212f3  jz      loc_1800210B3
0x1800212f9  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x180021300  jz      short loc_180021343
0x180021302  cmp     cs:qword_18003EC40, r14
0x180021309  jz      short loc_18002135E
0x18002130b  mov     r8d, eax
0x18002130e  mov     word ptr [rbp+7F0h+var_840], r14w
0x180021313  lea     rdx, aAsynceventsthr_21; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x18002131a  lea     rcx, [rbp+7F0h+var_840]
0x18002131e  call    FormatRRASErrorString
0x180021323  mov     rdx, cs:qword_18003EC40
0x18002132a  lea     r8, [rbp+7F0h+var_840]
0x18002132e  mov     rcx, cs:gNdpspEtwContext
0x180021335  mov     rax, cs:gNdpspTemplateFunc
0x18002133c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021341  jmp     short loc_18002135E
0x180021343  mov     ecx, cs:dwTraceId; dwTraceID
0x180021349  cmp     ecx, r15d
0x18002134c  jz      short loc_18002135E
0x18002134e  mov     r8d, eax
0x180021351  lea     rdx, aAsynceventsthr_1; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180021358  call    cs:__imp_TracePrintfA
0x18002135e  mov     ecx, 1; dwMilliseconds
0x180021363  call    cs:__imp_Sleep
0x180021369  jmp     loc_1800210B3
0x18002136e  xor     eax, eax
0x180021370  xorps   xmm0, xmm0
0x180021373  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18002137a  movups  [rbp+7F0h+var_870], xmm0
0x18002137e  mov     qword ptr [rbp+7F0h+var_860+10h], rax
0x180021382  movups  xmmword ptr [rbp+7F0h+var_860], xmm0
0x180021386  jz      short loc_1800213B8
0x180021388  mov     rdx, cs:qword_18003EC48
0x18002138f  test    rdx, rdx
0x180021392  jz      short loc_1800213B0
0x180021394  mov     rcx, cs:gNdpspEtwContext
0x18002139b  lea     r8, aAsynceventsthr_18; "AsyncEventsThread: Got a completed requ"...
0x1800213a2  mov     rax, cs:gNdpspTemplateFunc
0x1800213a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213ae  jmp     short loc_1800213D0
0x1800213b0  mov     ecx, cs:dwTraceId
0x1800213b6  jmp     short loc_1800213DD
0x1800213b8  mov     ecx, cs:dwTraceId; dwTraceID
0x1800213be  cmp     ecx, r15d
0x1800213c1  jz      short loc_1800213D6
0x1800213c3  lea     rdx, aAsynceventsthr_13; "AsyncEventsThread: Got a completed requ"...
0x1800213ca  call    cs:__imp_TracePrintfA
0x1800213d0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800213d6  mov     rdx, cs:qword_18003EC48
0x1800213dd  cmp     dword ptr [rbx+20h], 4152574Bh
0x1800213e4  jz      short loc_180021432
0x1800213e6  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800213ed  jz      short loc_180021417
0x1800213ef  test    rdx, rdx
0x1800213f2  jz      loc_1800210B3
0x1800213f8  lea     r8, aAsynceventsthr_12; "AsyncEventsThread: Got a bogus request"
0x1800213ff  mov     rcx, cs:gNdpspEtwContext
0x180021406  mov     rax, cs:gNdpspTemplateFunc
0x18002140d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021412  jmp     loc_1800210B3
0x180021417  cmp     ecx, r15d
0x18002141a  jz      loc_1800210B3
0x180021420  lea     rdx, aAsynceventsthr_24; "AsyncEventsThread: Got a bogus request"
0x180021427  call    cs:__imp_TracePrintfA
0x18002142d  jmp     loc_1800210B3
0x180021432  mov     ecx, [rbx+84h]
0x180021438  mov     esi, [rbx+98h]
0x18002143e  call    TranslateDriverResult
0x180021443  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18002144a  mov     edi, eax
0x18002144c  jz      short loc_180021496
0x18002144e  cmp     cs:qword_18003EC40, r14
0x180021455  jz      short loc_1800214B8
0x180021457  mov     r9d, esi
0x18002145a  mov     word ptr [rbp+7F0h+var_840], r14w
0x18002145f  mov     r8, rbx
0x180021462  mov     dword ptr [rsp+8F0h+lpOutBuffer], edi
0x180021466  lea     rdx, aAsynceventsthr_15; "AsyncEventsThread: Request (%p) with re"...
0x18002146d  lea     rcx, [rbp+7F0h+var_840]
0x180021471  call    FormatRRASErrorString
0x180021476  mov     rdx, cs:qword_18003EC40
0x18002147d  lea     r8, [rbp+7F0h+var_840]
0x180021481  mov     rcx, cs:gNdpspEtwContext
0x180021488  mov     rax, cs:gNdpspTemplateFunc
0x18002148f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021494  jmp     short loc_1800214B8
0x180021496  mov     ecx, cs:dwTraceId; dwTraceID
0x18002149c  cmp     ecx, r15d
0x18002149f  jz      short loc_1800214B8
0x1800214a1  mov     r9d, esi
0x1800214a4  mov     dword ptr [rsp+8F0h+lpOutBuffer], edi
0x1800214a8  mov     r8, rbx
0x1800214ab  lea     rdx, aAsynceventsthr; "AsyncEventsThread: Request (%p) with re"...
0x1800214b2  call    cs:__imp_TracePrintfA
0x1800214b8  mov     qword ptr [rbp+7F0h+var_870], r14
0x1800214bc  mov     rax, [rbx+28h]
0x1800214c0  test    rax, rax
0x1800214c3  jz      short loc_1800214D3
0x1800214c5  lea     r8, [rbp+7F0h+var_870]
0x1800214c9  mov     edx, edi
0x1800214cb  mov     rcx, rbx
0x1800214ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800214d3  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800214da  jz      short loc_180021520
0x1800214dc  cmp     cs:qword_18003EC40, r14
  ... truncated ...
```
