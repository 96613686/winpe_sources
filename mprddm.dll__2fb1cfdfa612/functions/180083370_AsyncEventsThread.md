# AsyncEventsThread

- ea: `0x180083370`
- end: `0x180083c08`
- name: `AsyncEventsThread`
- size: `2200`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180071cec`
- `0x180083370`
- `0x180084ae0`
- `0x1800892bc`
- `0x1800896e4`
- `0x18008a408`
- `0x18008c5f2`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x18008396f`
- `KERNEL32!DeleteCriticalSection` at `0x18008396f`
- `KERNEL32!DeviceIoControl` at `0x180083418`
- `KERNEL32!DeviceIoControl` at `0x1800836c9`
- `KERNEL32!DeviceIoControl` at `0x180083418`
- `KERNEL32!DeviceIoControl` at `0x1800836c9`
- `KERNEL32!Sleep` at `0x1800835c0`
- `KERNEL32!Sleep` at `0x180083753`
- `KERNEL32!Sleep` at `0x1800835c0`
- `KERNEL32!Sleep` at `0x180083753`
- `KERNEL32!GetProcessHeap` at `0x180083975`
- `KERNEL32!GetProcessHeap` at `0x180083975`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800834cd`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1800834cd`
- `KERNEL32!GetLastError` at `0x180083427`
- `KERNEL32!GetLastError` at `0x180083547`
- `KERNEL32!GetLastError` at `0x1800836d8`
- `KERNEL32!GetLastError` at `0x180083427`
- `KERNEL32!GetLastError` at `0x180083547`
- `KERNEL32!GetLastError` at `0x1800836d8`
- `KERNEL32!LeaveCriticalSection` at `0x180083966`
- `KERNEL32!LeaveCriticalSection` at `0x18008398b`
- `KERNEL32!LeaveCriticalSection` at `0x180083966`
- `KERNEL32!LeaveCriticalSection` at `0x18008398b`
- `KERNEL32!EnterCriticalSection` at `0x180083957`
- `KERNEL32!EnterCriticalSection` at `0x180083957`
- `KERNEL32!HeapFree` at `0x180083983`
- `KERNEL32!HeapFree` at `0x180083983`
- `rtutils!TracePrintfA` at `0x180083493`
- `rtutils!TracePrintfA` at `0x18008353c`
- `rtutils!TracePrintfA` at `0x1800835b5`
- `rtutils!TracePrintfA` at `0x18008361c`
- `rtutils!TracePrintfA` at `0x180083748`
- `rtutils!TracePrintfA` at `0x1800837ba`
- `rtutils!TracePrintfA` at `0x180083817`
- `rtutils!TracePrintfA` at `0x1800838a2`
- `rtutils!TracePrintfA` at `0x180083928`
- `rtutils!TracePrintfA` at `0x1800839f1`
- `rtutils!TracePrintfA` at `0x180083a9a`
- `rtutils!TracePrintfA` at `0x180083b0a`
- `rtutils!TracePrintfA` at `0x180083b8c`
- `rtutils!TracePrintfA` at `0x180083bf9`
- `rtutils!TracePrintfA` at `0x180083493`
- `rtutils!TracePrintfA` at `0x18008353c`
- `rtutils!TracePrintfA` at `0x1800835b5`
- `rtutils!TracePrintfA` at `0x18008361c`
- `rtutils!TracePrintfA` at `0x180083748`
- `rtutils!TracePrintfA` at `0x1800837ba`
- `rtutils!TracePrintfA` at `0x180083817`
- `rtutils!TracePrintfA` at `0x1800838a2`
- `rtutils!TracePrintfA` at `0x180083928`
- `rtutils!TracePrintfA` at `0x1800839f1`
- `rtutils!TracePrintfA` at `0x180083a9a`
- `rtutils!TracePrintfA` at `0x180083b0a`
- `rtutils!TracePrintfA` at `0x180083b8c`
- `rtutils!TracePrintfA` at `0x180083bf9`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180083c01`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x180083c01`

## string_xrefs

- `0x18008348c`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x18008344e`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)`
- `0x180083b85`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x180083b71`: `AsyncEventsThread: Got exit message from CleanupNdproxyIoControl`
- `0x180083535`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x180083511`: `AsyncEventsThread: GetQueuedCompletionStatus lpOverlapped == NULL!`
- `0x1800835ae`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x180083570`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second`
- `0x180083bf2`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x180083bb1`: `AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread`
- `0x180083615`: `AsyncEventsThread: Got a line event`
- `0x1800835f5`: `AsyncEventsThread: Got a line event`
- `0x180083741`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x180083703`: `AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)`
- `0x1800837b3`: `AsyncEventsThread: Got a completed request`
- `0x18008378b`: `AsyncEventsThread: Got a completed request`
- `0x180083810`: `AsyncEventsThread: Got a bogus request`
- `0x1800837e8`: `AsyncEventsThread: Got a bogus request`
- `0x18008389b`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x180083856`: `AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)`
- `0x18008391e`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x1800838e0`: `AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)`
- `0x1800839ea`: `AsyncEventsThread: Report back the saved call state`
- `0x1800839c6`: `AsyncEventsThread: Report back the saved call state`
- `0x180083a74`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x180083a11`: `AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)`
- `0x180083b03`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180083ad1`: `AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)`

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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed (0x%x)",
            LastError);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
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
              if ( (_QWORD)xmmword_1800C9BE0 )
              {
                LOWORD(v34) = 0;
                FormatRRASErrorString(
                  &v34,
                  L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Exiting thread",
                  6);
                v25 = xmmword_1800C9BE0;
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
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: GetQueuedCompletionStatus failed (0x%x). Sleeping for a second",
                v5);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800C9BE0,
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
            v25 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
            if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
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
          if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
        if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
          ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
            gNdpspEtwContext,
            *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: IoCtl(IOCTL_NDISTAPI_GET_LINE_EVENTS) failed to get line events (0x%x)",
                v11);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800C9BE0,
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
    v12 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
    if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
    {
      ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
        gNdpspEtwContext,
        *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          LODWORD(lpOutBuffer) = v16;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Request (%p) with reqID (0x%x) returned dwResult (0x%x)",
            v4,
            (unsigned int)hEvent_low,
            lpOutBuffer);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v34) = 0;
          FormatRRASErrorString(
            &v34,
            L"AsyncEventsThread: Async call completed with ReqID (%x), dwResult (%x)",
            (unsigned int)hEvent_low,
            (unsigned int)v17);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v34);
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
          if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              *((_QWORD *)&xmmword_1800C9BE0 + 1),
              L"AsyncEventsThread: Report back the saved call state");
          goto LABEL_78;
        }
        if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "AsyncEventsThread: Report back the saved call state");
LABEL_78:
          if ( gIsndpspEtwTracingAvailable )
          {
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(
                &v34,
                L"AsyncEventsThread: LINE_CALLSTATE htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
                v33[0],
                v33[1],
                *(_QWORD *)&v33[2]);
              ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                gNdpspEtwContext,
                xmmword_1800C9BE0,
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
            if ( (_QWORD)xmmword_1800C9BE0 )
            {
              LOWORD(v34) = 0;
              FormatRRASErrorString(&v34, L"AsyncEventsThread: GetLineObjWithReadLock failed with error (0x%x)", Lock);
              v12 = xmmword_1800C9BE0;
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
  v12 = *((_QWORD *)&xmmword_1800C9BE0 + 1);
  goto LABEL_50;
}

```

## disassembly

```asm
0x180083370  push    rbp
0x180083372  push    rbx
0x180083373  push    rsi
0x180083374  push    rdi
0x180083375  push    r14
0x180083377  push    r15
0x180083379  lea     rbp, [rsp-7C8h]
0x180083381  sub     rsp, 8C8h
0x180083388  mov     rax, cs:__security_cookie
0x18008338f  xor     rax, rsp
0x180083392  mov     [rbp+7F0h+var_40], rax
0x180083399  xor     r14d, r14d
0x18008339c  lea     rcx, [rbp+7F0h+var_83C]; void *
0x1800833a0  xorps   xmm0, xmm0
0x1800833a3  mov     [rsp+8F0h+Overlapped.Internal], r14
0x1800833a8  xor     edx, edx; Val
0x1800833aa  mov     [rsp+8F0h+BytesReturned], r14d
0x1800833af  mov     r8d, 7FCh; Size
0x1800833b5  mov     [rbp+7F0h+var_840], r14d
0x1800833b9  movdqu  xmmword ptr [rsp+8F0h+Overlapped.InternalHigh], xmm0
0x1800833bf  call    memset_0
0x1800833c4  mov     rdx, cs:g_pAsyncEventsThreadInfo
0x1800833cb  lea     r9d, [r14+0Ch]; nInBufferSize
0x1800833cf  mov     [rsp+8F0h+Overlapped.hEvent], r14
0x1800833d4  mov     ecx, [rdx+10h]
0x1800833d7  mov     rax, [rdx+8]
0x1800833db  sub     ecx, 0Ch
0x1800833de  mov     [rax], ecx
0x1800833e0  mov     rax, [rdx+8]
0x1800833e4  mov     rcx, cs:g_hDriverAsync; hDevice
0x1800833eb  mov     [rax+4], r14d
0x1800833ef  lea     rax, [rsp+8F0h+Overlapped]
0x1800833f4  mov     r8, [rdx+8]; lpInBuffer
0x1800833f8  mov     [rsp+8F0h+lpOverlapped], rax; lpOverlapped
0x1800833fd  lea     rax, [rsp+8F0h+BytesReturned]
0x180083402  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x180083407  mov     eax, [rdx+10h]
0x18008340a  mov     edx, 8FFF23D0h; dwIoControlCode
0x18008340f  mov     dword ptr [rsp+8F0h+lpOutBuffer+8], eax; nOutBufferSize
0x180083413  mov     qword ptr [rsp+8F0h+lpOutBuffer], r8; lpOutBuffer
0x180083418  call    cs:__imp_DeviceIoControl
0x18008341e  or      r15d, 0FFFFFFFFh
0x180083422  cmp     eax, 1
0x180083425  jz      short loc_180083499
0x180083427  call    cs:__imp_GetLastError
0x18008342d  cmp     eax, 3E5h
0x180083432  jz      short loc_180083499
0x180083434  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008343b  jz      short loc_18008347E
0x18008343d  cmp     qword ptr cs:xmmword_1800C9BE0, r14
0x180083444  jz      short loc_180083499
0x180083446  mov     r8d, eax
0x180083449  mov     word ptr [rbp+7F0h+var_840], r14w
0x18008344e  lea     rdx, aAsynceventsthr_20; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180083455  lea     rcx, [rbp+7F0h+var_840]
0x180083459  call    FormatRRASErrorString
0x18008345e  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180083465  lea     r8, [rbp+7F0h+var_840]
0x180083469  mov     rcx, cs:gNdpspEtwContext
0x180083470  mov     rax, cs:gNdpspTemplateFunc
0x180083477  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008347c  jmp     short loc_180083499
0x18008347e  mov     ecx, cs:dwTraceId; dwTraceID
0x180083484  cmp     ecx, r15d
0x180083487  jz      short loc_180083499
0x180083489  mov     r8d, eax
0x18008348c  lea     rdx, aAsynceventsthr_3; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180083493  call    cs:__imp_TracePrintfA
0x180083499  mov     rsi, 0AAAAAAAAAAAAAAABh
0x1800834a3  mov     [rsp+8F0h+var_8A0], r14
0x1800834a8  mov     rcx, cs:g_hAsyncIoCompletionPort; CompletionPort
0x1800834af  lea     r9, [rsp+8F0h+var_8A0]; lpOverlapped
0x1800834b4  lea     r8, [rsp+8F0h+CompletionKey]; lpCompletionKey
0x1800834b9  mov     [rsp+8F0h+NumberOfBytesTransferred], r14d
0x1800834be  lea     rdx, [rsp+8F0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1800834c3  mov     [rsp+8F0h+CompletionKey], r14
0x1800834c8  mov     dword ptr [rsp+8F0h+lpOutBuffer], r15d; dwMilliseconds
0x1800834cd  call    cs:__imp_GetQueuedCompletionStatus
0x1800834d3  test    eax, eax
0x1800834d5  jz      short loc_180083547
0x1800834d7  mov     rbx, [rsp+8F0h+var_8A0]
0x1800834dc  lea     rax, g_OverlappedTerminate
0x1800834e3  cmp     rax, rbx
0x1800834e6  jz      loc_180083B58
0x1800834ec  test    rbx, rbx
0x1800834ef  jnz     loc_1800835CB
0x1800834f5  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800834fc  jz      short loc_180083526
0x1800834fe  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x180083505  test    rdx, rdx
0x180083508  jz      short loc_1800834A8
0x18008350a  mov     rcx, cs:gNdpspEtwContext
0x180083511  lea     r8, aAsynceventsthr_14; "AsyncEventsThread: GetQueuedCompletionS"...
0x180083518  mov     rax, cs:gNdpspTemplateFunc
0x18008351f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083524  jmp     short loc_1800834A8
0x180083526  mov     ecx, cs:dwTraceId; dwTraceID
0x18008352c  cmp     ecx, r15d
0x18008352f  jz      loc_1800834A8
0x180083535  lea     rdx, aAsynceventsthr_22; "AsyncEventsThread: GetQueuedCompletionS"...
0x18008353c  call    cs:__imp_TracePrintfA
0x180083542  jmp     loc_1800834A8
0x180083547  call    cs:__imp_GetLastError
0x18008354d  cmp     eax, 6
0x180083550  jz      loc_180083B94
0x180083556  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008355d  jz      short loc_1800835A0
0x18008355f  cmp     qword ptr cs:xmmword_1800C9BE0, r14
0x180083566  jz      short loc_1800835BB
0x180083568  mov     r8d, eax
0x18008356b  mov     word ptr [rbp+7F0h+var_840], r14w
0x180083570  lea     rdx, aAsynceventsthr_19; "AsyncEventsThread: GetQueuedCompletionS"...
0x180083577  lea     rcx, [rbp+7F0h+var_840]
0x18008357b  call    FormatRRASErrorString
0x180083580  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180083587  lea     r8, [rbp+7F0h+var_840]
0x18008358b  mov     rcx, cs:gNdpspEtwContext
0x180083592  mov     rax, cs:gNdpspTemplateFunc
0x180083599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008359e  jmp     short loc_1800835BB
0x1800835a0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800835a6  cmp     ecx, r15d
0x1800835a9  jz      short loc_1800835BB
0x1800835ab  mov     r8d, eax
0x1800835ae  lea     rdx, aAsynceventsthr_0; "AsyncEventsThread: GetQueuedCompletionS"...
0x1800835b5  call    cs:__imp_TracePrintfA
0x1800835bb  mov     ecx, 1; dwMilliseconds
0x1800835c0  call    cs:__imp_Sleep
0x1800835c6  jmp     loc_1800834A8
0x1800835cb  lea     rax, [rsp+8F0h+Overlapped]
0x1800835d0  cmp     rbx, rax
0x1800835d3  jnz     loc_18008375E
0x1800835d9  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800835e0  jz      short loc_18008360A
0x1800835e2  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x1800835e9  test    rdx, rdx
0x1800835ec  jz      short loc_180083622
0x1800835ee  mov     rcx, cs:gNdpspEtwContext
0x1800835f5  lea     r8, aAsynceventsthr_25; "AsyncEventsThread: Got a line event"
0x1800835fc  mov     rax, cs:gNdpspTemplateFunc
0x180083603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083608  jmp     short loc_180083622
0x18008360a  mov     ecx, cs:dwTraceId; dwTraceID
0x180083610  cmp     ecx, r15d
0x180083613  jz      short loc_180083622
0x180083615  lea     rdx, aAsynceventsthr_11; "AsyncEventsThread: Got a line event"
0x18008361c  call    cs:__imp_TracePrintfA
0x180083622  mov     r9, cs:g_pAsyncEventsThreadInfo
0x180083629  mov     edi, r14d
0x18008362c  mov     rax, [r9+8]
0x180083630  mov     ecx, [rax+4]
0x180083633  lea     rbx, [rax+8]
0x180083637  mov     rax, rsi
0x18008363a  mul     rcx
0x18008363d  shr     rdx, 5
0x180083641  test    rdx, rdx
0x180083644  jz      short loc_180083678
0x180083646  test    rbx, rbx
0x180083649  jz      short loc_18008365E
0x18008364b  mov     rcx, rbx; eventRecord
0x18008364e  call    ProcessEvent
0x180083653  mov     r9, cs:g_pAsyncEventsThreadInfo
0x18008365a  add     rbx, 30h ; '0'
0x18008365e  mov     rax, [r9+8]
0x180083662  inc     edi
0x180083664  mov     ecx, [rax+4]
0x180083667  mov     rax, rsi
0x18008366a  mul     rcx
0x18008366d  mov     eax, edi
0x18008366f  shr     rdx, 5
0x180083673  cmp     rax, rdx
0x180083676  jb      short loc_180083646
0x180083678  mov     [rsp+8F0h+Overlapped.hEvent], r14
0x18008367d  mov     edx, 8FFF23D0h; dwIoControlCode
0x180083682  mov     ecx, [r9+10h]
0x180083686  mov     rax, [r9+8]
0x18008368a  sub     ecx, 0Bh
0x18008368d  mov     [rax], ecx
0x18008368f  mov     rax, [r9+8]
0x180083693  mov     rcx, cs:g_hDriverAsync; hDevice
0x18008369a  mov     [rax+4], r14d
0x18008369e  lea     rax, [rsp+8F0h+Overlapped]
0x1800836a3  mov     r8, [r9+8]; lpInBuffer
0x1800836a7  mov     [rsp+8F0h+lpOverlapped], rax; lpOverlapped
0x1800836ac  lea     rax, [rsp+8F0h+BytesReturned]
0x1800836b1  mov     [rsp+8F0h+lpBytesReturned], rax; lpBytesReturned
0x1800836b6  mov     eax, [r9+10h]
0x1800836ba  mov     r9d, 0Ch; nInBufferSize
0x1800836c0  mov     dword ptr [rsp+8F0h+lpOutBuffer+8], eax; nOutBufferSize
0x1800836c4  mov     qword ptr [rsp+8F0h+lpOutBuffer], r8; lpOutBuffer
0x1800836c9  call    cs:__imp_DeviceIoControl
0x1800836cf  cmp     eax, 1
0x1800836d2  jz      loc_1800834A3
0x1800836d8  call    cs:__imp_GetLastError
0x1800836de  cmp     eax, 3E5h
0x1800836e3  jz      loc_1800834A3
0x1800836e9  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800836f0  jz      short loc_180083733
0x1800836f2  cmp     qword ptr cs:xmmword_1800C9BE0, r14
0x1800836f9  jz      short loc_18008374E
0x1800836fb  mov     r8d, eax
0x1800836fe  mov     word ptr [rbp+7F0h+var_840], r14w
0x180083703  lea     rdx, aAsynceventsthr_21; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x18008370a  lea     rcx, [rbp+7F0h+var_840]
0x18008370e  call    FormatRRASErrorString
0x180083713  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008371a  lea     r8, [rbp+7F0h+var_840]
0x18008371e  mov     rcx, cs:gNdpspEtwContext
0x180083725  mov     rax, cs:gNdpspTemplateFunc
0x18008372c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083731  jmp     short loc_18008374E
0x180083733  mov     ecx, cs:dwTraceId; dwTraceID
0x180083739  cmp     ecx, r15d
0x18008373c  jz      short loc_18008374E
0x18008373e  mov     r8d, eax
0x180083741  lea     rdx, aAsynceventsthr_1; "AsyncEventsThread: IoCtl(IOCTL_NDISTAPI"...
0x180083748  call    cs:__imp_TracePrintfA
0x18008374e  mov     ecx, 1; dwMilliseconds
0x180083753  call    cs:__imp_Sleep
0x180083759  jmp     loc_1800834A3
0x18008375e  xor     eax, eax
0x180083760  xorps   xmm0, xmm0
0x180083763  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008376a  movups  [rbp+7F0h+var_870], xmm0
0x18008376e  mov     qword ptr [rbp+7F0h+var_860+10h], rax
0x180083772  movups  xmmword ptr [rbp+7F0h+var_860], xmm0
0x180083776  jz      short loc_1800837A8
0x180083778  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x18008377f  test    rdx, rdx
0x180083782  jz      short loc_1800837A0
0x180083784  mov     rcx, cs:gNdpspEtwContext
0x18008378b  lea     r8, aAsynceventsthr_18; "AsyncEventsThread: Got a completed requ"...
0x180083792  mov     rax, cs:gNdpspTemplateFunc
0x180083799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008379e  jmp     short loc_1800837C0
0x1800837a0  mov     ecx, cs:dwTraceId
0x1800837a6  jmp     short loc_1800837CD
0x1800837a8  mov     ecx, cs:dwTraceId; dwTraceID
0x1800837ae  cmp     ecx, r15d
0x1800837b1  jz      short loc_1800837C6
0x1800837b3  lea     rdx, aAsynceventsthr_13; "AsyncEventsThread: Got a completed requ"...
0x1800837ba  call    cs:__imp_TracePrintfA
0x1800837c0  mov     ecx, cs:dwTraceId; dwTraceID
0x1800837c6  mov     rdx, qword ptr cs:xmmword_1800C9BE0+8
0x1800837cd  cmp     dword ptr [rbx+20h], 4152574Bh
0x1800837d4  jz      short loc_180083822
0x1800837d6  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800837dd  jz      short loc_180083807
0x1800837df  test    rdx, rdx
0x1800837e2  jz      loc_1800834A3
0x1800837e8  lea     r8, aAsynceventsthr_12; "AsyncEventsThread: Got a bogus request"
0x1800837ef  mov     rcx, cs:gNdpspEtwContext
0x1800837f6  mov     rax, cs:gNdpspTemplateFunc
0x1800837fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083802  jmp     loc_1800834A3
0x180083807  cmp     ecx, r15d
0x18008380a  jz      loc_1800834A3
0x180083810  lea     rdx, aAsynceventsthr_24; "AsyncEventsThread: Got a bogus request"
0x180083817  call    cs:__imp_TracePrintfA
0x18008381d  jmp     loc_1800834A3
0x180083822  mov     ecx, [rbx+84h]
0x180083828  mov     esi, [rbx+98h]
0x18008382e  call    TranslateDriverResult
0x180083833  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x18008383a  mov     edi, eax
0x18008383c  jz      short loc_180083886
0x18008383e  cmp     qword ptr cs:xmmword_1800C9BE0, r14
0x180083845  jz      short loc_1800838A8
0x180083847  mov     r9d, esi
0x18008384a  mov     word ptr [rbp+7F0h+var_840], r14w
0x18008384f  mov     r8, rbx
0x180083852  mov     dword ptr [rsp+8F0h+lpOutBuffer], edi
0x180083856  lea     rdx, aAsynceventsthr_15; "AsyncEventsThread: Request (%p) with re"...
0x18008385d  lea     rcx, [rbp+7F0h+var_840]
0x180083861  call    FormatRRASErrorString
0x180083866  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x18008386d  lea     r8, [rbp+7F0h+var_840]
0x180083871  mov     rcx, cs:gNdpspEtwContext
0x180083878  mov     rax, cs:gNdpspTemplateFunc
0x18008387f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083884  jmp     short loc_1800838A8
0x180083886  mov     ecx, cs:dwTraceId; dwTraceID
0x18008388c  cmp     ecx, r15d
0x18008388f  jz      short loc_1800838A8
0x180083891  mov     r9d, esi
0x180083894  mov     dword ptr [rsp+8F0h+lpOutBuffer], edi
0x180083898  mov     r8, rbx
0x18008389b  lea     rdx, aAsynceventsthr; "AsyncEventsThread: Request (%p) with re"...
0x1800838a2  call    cs:__imp_TracePrintfA
0x1800838a8  mov     qword ptr [rbp+7F0h+var_870], r14
0x1800838ac  mov     rax, [rbx+28h]
0x1800838b0  test    rax, rax
0x1800838b3  jz      short loc_1800838C3
0x1800838b5  lea     r8, [rbp+7F0h+var_870]
0x1800838b9  mov     edx, edi
0x1800838bb  mov     rcx, rbx
0x1800838be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838c3  cmp     cs:gIsndpspEtwTracingAvailable, r14d
0x1800838ca  jz      short loc_180083910
0x1800838cc  cmp     qword ptr cs:xmmword_1800C9BE0, r14
  ... truncated ...
```
