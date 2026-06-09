# _Init_thread_footer

- ea: `0x18000185c`
- end: `0x1800018c5`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180002fac`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x1800018be`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000186c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000186c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800018ac`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800018ac`

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
0x18000185c  push    rbx
0x18000185e  sub     rsp, 20h
0x180001862  mov     rbx, rcx
0x180001865  lea     rcx, SRWLock; SRWLock
0x18000186c  call    cs:__imp_AcquireSRWLockExclusive
0x180001872  mov     eax, cs:_Init_global_epoch
0x180001878  lea     rcx, SRWLock; SRWLock
0x18000187f  mov     edx, cs:_tls_index
0x180001885  inc     eax
0x180001887  mov     cs:_Init_global_epoch, eax
0x18000188d  mov     [rbx], eax
0x18000188f  mov     rax, gs:58h
0x180001898  mov     r9d, 4
0x18000189e  mov     r8, [rax+rdx*8]
0x1800018a2  mov     eax, cs:_Init_global_epoch
0x1800018a8  mov     [r9+r8], eax
0x1800018ac  call    cs:__imp_ReleaseSRWLockExclusive
0x1800018b2  lea     rcx, ConditionVariable
0x1800018b9  add     rsp, 20h
0x1800018bd  pop     rbx
0x1800018be  jmp     cs:__imp_WakeAllConditionVariable
```
