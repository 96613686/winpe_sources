# _Init_thread_footer

- ea: `0x180001a94`
- end: `0x180001afd`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000972c`
- `0x180015fa0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001ae4`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001ae4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001aa4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001aa4`
- `KERNEL32!WakeAllConditionVariable` at `0x180001af6`

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
0x180001a94  push    rbx
0x180001a96  sub     rsp, 20h
0x180001a9a  mov     rbx, rcx
0x180001a9d  lea     rcx, SRWLock; SRWLock
0x180001aa4  call    cs:__imp_AcquireSRWLockExclusive
0x180001aaa  mov     eax, cs:_Init_global_epoch
0x180001ab0  lea     rcx, SRWLock; SRWLock
0x180001ab7  mov     edx, cs:_tls_index
0x180001abd  inc     eax
0x180001abf  mov     cs:_Init_global_epoch, eax
0x180001ac5  mov     [rbx], eax
0x180001ac7  mov     rax, gs:58h
0x180001ad0  mov     r9d, 4
0x180001ad6  mov     r8, [rax+rdx*8]
0x180001ada  mov     eax, cs:_Init_global_epoch
0x180001ae0  mov     [r9+r8], eax
0x180001ae4  call    cs:__imp_ReleaseSRWLockExclusive
0x180001aea  lea     rcx, ConditionVariable
0x180001af1  add     rsp, 20h
0x180001af5  pop     rbx
0x180001af6  jmp     cs:__imp_WakeAllConditionVariable
```
