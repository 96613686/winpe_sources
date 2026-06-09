# _Init_thread_footer

- ea: `0x1400029ac`
- end: `0x140002a15`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b708`
- `0x14000e4f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400029bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400029bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400029fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400029fc`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x140002a0e`

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
0x1400029ac  push    rbx
0x1400029ae  sub     rsp, 20h
0x1400029b2  mov     rbx, rcx
0x1400029b5  lea     rcx, SRWLock; SRWLock
0x1400029bc  call    cs:__imp_AcquireSRWLockExclusive
0x1400029c2  mov     eax, cs:_Init_global_epoch
0x1400029c8  lea     rcx, SRWLock; SRWLock
0x1400029cf  mov     edx, cs:_tls_index
0x1400029d5  inc     eax
0x1400029d7  mov     cs:_Init_global_epoch, eax
0x1400029dd  mov     [rbx], eax
0x1400029df  mov     rax, gs:58h
0x1400029e8  mov     r9d, 4
0x1400029ee  mov     r8, [rax+rdx*8]
0x1400029f2  mov     eax, cs:_Init_global_epoch
0x1400029f8  mov     [r9+r8], eax
0x1400029fc  call    cs:__imp_ReleaseSRWLockExclusive
0x140002a02  lea     rcx, ConditionVariable
0x140002a09  add     rsp, 20h
0x140002a0d  pop     rbx
0x140002a0e  jmp     cs:__imp_WakeAllConditionVariable
```
