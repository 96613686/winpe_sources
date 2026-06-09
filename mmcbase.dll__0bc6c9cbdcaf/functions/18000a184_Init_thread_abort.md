# _Init_thread_abort

- ea: `0x18000a184`
- end: `0x18000a1c0`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b876`
- `0x18001bdee`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a194`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a194`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a1a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a1a7`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18000a1b9`

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
0x18000a184  push    rbx
0x18000a186  sub     rsp, 20h
0x18000a18a  mov     rbx, rcx
0x18000a18d  lea     rcx, SRWLock; SRWLock
0x18000a194  call    cs:__imp_AcquireSRWLockExclusive
0x18000a19a  lea     rcx, SRWLock; SRWLock
0x18000a1a1  mov     dword ptr [rbx], 0
0x18000a1a7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000a1ad  lea     rcx, ConditionVariable
0x18000a1b4  add     rsp, 20h
0x18000a1b8  pop     rbx
0x18000a1b9  jmp     cs:__imp_WakeAllConditionVariable
```
