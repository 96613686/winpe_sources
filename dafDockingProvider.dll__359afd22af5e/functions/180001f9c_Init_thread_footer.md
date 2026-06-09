# _Init_thread_footer

- ea: `0x180001f9c`
- end: `0x180002005`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016db4`
- `0x180017374`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001fac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001fac`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001fec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001fec`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180001ffe`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&SRWLock);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x180001f9c  push    rbx
0x180001f9e  sub     rsp, 20h
0x180001fa2  mov     rbx, rcx
0x180001fa5  lea     rcx, SRWLock; SRWLock
0x180001fac  call    cs:__imp_AcquireSRWLockExclusive
0x180001fb2  mov     eax, cs:_Init_global_epoch
0x180001fb8  lea     rcx, SRWLock; SRWLock
0x180001fbf  mov     edx, cs:_tls_index
0x180001fc5  inc     eax
0x180001fc7  mov     cs:_Init_global_epoch, eax
0x180001fcd  mov     [rbx], eax
0x180001fcf  mov     rax, gs:58h
0x180001fd8  mov     r9d, 4
0x180001fde  mov     r8, [rax+rdx*8]
0x180001fe2  mov     eax, cs:_Init_global_epoch
0x180001fe8  mov     [r9+r8], eax
0x180001fec  call    cs:__imp_ReleaseSRWLockExclusive
0x180001ff2  lea     rcx, ConditionVariable
0x180001ff9  add     rsp, 20h
0x180001ffd  pop     rbx
0x180001ffe  jmp     cs:__imp_WakeAllConditionVariable
```
