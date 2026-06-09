# _Init_thread_abort

- ea: `0x140002968`
- end: `0x1400029a4`
- name: `_Init_thread_abort`
- size: `60`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x140015c37`
- `0x140015ceb`
- `0x140015cfd`
- `0x140015d0f`
- `0x140015d21`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002978`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002978`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000298b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000298b`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x14000299d`

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
0x140002968  push    rbx
0x14000296a  sub     rsp, 20h
0x14000296e  mov     rbx, rcx
0x140002971  lea     rcx, SRWLock; SRWLock
0x140002978  call    cs:__imp_AcquireSRWLockExclusive
0x14000297e  lea     rcx, SRWLock; SRWLock
0x140002985  mov     dword ptr [rbx], 0
0x14000298b  call    cs:__imp_ReleaseSRWLockExclusive
0x140002991  lea     rcx, ConditionVariable
0x140002998  add     rsp, 20h
0x14000299c  pop     rbx
0x14000299d  jmp     cs:__imp_WakeAllConditionVariable
```
