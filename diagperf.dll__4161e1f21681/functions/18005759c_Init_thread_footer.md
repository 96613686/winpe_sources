# _Init_thread_footer

- ea: `0x18005759c`
- end: `0x180057605`
- name: `_Init_thread_footer`
- size: `105`
- prototype: ``
- caller_count: `71`
- callee_count: `0`
- tags: ``

## callers

- `0x1800296a0`
- `0x18002afa0`
- `0x18002b130`
- `0x18002bd40`
- `0x18002bdc0`
- `0x18002c3f0`
- `0x18002ce60`
- `0x18002d0c0`
- `0x18002d160`
- `0x18002d210`
- `0x18002d2b0`
- `0x18002d350`
- `0x18002d4b0`
- `0x18002d5c0`
- `0x18002d660`
- `0x18002d700`
- `0x18002d7a0`
- `0x18002d840`
- `0x18002d8e0`
- `0x18002d980`
- `0x18003ffa0`
- `0x180040040`
- `0x1800400e0`
- `0x180040180`
- `0x180040230`
- `0x1800402d0`
- `0x180040370`
- `0x18005e800`
- `0x18005e8a0`
- `0x180063500`
- `0x18006a350`
- `0x18006c0f0`
- `0x18006e7d0`
- `0x18006ef70`
- `0x1800704a0`
- `0x180075510`
- `0x18007e680`
- `0x180084290`
- `0x180093080`
- `0x180098410`
- `0x18009ca40`
- `0x1800a19f0`
- `0x1800a8600`
- `0x1800aba50`
- `0x1800adb80`
- `0x1800aefa0`
- `0x1800b17c0`
- `0x1800b18d0`
- `0x1800b1a10`
- `0x1800b4810`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800575ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800575ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800575ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800575ac`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x1800575fe`

## pseudocode

```c
void __fastcall Init_thread_footer(_DWORD *a1)
{
  __int64 v2; // rdx

  AcquireSRWLockExclusive(&stru_1801011D8);
  v2 = (unsigned int)tls_index;
  *a1 = ++Init_global_epoch;
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + v2) + 4LL) = Init_global_epoch;
  ReleaseSRWLockExclusive(&stru_1801011D8);
  WakeAllConditionVariable(&ConditionVariable);
}

```

## disassembly

```asm
0x18005759c  push    rbx
0x18005759e  sub     rsp, 20h
0x1800575a2  mov     rbx, rcx
0x1800575a5  lea     rcx, stru_1801011D8; SRWLock
0x1800575ac  call    cs:__imp_AcquireSRWLockExclusive
0x1800575b2  mov     eax, cs:_Init_global_epoch
0x1800575b8  lea     rcx, stru_1801011D8; SRWLock
0x1800575bf  mov     edx, cs:_tls_index
0x1800575c5  inc     eax
0x1800575c7  mov     cs:_Init_global_epoch, eax
0x1800575cd  mov     [rbx], eax
0x1800575cf  mov     rax, gs:58h
0x1800575d8  mov     r9d, 4
0x1800575de  mov     r8, [rax+rdx*8]
0x1800575e2  mov     eax, cs:_Init_global_epoch
0x1800575e8  mov     [r9+r8], eax
0x1800575ec  call    cs:__imp_ReleaseSRWLockExclusive
0x1800575f2  lea     rcx, ConditionVariable
0x1800575f9  add     rsp, 20h
0x1800575fd  pop     rbx
0x1800575fe  jmp     cs:__imp_WakeAllConditionVariable
```
