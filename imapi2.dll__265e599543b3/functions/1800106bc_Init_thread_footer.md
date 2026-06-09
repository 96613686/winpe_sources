# _Init_thread_footer

- ea: `0x1800106bc`
- end: `0x180010725`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b260`
- `0x18000b3f0`
- `0x18000bb10`
- `0x18000c760`
- `0x18000cb70`
- `0x18000f064`
- `0x18000f4b8`
- `0x1800276fc`
- `0x180031248`
- `0x18003a8c0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001070c`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18001070c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800106cc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800106cc`
- `KERNEL32!WakeAllConditionVariable` at `0x18001071e`

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
0x1800106bc  push    rbx
0x1800106be  sub     rsp, 20h
0x1800106c2  mov     rbx, rcx
0x1800106c5  lea     rcx, SRWLock; SRWLock
0x1800106cc  call    cs:__imp_AcquireSRWLockExclusive
0x1800106d2  mov     eax, cs:_Init_global_epoch
0x1800106d8  lea     rcx, SRWLock; SRWLock
0x1800106df  mov     edx, cs:_tls_index
0x1800106e5  inc     eax
0x1800106e7  mov     cs:_Init_global_epoch, eax
0x1800106ed  mov     [rbx], eax
0x1800106ef  mov     rax, gs:58h
0x1800106f8  mov     r9d, 4
0x1800106fe  mov     r8, [rax+rdx*8]
0x180010702  mov     eax, cs:_Init_global_epoch
0x180010708  mov     [r9+r8], eax
0x18001070c  call    cs:__imp_ReleaseSRWLockExclusive
0x180010712  lea     rcx, ConditionVariable
0x180010719  add     rsp, 20h
0x18001071d  pop     rbx
0x18001071e  jmp     cs:__imp_WakeAllConditionVariable
```
