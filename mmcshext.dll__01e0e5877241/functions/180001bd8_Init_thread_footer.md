# _Init_thread_footer

- ea: `0x180001bd8`
- end: `0x180001c41`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180006f04`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x180001c3a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001be8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001be8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001c28`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001c28`

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
0x180001bd8  push    rbx
0x180001bda  sub     rsp, 20h
0x180001bde  mov     rbx, rcx
0x180001be1  lea     rcx, SRWLock; SRWLock
0x180001be8  call    cs:__imp_AcquireSRWLockExclusive
0x180001bee  mov     eax, cs:_Init_global_epoch
0x180001bf4  lea     rcx, SRWLock; SRWLock
0x180001bfb  mov     edx, cs:_tls_index
0x180001c01  inc     eax
0x180001c03  mov     cs:_Init_global_epoch, eax
0x180001c09  mov     [rbx], eax
0x180001c0b  mov     rax, gs:58h
0x180001c14  mov     r9d, 4
0x180001c1a  mov     r8, [rax+rdx*8]
0x180001c1e  mov     eax, cs:_Init_global_epoch
0x180001c24  mov     [r9+r8], eax
0x180001c28  call    cs:__imp_ReleaseSRWLockExclusive
0x180001c2e  lea     rcx, ConditionVariable
0x180001c35  add     rsp, 20h
0x180001c39  pop     rbx
0x180001c3a  jmp     cs:__imp_WakeAllConditionVariable
```
