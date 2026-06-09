# FvepAcquireRemoveLockEx

- ea: `0x14002d630`
- end: `0x14002d75c`
- name: `FvepAcquireRemoveLockEx`
- size: `300`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140026aec`
- `0x140026db8`
- `0x140029e98`
- `0x1400cf640`
- `0x1400e53f0`
- `0x1400e5480`

## callees

- `0x14002d630`
- `0x14002d764`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002d675`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14002d675`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d6aa`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14002d6aa`
- `ntoskrnl!KeBugCheckEx` at `0x14002d729`
- `ntoskrnl!KeBugCheckEx` at `0x14002d74f`
- `ntoskrnl!KeBugCheckEx` at `0x14002d729`
- `ntoskrnl!KeBugCheckEx` at `0x14002d74f`

## pseudocode

```c
__int64 __fastcall FvepAcquireRemoveLockEx(ULONG_PTR BugCheckParameter2, char a2)
{
  NTSTATUS v5; // edx
  signed __int64 v6; // rsi
  unsigned int v7; // r8d
  ULONG_PTR BugCheckParameter4; // [rsp+70h] [rbp+18h]

  if ( *(_QWORD *)(BugCheckParameter2 + 48) )
    return FvepAcquireScalableRemoveLockEx(BugCheckParameter2);
  v5 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(BugCheckParameter2 + 16), *(PVOID *)BugCheckParameter2, File, 1u, 0x20u);
  do
  {
    BugCheckParameter4 = *(_QWORD *)(BugCheckParameter2 + 8);
    v6 = BugCheckParameter4;
    if ( (BugCheckParameter4 & 0xFF000000000000LL) == 0 )
    {
      if ( v5 )
        KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, v5, (unsigned int)BugCheckParameter4);
      LODWORD(BugCheckParameter4) = BugCheckParameter4 + 1;
      v7 = 0;
      continue;
    }
    if ( !v5 )
      IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(BugCheckParameter2 + 16), *(PVOID *)BugCheckParameter2, 0x20u);
    v7 = -1073741738;
    if ( !a2 )
      break;
    if ( !(_DWORD)BugCheckParameter4 )
      KeBugCheckEx(0x120u, 0xEu, BugCheckParameter2, 0xFFFFFFFFC0000056uLL, 0);
    v5 = -1073741738;
    HIDWORD(BugCheckParameter4) = HIDWORD(BugCheckParameter4) & 0xFFFF0000
                                | (unsigned __int16)(WORD2(BugCheckParameter4) + 1);
    v7 = 0;
  }
  while ( v6 != _InterlockedCompareExchange64(
                  (volatile signed __int64 *)(BugCheckParameter2 + 8),
                  BugCheckParameter4,
                  v6) );
  return v7;
}

```

## disassembly

```asm
0x14002d630  mov     [rsp+BugCheckParameter4], r8
0x14002d635  push    rbx
0x14002d636  push    rbp
0x14002d637  push    rsi
0x14002d638  push    rdi
0x14002d639  sub     rsp, 38h
0x14002d63d  cmp     qword ptr [rcx+30h], 0
0x14002d642  mov     dil, dl
0x14002d645  mov     rbx, rcx
0x14002d648  jz      short loc_14002D659
0x14002d64a  call    FvepAcquireScalableRemoveLockEx
0x14002d64f  add     rsp, 38h
0x14002d653  pop     rdi
0x14002d654  pop     rsi
0x14002d655  pop     rbp
0x14002d656  pop     rbx
0x14002d657  retn
0x14002d659  mov     rdx, [rcx]; Tag
0x14002d65c  lea     r8, File; File
0x14002d663  add     rcx, 10h; RemoveLock
0x14002d667  mov     [rsp+58h+RemlockSize], 20h ; ' '; RemlockSize
0x14002d66f  mov     r9d, 1; Line
0x14002d675  call    cs:__imp_IoAcquireRemoveLockEx
0x14002d67c  nop     dword ptr [rax+rax+00h]
0x14002d681  mov     edx, eax
0x14002d683  mov     rsi, [rbx+8]
0x14002d687  mov     rcx, rsi
0x14002d68a  mov     [rsp+58h+BugCheckParameter4], rsi
0x14002d68f  shr     rcx, 20h
0x14002d693  test    ecx, 0FF0000h
0x14002d699  jz      short loc_14002D6E9
0x14002d69b  test    edx, edx
0x14002d69d  jnz     short loc_14002D6B6
0x14002d69f  lea     r8d, [rdx+20h]; RemlockSize
0x14002d6a3  mov     rdx, [rbx]; Tag
0x14002d6a6  lea     rcx, [rbx+10h]; RemoveLock
0x14002d6aa  call    cs:__imp_IoReleaseRemoveLockEx
0x14002d6b1  nop     dword ptr [rax+rax+00h]
0x14002d6b6  mov     r8d, 0C0000056h
0x14002d6bc  test    dil, dil
0x14002d6bf  jz      short loc_14002D708
0x14002d6c1  mov     eax, dword ptr [rsp+58h+BugCheckParameter4]
0x14002d6c5  test    eax, eax
0x14002d6c7  jz      short loc_14002D710
0x14002d6c9  mov     edx, dword ptr [rsp+58h+BugCheckParameter4+4]
0x14002d6cd  lea     eax, [rdx+1]
0x14002d6d0  and     edx, 0FFFF0000h
0x14002d6d6  movzx   ecx, ax
0x14002d6d9  or      ecx, edx
0x14002d6db  mov     edx, 0C0000056h
0x14002d6e0  mov     dword ptr [rsp+58h+BugCheckParameter4+4], ecx
0x14002d6e4  xor     r8d, r8d
0x14002d6e7  jmp     short loc_14002D6F4
0x14002d6e9  test    edx, edx
0x14002d6eb  jnz     short loc_14002D736
0x14002d6ed  inc     dword ptr [rsp+58h+BugCheckParameter4]
0x14002d6f1  mov     r8d, edx
0x14002d6f4  mov     rcx, [rsp+58h+BugCheckParameter4]
0x14002d6f9  mov     rax, rsi
0x14002d6fc  lock cmpxchg [rbx+8], rcx
0x14002d702  jnz     loc_14002D683
0x14002d708  mov     eax, r8d
0x14002d70b  jmp     loc_14002D64F
0x14002d710  mov     r9, 0FFFFFFFFC0000056h; BugCheckParameter3
0x14002d717  mov     qword ptr [rsp+58h+RemlockSize], rax; BugCheckParameter4
0x14002d71c  mov     r8, rbx; BugCheckParameter2
0x14002d71f  mov     edx, 0Eh; BugCheckParameter1
0x14002d724  mov     ecx, 120h; BugCheckCode
0x14002d729  call    cs:__imp_KeBugCheckEx
0x14002d736  mov     eax, dword ptr [rsp+58h+BugCheckParameter4]
0x14002d73a  mov     r8, rbx; BugCheckParameter2
0x14002d73d  movsxd  r9, edx; BugCheckParameter3
0x14002d740  mov     ecx, 120h; BugCheckCode
0x14002d745  mov     edx, 0Eh; BugCheckParameter1
0x14002d74a  mov     qword ptr [rsp+58h+RemlockSize], rax; BugCheckParameter4
0x14002d74f  call    cs:__imp_KeBugCheckEx
```
