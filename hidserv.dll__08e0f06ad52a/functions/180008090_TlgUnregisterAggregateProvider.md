# TlgUnregisterAggregateProvider

- ea: `0x180008090`
- end: `0x1800081cb`
- name: `TlgUnregisterAggregateProvider`
- size: `315`
- prototype: `ULONG()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001f8c`

## callees

- `0x180007130`
- `0x180007988`
- `0x180008090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800080b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800080f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008146`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008146`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008159`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008124`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008198`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800081bf`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008124`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x180008198`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800081bf`

## pseudocode

```c
ULONG TlgUnregisterAggregateProvider()
{
  __int64 v0; // r8
  __int64 v1; // r9
  __int64 v2; // rdi
  __int64 *v3; // rcx
  __int64 *v4; // rax
  REGHANDLE v5; // rcx
  ULONG result; // eax
  HANDLE ProcessHeap; // rax
  REGHANDLE v8; // rcx
  REGHANDLE v9; // rcx

  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_18000D028 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v2 = qword_18000D728;
    if ( qword_18000D728 )
    {
      v3 = &qword_18000D728;
      while ( 1 )
      {
        v4 = (__int64 *)(v2 + 336);
        if ( *(int **)(v2 + 328) == &dword_18000D000 )
          break;
        v2 = *v4;
        v3 = v4;
        if ( !*v4 )
          goto LABEL_6;
      }
      *v3 = *v4;
      LookUpTableFlushComplete((const __m128i *)v2, (__int64)&dword_18000D000, v0, v1);
      if ( !qword_18000D728 )
      {
        v8 = qword_18000D060;
        dword_18000D040 = 0;
        qword_18000D060 = 0;
        EventUnregister(v8);
      }
    }
    else
    {
LABEL_6:
      v2 = 0;
    }
    ReleaseSRWLockExclusive(&SRWLock);
    if ( v2 )
      CancelTimerCallbacksAndDeleteTimer(v2);
    v5 = RegHandle;
    dword_18000D000 = 0;
    RegHandle = 0;
    result = EventUnregister(v5);
    qword_18000D028 = 0;
    if ( v2 )
    {
      CancelTimerCallbacksAndDeleteTimer(v2);
      ProcessHeap = GetProcessHeap();
      return HeapFree(ProcessHeap, 0, (LPVOID)v2);
    }
  }
  else
  {
    v9 = RegHandle;
    dword_18000D000 = 0;
    RegHandle = 0;
    return EventUnregister(v9);
  }
  return result;
}

```

## disassembly

```asm
0x180008090  push    rdi
0x180008092  sub     rsp, 20h
0x180008096  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x18000809d  cmp     cs:qword_18000D028, rax
0x1800080a4  jnz     loc_1800081A3
0x1800080aa  lea     rcx, SRWLock; SRWLock
0x1800080b1  call    cs:__imp_AcquireSRWLockExclusive
0x1800080b7  mov     rdi, cs:qword_18000D728
0x1800080be  test    rdi, rdi
0x1800080c1  jz      short loc_1800080EC
0x1800080c3  lea     rcx, qword_18000D728
0x1800080ca  lea     rdx, dword_18000D000
0x1800080d1  lea     rax, [rdi+150h]
0x1800080d8  cmp     [rdi+148h], rdx
0x1800080df  jz      short loc_180008160
0x1800080e1  mov     rdi, [rax]
0x1800080e4  mov     rcx, rax
0x1800080e7  test    rdi, rdi
0x1800080ea  jnz     short loc_1800080CA
0x1800080ec  xor     edi, edi
0x1800080ee  lea     rcx, SRWLock; SRWLock
0x1800080f5  call    cs:__imp_ReleaseSRWLockExclusive
0x1800080fb  test    rdi, rdi
0x1800080fe  jz      short loc_180008108
0x180008100  mov     rcx, rdi
0x180008103  call    CancelTimerCallbacksAndDeleteTimer
0x180008108  mov     rcx, cs:RegHandle; RegHandle
0x18000810f  mov     cs:dword_18000D000, 0
0x180008119  mov     cs:RegHandle, 0
0x180008124  call    cs:__imp_EventUnregister
0x18000812a  mov     cs:qword_18000D028, 0
0x180008135  test    rdi, rdi
0x180008138  jz      loc_1800081C5
0x18000813e  mov     rcx, rdi
0x180008141  call    CancelTimerCallbacksAndDeleteTimer
0x180008146  call    cs:__imp_GetProcessHeap
0x18000814c  mov     r8, rdi
0x18000814f  xor     edx, edx
0x180008151  mov     rcx, rax
0x180008154  add     rsp, 20h
0x180008158  pop     rdi
0x180008159  jmp     cs:__imp_HeapFree
0x180008160  mov     rax, [rax]
0x180008163  mov     [rcx], rax
0x180008166  mov     rcx, rdi
0x180008169  call    LookUpTableFlushComplete
0x18000816e  cmp     cs:qword_18000D728, 0
0x180008176  jnz     loc_1800080EE
0x18000817c  mov     rcx, cs:qword_18000D060; RegHandle
0x180008183  mov     cs:dword_18000D040, 0
0x18000818d  mov     cs:qword_18000D060, 0
0x180008198  call    cs:__imp_EventUnregister
0x18000819e  jmp     loc_1800080EE
0x1800081a3  mov     rcx, cs:RegHandle; RegHandle
0x1800081aa  mov     cs:dword_18000D000, 0
0x1800081b4  mov     cs:RegHandle, 0
0x1800081bf  call    cs:__imp_EventUnregister
0x1800081c5  add     rsp, 20h
0x1800081c9  pop     rdi
0x1800081ca  retn
```
