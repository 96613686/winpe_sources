# EtwpFreeTraceHandle(unsigned __int64)

- ea: `0x180004ea8`
- end: `0x180004f83`
- name: `?EtwpFreeTraceHandle@@YAK_K@Z`
- size: `219`
- prototype: `unsigned int __fastcall(unsigned __int64)`
- caller_count: `5`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180006520`
- `0x180006740`
- `0x180006970`
- `0x180006c60`
- `0x180007060`

## callees

- `0x180004da0`
- `0x180004ea8`
- `0x18000ff24`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004f6b`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180004f6b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ec6`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004ec6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004f2a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004f3a`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180004f47`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180004f47`

## pseudocode

```c
__int64 __fastcall EtwpFreeTraceHandle(__int64 a1)
{
  unsigned int v2; // ebx
  struct _TRACELOG_CONTEXT *i; // rdi
  signed __int32 v5[10]; // [rsp+0h] [rbp-28h] BYREF

  v2 = 6;
  RtlAcquireSRWLockExclusive(&EtwpConsumerLock);
  for ( i = EtwpTraceHandleList; i != (struct _TRACELOG_CONTEXT *)&EtwpTraceHandleList; i = *(struct _TRACELOG_CONTEXT **)i )
  {
    if ( a1 == *((_QWORD *)i + 2) )
    {
      if ( i )
      {
        if ( *((_DWORD *)i + 6) == 1 )
        {
          *((_DWORD *)i + 6) = 2;
          _InterlockedOr(v5, 0);
          if ( *((_QWORD *)i + 70) )
          {
            EtwpRealTimeDisconnect(i);
          }
          else if ( *((_BYTE *)i + 552) == 2 )
          {
            AcquireSRWLockExclusive((PSRWLOCK)i + 127);
            *((_BYTE *)i + 1024) = 0;
            ReleaseSRWLockExclusive((PSRWLOCK)i + 127);
            WakeConditionVariable((PCONDITION_VARIABLE)i + 126);
          }
          v2 = 7007;
        }
        else if ( *((_DWORD *)i + 6) != 2 )
        {
          EtwpFreeTraceContextWithLock(i);
          v2 = 0;
        }
      }
      break;
    }
  }
  RtlReleaseSRWLockExclusive(&EtwpConsumerLock);
  return v2;
}

```

## disassembly

```asm
0x180004ea8  mov     [rsp+arg_0], rbx
0x180004ead  mov     [rsp+arg_8], rsi
0x180004eb2  push    rdi
0x180004eb3  sub     rsp, 20h
0x180004eb7  mov     rsi, rcx
0x180004eba  mov     ebx, 6
0x180004ebf  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x180004ec6  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180004ecc  mov     rdi, cs:?EtwpTraceHandleList@@3U_LIST_ENTRY@@A; _LIST_ENTRY EtwpTraceHandleList
0x180004ed3  lea     rax, ?EtwpTraceHandleList@@3U_LIST_ENTRY@@A; _LIST_ENTRY EtwpTraceHandleList
0x180004eda  jmp     short loc_180004EE5
0x180004edc  cmp     rsi, [rdi+10h]
0x180004ee0  jz      short loc_180004EEC
0x180004ee2  mov     rdi, [rdi]
0x180004ee5  cmp     rdi, rax
0x180004ee8  jnz     short loc_180004EDC
0x180004eea  jmp     short loc_180004F64
0x180004eec  xor     esi, esi
0x180004eee  test    rdi, rdi
0x180004ef1  jz      short loc_180004F64
0x180004ef3  cmp     dword ptr [rdi+18h], 1
0x180004ef7  jnz     short loc_180004F54
0x180004ef9  mov     dword ptr [rdi+18h], 2
0x180004f00  lock or [rsp+28h+var_28], esi
0x180004f04  cmp     [rdi+230h], rsi
0x180004f0b  jz      short loc_180004F17
0x180004f0d  mov     rcx, rdi; struct _TRACELOG_CONTEXT *
0x180004f10  call    ?EtwpRealTimeDisconnect@@YAXPEAU_TRACELOG_CONTEXT@@@Z; EtwpRealTimeDisconnect(_TRACELOG_CONTEXT *)
0x180004f15  jmp     short loc_180004F4D
0x180004f17  cmp     byte ptr [rdi+228h], 2
0x180004f1e  jnz     short loc_180004F4D
0x180004f20  lea     rbx, [rdi+3F8h]
0x180004f27  mov     rcx, rbx; SRWLock
0x180004f2a  call    cs:__imp_AcquireSRWLockExclusive
0x180004f30  mov     rcx, rbx; SRWLock
0x180004f33  mov     [rdi+400h], sil
0x180004f3a  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f40  lea     rcx, [rdi+3F0h]; ConditionVariable
0x180004f47  call    cs:__imp_WakeConditionVariable
0x180004f4d  mov     ebx, 1B5Fh
0x180004f52  jmp     short loc_180004F64
0x180004f54  cmp     dword ptr [rdi+18h], 2
0x180004f58  jz      short loc_180004F64
0x180004f5a  mov     rcx, rdi; Block
0x180004f5d  call    ?EtwpFreeTraceContextWithLock@@YAXPEAU_TRACELOG_CONTEXT@@@Z; EtwpFreeTraceContextWithLock(_TRACELOG_CONTEXT *)
0x180004f62  mov     ebx, esi
0x180004f64  lea     rcx, ?EtwpConsumerLock@@3U_RTL_SRWLOCK@@A; _RTL_SRWLOCK EtwpConsumerLock
0x180004f6b  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180004f71  mov     rsi, [rsp+28h+arg_8]
0x180004f76  mov     eax, ebx
0x180004f78  mov     rbx, [rsp+28h+arg_0]
0x180004f7d  add     rsp, 20h
0x180004f81  pop     rdi
0x180004f82  retn
```
