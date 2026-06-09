# _Init_thread_header

- ea: `0x180003d28`
- end: `0x180003da3`
- name: `_Init_thread_header`
- size: `123`
- prototype: `void __fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000e250`

## callees

- `0x180003d28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d38`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003d38`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d9c`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003d60`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180003d60`

## pseudocode

```c
void __fastcall Init_thread_header(_DWORD *a1)
{
  AcquireSRWLockExclusive(&stru_180028508);
  while ( 1 )
  {
    if ( !*a1 )
    {
      *a1 = -1;
      goto LABEL_7;
    }
    if ( *a1 != -1 )
      break;
    SleepConditionVariableSRW(&ConditionVariable, &stru_180028508, 0xFFFFFFFF, 0);
  }
  *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) = Init_global_epoch;
LABEL_7:
  ReleaseSRWLockExclusive(&stru_180028508);
}

```

## disassembly

```asm
0x180003d28  push    rbx
0x180003d2a  sub     rsp, 20h
0x180003d2e  mov     rbx, rcx
0x180003d31  lea     rcx, stru_180028508; SRWLock
0x180003d38  call    cs:__imp_AcquireSRWLockExclusive
0x180003d3e  cmp     dword ptr [rbx], 0
0x180003d41  jnz     short loc_180003D68
0x180003d43  mov     dword ptr [rbx], 0FFFFFFFFh
0x180003d49  jmp     short loc_180003D90
0x180003d4b  xor     r9d, r9d; Flags
0x180003d4e  lea     rdx, stru_180028508; SRWLock
0x180003d55  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x180003d59  lea     rcx, ConditionVariable; ConditionVariable
0x180003d60  call    cs:__imp_SleepConditionVariableSRW
0x180003d66  jmp     short loc_180003D3E
0x180003d68  cmp     dword ptr [rbx], 0FFFFFFFFh
0x180003d6b  jz      short loc_180003D4B
0x180003d6d  mov     rax, gs:58h
0x180003d76  mov     ecx, cs:_tls_index
0x180003d7c  mov     r8d, 4
0x180003d82  mov     rdx, [rax+rcx*8]
0x180003d86  mov     eax, cs:_Init_global_epoch
0x180003d8c  mov     [r8+rdx], eax
0x180003d90  lea     rcx, stru_180028508
0x180003d97  add     rsp, 20h
0x180003d9b  pop     rbx
0x180003d9c  jmp     cs:__imp_ReleaseSRWLockExclusive
```
