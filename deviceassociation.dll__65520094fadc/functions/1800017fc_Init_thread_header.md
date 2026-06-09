# _Init_thread_header

- ea: `0x1800017fc`
- end: `0x180001877`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180009aa0`
- `0x180009e20`

## callees

- `0x1800017fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180001870`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000180c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000180c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001834`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180001834`

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
0x1800017fc  push    rbx
0x1800017fe  sub     rsp, 20h
0x180001802  mov     rbx, rcx
0x180001805  lea     rcx, SRWLock; SRWLock
0x18000180c  call    cs:__imp_AcquireSRWLockExclusive
0x180001812  cmp     dword ptr [rbx], 0
0x180001815  jnz     short loc_18000183C
0x180001817  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000181d  jmp     short loc_180001864
0x18000181f  xor     r9d, r9d; Flags
0x180001822  lea     rdx, SRWLock; SRWLock
0x180001829  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000182d  lea     rcx, ConditionVariable; ConditionVariable
0x180001834  call    cs:__imp_SleepConditionVariableSRW
0x18000183a  jmp     short loc_180001812
0x18000183c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000183f  jz      short loc_18000181F
0x180001841  mov     rax, gs:58h
0x18000184a  mov     ecx, cs:_tls_index
0x180001850  mov     r8d, 4
0x180001856  mov     rdx, [rax+rcx*8]
0x18000185a  mov     eax, cs:_Init_global_epoch
0x180001860  mov     [r8+rdx], eax
0x180001864  lea     rcx, SRWLock
0x18000186b  add     rsp, 20h
0x18000186f  pop     rbx
0x180001870  jmp     cs:__imp_ReleaseSRWLockExclusive
```
