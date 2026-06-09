# _Init_thread_header

- ea: `0x180001c48`
- end: `0x180001cc3`
- name: `_Init_thread_header`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006f04`

## callees

- `0x180001c48`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180001c58`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180001c58`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001cbc`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001c80`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001c80`

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
0x180001c48  push    rbx
0x180001c4a  sub     rsp, 20h
0x180001c4e  mov     rbx, rcx
0x180001c51  lea     rcx, SRWLock; SRWLock
0x180001c58  call    cs:__imp_AcquireSRWLockExclusive
0x180001c5e  cmp     dword ptr [rbx], 0
0x180001c61  jnz     short loc_180001C88
0x180001c63  mov     dword ptr [rbx], 0FFFFFFFFh
0x180001c69  jmp     short loc_180001CB0
0x180001c6b  xor     r9d, r9d; Flags
0x180001c6e  lea     rdx, SRWLock; SRWLock
0x180001c75  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180001c79  lea     rcx, ConditionVariable; ConditionVariable
0x180001c80  call    cs:__imp_SleepConditionVariableSRW
0x180001c86  jmp     short loc_180001C5E
0x180001c88  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180001c8b  jz      short loc_180001C6B
0x180001c8d  mov     rax, gs:58h
0x180001c96  mov     ecx, cs:_tls_index
0x180001c9c  mov     r8d, 4
0x180001ca2  mov     rdx, [rax+rcx*8]
0x180001ca6  mov     eax, cs:_Init_global_epoch
0x180001cac  mov     [r8+rdx], eax
0x180001cb0  lea     rcx, SRWLock
0x180001cb7  add     rsp, 20h
0x180001cbb  pop     rbx
0x180001cbc  jmp     cs:__imp_ReleaseSRWLockExclusive
```
