# ProcessEvent

- ea: `0x180084ae0`
- end: `0x1800855e2`
- name: `ProcessEvent`
- size: `2818`
- prototype: `HRESULT __stdcall(PEVENT_RECORD eventRecord)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180083370`

## callees

- `0x180071cec`
- `0x18008490c`
- `0x180084ae0`
- `0x1800864d8`
- `0x1800884f8`
- `0x180088cc0`
- `0x180088e64`
- `0x1800892bc`
- `0x180089450`
- `0x180089924`
- `0x180089a9c`
- `0x18008a084`
- `0x18008a408`
- `0x18008a51c`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!DeviceIoControl` at `0x1800850d2`
- `KERNEL32!DeviceIoControl` at `0x1800850d2`
- `KERNEL32!GetProcessHeap` at `0x180084d24`
- `KERNEL32!GetProcessHeap` at `0x180084e5c`
- `KERNEL32!GetProcessHeap` at `0x180084f3d`
- `KERNEL32!GetProcessHeap` at `0x180084f9b`
- `KERNEL32!GetProcessHeap` at `0x180084d24`
- `KERNEL32!GetProcessHeap` at `0x180084e5c`
- `KERNEL32!GetProcessHeap` at `0x180084f3d`
- `KERNEL32!GetProcessHeap` at `0x180084f9b`
- `KERNEL32!HeapAlloc` at `0x180084d36`
- `KERNEL32!HeapAlloc` at `0x180084d36`
- `KERNEL32!GetLastError` at `0x1800850fa`
- `KERNEL32!GetLastError` at `0x18008511c`
- `KERNEL32!GetLastError` at `0x1800850fa`
- `KERNEL32!GetLastError` at `0x18008511c`
- `KERNEL32!HeapFree` at `0x180084e6a`
- `KERNEL32!HeapFree` at `0x180084f4b`
- `KERNEL32!HeapFree` at `0x180084fa9`
- `KERNEL32!HeapFree` at `0x180084e6a`
- `KERNEL32!HeapFree` at `0x180084f4b`
- `KERNEL32!HeapFree` at `0x180084fa9`
- `rtutils!TracePrintfA` at `0x180084bf9`
- `rtutils!TracePrintfA` at `0x180084e56`
- `rtutils!TracePrintfA` at `0x180084f37`
- `rtutils!TracePrintfA` at `0x180085001`
- `rtutils!TracePrintfA` at `0x180085288`
- `rtutils!TracePrintfA` at `0x180085386`
- `rtutils!TracePrintfA` at `0x1800853f0`
- `rtutils!TracePrintfA` at `0x180085499`
- `rtutils!TracePrintfA` at `0x18008557c`
- `rtutils!TracePrintfA` at `0x180084bf9`
- `rtutils!TracePrintfA` at `0x180084e56`
- `rtutils!TracePrintfA` at `0x180084f37`
- `rtutils!TracePrintfA` at `0x180085001`
- `rtutils!TracePrintfA` at `0x180085288`
- `rtutils!TracePrintfA` at `0x180085386`
- `rtutils!TracePrintfA` at `0x1800853f0`
- `rtutils!TracePrintfA` at `0x180085499`
- `rtutils!TracePrintfA` at `0x18008557c`

## string_xrefs

- `0x180085572`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008555b`: `ProcessEvent: GetLineObjWithReadLock failed with error (0x%x)`
- `0x18008526a`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x18008524f`: `ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)`
- `0x180085281`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x18008522a`: `ProcessEvent: Incomplete outbound call, saving state`
- `0x1800852d2`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x1800852b7`: `ProcessEvent: GetCallObjWithWriteLock failed with error (0x%x)`
- `0x180084d18`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x180084cfd`: `ProcessEvent: GetLineObjWithWriteLock failed with error (0x%x)`
- `0x18008505a`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x18008503c`: `ProcessEvent: AcquireObjWriteLock failed with error (0x%x)`
- `0x180085128`: `ProcessEvent: CREATE failed (0x%x)`
- `0x180085103`: `ProcessEvent: CREATE failed (0x%x)`

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
  void *v16; // rbx
  _DWORD *v17; // rdx
  unsigned int v18; // eax
  HANDLE v19; // rax
  void *v20; // rbx
  void *v21; // rdx
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
    if ( (_QWORD)xmmword_1800C9BE0 )
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
      ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v54);
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
          return result;
        v7 = (unsigned int)result;
        v8 = L"ProcessEvent: GetLineAndCallObjWithReadLock failed with error (0x%x)";
LABEL_19:
        LOWORD(v54) = 0;
        FormatRRASErrorString(&v54, v8, v7);
        return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                 gNdpspEtwContext,
                 xmmword_1800C9BE0,
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
          if ( *((_QWORD *)&xmmword_1800C9BE0 + 1) )
            ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gNdpspTemplateFunc)(
              gNdpspEtwContext,
              *((_QWORD *)&xmmword_1800C9BE0 + 1),
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
          if ( !(_QWORD)xmmword_1800C9BE0 )
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
          if ( (_QWORD)xmmword_1800C9BE0 )
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
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: Setting media mode to 0x%x");
LABEL_108:
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v54);
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
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v54) = 0;
          FormatRRASErrorString(&v54, L"ProcessEvent: LINECALLSTATE_IDLE: hCall(%p)", (unsigned int)v32);
          ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v54);
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
          return result;
        v7 = (unsigned int)g_dwNumNDProxyLines;
        v8 = L"ProcessEvent: New line added. Total number of NDProxy lines is now 0x%x";
        goto LABEL_19;
      }
      if ( gIsndpspEtwTracingAvailable )
      {
        if ( (_QWORD)xmmword_1800C9BE0 )
        {
          LOWORD(v54) = 0;
          LastError = GetLastError();
          FormatRRASErrorString(&v54, L"ProcessEvent: CREATE failed (0x%x)", LastError);
          return ((__int64 (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(
                   gNdpspEtwContext,
                   xmmword_1800C9BE0,
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
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
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: Failed to map call object (%p) to handle", v13);
            return ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))gNdpspTemplateFunc)(
                     gNdpspEtwContext,
                     xmmword_1800C9BE0,
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
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
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(&v54, L"ProcessEvent: SyncDriverRequest(OID_TAPI_DROP) failed with error (0x%x)", v18);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v54);
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
        if ( !(_QWORD)xmmword_1800C9BE0 )
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
          if ( (_QWORD)xmmword_1800C9BE0 )
          {
            LOWORD(v54) = 0;
            FormatRRASErrorString(
              &v54,
              L"ProcessEvent: SyncDriverRequest(OID_TAPI_CLOSE_CALL) failed with error (0x%x)",
              v22);
            ((void (__fastcall *)(__int64, _QWORD, int *))gNdpspTemplateFunc)(gNdpspEtwContext, xmmword_1800C9BE0, &v54);
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
    if ( !(_QWORD)xmmword_1800C9BE0 )
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
0x180084ae0  push    rbp
0x180084ae2  push    rbx
0x180084ae3  push    rsi
0x180084ae4  push    rdi
0x180084ae5  push    r12
0x180084ae7  push    r13
0x180084ae9  push    r14
0x180084aeb  push    r15
0x180084aed  lea     rbp, [rsp-8E8h]
0x180084af5  sub     rsp, 9E8h
0x180084afc  mov     rax, cs:__security_cookie
0x180084b03  xor     rax, rsp
0x180084b06  mov     [rbp+920h+var_50], rax
0x180084b0d  mov     r15d, [rcx+10h]
0x180084b11  mov     rsi, rcx
0x180084b14  mov     r14d, [rcx]
0x180084b17  xor     r13d, r13d
0x180084b1a  mov     rbx, [rcx+8]
0x180084b1e  xor     edx, edx; Val
0x180084b20  lea     rcx, [rbp+920h+var_84C]; void *
0x180084b27  mov     [rbp+920h+var_850], r13d
0x180084b2e  mov     r8d, 7FCh; Size
0x180084b34  call    memset_0
0x180084b39  or      r12d, 0FFFFFFFFh
0x180084b3d  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084b44  jz      short loc_180084BBC
0x180084b46  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084b4d  jz      loc_180084BFF
0x180084b53  mov     rax, [rsi+28h]
0x180084b57  lea     rdx, aProcesseventEv; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x180084b5e  mov     [rsp+0A20h+var_9E0], rax
0x180084b63  lea     rcx, [rbp+920h+var_850]
0x180084b6a  mov     rax, [rsi+20h]
0x180084b6e  mov     r9d, r15d
0x180084b71  mov     [rsp+0A20h+lpOverlapped], rax
0x180084b76  mov     r8, rsi
0x180084b79  mov     rax, [rsi+18h]
0x180084b7d  mov     [rsp+0A20h+lpBytesReturned], rax
0x180084b82  mov     qword ptr [rsp+0A20h+nOutBufferSize], rbx
0x180084b87  mov     dword ptr [rsp+0A20h+lpOutBuffer], r14d
0x180084b8c  mov     word ptr [rbp+920h+var_850], r13w
0x180084b94  call    FormatRRASErrorString
0x180084b99  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180084ba0  lea     r8, [rbp+920h+var_850]
0x180084ba7  mov     rcx, cs:gNdpspEtwContext
0x180084bae  mov     rax, cs:gNdpspTemplateFunc
0x180084bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bba  jmp     short loc_180084BFF
0x180084bbc  mov     ecx, cs:dwTraceId; dwTraceID
0x180084bc2  cmp     ecx, r12d
0x180084bc5  jz      short loc_180084C05
0x180084bc7  mov     rax, [rsi+28h]
0x180084bcb  lea     rdx, aProcesseventEv_0; "ProcessEvent: Event(%p), msg(0x%x), ht_"...
0x180084bd2  mov     [rsp+0A20h+var_9E0], rax
0x180084bd7  mov     r9d, r15d
0x180084bda  mov     rax, [rsi+20h]
0x180084bde  mov     r8, rsi
0x180084be1  mov     [rsp+0A20h+lpOverlapped], rax
0x180084be6  mov     rax, [rsi+18h]
0x180084bea  mov     [rsp+0A20h+lpBytesReturned], rax
0x180084bef  mov     qword ptr [rsp+0A20h+nOutBufferSize], rbx
0x180084bf4  mov     dword ptr [rsp+0A20h+lpOutBuffer], r14d
0x180084bf9  call    cs:__imp_TracePrintfA
0x180084bff  mov     ecx, cs:dwTraceId
0x180084c05  mov     eax, r15d
0x180084c08  test    r15d, r15d
0x180084c0b  jz      loc_180085530
0x180084c11  sub     eax, 1
0x180084c14  jz      loc_1800854C2
0x180084c1a  sub     eax, 1
0x180084c1d  jz      loc_1800851AB
0x180084c23  sub     eax, 1
0x180084c26  jz      loc_180085530
0x180084c2c  sub     eax, 1
0x180084c2f  jz      loc_180085530
0x180084c35  sub     eax, 4
0x180084c38  jz      loc_180085530
0x180084c3e  sub     eax, 0Bh
0x180084c41  jz      loc_180085087
0x180084c47  sub     eax, 1E1h
0x180084c4c  jz      short loc_180084CC9
0x180084c4e  cmp     eax, 1
0x180084c51  jz      loc_1800854C2
0x180084c57  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084c5e  jz      short loc_180084CB1
0x180084c60  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084c67  jz      loc_1800855BF
0x180084c6d  mov     r8d, r15d
0x180084c70  lea     rdx, aProcesseventUn_0; "ProcessEvent: Unhandled msg (0x%x)"
0x180084c77  mov     word ptr [rbp+920h+var_850], r13w
0x180084c7f  lea     rcx, [rbp+920h+var_850]
0x180084c86  call    FormatRRASErrorString
0x180084c8b  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180084c92  lea     r8, [rbp+920h+var_850]
0x180084c99  mov     rcx, cs:gNdpspEtwContext
0x180084ca0  mov     rax, cs:gNdpspTemplateFunc
0x180084ca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084cac  jmp     loc_1800855BF
0x180084cb1  cmp     ecx, r12d
0x180084cb4  jz      loc_1800855BF
0x180084cba  mov     r8d, r15d
0x180084cbd  lea     rdx, aProcesseventUn; "ProcessEvent: Unhandled msg (0x%x)"
0x180084cc4  jmp     loc_18008557C
0x180084cc9  lea     rdx, [rsp+0A20h+OutBuffer]
0x180084cce  mov     [rsp+0A20h+OutBuffer], r13
0x180084cd3  mov     ecx, r14d
0x180084cd6  mov     dword ptr [rsp+0A20h+lpMem], r13d
0x180084cdb  call    GetLineObjWithWriteLock
0x180084ce0  test    eax, eax
0x180084ce2  jz      short loc_180084D24
0x180084ce4  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084ceb  jz      short loc_180084D09
0x180084ced  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084cf4  jz      loc_1800855BF
0x180084cfa  mov     r8d, eax
0x180084cfd  lea     rdx, aProcesseventGe_1; "ProcessEvent: GetLineObjWithWriteLock f"...
0x180084d04  jmp     loc_180084C77
0x180084d09  mov     ecx, cs:dwTraceId
0x180084d0f  cmp     ecx, r12d
0x180084d12  jz      loc_1800855BF
0x180084d18  lea     rdx, aProcesseventGe_2; "ProcessEvent: GetLineObjWithWriteLock f"...
0x180084d1f  jmp     loc_180085579
0x180084d24  call    cs:__imp_GetProcessHeap
0x180084d2a  mov     edx, 8; dwFlags
0x180084d2f  mov     rcx, rax; hHeap
0x180084d32  lea     r8d, [rdx+40h]; dwBytes
0x180084d36  call    cs:__imp_HeapAlloc
0x180084d3c  mov     rbx, rax
0x180084d3f  test    rax, rax
0x180084d42  jnz     loc_180084F59
0x180084d48  mov     rdi, [rsp+0A20h+OutBuffer]
0x180084d4d  lea     r9, [rsp+0A20h+lpMem]
0x180084d52  lea     r8d, [rax+18h]
0x180084d56  mov     [rsp+0A20h+lpMem], r13
0x180084d5b  mov     ecx, 7030109h
0x180084d60  mov     [rsp+0A20h+lpInBuffer], r13
0x180084d65  mov     edx, [rdi+4]
0x180084d68  call    PrepareSyncRequest
0x180084d6d  mov     ebx, eax
0x180084d6f  test    eax, eax
0x180084d71  jnz     loc_180084E8E
0x180084d77  mov     rbx, [rsp+0A20h+lpMem]
0x180084d7c  mov     r15d, 8FFF23CCh
0x180084d82  mov     rax, [rsi+18h]
0x180084d86  mov     rdx, rbx; lpInBuffer
0x180084d89  mov     ecx, r15d; dwIoControlCode
0x180084d8c  mov     [rbx+38h], rax
0x180084d90  mov     [rbx+40h], r13d
0x180084d94  call    SyncDriverRequest
0x180084d99  mov     rdx, rbx; lpInBuffer
0x180084d9c  mov     ecx, r15d; dwIoControlCode
0x180084d9f  call    SyncDriverRequest
0x180084da4  test    eax, eax
0x180084da6  jz      loc_180084E5C
0x180084dac  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084db3  jz      loc_180084E41
0x180084db9  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084dc0  jz      loc_180084E5C
0x180084dc6  mov     r8d, eax
0x180084dc9  mov     word ptr [rbp+920h+var_850], r13w
0x180084dd1  lea     rdx, aProcesseventSy_1; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180084dd8  lea     rcx, [rbp+920h+var_850]
0x180084ddf  call    FormatRRASErrorString
0x180084de4  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180084deb  lea     r8, [rbp+920h+var_850]
0x180084df2  mov     rcx, cs:gNdpspEtwContext
0x180084df9  mov     rax, cs:gNdpspTemplateFunc
0x180084e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084e05  jmp     short loc_180084E5C
0x180084e07  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084e0e  jz      loc_1800855BF
0x180084e14  mov     r8d, ebx
0x180084e17  lea     rdx, aProcesseventPr; "ProcessEvent: PrepareSyncRequest failed"...
0x180084e1e  jmp     loc_180084C77
0x180084e23  mov     ecx, cs:dwTraceId
0x180084e29  cmp     ecx, r12d
0x180084e2c  jz      loc_1800855BF
0x180084e32  mov     r8d, ebx
0x180084e35  lea     rdx, aProcesseventPr_0; "ProcessEvent: PrepareSyncRequest failed"...
0x180084e3c  jmp     loc_18008557C
0x180084e41  mov     ecx, cs:dwTraceId; dwTraceID
0x180084e47  cmp     ecx, r12d
0x180084e4a  jz      short loc_180084E5C
0x180084e4c  mov     r8d, eax
0x180084e4f  lea     rdx, aProcesseventSy; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180084e56  call    cs:__imp_TracePrintfA
0x180084e5c  call    cs:__imp_GetProcessHeap
0x180084e62  mov     r8, rbx; lpMem
0x180084e65  xor     edx, edx; dwFlags
0x180084e67  mov     rcx, rax; hHeap
0x180084e6a  call    cs:__imp_HeapFree
0x180084e70  mov     edx, [rdi+4]
0x180084e73  lea     r9, [rsp+0A20h+lpInBuffer]
0x180084e78  mov     r8d, 10h
0x180084e7e  mov     ecx, 7030104h
0x180084e83  call    PrepareSyncRequest
0x180084e88  mov     ebx, eax
0x180084e8a  test    eax, eax
0x180084e8c  jz      short loc_180084EA8
0x180084e8e  mov     ecx, r14d
0x180084e91  call    ReleaseObjWriteLock
0x180084e96  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084e9d  jnz     loc_180084E07
0x180084ea3  jmp     loc_180084E23
0x180084ea8  mov     rbx, [rsp+0A20h+lpInBuffer]
0x180084ead  mov     ecx, r15d; dwIoControlCode
0x180084eb0  mov     rax, [rsi+18h]
0x180084eb4  mov     rdx, rbx; lpInBuffer
0x180084eb7  mov     [rbx+38h], rax
0x180084ebb  call    SyncDriverRequest
0x180084ec0  mov     rdx, rbx; lpInBuffer
0x180084ec3  mov     ecx, r15d; dwIoControlCode
0x180084ec6  call    SyncDriverRequest
0x180084ecb  test    eax, eax
0x180084ecd  jz      short loc_180084F3D
0x180084ecf  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084ed6  jz      short loc_180084F22
0x180084ed8  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084edf  jz      short loc_180084F3D
0x180084ee1  mov     r8d, eax
0x180084ee4  mov     word ptr [rbp+920h+var_850], r13w
0x180084eec  lea     rdx, aProcesseventSy_0; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180084ef3  lea     rcx, [rbp+920h+var_850]
0x180084efa  call    FormatRRASErrorString
0x180084eff  mov     rdx, qword ptr cs:xmmword_1800C9BE0
0x180084f06  lea     r8, [rbp+920h+var_850]
0x180084f0d  mov     rcx, cs:gNdpspEtwContext
0x180084f14  mov     rax, cs:gNdpspTemplateFunc
0x180084f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084f20  jmp     short loc_180084F3D
0x180084f22  mov     ecx, cs:dwTraceId; dwTraceID
0x180084f28  cmp     ecx, r12d
0x180084f2b  jz      short loc_180084F3D
0x180084f2d  mov     r8d, eax
0x180084f30  lea     rdx, aProcesseventSy_2; "ProcessEvent: SyncDriverRequest(OID_TAP"...
0x180084f37  call    cs:__imp_TracePrintfA
0x180084f3d  call    cs:__imp_GetProcessHeap
0x180084f43  mov     r8, rbx; lpMem
0x180084f46  xor     edx, edx; dwFlags
0x180084f48  mov     rcx, rax; hHeap
0x180084f4b  call    cs:__imp_HeapFree
0x180084f51  mov     ecx, r14d
0x180084f54  jmp     loc_1800852F7
0x180084f59  mov     dword ptr [rax], 4943414Ch
0x180084f5f  mov     ecx, r14d
0x180084f62  mov     rax, [rsi+18h]
0x180084f66  mov     [rbx+18h], rax
0x180084f6a  mov     rax, [rsi+20h]
0x180084f6e  mov     rsi, [rsp+0A20h+OutBuffer]
0x180084f73  mov     [rbx+10h], rax
0x180084f77  mov     [rbx+20h], r14d
0x180084f7b  mov     [rbx+40h], r13d
0x180084f7f  mov     eax, [rsi+4]
0x180084f82  mov     [rbx+4], eax
0x180084f85  call    ReleaseObjWriteLock
0x180084f8a  lea     rdx, [rsp+0A20h+lpMem]
0x180084f8f  mov     rcx, rbx
0x180084f92  call    OpenObjHandle
0x180084f97  test    eax, eax
0x180084f99  jz      short loc_18008500C
0x180084f9b  call    cs:__imp_GetProcessHeap
0x180084fa1  mov     r8, rbx; lpMem
0x180084fa4  xor     edx, edx; dwFlags
0x180084fa6  mov     rcx, rax; hHeap
0x180084fa9  call    cs:__imp_HeapFree
0x180084faf  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x180084fb6  jz      short loc_180084FE8
0x180084fb8  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180084fbf  jz      loc_1800855BF
0x180084fc5  mov     r8, rbx
0x180084fc8  mov     word ptr [rbp+920h+var_850], r13w
0x180084fd0  lea     rdx, aProcesseventFa; "ProcessEvent: Failed to map call object"...
0x180084fd7  lea     rcx, [rbp+920h+var_850]
0x180084fde  call    FormatRRASErrorString
0x180084fe3  jmp     loc_180084C8B
0x180084fe8  mov     ecx, cs:dwTraceId; dwTraceID
0x180084fee  cmp     ecx, r12d
0x180084ff1  jz      loc_1800855BF
0x180084ff7  mov     r8, rbx
0x180084ffa  lea     rdx, aProcesseventFa_0; "ProcessEvent: Failed to map call object"...
0x180085001  call    cs:__imp_TracePrintfA
0x180085007  jmp     loc_1800855BF
0x18008500c  mov     ecx, r14d
0x18008500f  call    AcquireObjWriteLock
0x180085014  mov     edi, eax
0x180085016  test    eax, eax
0x180085018  jz      short loc_180085066
0x18008501a  mov     ecx, dword ptr [rsp+0A20h+lpMem]
0x18008501e  call    CloseObjHandle
0x180085023  cmp     cs:gIsndpspEtwTracingAvailable, r13d
0x18008502a  jz      short loc_180085048
0x18008502c  cmp     qword ptr cs:xmmword_1800C9BE0, r13
0x180085033  jz      loc_1800855BF
0x180085039  mov     r8d, edi
0x18008503c  lea     rdx, aProcesseventAc; "ProcessEvent: AcquireObjWriteLock faile"...
0x180085043  jmp     loc_180084C77
0x180085048  mov     ecx, cs:dwTraceId
0x18008504e  cmp     ecx, r12d
0x180085051  jz      loc_1800855BF
0x180085057  mov     r8d, edi
  ... truncated ...
```
