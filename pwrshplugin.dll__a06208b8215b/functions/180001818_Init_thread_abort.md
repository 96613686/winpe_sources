# _Init_thread_abort

- ea: `0x180001818`
- end: `0x180001854`
- name: `_Init_thread_abort`
- size: `60`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180009aac`

## import_xrefs

- `KERNEL32!WakeAllConditionVariable` at `0x18000184d`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001828`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001828`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000183b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000183b`

## pseudocode

```c
void __fastcall Init_thread_abort(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  *a1 = 0;
  ReleaseSRWLockExclusive(&SRWLock);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x180001818  push    rbx
0x18000181a  sub     rsp, 20h
0x18000181e  mov     rbx, rcx
0x180001821  lea     rcx, SRWLock; SRWLock
0x180001828  call    cs:__imp_AcquireSRWLockExclusive
0x18000182e  lea     rcx, SRWLock; SRWLock
0x180001835  mov     dword ptr [rbx], 0
0x18000183b  call    cs:__imp_ReleaseSRWLockExclusive
0x180001841  lea     rcx, ConditionVariable
0x180001848  add     rsp, 20h
0x18000184c  pop     rbx
0x18000184d  jmp     cs:__imp_WakeAllConditionVariable
```
