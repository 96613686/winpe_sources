# _Init_thread_footer

- ea: `0x18000a1c8`
- end: `0x18000a231`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180006350`
- `0x180013190`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1d8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a1d8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a218`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a218`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a22a`

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
0x18000a1c8  push    rbx
0x18000a1ca  sub     rsp, 20h
0x18000a1ce  mov     rbx, rcx
0x18000a1d1  lea     rcx, SRWLock; SRWLock
0x18000a1d8  call    cs:__imp_AcquireSRWLockExclusive
0x18000a1de  mov     eax, cs:_Init_global_epoch
0x18000a1e4  lea     rcx, SRWLock; SRWLock
0x18000a1eb  mov     edx, cs:_tls_index
0x18000a1f1  inc     eax
0x18000a1f3  mov     cs:_Init_global_epoch, eax
0x18000a1f9  mov     [rbx], eax
0x18000a1fb  mov     rax, gs:58h
0x18000a204  mov     r9d, 4
0x18000a20a  mov     r8, [rax+rdx*8]
0x18000a20e  mov     eax, cs:_Init_global_epoch
0x18000a214  mov     [r9+r8], eax
0x18000a218  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a21e  lea     rcx, ConditionVariable
0x18000a225  add     rsp, 20h
0x18000a229  pop     rbx
0x18000a22a  jmp     cs:__imp_WakeAllConditionVariable
```
