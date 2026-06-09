# _Init_thread_footer

- ea: `0x180003cb8`
- end: `0x180003d21`
- name: `_Init_thread_footer`
- size: `105`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e250`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003cc8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003cc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d08`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d08`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180003d1a`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&stru_180028508);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&stru_180028508);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x180003cb8  push    rbx
0x180003cba  sub     rsp, 20h
0x180003cbe  mov     rbx, rcx
0x180003cc1  lea     rcx, stru_180028508; SRWLock
0x180003cc8  call    cs:__imp_AcquireSRWLockExclusive
0x180003cce  mov     eax, cs:_Init_global_epoch
0x180003cd4  lea     rcx, stru_180028508; SRWLock
0x180003cdb  mov     edx, cs:_tls_index
0x180003ce1  inc     eax
0x180003ce3  mov     cs:_Init_global_epoch, eax
0x180003ce9  mov     [rbx], eax
0x180003ceb  mov     rax, gs:58h
0x180003cf4  mov     r9d, 4
0x180003cfa  mov     r8, [rax+rdx*8]
0x180003cfe  mov     eax, cs:_Init_global_epoch
0x180003d04  mov     [r9+r8], eax
0x180003d08  call    cs:__imp_ReleaseSRWLockExclusive
0x180003d0e  lea     rcx, ConditionVariable
0x180003d15  add     rsp, 20h
0x180003d19  pop     rbx
0x180003d1a  jmp     cs:__imp_WakeAllConditionVariable
```
