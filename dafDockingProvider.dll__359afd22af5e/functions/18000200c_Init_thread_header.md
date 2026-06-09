# _Init_thread_header

- ea: `0x18000200c`
- end: `0x180002087`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180016db4`
- `0x180017374`

## callees

- `0x18000200c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000201c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000201c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002080`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002044`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180002044`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&SRWLock);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &SRWLock, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&SRWLock);
}

```

## disassembly

```asm
0x18000200c  push    rbx
0x18000200e  sub     rsp, 20h
0x180002012  mov     rbx, rcx
0x180002015  lea     rcx, SRWLock; SRWLock
0x18000201c  call    cs:__imp_AcquireSRWLockExclusive
0x180002022  cmp     dword ptr [rbx], 0
0x180002025  jnz     short loc_18000204C
0x180002027  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000202d  jmp     short loc_180002074
0x18000202f  xor     r9d, r9d; Flags
0x180002032  lea     rdx, SRWLock; SRWLock
0x180002039  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000203d  lea     rcx, ConditionVariable; ConditionVariable
0x180002044  call    cs:__imp_SleepConditionVariableSRW
0x18000204a  jmp     short loc_180002022
0x18000204c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000204f  jz      short loc_18000202F
0x180002051  mov     rax, gs:58h
0x18000205a  mov     ecx, cs:_tls_index
0x180002060  mov     r8d, 4
0x180002066  mov     rdx, [rax+rcx*8]
0x18000206a  mov     eax, cs:_Init_global_epoch
0x180002070  mov     [r8+rdx], eax
0x180002074  lea     rcx, SRWLock
0x18000207b  add     rsp, 20h
0x18000207f  pop     rbx
0x180002080  jmp     cs:__imp_ReleaseSRWLockExclusive
```
