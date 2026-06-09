# ProcessEvent

- ea: `0x18008aa50`
- end: `0x18008b5f0`
- name: `ProcessEvent`
- size: `2976`
- prototype: `HRESULT __stdcall(PEVENT_RECORD eventRecord)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800890b0`

## callees

- `0x1800755b8`
- `0x18008a88c`
- `0x18008aa50`
- `0x18008c578`
- `0x18008e6f4`
- `0x18008ef04`
- `0x18008f0a4`
- `0x18008f50c`
- `0x18008f69c`
- `0x18008fb8c`
- `0x18008fd44`
- `0x180090344`
- `0x180090714`
- `0x180090834`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x18008b098`
- `KERNEL32!DeviceIoControl` at `0x18008b098`
- `KERNEL32!GetProcessHeap` at `0x18008aca4`
- `KERNEL32!GetProcessHeap` at `0x18008adee`
- `KERNEL32!GetProcessHeap` at `0x18008aee1`
- `KERNEL32!GetProcessHeap` at `0x18008af4f`
- `KERNEL32!GetProcessHeap` at `0x18008aca4`
- `KERNEL32!GetProcessHeap` at `0x18008adee`
- `KERNEL32!GetProcessHeap` at `0x18008aee1`
- `KERNEL32!GetProcessHeap` at `0x18008af4f`
- `KERNEL32!HeapAlloc` at `0x18008acbc`
- `KERNEL32!HeapAlloc` at `0x18008acbc`
- `KERNEL32!GetLastError` at `0x18008b0c6`
- `KERNEL32!GetLastError` at `0x18008b0ee`
- `KERNEL32!GetLastError` at `0x18008b0c6`
- `KERNEL32!GetLastError` at `0x18008b0ee`
- `KERNEL32!HeapFree` at `0x18008ae02`
- `KERNEL32!HeapFree` at `0x18008aef5`
- `KERNEL32!HeapFree` at `0x18008af63`
- `KERNEL32!HeapFree` at `0x18008ae02`
- `KERNEL32!HeapFree` at `0x18008aef5`
- `KERNEL32!HeapFree` at `0x18008af63`
- `rtutils!TracePrintfA` at `0x18008ab73`
- `rtutils!TracePrintfA` at `0x18008ade2`
- `rtutils!TracePrintfA` at `0x18008aed5`
- `rtutils!TracePrintfA` at `0x18008afc1`
- `rtutils!TracePrintfA` at `0x18008b260`
- `rtutils!TracePrintfA` at `0x18008b365`
- `rtutils!TracePrintfA` at `0x18008b3db`
- `rtutils!TracePrintfA` at `0x18008b48a`
- `rtutils!TracePrintfA` at `0x18008b576`
- `rtutils!TracePrintfA` at `0x18008ab73`
- `rtutils!TracePrintfA` at `0x18008ade2`
- `rtutils!TracePrintfA` at `0x18008aed5`
- `rtutils!TracePrintfA` at `0x18008afc1`
- `rtutils!TracePrintfA` at `0x18008b260`
- `rtutils!TracePrintfA` at `0x18008b365`
- `rtutils!TracePrintfA` at `0x18008b3db`
- `rtutils!TracePrintfA` at `0x18008b48a`
- `rtutils!TracePrintfA` at `0x18008b576`

## string_xrefs

- `0x18008b555`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008b227`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x18008b56c`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008b202`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x18008b242`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x18008b295`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x18008b259`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x18008b2b0`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x18008ac7d`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008ac98`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008b002`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008b0d5`: `ProcessEvent: CREATE failed (0x%x)`
- `0x18008b020`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008b100`: `ProcessEvent: CREATE failed (0x%x)`

## pseudocode

```c
HRESULT __stdcall ProcessEvent(PEVENT_RECORD eventRecord)
{
  DWORD LowPart; // r15d
  unsigned int v3; // r14d
  __int64 v4; // rbx
  DWORD v5; // ecx
  HRESULT result; // eax
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  DWORD v9; // ecx
  const CHAR *v10; // rdx
  HANDLE ProcessHeap; // rax
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // rbx
  _DWORD *v15; // rdi
  __int64 v16; // rdx
  unsigned int v17; // ebx
  void *v18; // rbx
  _DWORD *v19; // rdx
  unsigned int v20; // eax
  HANDLE v21; // rax
  void *v22; // rbx
  void *v23; // rdx
  unsigned int v24; // eax
  HANDLE v25; // rax
  _DWORD *v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  _DWORD *v29; // rsi
  HANDLE v30; // rax
  unsigned int v31; // edi
  __int64 v32; // rax
  __int64 LastError; // r8
  __int64 v34; // r12
  __int64 v35; // rdi
  int v36; // ebx
  int v37; // r15d
  unsigned int v38; // eax
  bool v39; // zf
  int v40; // r8d
  __int64 v41; // r8
  __int64 v42; // rcx
  __int64 v43; // rdx
  __int64 v44; // rdi
  unsigned int v45; // ebx
  __int64 v46; // rbx
  LPDWORD lpBytesReturned; // [rsp+38h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+40h] [rbp-C8h]
  __int64 v49; // [rsp+48h] [rbp-C0h]
  _DWORD *OutBuffer; // [rsp+58h] [rbp-B0h] BYREF
  LPVOID lpInBuffer; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID lpMem[2]; // [rsp+68h] [rbp-A0h] BYREF
  int v53; // [rsp+78h] [rbp-90h] BYREF
  char v54[28]; // [rsp+7Ch] [rbp-8Ch] BYREF
  unsigned int v55; // [rsp+98h] [rbp-70h]
  int v56; // [rsp+1D8h] [rbp+D0h] BYREF
  char v57[2044]; // [rsp+1DCh] [rbp+D4h] BYREF

  LowPart = eventRecord->EventHeader.TimeStamp.LowPart;
  v3 = *(_DWORD *)&eventRecord->EventHeader.Size;
  v4 = *(_QWORD *)&eventRecord->EventHeader.ThreadId;
  v56 = 0;
  memset_0(v57, 0, sizeof(v57));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( (_QWORD)xmmword_1800D0BE0 )
    {
      v49 = *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id;
      lpOverlapped = *(LPOVERLAPPED *)eventRecord->EventHeader.ProviderId.Data4;
      lpBytesReturned = *(LPDWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      LOWORD(v56) = 0;
      FormatRRASErrorString(
        &v56,
        L"ProcessEvent: Event(%p), msg(0x%x), ht_line(0x%x), ht_call(0x%x), p1(%p), p2(%p), p3(%p)",
        eventRecord,
        LowPart,
        v3,
        v4,
        lpBytesReturned,
        lpOverlapped,
        v49);
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v56);
    }
  }
  else
  {
    v5 = dwTraceId;
    if ( dwTraceId == -1 )
      goto LABEL_7;
    TracePrintfA(
      dwTraceId,
      "ProcessEvent: Event(%p), msg(0x%x), ht_line(0x%x), ht_call(0x%x), p1(%p), p2(%p), p3(%p)",
      eventRecord,
      LowPart,
      v3,
      v4,
      *(const void **)&eventRecord->EventHeader.ProviderId.Data1,
      *(const void **)eventRecord->EventHeader.ProviderId.Data4,
      *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
  }
  v5 = dwTraceId;
LABEL_7:
  switch ( LowPart )
  {
    case 0u:
LABEL_122:
      lpInBuffer = 0;
      result = GetLineObjWithReadLock(v3, &lpInBuffer);
      if ( result )
      {
        if ( !gIsndpspEtwTracingAvailable )
        {
          v9 = dwTraceId;
          if ( dwTraceId == -1 )
            return result;
          v10 = "ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)";
          return TracePrintfA(v9, v10, (unsigned int)result);
        }
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)";
        goto LABEL_19;
      }
      v46 = *((_QWORD *)lpInBuffer + 4);
      ReleaseObjReadLock(v3);
      v41 = v46;
      v42 = 0;
LABEL_130:
      v43 = LowPart;
      return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnCallback)(v42, v43, v41);
    case 1u:
LABEL_118:
      lpInBuffer = 0;
      OutBuffer = 0;
      result = GetLineAndCallObjWithReadLock(v3, v4, &lpInBuffer, &OutBuffer);
      if ( result )
        goto LABEL_119;
      v44 = *((_QWORD *)lpInBuffer + 4);
      v45 = OutBuffer[2];
      ReleaseObjReadLock(v45);
      ReleaseObjReadLock(v3);
      v42 = v45;
      v41 = v44;
      goto LABEL_130;
    case 2u:
      lpInBuffer = 0;
      OutBuffer = 0;
      result = GetLineAndCallObjWithReadLock(v3, v4, &lpInBuffer, &OutBuffer);
      if ( result )
      {
LABEL_119:
        if ( !gIsndpspEtwTracingAvailable )
        {
          v9 = dwTraceId;
          if ( dwTraceId == -1 )
            return result;
          v10 = "ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)";
          return TracePrintfA(v9, v10, (unsigned int)result);
        }
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)";
LABEL_19:
        LOWORD(v56) = 0;
        FormatRRASErrorString(&v56, v8, v7);
        return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                 gNdpspEtwContext,
                 xmmword_1800D0BE0,
                 &v56);
      }
      v34 = *((_QWORD *)lpInBuffer + 4);
      v35 = (unsigned int)OutBuffer[2];
      v36 = *OutBuffer;
      v37 = OutBuffer[16];
      ReleaseObjReadLock(v35);
      ReleaseObjReadLock(v3);
      if ( v36 == 1329807692 && v37 == 1 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( *((_QWORD *)&xmmword_1800D0BE0 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              *((_QWORD *)&xmmword_1800D0BE0 + 1),
              L"ProcessEvent: Incomplete outbound call, saving state");
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: Incomplete outbound call, saving state");
        }
        result = GetCallObjWithWriteLock((unsigned int)v35, &OutBuffer);
        if ( result )
        {
          if ( !gIsndpspEtwTracingAvailable )
          {
            v9 = dwTraceId;
            if ( dwTraceId == -1 )
              return result;
            v10 = "ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)";
            return TracePrintfA(v9, v10, (unsigned int)result);
          }
          if ( !(_QWORD)xmmword_1800D0BE0 )
            return result;
          v7 = (unsigned int)result;
          v8 = L"ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)";
          goto LABEL_19;
        }
        v27 = (unsigned int)v35;
        v26 = OutBuffer;
        OutBuffer[9] = eventRecord->EventHeader.ProviderId.Data1;
        v26[10] = *(_DWORD *)eventRecord->EventHeader.ProviderId.Data4;
        v26[11] = *(_DWORD *)&eventRecord->EventHeader.EventDescriptor.Id;
        return ReleaseObjWriteLock(v27, v26);
      }
      if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 == 2 )
      {
        memset_0(v54, 0, 0x154u);
        v53 = 344;
        v38 = RasLineGetCallInfo((unsigned int)v35, &v53);
        if ( v38 )
        {
          if ( !gIsndpspEtwTracingAvailable )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "ProcessEvent: RasLineGetCallInfo failed with error 0x%x", v38);
            goto LABEL_111;
          }
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"ProcessEvent: RasLineGetCallInfo failed with error 0x%x", v38);
            goto LABEL_108;
          }
        }
        else
        {
          v39 = gIsndpspEtwTracingAvailable == 0;
          v40 = v55;
          *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id = v55;
          if ( v39 )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "ProcessEvent: Setting media mode to 0x%x", v40);
            goto LABEL_111;
          }
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"ProcessEvent: Setting media mode to 0x%x");
LABEL_108:
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v56);
          }
        }
      }
LABEL_111:
      result = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, _QWORD, _QWORD))g_pfnCallback)(
                 v35,
                 2,
                 v34,
                 *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1,
                 *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
                 *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
      if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 != 0x4000 )
        return result;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v56) = 0;
          FormatRRASErrorString(&v56, L"ProcessEvent: LINECALLSTATE_IDLE: hCall(%p)", (unsigned int)v35);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v56);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "ProcessEvent: LINECALLSTATE_IDLE: hCall(%p)", (const void *)(unsigned int)v35);
      }
      v41 = v34;
      v42 = v35;
      v43 = 2;
      return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnCallback)(v42, v43, v41);
    case 3u:
    case 4u:
    case 8u:
      goto LABEL_122;
    case 0x13u:
      LODWORD(OutBuffer) = *(_DWORD *)eventRecord->EventHeader.ProviderId.Data4;
      HIDWORD(OutBuffer) = g_dwNumNDProxyLines;
      LODWORD(lpMem[0]) = 0;
      result = DeviceIoControl(g_hDriverSync, 0x8FFF23D8, &OutBuffer, 8u, &OutBuffer, 8u, (LPDWORD)lpMem, 0);
      if ( result )
      {
        result = ((__int64 (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD, _QWORD, __int64))g_pfnCallback)(
                   0,
                   19,
                   0,
                   HIDWORD(OutBuffer),
                   *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
                   1);
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            return TracePrintfA(
                     dwTraceId,
                     "ProcessEvent: New line added. Total number of NDProxy lines is now 0x%x",
                     (unsigned int)g_dwNumNDProxyLines);
          return result;
        }
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = (unsigned int)g_dwNumNDProxyLines;
        v8 = L"ProcessEvent: New line added. Total number of NDProxy lines is now 0x%x";
        goto LABEL_19;
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800D0BE0 )
        {
          LOWORD(v56) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(&v56, L"ProcessEvent: CREATE failed (0x%x)", LastError);
          return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                   gNdpspEtwContext,
                   xmmword_1800D0BE0,
                   &v56);
        }
        return result;
      }
      if ( dwTraceId == -1 )
        return result;
      result = GetLastError();
      v9 = dwTraceId;
      v10 = "ProcessEvent: CREATE failed (0x%x)";
      return TracePrintfA(v9, v10, (unsigned int)result);
  }
  result = LowPart - 500;
  if ( LowPart == 500 )
  {
    OutBuffer = 0;
    LODWORD(lpMem[0]) = 0;
    result = GetLineObjWithWriteLock(v3, &OutBuffer);
    if ( result )
    {
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)";
        goto LABEL_19;
      }
      v9 = dwTraceId;
      if ( dwTraceId == -1 )
        return result;
      v10 = "ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)";
      return TracePrintfA(v9, v10, (unsigned int)result);
    }
    ProcessHeap = GetProcessHeap();
    v12 = HeapAlloc(ProcessHeap, 8u, 0x48u);
    v14 = v12;
    if ( v12 )
    {
      *(_DWORD *)v12 = 1229144396;
      v12[3] = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      v28 = *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4;
      v29 = OutBuffer;
      v14[2] = v28;
      *((_DWORD *)v14 + 8) = v3;
      *((_DWORD *)v14 + 16) = 0;
      *((_DWORD *)v14 + 1) = v29[1];
      ReleaseObjWriteLock(v3, v13);
      if ( (unsigned int)OpenObjHandle(v14, lpMem) )
      {
        v30 = GetProcessHeap();
        result = HeapFree(v30, 0, v14);
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"ProcessEvent: Failed to map call object (%p) to handle", v14);
            return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))gNdpspTemplateFunc)(
                     gNdpspEtwContext,
                     xmmword_1800D0BE0,
                     &v56);
          }
        }
        else if ( dwTraceId != -1 )
        {
          return TracePrintfA(dwTraceId, "ProcessEvent: Failed to map call object (%p) to handle", v14);
        }
        return result;
      }
      v31 = AcquireObjWriteLock(v3);
      if ( v31 )
      {
        result = CloseObjHandle(LODWORD(lpMem[0]));
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            return TracePrintfA(dwTraceId, "ProcessEvent: AcquireObjWriteLock failed with error (0x%x)", v31);
          return result;
        }
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = v31;
        v8 = L"ProcessEvent: AcquireObjWriteLock failed with error (0x%x)";
        goto LABEL_19;
      }
      *((_DWORD *)v14 + 2) = lpMem[0];
      v32 = *((_QWORD *)v29 + 3);
      v14[7] = v32;
      if ( v32 )
        *(_QWORD *)(v32 + 48) = v14;
      *((_QWORD *)v29 + 3) = v14;
    }
    else
    {
      v15 = OutBuffer;
      lpMem[0] = 0;
      lpInBuffer = 0;
      v17 = PrepareSyncRequest(117637385, (unsigned int)OutBuffer[1], 24, lpMem);
      if ( v17 )
        goto LABEL_42;
      v18 = lpMem[0];
      v19 = lpMem[0];
      *((_QWORD *)lpMem[0] + 7) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      v19[16] = 0;
      SyncDriverRequest(0x8FFF23CC, v19);
      v20 = SyncDriverRequest(0x8FFF23CC, v18);
      if ( v20 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(&v56, L"ProcessEvent: SyncDriverRequest(OID_TAPI_DROP) failed with error (0x%x)", v20);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v56);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: SyncDriverRequest(OID_TAPI_DROP) failed with error (0x%x)", v20);
        }
      }
      v21 = GetProcessHeap();
      HeapFree(v21, 0, v18);
      v17 = PrepareSyncRequest(117637380, (unsigned int)v15[1], 16, &lpInBuffer);
      if ( v17 )
      {
LABEL_42:
        result = ReleaseObjWriteLock(v3, v16);
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            return TracePrintfA(dwTraceId, "ProcessEvent: PrepareSyncRequest failed with error (0x%x)", v17);
          return result;
        }
        if ( !(_QWORD)xmmword_1800D0BE0 )
          return result;
        v7 = v17;
        v8 = L"ProcessEvent: PrepareSyncRequest failed with error (0x%x)";
        goto LABEL_19;
      }
      v22 = lpInBuffer;
      v23 = lpInBuffer;
      *((_QWORD *)lpInBuffer + 7) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      SyncDriverRequest(0x8FFF23CC, v23);
      v24 = SyncDriverRequest(0x8FFF23CC, v22);
      if ( v24 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( (_QWORD)xmmword_1800D0BE0 )
          {
            LOWORD(v56) = 0;
            FormatRRASErrorString(
              &v56,
              L"ProcessEvent: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
              v24);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800D0BE0, &v56);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)", v24);
        }
      }
      v25 = GetProcessHeap();
      HeapFree(v25, 0, v22);
    }
    v27 = v3;
    return ReleaseObjWriteLock(v27, v26);
  }
  if ( LowPart == 501 )
    goto LABEL_118;
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( !(_QWORD)xmmword_1800D0BE0 )
      return result;
    v7 = LowPart;
    v8 = L"ProcessEvent: Unhandled msg (0x%x)";
    goto LABEL_19;
  }
  if ( v5 != -1 )
    return TracePrintfA(v5, "ProcessEvent: Unhandled msg (0x%x)", LowPart);
  return result;
}

```

## disassembly

```asm
0x18008aa50  mov     rax, rsp
0x18008aa53  mov     [rax+10h], rbx
0x18008aa57  mov     [rax+18h], rsi
0x18008aa5b  mov     [rax+20h], rdi
0x18008aa5f  push    rbp
0x18008aa60  push    r12
0x18008aa62  push    r13
0x18008aa64  push    r14
0x18008aa66  push    r15
0x18008aa68  lea     rbp, [rax-908h]
0x18008aa6f  sub     rsp, 9E0h
0x18008aa76  mov     rax, cs:__security_cookie
0x18008aa7d  xor     rax, rsp
0x18008aa80  mov     [rbp+900h+var_30], rax
0x18008aa87  mov     r15d, [rcx+10h]
0x18008aa8b  mov     rsi, rcx
0x18008aa8e  mov     r14d, [rcx]
0x18008aa91  xor     r13d, r13d
0x18008aa94  mov     rbx, [rcx+8]
0x18008aa98  xor     edx, edx; Val
0x18008aa9a  lea     rcx, [rbp+900h+var_82C]; void *
0x18008aaa1  mov     [rbp+900h+var_830], r13d
0x18008aaa8  mov     r8d, 7FCh; Size
0x18008aaae  call    memset_0
0x18008aab3  or      r12d, 0FFFFFFFFh
0x18008aab7  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008aabe  jz      short loc_18008AB36
0x18008aac0  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008aac7  jz      loc_18008AB7F
0x18008aacd  mov     rax, [rsi+28h]
0x18008aad1  lea     rdx, aProcesseventEv; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x18008aad8  mov     [rsp+0A00h+var_9C0], rax
0x18008aadd  lea     rcx, [rbp+900h+var_830]
0x18008aae4  mov     rax, [rsi+20h]
0x18008aae8  mov     r9d, r15d
0x18008aaeb  mov     [rsp+0A00h+lpOverlapped], rax
0x18008aaf0  mov     r8, rsi
0x18008aaf3  mov     rax, [rsi+18h]
0x18008aaf7  mov     [rsp+0A00h+lpBytesReturned], rax
0x18008aafc  mov     qword ptr [rsp+0A00h+nOutBufferSize], rbx
0x18008ab01  mov     dword ptr [rsp+0A00h+lpOutBuffer], r14d
0x18008ab06  mov     word ptr [rbp+900h+var_830], r13w
0x18008ab0e  call    FormatRRASErrorString
0x18008ab13  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008ab1a  lea     r8, [rbp+900h+var_830]
0x18008ab21  mov     rcx, cs:gNdpspEtwContext
0x18008ab28  mov     rax, cs:gNdpspTemplateFunc
0x18008ab2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ab34  jmp     short loc_18008AB7F
0x18008ab36  mov     ecx, cs:dwTraceId; dwTraceID
0x18008ab3c  cmp     ecx, r12d
0x18008ab3f  jz      short loc_18008AB85
0x18008ab41  mov     rax, [rsi+28h]
0x18008ab45  lea     rdx, aProcesseventEv_0; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x18008ab4c  mov     [rsp+0A00h+var_9C0], rax
0x18008ab51  mov     r9d, r15d
0x18008ab54  mov     rax, [rsi+20h]
0x18008ab58  mov     r8, rsi
0x18008ab5b  mov     [rsp+0A00h+lpOverlapped], rax
0x18008ab60  mov     rax, [rsi+18h]
0x18008ab64  mov     [rsp+0A00h+lpBytesReturned], rax
0x18008ab69  mov     qword ptr [rsp+0A00h+nOutBufferSize], rbx
0x18008ab6e  mov     dword ptr [rsp+0A00h+lpOutBuffer], r14d
0x18008ab73  call    cs:__imp_TracePrintfA
0x18008ab7a  nop     dword ptr [rax+rax+00h]
0x18008ab7f  mov     ecx, cs:dwTraceId
0x18008ab85  mov     eax, r15d
0x18008ab88  test    r15d, r15d
0x18008ab8b  jz      loc_18008B52A
0x18008ab91  sub     eax, 1
0x18008ab94  jz      loc_18008B4B9
0x18008ab9a  sub     eax, 1
0x18008ab9d  jz      loc_18008B183
0x18008aba3  sub     eax, 1
0x18008aba6  jz      loc_18008B52A
0x18008abac  sub     eax, 1
0x18008abaf  jz      loc_18008B52A
0x18008abb5  sub     eax, 4
0x18008abb8  jz      loc_18008B52A
0x18008abbe  sub     eax, 0Bh
0x18008abc1  jz      loc_18008B04D
0x18008abc7  sub     eax, 1E1h
0x18008abcc  jz      short loc_18008AC49
0x18008abce  cmp     eax, 1
0x18008abd1  jz      loc_18008B4B9
0x18008abd7  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008abde  jz      short loc_18008AC31
0x18008abe0  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008abe7  jz      loc_18008B5BF
0x18008abed  mov     r8d, r15d
0x18008abf0  lea     rdx, aProcesseventUn_0; "ProcessEvent: Unhandled msg (0x%x)"
0x18008abf7  mov     word ptr [rbp+900h+var_830], r13w
0x18008abff  lea     rcx, [rbp+900h+var_830]
0x18008ac06  call    FormatRRASErrorString
0x18008ac0b  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008ac12  lea     r8, [rbp+900h+var_830]
0x18008ac19  mov     rcx, cs:gNdpspEtwContext
0x18008ac20  mov     rax, cs:gNdpspTemplateFunc
0x18008ac27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac2c  jmp     loc_18008B5BF
0x18008ac31  cmp     ecx, r12d
0x18008ac34  jz      loc_18008B5BF
0x18008ac3a  mov     r8d, r15d
0x18008ac3d  lea     rdx, aProcesseventUn; "ProcessEvent: Unhandled msg (0x%x)"
0x18008ac44  jmp     loc_18008B576
0x18008ac49  lea     rdx, [rsp+0A00h+OutBuffer]
0x18008ac4e  mov     [rsp+0A00h+OutBuffer], r13
0x18008ac53  mov     ecx, r14d
0x18008ac56  mov     dword ptr [rsp+0A00h+lpMem], r13d
0x18008ac5b  call    GetLineObjWithWriteLock
0x18008ac60  test    eax, eax
0x18008ac62  jz      short loc_18008ACA4
0x18008ac64  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008ac6b  jz      short loc_18008AC89
0x18008ac6d  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008ac74  jz      loc_18008B5BF
0x18008ac7a  mov     r8d, eax
0x18008ac7d  lea     rdx, aProcesseventGe_1; "ProcessEvent: GetLineObjWithWriteLock f"...
0x18008ac84  jmp     loc_18008ABF7
0x18008ac89  mov     ecx, cs:dwTraceId
0x18008ac8f  cmp     ecx, r12d
0x18008ac92  jz      loc_18008B5BF
0x18008ac98  lea     rdx, aProcesseventGe_2; "ProcessEvent: GetLineObjWithWriteLock f"...
0x18008ac9f  jmp     loc_18008B573
0x18008aca4  call    cs:__imp_GetProcessHeap
0x18008acab  nop     dword ptr [rax+rax+00h]
0x18008acb0  mov     edx, 8; dwFlags
0x18008acb5  mov     rcx, rax; hHeap
0x18008acb8  lea     r8d, [rdx+40h]; dwBytes
0x18008acbc  call    cs:__imp_HeapAlloc
0x18008acc3  nop     dword ptr [rax+rax+00h]
0x18008acc8  mov     rbx, rax
0x18008accb  test    rax, rax
0x18008acce  jnz     loc_18008AF09
0x18008acd4  mov     rdi, [rsp+0A00h+OutBuffer]
0x18008acd9  lea     r9, [rsp+0A00h+lpMem]
0x18008acde  lea     r8d, [rax+18h]
0x18008ace2  mov     [rsp+0A00h+lpMem], r13
0x18008ace7  mov     ecx, 7030109h
0x18008acec  mov     [rsp+0A00h+lpInBuffer], r13
0x18008acf1  mov     edx, [rdi+4]
0x18008acf4  call    PrepareSyncRequest
0x18008acf9  mov     ebx, eax
0x18008acfb  test    eax, eax
0x18008acfd  jnz     loc_18008AE2C
0x18008ad03  mov     rbx, [rsp+0A00h+lpMem]
0x18008ad08  mov     r15d, 8FFF23CCh
0x18008ad0e  mov     rax, [rsi+18h]
0x18008ad12  mov     rdx, rbx; lpInBuffer
0x18008ad15  mov     ecx, r15d; dwIoControlCode
0x18008ad18  mov     [rbx+38h], rax
0x18008ad1c  mov     [rbx+40h], r13d
0x18008ad20  call    SyncDriverRequest
0x18008ad25  mov     rdx, rbx; lpInBuffer
0x18008ad28  mov     ecx, r15d; dwIoControlCode
0x18008ad2b  call    SyncDriverRequest
0x18008ad30  test    eax, eax
0x18008ad32  jz      loc_18008ADEE
0x18008ad38  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008ad3f  jz      loc_18008ADCD
0x18008ad45  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008ad4c  jz      loc_18008ADEE
0x18008ad52  mov     r8d, eax
0x18008ad55  mov     word ptr [rbp+900h+var_830], r13w
0x18008ad5d  lea     rdx, aProcesseventSy_1; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x18008ad64  lea     rcx, [rbp+900h+var_830]
0x18008ad6b  call    FormatRRASErrorString
0x18008ad70  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008ad77  lea     r8, [rbp+900h+var_830]
0x18008ad7e  mov     rcx, cs:gNdpspEtwContext
0x18008ad85  mov     rax, cs:gNdpspTemplateFunc
0x18008ad8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ad91  jmp     short loc_18008ADEE
0x18008ad93  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008ad9a  jz      loc_18008B5BF
0x18008ada0  mov     r8d, ebx
0x18008ada3  lea     rdx, aProcesseventPr; "ProcessEvent: PrepareSyncRequest failed"...
0x18008adaa  jmp     loc_18008ABF7
0x18008adaf  mov     ecx, cs:dwTraceId
0x18008adb5  cmp     ecx, r12d
0x18008adb8  jz      loc_18008B5BF
0x18008adbe  mov     r8d, ebx
0x18008adc1  lea     rdx, aProcesseventPr_0; "ProcessEvent: PrepareSyncRequest failed"...
0x18008adc8  jmp     loc_18008B576
0x18008adcd  mov     ecx, cs:dwTraceId; dwTraceID
0x18008add3  cmp     ecx, r12d
0x18008add6  jz      short loc_18008ADEE
0x18008add8  mov     r8d, eax
0x18008addb  lea     rdx, aProcesseventSy; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x18008ade2  call    cs:__imp_TracePrintfA
0x18008ade9  nop     dword ptr [rax+rax+00h]
0x18008adee  call    cs:__imp_GetProcessHeap
0x18008adf5  nop     dword ptr [rax+rax+00h]
0x18008adfa  mov     r8, rbx; lpMem
0x18008adfd  xor     edx, edx; dwFlags
0x18008adff  mov     rcx, rax; hHeap
0x18008ae02  call    cs:__imp_HeapFree
0x18008ae09  nop     dword ptr [rax+rax+00h]
0x18008ae0e  mov     edx, [rdi+4]
0x18008ae11  lea     r9, [rsp+0A00h+lpInBuffer]
0x18008ae16  mov     r8d, 10h
0x18008ae1c  mov     ecx, 7030104h
0x18008ae21  call    PrepareSyncRequest
0x18008ae26  mov     ebx, eax
0x18008ae28  test    eax, eax
0x18008ae2a  jz      short loc_18008AE46
0x18008ae2c  mov     ecx, r14d
0x18008ae2f  call    ReleaseObjWriteLock
0x18008ae34  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008ae3b  jnz     loc_18008AD93
0x18008ae41  jmp     loc_18008ADAF
0x18008ae46  mov     rbx, [rsp+0A00h+lpInBuffer]
0x18008ae4b  mov     ecx, r15d; dwIoControlCode
0x18008ae4e  mov     rax, [rsi+18h]
0x18008ae52  mov     rdx, rbx; lpInBuffer
0x18008ae55  mov     [rbx+38h], rax
0x18008ae59  call    SyncDriverRequest
0x18008ae5e  mov     rdx, rbx; lpInBuffer
0x18008ae61  mov     ecx, r15d; dwIoControlCode
0x18008ae64  call    SyncDriverRequest
0x18008ae69  test    eax, eax
0x18008ae6b  jz      short loc_18008AEE1
0x18008ae6d  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008ae74  jz      short loc_18008AEC0
0x18008ae76  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008ae7d  jz      short loc_18008AEE1
0x18008ae7f  mov     r8d, eax
0x18008ae82  mov     word ptr [rbp+900h+var_830], r13w
0x18008ae8a  lea     rdx, aProcesseventSy_0; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x18008ae91  lea     rcx, [rbp+900h+var_830]
0x18008ae98  call    FormatRRASErrorString
0x18008ae9d  mov     rdx, qword ptr cs:xmmword_1800D0BE0
0x18008aea4  lea     r8, [rbp+900h+var_830]
0x18008aeab  mov     rcx, cs:gNdpspEtwContext
0x18008aeb2  mov     rax, cs:gNdpspTemplateFunc
0x18008aeb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008aebe  jmp     short loc_18008AEE1
0x18008aec0  mov     ecx, cs:dwTraceId; dwTraceID
0x18008aec6  cmp     ecx, r12d
0x18008aec9  jz      short loc_18008AEE1
0x18008aecb  mov     r8d, eax
0x18008aece  lea     rdx, aProcesseventSy_2; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x18008aed5  call    cs:__imp_TracePrintfA
0x18008aedc  nop     dword ptr [rax+rax+00h]
0x18008aee1  call    cs:__imp_GetProcessHeap
0x18008aee8  nop     dword ptr [rax+rax+00h]
0x18008aeed  mov     r8, rbx; lpMem
0x18008aef0  xor     edx, edx; dwFlags
0x18008aef2  mov     rcx, rax; hHeap
0x18008aef5  call    cs:__imp_HeapFree
0x18008aefc  nop     dword ptr [rax+rax+00h]
0x18008af01  mov     ecx, r14d
0x18008af04  jmp     loc_18008B2D5
0x18008af09  mov     dword ptr [rax], 4943414Ch
0x18008af0f  mov     ecx, r14d
0x18008af12  mov     rax, [rsi+18h]
0x18008af16  mov     [rbx+18h], rax
0x18008af1a  mov     rax, [rsi+20h]
0x18008af1e  mov     rsi, [rsp+0A00h+OutBuffer]
0x18008af23  mov     [rbx+10h], rax
0x18008af27  mov     [rbx+20h], r14d
0x18008af2b  mov     [rbx+40h], r13d
0x18008af2f  mov     eax, [rsi+4]
0x18008af32  mov     [rbx+4], eax
0x18008af35  call    ReleaseObjWriteLock
0x18008af3a  lea     rdx, [rsp+0A00h+lpMem]
0x18008af3f  mov     rcx, rbx
0x18008af42  call    OpenObjHandle
0x18008af47  test    eax, eax
0x18008af49  jz      loc_18008AFD2
0x18008af4f  call    cs:__imp_GetProcessHeap
0x18008af56  nop     dword ptr [rax+rax+00h]
0x18008af5b  mov     r8, rbx; lpMem
0x18008af5e  xor     edx, edx; dwFlags
0x18008af60  mov     rcx, rax; hHeap
0x18008af63  call    cs:__imp_HeapFree
0x18008af6a  nop     dword ptr [rax+rax+00h]
0x18008af6f  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008af76  jz      short loc_18008AFA8
0x18008af78  cmp     qword ptr cs:xmmword_1800D0BE0, r13
0x18008af7f  jz      loc_18008B5BF
0x18008af85  mov     r8, rbx
0x18008af88  mov     word ptr [rbp+900h+var_830], r13w
0x18008af90  lea     rdx, aProcesseventFa; "ProcessEvent: Failed to map call object"...
0x18008af97  lea     rcx, [rbp+900h+var_830]
0x18008af9e  call    FormatRRASErrorString
0x18008afa3  jmp     loc_18008AC0B
0x18008afa8  mov     ecx, cs:dwTraceId; dwTraceID
0x18008afae  cmp     ecx, r12d
0x18008afb1  jz      loc_18008B5BF
0x18008afb7  mov     r8, rbx
0x18008afba  lea     rdx, aProcesseventFa_0; "ProcessEvent: Failed to map call object"...
0x18008afc1  call    cs:__imp_TracePrintfA
0x18008afc8  nop     dword ptr [rax+rax+00h]
0x18008afcd  jmp     loc_18008B5BF
0x18008afd2  mov     ecx, r14d
0x18008afd5  call    AcquireObjWriteLock
0x18008afda  mov     edi, eax
0x18008afdc  test    eax, eax
0x18008afde  jz      short loc_18008B02C
  ... truncated ...
```
