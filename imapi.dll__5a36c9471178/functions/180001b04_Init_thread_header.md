# _Init_thread_header

- ea: `0x180001b04`
- end: `0x180001b7f`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000972c`
- `0x180015fa0`

## callees

- `0x180001b04`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001b78`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001b14`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001b14`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001b3c`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001b3c`

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
0x180001b04  push    rbx
0x180001b06  sub     rsp, 20h
0x180001b0a  mov     rbx, rcx
0x180001b0d  lea     rcx, SRWLock; SRWLock
0x180001b14  call    cs:__imp_AcquireSRWLockExclusive
0x180001b1a  cmp     dword ptr [rbx], 0
0x180001b1d  jnz     short loc_180001B44
0x180001b1f  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001b25  jmp     short loc_180001B6C
0x180001b27  xor     r9d, r9d; Flags
0x180001b2a  lea     rdx, SRWLock; SRWLock
0x180001b31  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001b35  lea     rcx, ConditionVariable; ConditionVariable
0x180001b3c  call    cs:__imp_SleepConditionVariableSRW
0x180001b42  jmp     short loc_180001B1A
0x180001b44  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001b47  jz      short loc_180001B27
0x180001b49  mov     rax, gs:58h
0x180001b52  mov     ecx, cs:_tls_index
0x180001b58  mov     r8d, 4
0x180001b5e  mov     rdx, [rax+rcx*8]
0x180001b62  mov     eax, cs:_Init_global_epoch
0x180001b68  mov     [r8+rdx], eax
0x180001b6c  lea     rcx, SRWLock
0x180001b73  add     rsp, 20h
0x180001b77  pop     rbx
0x180001b78  jmp     cs:__imp_ReleaseSRWLockExclusive
```
