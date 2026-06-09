# _Init_thread_header

- ea: `0x180003430`
- end: `0x1800034ab`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c7e8`
- `0x18000dfdc`

## callees

- `0x180003430`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800034a4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003440`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180003440`
- `KERNEL32!SleepConditionVariableSRW` at `0x180003468`
- `KERNEL32!SleepConditionVariableSRW` at `0x180003468`

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
0x180003430  push    rbx
0x180003432  sub     rsp, 20h
0x180003436  mov     rbx, rcx
0x180003439  lea     rcx, SRWLock; SRWLock
0x180003440  call    cs:__imp_AcquireSRWLockExclusive
0x180003446  cmp     dword ptr [rbx], 0
0x180003449  jnz     short loc_180003470
0x18000344b  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003451  jmp     short loc_180003498
0x180003453  xor     r9d, r9d; Flags
0x180003456  lea     rdx, SRWLock; SRWLock
0x18000345d  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180003461  lea     rcx, ConditionVariable; ConditionVariable
0x180003468  call    cs:__imp_SleepConditionVariableSRW
0x18000346e  jmp     short loc_180003446
0x180003470  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003473  jz      short loc_180003453
0x180003475  mov     rax, gs:58h
0x18000347e  mov     ecx, cs:_tls_index
0x180003484  mov     r8d, 4
0x18000348a  mov     rdx, [rax+rcx*8]
0x18000348e  mov     eax, cs:_Init_global_epoch
0x180003494  mov     [r8+rdx], eax
0x180003498  lea     rcx, SRWLock
0x18000349f  add     rsp, 20h
0x1800034a3  pop     rbx
0x1800034a4  jmp     cs:__imp_ReleaseSRWLockExclusive
```
