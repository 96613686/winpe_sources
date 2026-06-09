# _Init_thread_header

- ea: `0x18005760c`
- end: `0x180057687`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `71`
- callee_count: `1`
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

## callees

- `0x18005760c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180057680`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005761c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005761c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180057644`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180057644`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&stru_1801011D8);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &stru_1801011D8, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&stru_1801011D8);
}

```

## disassembly

```asm
0x18005760c  push    rbx
0x18005760e  sub     rsp, 20h
0x180057612  mov     rbx, rcx
0x180057615  lea     rcx, stru_1801011D8; SRWLock
0x18005761c  call    cs:__imp_AcquireSRWLockExclusive
0x180057622  cmp     dword ptr [rbx], 0
0x180057625  jnz     short loc_18005764C
0x180057627  mov     dword ptr [rbx], 0FFFFFFFFh
0x18005762d  jmp     short loc_180057674
0x18005762f  xor     r9d, r9d; Flags
0x180057632  lea     rdx, stru_1801011D8; SRWLock
0x180057639  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18005763d  lea     rcx, ConditionVariable; ConditionVariable
0x180057644  call    cs:__imp_SleepConditionVariableSRW
0x18005764a  jmp     short loc_180057622
0x18005764c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18005764f  jz      short loc_18005762F
0x180057651  mov     rax, gs:58h
0x18005765a  mov     ecx, cs:_tls_index
0x180057660  mov     r8d, 4
0x180057666  mov     rdx, [rax+rcx*8]
0x18005766a  mov     eax, cs:_Init_global_epoch
0x180057670  mov     [r8+rdx], eax
0x180057674  lea     rcx, stru_1801011D8
0x18005767b  add     rsp, 20h
0x18005767f  pop     rbx
0x180057680  jmp     cs:__imp_ReleaseSRWLockExclusive
```
