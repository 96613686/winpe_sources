# _Init_thread_header

- ea: `0x18000a238`
- end: `0x18000a2b3`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006350`
- `0x180013190`

## callees

- `0x18000a238`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a248`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a248`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000a2ac`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000a270`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x18000a270`

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
0x18000a238  push    rbx
0x18000a23a  sub     rsp, 20h
0x18000a23e  mov     rbx, rcx
0x18000a241  lea     rcx, SRWLock; SRWLock
0x18000a248  call    cs:__imp_AcquireSRWLockExclusive
0x18000a24e  cmp     dword ptr [rbx], 0
0x18000a251  jnz     short loc_18000A278
0x18000a253  mov     dword ptr [rbx], 0FFFFFFFFh
0x18000a259  jmp     short loc_18000A2A0
0x18000a25b  xor     r9d, r9d; Flags
0x18000a25e  lea     rdx, SRWLock; SRWLock
0x18000a265  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18000a269  lea     rcx, ConditionVariable; ConditionVariable
0x18000a270  call    cs:__imp_SleepConditionVariableSRW
0x18000a276  jmp     short loc_18000A24E
0x18000a278  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18000a27b  jz      short loc_18000A25B
0x18000a27d  mov     rax, gs:58h
0x18000a286  mov     ecx, cs:_tls_index
0x18000a28c  mov     r8d, 4
0x18000a292  mov     rdx, [rax+rcx*8]
0x18000a296  mov     eax, cs:_Init_global_epoch
0x18000a29c  mov     [r8+rdx], eax
0x18000a2a0  lea     rcx, SRWLock
0x18000a2a7  add     rsp, 20h
0x18000a2ab  pop     rbx
0x18000a2ac  jmp     cs:__imp_ReleaseSRWLockExclusive
```
