# ProcessEvent

- ea: `0x1800226f0`
- end: `0x1800231f2`
- name: `ProcessEvent`
- size: `2818`
- prototype: `HRESULT __stdcall(PEVENT_RECORD eventRecord)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180020f80`

## callees

- `0x18002251c`
- `0x1800226f0`
- `0x1800244ec`
- `0x180026c4c`
- `0x180027414`
- `0x1800275b8`
- `0x180027a10`
- `0x180027ba4`
- `0x180028078`
- `0x1800281f0`
- `0x1800287d8`
- `0x180028b5c`
- `0x180028c70`
- `0x180029130`
- `0x18002927e`
- `0x1800292b0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022d2c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022946`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180022946`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022934`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bab`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022934`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022a6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022b4d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180022bab`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022bb9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022a7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022b5b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180022bb9`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180022ce2`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180022ce2`
- `rtutils!TracePrintfA` at `0x180022809`
- `rtutils!TracePrintfA` at `0x180022a66`
- `rtutils!TracePrintfA` at `0x180022b47`
- `rtutils!TracePrintfA` at `0x180022c11`
- `rtutils!TracePrintfA` at `0x180022e98`
- `rtutils!TracePrintfA` at `0x180022f96`
- `rtutils!TracePrintfA` at `0x180023000`
- `rtutils!TracePrintfA` at `0x1800230a9`
- `rtutils!TracePrintfA` at `0x18002318c`
- `rtutils!TracePrintfA` at `0x180022809`
- `rtutils!TracePrintfA` at `0x180022a66`
- `rtutils!TracePrintfA` at `0x180022b47`
- `rtutils!TracePrintfA` at `0x180022c11`
- `rtutils!TracePrintfA` at `0x180022e98`
- `rtutils!TracePrintfA` at `0x180022f96`
- `rtutils!TracePrintfA` at `0x180023000`
- `rtutils!TracePrintfA` at `0x1800230a9`
- `rtutils!TracePrintfA` at `0x18002318c`

## string_xrefs

- `0x18002316b`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180023182`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x180022e5f`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x180022e7a`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x180022e3a`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x180022e91`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x180022ec7`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x180022ee2`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x18002290d`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180022928`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180022c4c`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x180022c6a`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x180022d13`: `ProcessEvent: CREATE failed (0x%x)`
- `0x180022d38`: `ProcessEvent: CREATE failed (0x%x)`

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
  _QWORD *v13; // rbx
  _DWORD *v14; // rdi
  unsigned int v15; // ebx
  _DWORD *v16; // rbx
  _DWORD *v17; // rdx
  unsigned int v18; // eax
  HANDLE v19; // rax
  _DWORD *v20; // rbx
  _DWORD *v21; // rdx
  unsigned int v22; // eax
  HANDLE v23; // rax
  __int64 v24; // rcx
  __int64 v25; // rax
  _DWORD *v26; // rsi
  HANDLE v27; // rax
  unsigned int v28; // edi
  __int64 v29; // rax
  __int64 LastError; // r8
  __int64 v31; // r12
  __int64 v32; // rdi
  int v33; // ebx
  int v34; // r15d
  _DWORD *v35; // rdx
  unsigned int v36; // eax
  bool v37; // zf
  int v38; // r8d
  __int64 v39; // r8
  __int64 v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rdi
  unsigned int v43; // ebx
  __int64 v44; // rbx
  LPDWORD lpBytesReturned; // [rsp+30h] [rbp-D0h]
  LPOVERLAPPED lpOverlapped; // [rsp+38h] [rbp-C8h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  _DWORD *OutBuffer; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID lpInBuffer; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpMem[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v51; // [rsp+70h] [rbp-90h] BYREF
  char v52[28]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v53; // [rsp+90h] [rbp-70h]
  int v54; // [rsp+1D0h] [rbp+D0h] BYREF
  char v55[2044]; // [rsp+1D4h] [rbp+D4h] BYREF

  LowPart = eventRecord->EventHeader.TimeStamp.LowPart;
  v3 = *(_DWORD *)&eventRecord->EventHeader.Size;
  v4 = *(_QWORD *)&eventRecord->EventHeader.ThreadId;
  v54 = 0;
  memset_0(v55, 0, sizeof(v55));
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( qword_18003EC40 )
    {
      v47 = *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id;
      lpOverlapped = *(LPOVERLAPPED *)eventRecord->EventHeader.ProviderId.Data4;
      lpBytesReturned = *(LPDWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      LOWORD(v54) = 0;
      FormatRRASErrorString(
        &v54,
        L"ProcessEvent: Event(%p), msg(0x%x), ht_line(0x%x), ht_call(0x%x), p1(%p), p2(%p), p3(%p)",
        eventRecord,
        LowPart,
        v3,
        v4,
        lpBytesReturned,
        lpOverlapped,
        v47);
      ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
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
        if ( !qword_18003EC40 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)";
        goto LABEL_19;
      }
      v44 = *((_QWORD *)lpInBuffer + 4);
      ReleaseObjReadLock(v3);
      v39 = v44;
      v40 = 0;
LABEL_130:
      v41 = LowPart;
      return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnCallback)(v40, v41, v39);
    case 1u:
LABEL_118:
      lpInBuffer = 0;
      OutBuffer = 0;
      result = GetLineAndCallObjWithReadLock(v3, v4, &lpInBuffer, &OutBuffer);
      if ( result )
        goto LABEL_119;
      v42 = *((_QWORD *)lpInBuffer + 4);
      v43 = OutBuffer[2];
      ReleaseObjReadLock(v43);
      ReleaseObjReadLock(v3);
      v40 = v43;
      v39 = v42;
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
        if ( !qword_18003EC40 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)";
LABEL_19:
        LOWORD(v54) = 0;
        FormatRRASErrorString(&v54, v8, v7);
        return ((__int64 (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                 gNdpspEtwContext,
                 qword_18003EC40,
                 &v54);
      }
      v31 = *((_QWORD *)lpInBuffer + 4);
      v32 = (unsigned int)OutBuffer[2];
      v33 = *OutBuffer;
      v34 = OutBuffer[16];
      ReleaseObjReadLock(v32);
      ReleaseObjReadLock(v3);
      if ( v33 == 1329807692 && v34 == 1 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC48 )
            ((void (__fastcall *)(__int64, __int64, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              qword_18003EC48,
              L"ProcessEvent: Incomplete outbound call, saving state");
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: Incomplete outbound call, saving state");
        }
        result = GetCallObjWithWriteLock((unsigned int)v32, &OutBuffer);
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
          if ( !qword_18003EC40 )
            return result;
          v7 = (unsigned int)result;
          v8 = L"ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)";
          goto LABEL_19;
        }
        v24 = (unsigned int)v32;
        v35 = OutBuffer;
        OutBuffer[9] = eventRecord->EventHeader.ProviderId.Data1;
        v35[10] = *(_DWORD *)eventRecord->EventHeader.ProviderId.Data4;
        v35[11] = *(_DWORD *)&eventRecord->EventHeader.EventDescriptor.Id;
        return ReleaseObjWriteLock(v24);
      }
      if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 == 2 )
      {
        memset_0(v52, 0, 0x154u);
        v51 = 344;
        v36 = RasLineGetCallInfo((unsigned int)v32, &v51);
        if ( v36 )
        {
          if ( !gIsndpspEtwTracingAvailable )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "ProcessEvent: RasLineGetCallInfo failed with error 0x%x", v36);
            goto LABEL_111;
          }
          if ( qword_18003EC40 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: RasLineGetCallInfo failed with error 0x%x", v36);
            goto LABEL_108;
          }
        }
        else
        {
          v37 = gIsndpspEtwTracingAvailable == 0;
          v38 = v53;
          *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id = v53;
          if ( v37 )
          {
            if ( dwTraceId != -1 )
              TracePrintfA(dwTraceId, "ProcessEvent: Setting media mode to 0x%x", v38);
            goto LABEL_111;
          }
          if ( qword_18003EC40 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: Setting media mode to 0x%x");
LABEL_108:
            ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
          }
        }
      }
LABEL_111:
      result = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, _QWORD, _QWORD))g_pfnCallback)(
                 v32,
                 2,
                 v31,
                 *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1,
                 *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
                 *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
      if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 != 0x4000 )
        return result;
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(&v54, L"ProcessEvent: LINECALLSTATE_IDLE: hCall(%p)", (unsigned int)v32);
          ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
        }
      }
      else if ( dwTraceId != -1 )
      {
        TracePrintfA(dwTraceId, "ProcessEvent: LINECALLSTATE_IDLE: hCall(%p)", (const void *)(unsigned int)v32);
      }
      v39 = v31;
      v40 = v32;
      v41 = 2;
      return ((__int64 (__fastcall *)(__int64, __int64, __int64))g_pfnCallback)(v40, v41, v39);
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
        if ( !qword_18003EC40 )
          return result;
        v7 = (unsigned int)g_dwNumNDProxyLines;
        v8 = L"ProcessEvent: New line added. Total number of NDProxy lines is now 0x%x";
        goto LABEL_19;
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( qword_18003EC40 )
        {
          LOWORD(v54) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(&v54, L"ProcessEvent: CREATE failed (0x%x)", LastError);
          return ((__int64 (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(
                   gNdpspEtwContext,
                   qword_18003EC40,
                   &v54);
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
        if ( !qword_18003EC40 )
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
    v13 = v12;
    if ( v12 )
    {
      *(_DWORD *)v12 = 1229144396;
      v12[3] = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      v25 = *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4;
      v26 = OutBuffer;
      v13[2] = v25;
      *((_DWORD *)v13 + 8) = v3;
      *((_DWORD *)v13 + 16) = 0;
      *((_DWORD *)v13 + 1) = v26[1];
      ReleaseObjWriteLock(v3);
      if ( (unsigned int)OpenObjHandle(v13, lpMem) )
      {
        v27 = GetProcessHeap();
        result = HeapFree(v27, 0, v13);
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC40 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: Failed to map call object (%p) to handle", v13);
            return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))gNdpspTemplateFunc)(
                     gNdpspEtwContext,
                     qword_18003EC40,
                     &v54);
          }
        }
        else if ( dwTraceId != -1 )
        {
          return TracePrintfA(dwTraceId, "ProcessEvent: Failed to map call object (%p) to handle", v13);
        }
        return result;
      }
      v28 = AcquireObjWriteLock(v3);
      if ( v28 )
      {
        result = CloseObjHandle(LODWORD(lpMem[0]));
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            return TracePrintfA(dwTraceId, "ProcessEvent: AcquireObjWriteLock failed with error (0x%x)", v28);
          return result;
        }
        if ( !qword_18003EC40 )
          return result;
        v7 = v28;
        v8 = L"ProcessEvent: AcquireObjWriteLock failed with error (0x%x)";
        goto LABEL_19;
      }
      *((_DWORD *)v13 + 2) = lpMem[0];
      v29 = *((_QWORD *)v26 + 3);
      v13[7] = v29;
      if ( v29 )
        *(_QWORD *)(v29 + 48) = v13;
      *((_QWORD *)v26 + 3) = v13;
    }
    else
    {
      v14 = OutBuffer;
      lpMem[0] = 0;
      lpInBuffer = 0;
      v15 = PrepareSyncRequest(117637385, (unsigned int)OutBuffer[1], 24, lpMem);
      if ( v15 )
        goto LABEL_42;
      v16 = lpMem[0];
      v17 = lpMem[0];
      *((_QWORD *)lpMem[0] + 7) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      v17[16] = 0;
      SyncDriverRequest(0x8FFF23CC, v17);
      v18 = SyncDriverRequest(0x8FFF23CC, v16);
      if ( v18 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC40 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: SyncDriverRequest(OID_TAPI_DROP) failed with error (0x%x)", v18);
            ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: SyncDriverRequest(OID_TAPI_DROP) failed with error (0x%x)", v18);
        }
      }
      v19 = GetProcessHeap();
      HeapFree(v19, 0, v16);
      v15 = PrepareSyncRequest(117637380, (unsigned int)v14[1], 16, &lpInBuffer);
      if ( v15 )
      {
LABEL_42:
        result = ReleaseObjWriteLock(v3);
        if ( !gIsndpspEtwTracingAvailable )
        {
          if ( dwTraceId != -1 )
            return TracePrintfA(dwTraceId, "ProcessEvent: PrepareSyncRequest failed with error (0x%x)", v15);
          return result;
        }
        if ( !qword_18003EC40 )
          return result;
        v7 = v15;
        v8 = L"ProcessEvent: PrepareSyncRequest failed with error (0x%x)";
        goto LABEL_19;
      }
      v20 = lpInBuffer;
      v21 = lpInBuffer;
      *((_QWORD *)lpInBuffer + 7) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      SyncDriverRequest(0x8FFF23CC, v21);
      v22 = SyncDriverRequest(0x8FFF23CC, v20);
      if ( v22 )
      {
        if ( gIsndpspEtwTracingAvailable )
        {
          if ( qword_18003EC40 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(
              &v54,
              L"ProcessEvent: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
              v22);
            ((void (__fastcall *)(__int64, __int64, int *))gNdpspTemplateFunc)(gNdpspEtwContext, qword_18003EC40, &v54);
          }
        }
        else if ( dwTraceId != -1 )
        {
          TracePrintfA(dwTraceId, "ProcessEvent: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)", v22);
        }
      }
      v23 = GetProcessHeap();
      HeapFree(v23, 0, v20);
    }
    v24 = v3;
    return ReleaseObjWriteLock(v24);
  }
  if ( LowPart == 501 )
    goto LABEL_118;
  if ( gIsndpspEtwTracingAvailable )
  {
    if ( !qword_18003EC40 )
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
0x1800226f0  push    rbp
0x1800226f2  push    rbx
0x1800226f3  push    rsi
0x1800226f4  push    rdi
0x1800226f5  push    r12
0x1800226f7  push    r13
0x1800226f9  push    r14
0x1800226fb  push    r15
0x1800226fd  lea     rbp, [rsp-8E8h]
0x180022705  sub     rsp, 9E8h
0x18002270c  mov     rax, cs:__security_cookie
0x180022713  xor     rax, rsp
0x180022716  mov     [rbp+920h+var_50], rax
0x18002271d  mov     r15d, [rcx+10h]
0x180022721  mov     rsi, rcx
0x180022724  mov     r14d, [rcx]
0x180022727  xor     r13d, r13d
0x18002272a  mov     rbx, [rcx+8]
0x18002272e  xor     edx, edx; Val
0x180022730  lea     rcx, [rbp+920h+var_84C]; void *
0x180022737  mov     [rbp+920h+var_850], r13d
0x18002273e  mov     r8d, 7FCh; Size
0x180022744  call    memset_0
0x180022749  or      r12d, 0FFFFFFFFh
0x18002274d  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180022754  jz      short loc_1800227CC
0x180022756  cmp     cs:qword_18003EC40, r13
0x18002275d  jz      loc_18002280F
0x180022763  mov     rax, [rsi+28h]
0x180022767  lea     rdx, aProcesseventEv; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x18002276e  mov     [rsp+0A20h+var_9E0], rax
0x180022773  lea     rcx, [rbp+920h+var_850]
0x18002277a  mov     rax, [rsi+20h]
0x18002277e  mov     r9d, r15d
0x180022781  mov     [rsp+0A20h+lpOverlapped], rax
0x180022786  mov     r8, rsi
0x180022789  mov     rax, [rsi+18h]
0x18002278d  mov     [rsp+0A20h+lpBytesReturned], rax
0x180022792  mov     qword ptr [rsp+0A20h+nOutBufferSize], rbx
0x180022797  mov     dword ptr [rsp+0A20h+lpOutBuffer], r14d
0x18002279c  mov     word ptr [rbp+920h+var_850], r13w
0x1800227a4  call    FormatRRASErrorString
0x1800227a9  mov     rdx, cs:qword_18003EC40
0x1800227b0  lea     r8, [rbp+920h+var_850]
0x1800227b7  mov     rcx, cs:gNdpspEtwContext
0x1800227be  mov     rax, cs:gNdpspTemplateFunc
0x1800227c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800227ca  jmp     short loc_18002280F
0x1800227cc  mov     ecx, cs:dwTraceId; dwTraceID
0x1800227d2  cmp     ecx, r12d
0x1800227d5  jz      short loc_180022815
0x1800227d7  mov     rax, [rsi+28h]
0x1800227db  lea     rdx, aProcesseventEv_0; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x1800227e2  mov     [rsp+0A20h+var_9E0], rax
0x1800227e7  mov     r9d, r15d
0x1800227ea  mov     rax, [rsi+20h]
0x1800227ee  mov     r8, rsi
0x1800227f1  mov     [rsp+0A20h+lpOverlapped], rax
0x1800227f6  mov     rax, [rsi+18h]
0x1800227fa  mov     [rsp+0A20h+lpBytesReturned], rax
0x1800227ff  mov     qword ptr [rsp+0A20h+nOutBufferSize], rbx
0x180022804  mov     dword ptr [rsp+0A20h+lpOutBuffer], r14d
0x180022809  call    cs:__imp_TracePrintfA
0x18002280f  mov     ecx, cs:dwTraceId
0x180022815  mov     eax, r15d
0x180022818  test    r15d, r15d
0x18002281b  jz      loc_180023140
0x180022821  sub     eax, 1
0x180022824  jz      loc_1800230D2
0x18002282a  sub     eax, 1
0x18002282d  jz      loc_180022DBB
0x180022833  sub     eax, 1
0x180022836  jz      loc_180023140
0x18002283c  sub     eax, 1
0x18002283f  jz      loc_180023140
0x180022845  sub     eax, 4
0x180022848  jz      loc_180023140
0x18002284e  sub     eax, 0Bh
0x180022851  jz      loc_180022C97
0x180022857  sub     eax, 1E1h
0x18002285c  jz      short loc_1800228D9
0x18002285e  cmp     eax, 1
0x180022861  jz      loc_1800230D2
0x180022867  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18002286e  jz      short loc_1800228C1
0x180022870  cmp     cs:qword_18003EC40, r13
0x180022877  jz      loc_1800231CF
0x18002287d  mov     r8d, r15d
0x180022880  lea     rdx, aProcesseventUn_0; "ProcessEvent: Unhandled msg (0x%x)"
0x180022887  mov     word ptr [rbp+920h+var_850], r13w
0x18002288f  lea     rcx, [rbp+920h+var_850]
0x180022896  call    FormatRRASErrorString
0x18002289b  mov     rdx, cs:qword_18003EC40
0x1800228a2  lea     r8, [rbp+920h+var_850]
0x1800228a9  mov     rcx, cs:gNdpspEtwContext
0x1800228b0  mov     rax, cs:gNdpspTemplateFunc
0x1800228b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228bc  jmp     loc_1800231CF
0x1800228c1  cmp     ecx, r12d
0x1800228c4  jz      loc_1800231CF
0x1800228ca  mov     r8d, r15d
0x1800228cd  lea     rdx, aProcesseventUn; "ProcessEvent: Unhandled msg (0x%x)"
0x1800228d4  jmp     loc_18002318C
0x1800228d9  lea     rdx, [rsp+0A20h+OutBuffer]
0x1800228de  mov     [rsp+0A20h+OutBuffer], r13
0x1800228e3  mov     ecx, r14d
0x1800228e6  mov     dword ptr [rsp+0A20h+lpMem], r13d
0x1800228eb  call    GetLineObjWithWriteLock
0x1800228f0  test    eax, eax
0x1800228f2  jz      short loc_180022934
0x1800228f4  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800228fb  jz      short loc_180022919
0x1800228fd  cmp     cs:qword_18003EC40, r13
0x180022904  jz      loc_1800231CF
0x18002290a  mov     r8d, eax
0x18002290d  lea     rdx, aProcesseventGe_1; "ProcessEvent: GetLineObjWithWriteLock f"...
0x180022914  jmp     loc_180022887
0x180022919  mov     ecx, cs:dwTraceId
0x18002291f  cmp     ecx, r12d
0x180022922  jz      loc_1800231CF
0x180022928  lea     rdx, aProcesseventGe_2; "ProcessEvent: GetLineObjWithWriteLock f"...
0x18002292f  jmp     loc_180023189
0x180022934  call    cs:__imp_GetProcessHeap
0x18002293a  mov     edx, 8; dwFlags
0x18002293f  mov     rcx, rax; hHeap
0x180022942  lea     r8d, [rdx+40h]; dwBytes
0x180022946  call    cs:__imp_HeapAlloc
0x18002294c  mov     rbx, rax
0x18002294f  test    rax, rax
0x180022952  jnz     loc_180022B69
0x180022958  mov     rdi, [rsp+0A20h+OutBuffer]
0x18002295d  lea     r9, [rsp+0A20h+lpMem]
0x180022962  lea     r8d, [rax+18h]
0x180022966  mov     [rsp+0A20h+lpMem], r13
0x18002296b  mov     ecx, 7030109h
0x180022970  mov     [rsp+0A20h+lpInBuffer], r13
0x180022975  mov     edx, [rdi+4]
0x180022978  call    PrepareSyncRequest
0x18002297d  mov     ebx, eax
0x18002297f  test    eax, eax
0x180022981  jnz     loc_180022A9E
0x180022987  mov     rbx, [rsp+0A20h+lpMem]
0x18002298c  mov     r15d, 8FFF23CCh
0x180022992  mov     rax, [rsi+18h]
0x180022996  mov     rdx, rbx; lpInBuffer
0x180022999  mov     ecx, r15d; dwIoControlCode
0x18002299c  mov     [rbx+38h], rax
0x1800229a0  mov     [rbx+40h], r13d
0x1800229a4  call    SyncDriverRequest
0x1800229a9  mov     rdx, rbx; lpInBuffer
0x1800229ac  mov     ecx, r15d; dwIoControlCode
0x1800229af  call    SyncDriverRequest
0x1800229b4  test    eax, eax
0x1800229b6  jz      loc_180022A6C
0x1800229bc  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x1800229c3  jz      loc_180022A51
0x1800229c9  cmp     cs:qword_18003EC40, r13
0x1800229d0  jz      loc_180022A6C
0x1800229d6  mov     r8d, eax
0x1800229d9  mov     word ptr [rbp+920h+var_850], r13w
0x1800229e1  lea     rdx, aProcesseventSy_1; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x1800229e8  lea     rcx, [rbp+920h+var_850]
0x1800229ef  call    FormatRRASErrorString
0x1800229f4  mov     rdx, cs:qword_18003EC40
0x1800229fb  lea     r8, [rbp+920h+var_850]
0x180022a02  mov     rcx, cs:gNdpspEtwContext
0x180022a09  mov     rax, cs:gNdpspTemplateFunc
0x180022a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a15  jmp     short loc_180022A6C
0x180022a17  cmp     cs:qword_18003EC40, r13
0x180022a1e  jz      loc_1800231CF
0x180022a24  mov     r8d, ebx
0x180022a27  lea     rdx, aProcesseventPr; "ProcessEvent: PrepareSyncRequest failed"...
0x180022a2e  jmp     loc_180022887
0x180022a33  mov     ecx, cs:dwTraceId
0x180022a39  cmp     ecx, r12d
0x180022a3c  jz      loc_1800231CF
0x180022a42  mov     r8d, ebx
0x180022a45  lea     rdx, aProcesseventPr_0; "ProcessEvent: PrepareSyncRequest failed"...
0x180022a4c  jmp     loc_18002318C
0x180022a51  mov     ecx, cs:dwTraceId; dwTraceID
0x180022a57  cmp     ecx, r12d
0x180022a5a  jz      short loc_180022A6C
0x180022a5c  mov     r8d, eax
0x180022a5f  lea     rdx, aProcesseventSy; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180022a66  call    cs:__imp_TracePrintfA
0x180022a6c  call    cs:__imp_GetProcessHeap
0x180022a72  mov     r8, rbx; lpMem
0x180022a75  xor     edx, edx; dwFlags
0x180022a77  mov     rcx, rax; hHeap
0x180022a7a  call    cs:__imp_HeapFree
0x180022a80  mov     edx, [rdi+4]
0x180022a83  lea     r9, [rsp+0A20h+lpInBuffer]
0x180022a88  mov     r8d, 10h
0x180022a8e  mov     ecx, 7030104h
0x180022a93  call    PrepareSyncRequest
0x180022a98  mov     ebx, eax
0x180022a9a  test    eax, eax
0x180022a9c  jz      short loc_180022AB8
0x180022a9e  mov     ecx, r14d
0x180022aa1  call    ReleaseObjWriteLock
0x180022aa6  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180022aad  jnz     loc_180022A17
0x180022ab3  jmp     loc_180022A33
0x180022ab8  mov     rbx, [rsp+0A20h+lpInBuffer]
0x180022abd  mov     ecx, r15d; dwIoControlCode
0x180022ac0  mov     rax, [rsi+18h]
0x180022ac4  mov     rdx, rbx; lpInBuffer
0x180022ac7  mov     [rbx+38h], rax
0x180022acb  call    SyncDriverRequest
0x180022ad0  mov     rdx, rbx; lpInBuffer
0x180022ad3  mov     ecx, r15d; dwIoControlCode
0x180022ad6  call    SyncDriverRequest
0x180022adb  test    eax, eax
0x180022add  jz      short loc_180022B4D
0x180022adf  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180022ae6  jz      short loc_180022B32
0x180022ae8  cmp     cs:qword_18003EC40, r13
0x180022aef  jz      short loc_180022B4D
0x180022af1  mov     r8d, eax
0x180022af4  mov     word ptr [rbp+920h+var_850], r13w
0x180022afc  lea     rdx, aProcesseventSy_0; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180022b03  lea     rcx, [rbp+920h+var_850]
0x180022b0a  call    FormatRRASErrorString
0x180022b0f  mov     rdx, cs:qword_18003EC40
0x180022b16  lea     r8, [rbp+920h+var_850]
0x180022b1d  mov     rcx, cs:gNdpspEtwContext
0x180022b24  mov     rax, cs:gNdpspTemplateFunc
0x180022b2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022b30  jmp     short loc_180022B4D
0x180022b32  mov     ecx, cs:dwTraceId; dwTraceID
0x180022b38  cmp     ecx, r12d
0x180022b3b  jz      short loc_180022B4D
0x180022b3d  mov     r8d, eax
0x180022b40  lea     rdx, aProcesseventSy_2; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180022b47  call    cs:__imp_TracePrintfA
0x180022b4d  call    cs:__imp_GetProcessHeap
0x180022b53  mov     r8, rbx; lpMem
0x180022b56  xor     edx, edx; dwFlags
0x180022b58  mov     rcx, rax; hHeap
0x180022b5b  call    cs:__imp_HeapFree
0x180022b61  mov     ecx, r14d
0x180022b64  jmp     loc_180022F07
0x180022b69  mov     dword ptr [rax], 4943414Ch
0x180022b6f  mov     ecx, r14d
0x180022b72  mov     rax, [rsi+18h]
0x180022b76  mov     [rbx+18h], rax
0x180022b7a  mov     rax, [rsi+20h]
0x180022b7e  mov     rsi, [rsp+0A20h+OutBuffer]
0x180022b83  mov     [rbx+10h], rax
0x180022b87  mov     [rbx+20h], r14d
0x180022b8b  mov     [rbx+40h], r13d
0x180022b8f  mov     eax, [rsi+4]
0x180022b92  mov     [rbx+4], eax
0x180022b95  call    ReleaseObjWriteLock
0x180022b9a  lea     rdx, [rsp+0A20h+lpMem]
0x180022b9f  mov     rcx, rbx
0x180022ba2  call    OpenObjHandle
0x180022ba7  test    eax, eax
0x180022ba9  jz      short loc_180022C1C
0x180022bab  call    cs:__imp_GetProcessHeap
0x180022bb1  mov     r8, rbx; lpMem
0x180022bb4  xor     edx, edx; dwFlags
0x180022bb6  mov     rcx, rax; hHeap
0x180022bb9  call    cs:__imp_HeapFree
0x180022bbf  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180022bc6  jz      short loc_180022BF8
0x180022bc8  cmp     cs:qword_18003EC40, r13
0x180022bcf  jz      loc_1800231CF
0x180022bd5  mov     r8, rbx
0x180022bd8  mov     word ptr [rbp+920h+var_850], r13w
0x180022be0  lea     rdx, aProcesseventFa; "ProcessEvent: Failed to map call object"...
0x180022be7  lea     rcx, [rbp+920h+var_850]
0x180022bee  call    FormatRRASErrorString
0x180022bf3  jmp     loc_18002289B
0x180022bf8  mov     ecx, cs:dwTraceId; dwTraceID
0x180022bfe  cmp     ecx, r12d
0x180022c01  jz      loc_1800231CF
0x180022c07  mov     r8, rbx
0x180022c0a  lea     rdx, aProcesseventFa_0; "ProcessEvent: Failed to map call object"...
0x180022c11  call    cs:__imp_TracePrintfA
0x180022c17  jmp     loc_1800231CF
0x180022c1c  mov     ecx, r14d
0x180022c1f  call    AcquireObjWriteLock
0x180022c24  mov     edi, eax
0x180022c26  test    eax, eax
0x180022c28  jz      short loc_180022C76
0x180022c2a  mov     ecx, dword ptr [rsp+0A20h+lpMem]
0x180022c2e  call    CloseObjHandle
0x180022c33  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180022c3a  jz      short loc_180022C58
0x180022c3c  cmp     cs:qword_18003EC40, r13
0x180022c43  jz      loc_1800231CF
0x180022c49  mov     r8d, edi
0x180022c4c  lea     rdx, aProcesseventAc; "ProcessEvent: AcquireObjWriteLock faile"...
0x180022c53  jmp     loc_180022887
0x180022c58  mov     ecx, cs:dwTraceId
0x180022c5e  cmp     ecx, r12d
0x180022c61  jz      loc_1800231CF
0x180022c67  mov     r8d, edi
  ... truncated ...
```
