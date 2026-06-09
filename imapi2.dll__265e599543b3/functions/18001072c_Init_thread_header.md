# _Init_thread_header

- ea: `0x18001072c`
- end: `0x1800107a7`
- name: `_Init_thread_header`
- size: `123`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b260`
- `0x18000b3f0`
- `0x18000bb10`
- `0x18000c760`
- `0x18000cb70`
- `0x18000f064`
- `0x18000f4b8`
- `0x1800276fc`
- `0x180031248`
- `0x18003a8c0`

## callees

- `0x18001072c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800107a0`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001073c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18001073c`
- `KERNEL32!SleepConditionVariableSRW` at `0x180010764`
- `KERNEL32!SleepConditionVariableSRW` at `0x180010764`

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
0x18001072c  push    rbx
0x18001072e  sub     rsp, 20h
0x180010732  mov     rbx, rcx
0x180010735  lea     rcx, SRWLock; SRWLock
0x18001073c  call    cs:__imp_AcquireSRWLockExclusive
0x180010742  cmp     dword ptr [rbx], 0
0x180010745  jnz     short loc_18001076C
0x180010747  mov     dword ptr [rbx], 0FFFFFFFFh
0x18001074d  jmp     short loc_180010794
0x18001074f  xor     r9d, r9d; Flags
0x180010752  lea     rdx, SRWLock; SRWLock
0x180010759  or      r8d, 0FFFFFFFFh; dwMilliseconds
0x18001075d  lea     rcx, ConditionVariable; ConditionVariable
0x180010764  call    cs:__imp_SleepConditionVariableSRW
0x18001076a  jmp     short loc_180010742
0x18001076c  cmp     dword ptr [rbx], 0FFFFFFFFh
0x18001076f  jz      short loc_18001074F
0x180010771  mov     rax, gs:58h
0x18001077a  mov     ecx, cs:_tls_index
0x180010780  mov     r8d, 4
0x180010786  mov     rdx, [rax+rcx*8]
0x18001078a  mov     eax, cs:_Init_global_epoch
0x180010790  mov     [r8+rdx], eax
0x180010794  lea     rcx, SRWLock
0x18001079b  add     rsp, 20h
0x18001079f  pop     rbx
0x1800107a0  jmp     cs:__imp_ReleaseSRWLockExclusive
```
