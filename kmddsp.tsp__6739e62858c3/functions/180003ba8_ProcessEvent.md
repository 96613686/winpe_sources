# ProcessEvent

- ea: `0x180003ba8`
- end: `0x18000417b`
- name: `ProcessEvent`
- size: `1491`
- prototype: `HRESULT __stdcall(PEVENT_RECORD eventRecord)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180002d40`

## callees

- `0x180001ca4`
- `0x180001d2c`
- `0x180001e40`
- `0x1800021ac`
- `0x180002494`
- `0x180002508`
- `0x1800026b8`
- `0x1800028d0`
- `0x18000298c`
- `0x18000338c`
- `0x1800037a8`
- `0x18000381c`
- `0x180003af0`
- `0x180003ba8`
- `0x180004184`
- `0x180004670`
- `0x180007df8`
- `0x180009010`

## string_xrefs

- `0x180003ee6`: `ProcessEvent: incomplete outbound call, saving state`
- `0x180003f4c`: `ProcessEvent: failed to acquire write lock for call(%p)`
- `0x180003f7d`: `ProcessEvent: failed to reacquire read lock for call(%p)`
- `0x180003d1b`: `ProcessEvent: failed to reacquire write lock for obj(%p)`
- `0x180003da7`: `ProcessEvent: TAPI failed to create its own handle for the new call, so we close the call`
- `0x180003e5c`: `PE::fnLineEvent(CREATE): ghProvider(%p), p2(%p), p3(%p)`

## pseudocode

```c
HRESULT __stdcall ProcessEvent(PEVENT_RECORD eventRecord)
{
  const void *v1; // rbx
  DWORD LowPart; // r15d
  const void *v4; // rdi
  HRESULT result; // eax
  __int64 v6; // rax
  __int64 v7; // rsi
  _QWORD *v8; // rbx
  HDRVCALL v9; // r14
  __int64 v10; // rax
  int v11; // edx
  struct HDRVCALL__ *v12; // rbx
  struct HDRVCALL__ *v13; // rdx
  void *v14; // rbx
  _DWORD *v15; // rdx
  HDRVCALL v16; // rbx
  const void *v17; // rsi
  __int64 v18; // rcx
  const void *v19; // rcx
  __int64 v20; // rdi
  __int64 v21; // rdi
  HDRVCALL v22; // rdi
  __int64 v23; // rbx
  HDRVCALL v24; // rbx
  HDRVCALL hdCall; // [rsp+90h] [rbp+40h] BYREF
  __int64 v26; // [rsp+98h] [rbp+48h] BYREF
  void *lpInBuffer; // [rsp+A0h] [rbp+50h] BYREF

  v1 = *(const void **)&eventRecord->EventHeader.ThreadId;
  LowPart = eventRecord->EventHeader.TimeStamp.LowPart;
  v4 = *(const void **)&eventRecord->EventHeader.Size;
  TspLog(
    4,
    "ProcessEvent: event(%p), msg(%x), ht_line(%p), ht_call(%p), p1(%p), p2(%p), p3(%p)",
    eventRecord,
    LowPart,
    *(const void **)&eventRecord->EventHeader.Size,
    v1,
    *(const void **)&eventRecord->EventHeader.ProviderId.Data1,
    *(const void **)eventRecord->EventHeader.ProviderId.Data4,
    *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
  switch ( LowPart )
  {
    case 0u:
      goto LABEL_45;
    case 1u:
LABEL_43:
      v26 = 0;
      hdCall = 0;
      result = GetLineAndCallObjWithReadLock(v4, v1, &v26, &hdCall);
      if ( result )
        return result;
      v22 = hdCall;
      v23 = v26;
      v17 = (const void *)*((_QWORD *)hdCall + 4);
      TspLog(
        4,
        "PE::fnLineEvent: msg(%x), htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
        LowPart,
        *(const void **)(v26 + 8),
        *((const void **)hdCall + 1),
        *(const void **)&eventRecord->EventHeader.ProviderId.Data1,
        *(const void **)eventRecord->EventHeader.ProviderId.Data4,
        *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))gpfnLineEvent)(
        *(_QWORD *)(v23 + 8),
        *((_QWORD *)v22 + 1),
        LowPart,
        *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1,
        *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
        *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
      v18 = *((_QWORD *)v22 + 2);
      goto LABEL_31;
    case 2u:
      v26 = 0;
      hdCall = 0;
      result = GetLineAndCallObjWithReadLock(v4, v1, &v26, &hdCall);
      if ( result )
        return result;
      v16 = hdCall;
      v17 = (const void *)*((_QWORD *)hdCall + 4);
      if ( *(_DWORD *)hdCall == 1329807692 && *((_DWORD *)hdCall + 16) == 1 )
      {
        TspLog(4, "ProcessEvent: incomplete outbound call, saving state");
        *(_DWORD *)(struct HDRVCALL__ *)(v16 + 10) = (const struct HDRVCALL__)eventRecord->EventHeader.ProviderId.Data1;
        *(_DWORD *)(struct HDRVCALL__ *)(v16 + 12) = *(_DWORD *)(HDRVCALL)eventRecord->EventHeader.ProviderId.Data4;
        *(_DWORD *)(struct HDRVCALL__ *)(v16 + 14) = *(_DWORD *)(HDRVCALL)&eventRecord->EventHeader.EventDescriptor.Id;
      }
      else if ( !*((_DWORD *)hdCall + 18) )
      {
        if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 == 0x4000
          || *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 == 1 )
        {
          v20 = *((_QWORD *)hdCall + 2);
          ReleaseObjReadLock(v20);
          if ( (unsigned int)AcquireObjWriteLock(v20) )
          {
            TspLog(2, "ProcessEvent: failed to acquire write lock for call(%p)", v20);
            goto LABEL_32;
          }
          *((_DWORD *)v16 + 18) = 1;
          ReleaseObjWriteLock(v20);
          if ( (unsigned int)AcquireObjReadLock(v20) )
          {
            TspLog(2, "ProcessEvent: failed to reacquire read lock for call(%p)", v20);
            goto LABEL_32;
          }
        }
        v21 = v26;
        TspLog(
          4,
          "PE::fnLineEvent(CALLSTATE): htline(%p), htcall(%p), p1(%p), p2(%p), p3(%p)",
          *(const void **)(v26 + 8),
          *((const void **)v16 + 1),
          *(const void **)&eventRecord->EventHeader.ProviderId.Data1,
          *(const void **)eventRecord->EventHeader.ProviderId.Data4,
          *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
        ((void (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, _QWORD, _QWORD))gpfnLineEvent)(
          *(_QWORD *)(v21 + 8),
          *((_QWORD *)v16 + 1),
          2,
          *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1,
          *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
          *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
        if ( *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1 == 0x4000 )
        {
          TspLog(
            4,
            "PE::fnLineEvent(CALLSTATE_IDLE): htline(%p), htcall(%p), p3(%p)",
            *(const void **)(v21 + 8),
            *((const void **)v16 + 1),
            *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
          ((void (__fastcall *)(_QWORD, _QWORD, __int64))gpfnLineEvent)(*(_QWORD *)(v21 + 8), *((_QWORD *)v16 + 1), 2);
        }
      }
      v18 = *((_QWORD *)v16 + 2);
LABEL_31:
      ReleaseObjReadLock(v18);
LABEL_32:
      v19 = v17;
      return ReleaseObjReadLock(v19);
    case 3u:
    case 4u:
    case 8u:
LABEL_45:
      hdCall = 0;
      result = GetLineObjWithReadLock(v4, &hdCall);
      if ( result )
        return result;
      v24 = hdCall;
      TspLog(
        4,
        "PE::fnLineEvent: msg(%x), line(%p), p1(%p), p2(%p), p3(%p)",
        LowPart,
        *((const void **)hdCall + 1),
        *(const void **)&eventRecord->EventHeader.ProviderId.Data1,
        *(const void **)eventRecord->EventHeader.ProviderId.Data4,
        *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))gpfnLineEvent)(
        *((_QWORD *)v24 + 1),
        0,
        LowPart,
        *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1,
        *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
        *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
      v19 = v4;
      return ReleaseObjReadLock(v19);
    case 0x13u:
      TspLog(
        4,
        "PE::fnLineEvent(CREATE): ghProvider(%p), p2(%p), p3(%p)",
        (const void *)ghProvider,
        *(const void **)eventRecord->EventHeader.ProviderId.Data4,
        *(const void **)&eventRecord->EventHeader.EventDescriptor.Id);
      return ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, __int64, _QWORD, _QWORD))gpfnLineEvent)(
               0,
               0,
               19,
               ghProvider,
               *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4,
               *(_QWORD *)&eventRecord->EventHeader.EventDescriptor.Id);
  }
  if ( LowPart != 500 )
  {
    if ( LowPart != 501 )
      return TspLog(1, "ProcessEvent: unknown msg(%x)", LowPart);
    goto LABEL_43;
  }
  hdCall = 0;
  v26 = 0;
  result = GetLineObjWithWriteLock(v4, &v26);
  if ( !result )
  {
    v6 = AllocCallObj();
    v7 = v26;
    v8 = (_QWORD *)v6;
    if ( v6 )
    {
      *(_DWORD *)v6 = 1229144396;
      *(_QWORD *)(v6 + 24) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
      *(_QWORD *)(v6 + 56) = *(_QWORD *)eventRecord->EventHeader.ProviderId.Data4;
      *(_QWORD *)(v6 + 32) = v4;
      *(_DWORD *)(v6 + 64) = 0;
      *(_DWORD *)(v6 + 4) = *(_DWORD *)(v7 + 4);
      ReleaseObjWriteLock(v4);
      if ( (unsigned int)OpenObjHandle((__int64)v8, (__int64)FreeCallObj, &hdCall) )
      {
        TspLog(1, "ProcessEvent: failed to map obj(%p) to handle", v8);
        return FreeCallObj(v8);
      }
      else if ( (unsigned int)AcquireObjWriteLock(v4) )
      {
        TspLog(1, "ProcessEvent: failed to reacquire write lock for obj(%p)", v4);
        return CloseObjHandle(hdCall);
      }
      else
      {
        v9 = hdCall;
        v8[2] = hdCall;
        TspLog(4, "PE::fnLineEvent(NEWCALL): htline(%p), call(%p)", *(const void **)(v7 + 8), v9);
        ((void (__fastcall *)(_QWORD, _QWORD, __int64, HDRVCALL, _QWORD *, _QWORD))gpfnLineEvent)(
          *(_QWORD *)(v7 + 8),
          0,
          500,
          v9,
          v8 + 1,
          0);
        v10 = *(_QWORD *)(v7 + 24);
        v8[6] = v10;
        if ( v10 )
          *(_QWORD *)(v10 + 40) = v8;
        *(_QWORD *)(v7 + 24) = v8;
        result = ReleaseObjWriteLock(v4);
        if ( !v8[1] )
        {
          TspLog(2, "ProcessEvent: TAPI failed to create its own handle for the new call, so we close the call");
          return TSPI_lineCloseCall(v9);
        }
      }
    }
    else
    {
      v11 = *(_DWORD *)(v26 + 4);
      hdCall = 0;
      lpInBuffer = 0;
      if ( !(unsigned int)PrepareSyncRequest(117637385, v11, 0x18u, &hdCall) )
      {
        v12 = (struct HDRVCALL__ *)hdCall;
        v13 = (struct HDRVCALL__ *)hdCall;
        *((_QWORD *)hdCall + 3) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
        *((_DWORD *)v13 + 8) = 0;
        SyncDriverRequest(0x8FFF23CC, v13);
        FreeRequest(v12);
        if ( !(unsigned int)PrepareSyncRequest(117637380, *(_DWORD *)(v7 + 4), 0x10u, &lpInBuffer) )
        {
          v14 = lpInBuffer;
          v15 = lpInBuffer;
          *((_QWORD *)lpInBuffer + 3) = *(_QWORD *)&eventRecord->EventHeader.ProviderId.Data1;
          SyncDriverRequest(0x8FFF23CC, v15);
          FreeRequest(v14);
        }
      }
      return ReleaseObjWriteLock(v4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180003ba8  mov     r11, rsp
0x180003bab  mov     [r11+20h], rbx
0x180003baf  push    rbp
0x180003bb0  push    rsi
0x180003bb1  push    rdi
0x180003bb2  push    r12
0x180003bb4  push    r13
0x180003bb6  push    r14
0x180003bb8  push    r15
0x180003bba  mov     rbp, rsp
0x180003bbd  sub     rsp, 50h
0x180003bc1  mov     rax, [rcx+28h]
0x180003bc5  lea     rdx, aProcesseventEv; "ProcessEvent: event(%p), msg(%x), ht_li"...
0x180003bcc  mov     rbx, [rcx+8]
0x180003bd0  mov     r14, rcx
0x180003bd3  mov     r15d, [rcx+10h]
0x180003bd7  mov     r8, rcx
0x180003bda  mov     rdi, [rcx]
0x180003bdd  mov     r13d, 4
0x180003be3  mov     [r11-48h], rax
0x180003be7  mov     r9d, r15d
0x180003bea  mov     rax, [rcx+20h]
0x180003bee  mov     [r11-50h], rax
0x180003bf2  mov     rax, [rcx+18h]
0x180003bf6  mov     ecx, r13d
0x180003bf9  mov     [r11-58h], rax
0x180003bfd  mov     [r11-60h], rbx
0x180003c01  mov     [r11-68h], rdi
0x180003c05  call    TspLog
0x180003c0a  xor     r12d, r12d
0x180003c0d  mov     eax, r15d
0x180003c10  test    r15d, r15d
0x180003c13  jz      loc_1800040E6
0x180003c19  sub     eax, 1
0x180003c1c  jz      loc_180004047
0x180003c22  sub     eax, 1
0x180003c25  jz      loc_180003EAD
0x180003c2b  sub     eax, 1
0x180003c2e  jz      loc_1800040E6
0x180003c34  sub     eax, 1
0x180003c37  jz      loc_1800040E6
0x180003c3d  sub     eax, r13d
0x180003c40  jz      loc_1800040E6
0x180003c46  sub     eax, 0Bh
0x180003c49  jz      loc_180003E58
0x180003c4f  sub     eax, 1E1h
0x180003c54  jz      short loc_180003C77
0x180003c56  cmp     eax, 1
0x180003c59  jz      loc_180004047
0x180003c5f  mov     r8d, r15d
0x180003c62  lea     rdx, aProcesseventUn; "ProcessEvent: unknown msg(%x)"
0x180003c69  lea     ecx, [r13-3]
0x180003c6d  call    TspLog
0x180003c72  jmp     loc_180004162
0x180003c77  lea     rdx, [rbp+arg_8]
0x180003c7b  mov     [rbp+hdCall], r12
0x180003c7f  mov     rcx, rdi
0x180003c82  mov     [rbp+arg_8], r12
0x180003c86  call    GetLineObjWithWriteLock
0x180003c8b  test    eax, eax
0x180003c8d  jnz     loc_180004162
0x180003c93  call    AllocCallObj
0x180003c98  mov     rsi, [rbp+arg_8]
0x180003c9c  mov     rbx, rax
0x180003c9f  test    rax, rax
0x180003ca2  jz      loc_180003DC5
0x180003ca8  mov     dword ptr [rax], 4943414Ch
0x180003cae  mov     rcx, [r14+18h]
0x180003cb2  mov     [rax+18h], rcx
0x180003cb6  mov     rcx, [r14+20h]
0x180003cba  mov     [rax+38h], rcx
0x180003cbe  mov     [rax+20h], rdi
0x180003cc2  mov     [rax+40h], r12d
0x180003cc6  mov     ecx, [rsi+4]
0x180003cc9  mov     [rax+4], ecx
0x180003ccc  mov     rcx, rdi
0x180003ccf  call    ReleaseObjWriteLock
0x180003cd4  lea     r8, [rbp+hdCall]
0x180003cd8  mov     rcx, rbx
0x180003cdb  lea     rdx, FreeCallObj
0x180003ce2  call    OpenObjHandle
0x180003ce7  test    eax, eax
0x180003ce9  jz      short loc_180003D0C
0x180003ceb  mov     r8, rbx
0x180003cee  lea     rdx, aProcesseventFa_1; "ProcessEvent: failed to map obj(%p) to "...
0x180003cf5  mov     ecx, 1
0x180003cfa  call    TspLog
0x180003cff  mov     rcx, rbx
0x180003d02  call    FreeCallObj
0x180003d07  jmp     loc_180004162
0x180003d0c  mov     rcx, rdi
0x180003d0f  call    AcquireObjWriteLock
0x180003d14  test    eax, eax
0x180003d16  jz      short loc_180003D3A
0x180003d18  mov     r8, rdi
0x180003d1b  lea     rdx, aProcesseventFa_0; "ProcessEvent: failed to reacquire write"...
0x180003d22  mov     ecx, 1
0x180003d27  call    TspLog
0x180003d2c  mov     rcx, [rbp+hdCall]
0x180003d30  call    CloseObjHandle
0x180003d35  jmp     loc_180004162
0x180003d3a  mov     r14, [rbp+hdCall]
0x180003d3e  lea     rdx, aPeFnlineeventN; "PE::fnLineEvent(NEWCALL): htline(%p), c"...
0x180003d45  mov     [rbx+10h], r14
0x180003d49  mov     r9, r14
0x180003d4c  mov     r8, [rsi+8]
0x180003d50  mov     ecx, r13d
0x180003d53  call    TspLog
0x180003d58  mov     rcx, [rsi+8]
0x180003d5c  lea     r15, [rbx+8]
0x180003d60  mov     rax, cs:gpfnLineEvent
0x180003d67  mov     r9, r14
0x180003d6a  xor     edx, edx
0x180003d6c  mov     [rsp+50h+var_28], r12
0x180003d71  mov     r8d, 1F4h
0x180003d77  mov     [rsp+50h+var_30], r15
0x180003d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d81  mov     rax, [rsi+18h]
0x180003d85  mov     [rbx+30h], rax
0x180003d89  test    rax, rax
0x180003d8c  jz      short loc_180003D92
0x180003d8e  mov     [rax+28h], rbx
0x180003d92  mov     rcx, rdi
0x180003d95  mov     [rsi+18h], rbx
0x180003d99  call    ReleaseObjWriteLock
0x180003d9e  cmp     [r15], r12
0x180003da1  jnz     loc_180004162
0x180003da7  lea     rdx, aProcesseventTa; "ProcessEvent: TAPI failed to create its"...
0x180003dae  mov     ecx, 2
0x180003db3  call    TspLog
0x180003db8  mov     rcx, r14; hdCall
0x180003dbb  call    TSPI_lineCloseCall
0x180003dc0  jmp     loc_180004162
0x180003dc5  mov     edx, [rsi+4]
0x180003dc8  lea     r9, [rbp+hdCall]
0x180003dcc  mov     r8d, 18h
0x180003dd2  mov     [rbp+hdCall], r12
0x180003dd6  mov     ecx, 7030109h
0x180003ddb  mov     [rbp+lpInBuffer], r12
0x180003ddf  call    PrepareSyncRequest
0x180003de4  test    eax, eax
0x180003de6  jnz     short loc_180003E4B
0x180003de8  mov     rbx, [rbp+hdCall]
0x180003dec  mov     r15d, 8FFF23CCh
0x180003df2  mov     rax, [r14+18h]
0x180003df6  mov     rdx, rbx; lpInBuffer
0x180003df9  mov     ecx, r15d; dwIoControlCode
0x180003dfc  mov     [rbx+18h], rax
0x180003e00  mov     [rbx+20h], r12d
0x180003e04  call    SyncDriverRequest
0x180003e09  mov     rcx, rbx; void *
0x180003e0c  call    FreeRequest
0x180003e11  mov     edx, [rsi+4]
0x180003e14  lea     r9, [rbp+lpInBuffer]
0x180003e18  mov     r8d, 10h
0x180003e1e  mov     ecx, 7030104h
0x180003e23  call    PrepareSyncRequest
0x180003e28  test    eax, eax
0x180003e2a  jnz     short loc_180003E4B
0x180003e2c  mov     rbx, [rbp+lpInBuffer]
0x180003e30  mov     ecx, r15d; dwIoControlCode
0x180003e33  mov     rax, [r14+18h]
0x180003e37  mov     rdx, rbx; lpInBuffer
0x180003e3a  mov     [rbx+18h], rax
0x180003e3e  call    SyncDriverRequest
0x180003e43  mov     rcx, rbx; void *
0x180003e46  call    FreeRequest
0x180003e4b  mov     rcx, rdi
0x180003e4e  call    ReleaseObjWriteLock
0x180003e53  jmp     loc_180004162
0x180003e58  mov     rax, [r14+28h]
0x180003e5c  lea     rdx, aPeFnlineeventC_1; "PE::fnLineEvent(CREATE): ghProvider(%p)"...
0x180003e63  mov     r9, [r14+20h]
0x180003e67  mov     ecx, r13d
0x180003e6a  mov     r8, cs:ghProvider
0x180003e71  mov     [rsp+50h+var_30], rax
0x180003e76  call    TspLog
0x180003e7b  mov     rcx, [r14+28h]
0x180003e7f  xor     edx, edx
0x180003e81  mov     r9, cs:ghProvider
0x180003e88  mov     rax, cs:gpfnLineEvent
0x180003e8f  mov     [rsp+50h+var_28], rcx
0x180003e94  mov     rcx, [r14+20h]
0x180003e98  lea     r8d, [rdx+13h]
0x180003e9c  mov     [rsp+50h+var_30], rcx
0x180003ea1  xor     ecx, ecx
0x180003ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ea8  jmp     loc_180004162
0x180003ead  lea     r9, [rbp+hdCall]
0x180003eb1  mov     [rbp+arg_8], r12
0x180003eb5  lea     r8, [rbp+arg_8]
0x180003eb9  mov     [rbp+hdCall], r12
0x180003ebd  mov     rdx, rbx
0x180003ec0  mov     rcx, rdi
0x180003ec3  call    GetLineAndCallObjWithReadLock
0x180003ec8  test    eax, eax
0x180003eca  jnz     loc_180004162
0x180003ed0  mov     rbx, [rbp+hdCall]
0x180003ed4  cmp     dword ptr [rbx], 4F43414Ch
0x180003eda  mov     rsi, [rbx+20h]
0x180003ede  jnz     short loc_180003F1B
0x180003ee0  cmp     dword ptr [rbx+40h], 1
0x180003ee4  jnz     short loc_180003F1B
0x180003ee6  lea     rdx, aProcesseventIn; "ProcessEvent: incomplete outbound call,"...
0x180003eed  mov     ecx, r13d
0x180003ef0  call    TspLog
0x180003ef5  mov     eax, [r14+18h]
0x180003ef9  mov     [rbx+28h], eax
0x180003efc  mov     eax, [r14+20h]
0x180003f00  mov     [rbx+30h], eax
0x180003f03  mov     eax, [r14+28h]
0x180003f07  mov     [rbx+38h], eax
0x180003f0a  mov     rcx, [rbx+10h]
0x180003f0e  call    ReleaseObjReadLock
0x180003f13  mov     rcx, rsi
0x180003f16  jmp     loc_18000415D
0x180003f1b  cmp     [rbx+48h], r12d
0x180003f1f  jnz     short loc_180003F0A
0x180003f21  mov     r15d, 4000h
0x180003f27  cmp     [r14+18h], r15
0x180003f2b  jz      short loc_180003F34
0x180003f2d  cmp     qword ptr [r14+18h], 1
0x180003f32  jnz     short loc_180003F86
0x180003f34  mov     rdi, [rbx+10h]
0x180003f38  mov     rcx, rdi
0x180003f3b  call    ReleaseObjReadLock
0x180003f40  mov     rcx, rdi
0x180003f43  call    AcquireObjWriteLock
0x180003f48  test    eax, eax
0x180003f4a  jz      short loc_180003F62
0x180003f4c  lea     rdx, aProcesseventFa_2; "ProcessEvent: failed to acquire write l"...
0x180003f53  mov     r8, rdi
0x180003f56  mov     ecx, 2
0x180003f5b  call    TspLog
0x180003f60  jmp     short loc_180003F13
0x180003f62  mov     rcx, rdi
0x180003f65  mov     dword ptr [rbx+48h], 1
0x180003f6c  call    ReleaseObjWriteLock
0x180003f71  mov     rcx, rdi
0x180003f74  call    AcquireObjReadLock
0x180003f79  test    eax, eax
0x180003f7b  jz      short loc_180003F86
0x180003f7d  lea     rdx, aProcesseventFa; "ProcessEvent: failed to reacquire read "...
0x180003f84  jmp     short loc_180003F53
0x180003f86  mov     rax, [r14+28h]
0x180003f8a  lea     rdx, aPeFnlineeventC_0; "PE::fnLineEvent(CALLSTATE): htline(%p),"...
0x180003f91  mov     rdi, [rbp+arg_8]
0x180003f95  mov     ecx, r13d
0x180003f98  mov     r9, [rbx+8]
0x180003f9c  mov     [rsp+50h+var_20], rax
0x180003fa1  mov     rax, [r14+20h]
0x180003fa5  mov     r8, [rdi+8]
0x180003fa9  mov     [rsp+50h+var_28], rax
0x180003fae  mov     rax, [r14+18h]
0x180003fb2  mov     [rsp+50h+var_30], rax
0x180003fb7  call    TspLog
0x180003fbc  mov     rcx, [r14+28h]
0x180003fc0  mov     r8d, 2
0x180003fc6  mov     r9, [r14+18h]
0x180003fca  mov     rdx, [rbx+8]
0x180003fce  mov     rax, cs:gpfnLineEvent
0x180003fd5  mov     [rsp+50h+var_28], rcx
0x180003fda  mov     rcx, [r14+20h]
0x180003fde  mov     [rsp+50h+var_30], rcx
0x180003fe3  mov     rcx, [rdi+8]
0x180003fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fec  cmp     [r14+18h], r15
0x180003ff0  jnz     loc_180003F0A
0x180003ff6  mov     rax, [r14+28h]
0x180003ffa  lea     rdx, aPeFnlineeventC; "PE::fnLineEvent(CALLSTATE_IDLE): htline"...
0x180004001  mov     r9, [rbx+8]
0x180004005  mov     ecx, r13d
0x180004008  mov     r8, [rdi+8]
0x18000400c  mov     [rsp+50h+var_30], rax
0x180004011  call    TspLog
0x180004016  mov     rcx, [r14+28h]
0x18000401a  mov     r9d, 1
0x180004020  mov     rdx, [rbx+8]
0x180004024  mov     rax, cs:gpfnLineEvent
0x18000402b  mov     [rsp+50h+var_28], rcx
0x180004030  mov     rcx, [rdi+8]
0x180004034  lea     r8d, [r9+1]
0x180004038  mov     [rsp+50h+var_30], r12
0x18000403d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004042  jmp     loc_180003F0A
0x180004047  lea     r9, [rbp+hdCall]
0x18000404b  mov     [rbp+arg_8], r12
0x18000404f  lea     r8, [rbp+arg_8]
0x180004053  mov     [rbp+hdCall], r12
0x180004057  mov     rdx, rbx
0x18000405a  mov     rcx, rdi
0x18000405d  call    GetLineAndCallObjWithReadLock
0x180004062  test    eax, eax
0x180004064  jnz     loc_180004162
0x18000406a  mov     rax, [r14+28h]
0x18000406e  lea     rdx, aPeFnlineeventM; "PE::fnLineEvent: msg(%x), htline(%p), h"...
0x180004075  mov     rdi, [rbp+hdCall]
0x180004079  mov     r8d, r15d
0x18000407c  mov     rbx, [rbp+arg_8]
0x180004080  mov     ecx, r13d
  ... truncated ...
```
