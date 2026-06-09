# _Init_thread_footer

- ea: `0x18000178c`
- end: `0x1800017f5`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009aa0`
- `0x180009e20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800017dc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800017dc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000179c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000179c`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800017ee`

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
0x18000178c  push    rbx
0x18000178e  sub     rsp, 20h
0x180001792  mov     rbx, rcx
0x180001795  lea     rcx, SRWLock; SRWLock
0x18000179c  call    cs:__imp_AcquireSRWLockExclusive
0x1800017a2  mov     eax, cs:_Init_global_epoch
0x1800017a8  lea     rcx, SRWLock; SRWLock
0x1800017af  mov     edx, cs:_tls_index
0x1800017b5  inc     eax
0x1800017b7  mov     cs:_Init_global_epoch, eax
0x1800017bd  mov     [rbx], eax
0x1800017bf  mov     rax, gs:58h
0x1800017c8  mov     r9d, 4
0x1800017ce  mov     r8, [rax+rdx*8]
0x1800017d2  mov     eax, cs:_Init_global_epoch
0x1800017d8  mov     [r9+r8], eax
0x1800017dc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800017e2  lea     rcx, ConditionVariable
0x1800017e9  add     rsp, 20h
0x1800017ed  pop     rbx
0x1800017ee  jmp     cs:__imp_WakeAllConditionVariable
```
