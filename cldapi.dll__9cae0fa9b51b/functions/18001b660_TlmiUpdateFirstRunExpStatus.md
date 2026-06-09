# TlmiUpdateFirstRunExpStatus

- ea: `0x18001b660`
- end: `0x18001b75e`
- name: `TlmiUpdateFirstRunExpStatus`
- size: `254`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180012c28`
- `0x180018564`

## callees

- `0x18001b660`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b6b8`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001b6b8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b748`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001b748`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001b735`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001b735`

## pseudocode

```c
void __fastcall TlmiUpdateFirstRunExpStatus(__int64 a1, char a2, __int64 a3, int a4)
{
  LARGE_INTEGER DueTime; // [rsp+30h] [rbp-38h] BYREF

  DueTime.QuadPart = 0;
  if ( byte_18002A930 && !NtCurrentPeb()->Ldr->ShutdownInProgress && byte_18002A968 )
  {
    RtlAcquireSRWLockExclusive(&qword_18002A970);
    if ( a4 < 0 && qword_18002A998 >= 0 )
      HIDWORD(qword_18002A998) = a4;
    qword_18002A980 = a1;
    if ( a2 && a3 )
    {
      if ( (int)qword_18002A998 <= 0 )
        qword_18002A988 = a1;
      LODWORD(qword_18002A998) = *(_DWORD *)(a3 + 16) + qword_18002A998;
      qword_18002A990 = a1;
    }
    DueTime.QuadPart = -150000000;
    SetWaitableTimer(hTimer, &DueTime, 0, 0, 0, 0);
    RtlReleaseSRWLockExclusive(&qword_18002A970);
  }
}

```

## disassembly

```asm
0x18001b660  push    rbx
0x18001b662  push    rbp
0x18001b663  push    rsi
0x18001b664  push    rdi
0x18001b665  sub     rsp, 48h
0x18001b669  cmp     cs:byte_18002A930, 0
0x18001b670  mov     esi, r9d
0x18001b673  mov     rdi, r8
0x18001b676  mov     qword ptr [rsp+68h+DueTime], 0
0x18001b67f  mov     bpl, dl
0x18001b682  mov     rbx, rcx
0x18001b685  jz      loc_18001B754
0x18001b68b  mov     rax, gs:60h
0x18001b694  mov     r10, [rax+18h]
0x18001b698  cmp     byte ptr [r10+48h], 0
0x18001b69d  jnz     loc_18001B754
0x18001b6a3  mov     al, cs:byte_18002A968
0x18001b6a9  test    al, al
0x18001b6ab  jz      loc_18001B754
0x18001b6b1  lea     rcx, qword_18002A970
0x18001b6b8  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18001b6bf  nop     dword ptr [rax+rax+00h]
0x18001b6c4  test    esi, esi
0x18001b6c6  jns     short loc_18001B6D7
0x18001b6c8  cmp     dword ptr cs:qword_18002A998+4, 0
0x18001b6cf  jl      short loc_18001B6D7
0x18001b6d1  mov     dword ptr cs:qword_18002A998+4, esi
0x18001b6d7  mov     cs:qword_18002A980, rbx
0x18001b6de  test    bpl, bpl
0x18001b6e1  jz      short loc_18001B709
0x18001b6e3  test    rdi, rdi
0x18001b6e6  jz      short loc_18001B709
0x18001b6e8  mov     eax, dword ptr cs:qword_18002A998
0x18001b6ee  test    eax, eax
0x18001b6f0  jg      short loc_18001B6F9
0x18001b6f2  mov     cs:qword_18002A988, rbx
0x18001b6f9  add     eax, [rdi+10h]
0x18001b6fc  mov     dword ptr cs:qword_18002A998, eax
0x18001b702  mov     cs:qword_18002A990, rbx
0x18001b709  mov     rcx, cs:hTimer; hTimer
0x18001b710  lea     rdx, [rsp+68h+DueTime]; lpDueTime
0x18001b715  mov     [rsp+68h+fResume], 0; fResume
0x18001b71d  xor     r9d, r9d; pfnCompletionRoutine
0x18001b720  xor     r8d, r8d; lPeriod
0x18001b723  mov     [rsp+68h+lpArgToCompletionRoutine], 0; lpArgToCompletionRoutine
0x18001b72c  mov     qword ptr [rsp+68h+DueTime], 0FFFFFFFFF70F2E80h
0x18001b735  call    cs:__imp_SetWaitableTimer
0x18001b73c  nop     dword ptr [rax+rax+00h]
0x18001b741  lea     rcx, qword_18002A970
0x18001b748  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18001b74f  nop     dword ptr [rax+rax+00h]
0x18001b754  add     rsp, 48h
0x18001b758  pop     rdi
0x18001b759  pop     rsi
0x18001b75a  pop     rbp
0x18001b75b  pop     rbx
0x18001b75c  retn
```
