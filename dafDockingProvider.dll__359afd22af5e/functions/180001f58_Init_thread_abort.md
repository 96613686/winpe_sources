# _Init_thread_abort

- ea: `0x180001f58`
- end: `0x180001f94`
- name: `_Init_thread_abort`
- size: `60`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x18001dc26`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f68`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180001f68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f7b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001f7b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180001f8d`

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
0x180001f58  push    rbx
0x180001f5a  sub     rsp, 20h
0x180001f5e  mov     rbx, rcx
0x180001f61  lea     rcx, SRWLock; SRWLock
0x180001f68  call    cs:__imp_AcquireSRWLockExclusive
0x180001f6e  lea     rcx, SRWLock; SRWLock
0x180001f75  mov     dword ptr [rbx], 0
0x180001f7b  call    cs:__imp_ReleaseSRWLockExclusive
0x180001f81  lea     rcx, ConditionVariable
0x180001f88  add     rsp, 20h
0x180001f8c  pop     rbx
0x180001f8d  jmp     cs:__imp_WakeAllConditionVariable
```
