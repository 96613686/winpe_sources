# _Init_thread_header

- ea: `0x140002a1c`
- end: `0x140002a97`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14000b708`
- `0x14000e4f0`

## callees

- `0x140002a1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002a2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140002a2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140002a90`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140002a54`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x140002a54`

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
0x140002a1c  push    rbx
0x140002a1e  sub     rsp, 20h
0x140002a22  mov     rbx, rcx
0x140002a25  lea     rcx, SRWLock; SRWLock
0x140002a2c  call    cs:__imp_AcquireSRWLockExclusive
0x140002a32  cmp     dword ptr [rbx], 0
0x140002a35  jnz     short loc_140002A5C
0x140002a37  mov     dword ptr [rbx], 0FFFFFFFFh
0x140002a3d  jmp     short loc_140002A84
0x140002a3f  xor     r9d, r9d; Flags
0x140002a42  lea     rdx, SRWLock; SRWLock
0x140002a49  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x140002a4d  lea     rcx, ConditionVariable; ConditionVariable
0x140002a54  call    cs:__imp_SleepConditionVariableSRW
0x140002a5a  jmp     short loc_140002A32
0x140002a5c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x140002a5f  jz      short loc_140002A3F
0x140002a61  mov     rax, gs:58h
0x140002a6a  mov     ecx, cs:_tls_index
0x140002a70  mov     r8d, 4
0x140002a76  mov     rdx, [rax+rcx*8]
0x140002a7a  mov     eax, cs:_Init_global_epoch
0x140002a80  mov     [r8+rdx], eax
0x140002a84  lea     rcx, SRWLock
0x140002a8b  add     rsp, 20h
0x140002a8f  pop     rbx
0x140002a90  jmp     cs:__imp_ReleaseSRWLockExclusive
```
