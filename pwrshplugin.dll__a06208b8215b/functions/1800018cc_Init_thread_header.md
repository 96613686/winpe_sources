# _Init_thread_header

- ea: `0x1800018cc`
- end: `0x180001947`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002fac`

## callees

- `0x1800018cc`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1800018dc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800018dc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180001940`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001904`
- `KERNEL32!SleepConditionVariableSRW` at `0x180001904`

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
0x1800018cc  push    rbx
0x1800018ce  sub     rsp, 20h
0x1800018d2  mov     rbx, rcx
0x1800018d5  lea     rcx, SRWLock; SRWLock
0x1800018dc  call    cs:__imp_AcquireSRWLockExclusive
0x1800018e2  cmp     dword ptr [rbx], 0
0x1800018e5  jnz     short loc_18000190C
0x1800018e7  mov     dword ptr [rbx], 0FFFFFFFFh
0x1800018ed  jmp     short loc_180001934
0x1800018ef  xor     r9d, r9d; Flags
0x1800018f2  lea     rdx, SRWLock; SRWLock
0x1800018f9  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x1800018fd  lea     rcx, ConditionVariable; ConditionVariable
0x180001904  call    cs:__imp_SleepConditionVariableSRW
0x18000190a  jmp     short loc_1800018E2
0x18000190c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000190f  jz      short loc_1800018EF
0x180001911  mov     rax, gs:58h
0x18000191a  mov     ecx, cs:_tls_index
0x180001920  mov     r8d, 4
0x180001926  mov     rdx, [rax+rcx*8]
0x18000192a  mov     eax, cs:_Init_global_epoch
0x180001930  mov     [r8+rdx], eax
0x180001934  lea     rcx, SRWLock
0x18000193b  add     rsp, 20h
0x18000193f  pop     rbx
0x180001940  jmp     cs:__imp_ReleaseSRWLockExclusive
```
