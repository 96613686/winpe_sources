# CipAllocateValidationContext

- ea: `0x18009f338`
- end: `0x18009f50a`
- name: `CipAllocateValidationContext`
- size: `466`
- prototype: `__int64 __fastcall(int, int, int, int, ULONGLONG Size, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18009fff8`
- `0x1800e5fd0`

## callees

- `0x18005bdf0`
- `0x180061010`
- `0x18009df48`
- `0x18009e8d4`
- `0x18009f338`
- `0x1800a8a34`

## import_xrefs

- `ntoskrnl!RtlImageNtHeaderEx` at `0x18009f415`
- `ntoskrnl!RtlImageNtHeaderEx` at `0x18009f415`

## pseudocode

```c
__int64 __fastcall CipAllocateValidationContext(
        __int64 a1,
        int a2,
        __int64 a3,
        void *a4,
        ULONGLONG Size,
        __int64 a6,
        _DWORD *a7,
        __int64 a8,
        _QWORD *a9)
{
  unsigned int v10; // r12d
  int CimContextIfPresent; // esi
  _QWORD *v13; // r14
  _BYTE *v14; // r13
  char ShouldImageBeForwardedToHvci; // al
  char v16; // r15
  WORD Machine; // cx
  bool v18; // al
  PVOID Entry; // [rsp+38h] [rbp-40h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+40h] [rbp-38h] BYREF

  v10 = a1;
  Entry = 0;
  NtHeader = 0;
  if ( !g_HvciSupported )
    return CipAllocateLocalValidationContext(a1, a6, a8, a3, a9);
  CimContextIfPresent = CipAllocateLocalValidationContext(a1, a6, a8, a3, &Entry);
  v13 = Entry;
  if ( CimContextIfPresent >= 0 )
  {
    v14 = (char *)Entry + 3320;
    ShouldImageBeForwardedToHvci = CipShouldImageBeForwardedToHvci(v10, a2, (char *)Entry + 3320);
    v16 = ShouldImageBeForwardedToHvci;
    if ( !ShouldImageBeForwardedToHvci && !*v14 )
      goto LABEL_18;
    if ( ShouldImageBeForwardedToHvci && a7 && (*a7 & 2) == 0 )
    {
      CimContextIfPresent = -1073741755;
      goto LABEL_21;
    }
    CimContextIfPresent = RtlImageNtHeaderEx(0, a4, (unsigned int)Size, &NtHeader);
    if ( CimContextIfPresent < 0 )
      goto LABEL_21;
    Machine = NtHeader->FileHeader.Machine;
    v18 = Machine != 0x8664u;
    if ( v16 && Machine == 332 )
      v18 = 0;
    if ( v18 )
    {
      *v14 = 0;
      goto LABEL_18;
    }
    if ( !v16
      || (CimContextIfPresent = CiHvciSetValidationContextForHvci(v13, v10, a4, (unsigned int)Size),
          CimContextIfPresent >= 0) )
    {
LABEL_18:
      if ( (a2 & 0x80000) == 0
        || (CimContextIfPresent = CipGetCimContextIfPresent(a3, v13 + 290), CimContextIfPresent >= 0) )
      {
        *a9 = v13;
        v13 = 0;
      }
    }
  }
LABEL_21:
  if ( v13 )
    CiFreeValidationContext(v13);
  return (unsigned int)CimContextIfPresent;
}

```

## disassembly

```asm
0x18009f338  mov     r11, rsp
0x18009f33b  mov     [r11+8], rbx
0x18009f33f  mov     [r11+10h], rsi
0x18009f343  mov     [r11+20h], r9
0x18009f347  mov     [r11+18h], r8
0x18009f34b  push    rdi
0x18009f34c  push    r12
0x18009f34e  push    r13
0x18009f350  push    r14
0x18009f352  push    r15
0x18009f354  sub     rsp, 50h
0x18009f358  mov     ebx, edx
0x18009f35a  mov     r12d, ecx
0x18009f35d  xor     edi, edi
0x18009f35f  mov     [r11-40h], rdi
0x18009f363  mov     [r11-38h], rdi
0x18009f367  mov     r9, r8
0x18009f36a  mov     rdx, [rsp+78h+arg_28]
0x18009f372  mov     r8, [rsp+78h+arg_38]
0x18009f37a  cmp     cs:g_HvciSupported, dil
0x18009f381  jnz     short loc_18009F399
0x18009f383  mov     rax, [rsp+78h+arg_40]
0x18009f38b  mov     [r11-58h], rax
0x18009f38f  call    CipAllocateLocalValidationContext
0x18009f394  jmp     loc_18009F4EF
0x18009f399  lea     rax, [rsp+78h+Entry]
0x18009f39e  mov     [rsp+78h+var_58], rax
0x18009f3a3  call    CipAllocateLocalValidationContext
0x18009f3a8  mov     esi, eax
0x18009f3aa  mov     r14, [rsp+78h+Entry]
0x18009f3af  test    eax, eax
0x18009f3b1  js      loc_18009F4E0
0x18009f3b7  lea     r13, [r14+0CF8h]
0x18009f3be  mov     r8, r13
0x18009f3c1  mov     edx, ebx
0x18009f3c3  mov     ecx, r12d
0x18009f3c6  call    CipShouldImageBeForwardedToHvci
0x18009f3cb  mov     r15b, al
0x18009f3ce  test    al, al
0x18009f3d0  jnz     short loc_18009F3DC
0x18009f3d2  cmp     [r13+0], dil
0x18009f3d6  jz      loc_18009F4A5
0x18009f3dc  test    r15b, r15b
0x18009f3df  jz      short loc_18009F3FE
0x18009f3e1  mov     rax, [rsp+78h+arg_30]
0x18009f3e9  test    rax, rax
0x18009f3ec  jz      short loc_18009F3FE
0x18009f3ee  mov     eax, [rax]
0x18009f3f0  test    al, 2
0x18009f3f2  jnz     short loc_18009F3FE
0x18009f3f4  mov     esi, 0C0000045h
0x18009f3f9  jmp     loc_18009F4E0
0x18009f3fe  mov     r8d, dword ptr [rsp+78h+Size]; Size
0x18009f406  lea     r9, [rsp+78h+NtHeader]; NtHeader
0x18009f40b  mov     rdx, [rsp+78h+BaseAddress]; BaseAddress
0x18009f413  xor     ecx, ecx; Flags
0x18009f415  call    cs:__imp_RtlImageNtHeaderEx
0x18009f41c  nop     dword ptr [rax+rax+00h]
0x18009f421  mov     esi, eax
0x18009f423  mov     [rsp+78h+var_44], eax
0x18009f427  test    eax, eax
0x18009f429  js      loc_18009F4E0
0x18009f42f  mov     rax, [rsp+78h+NtHeader]
0x18009f434  movzx   ecx, word ptr [rax+4]
0x18009f438  movzx   eax, dil
0x18009f43c  mov     edx, 8664h
0x18009f441  mov     r9d, 1
0x18009f447  cmp     cx, dx
0x18009f44a  cmovnz  eax, r9d
0x18009f44e  mov     [rsp+78h+var_48], al
0x18009f452  movzx   edx, dil
0x18009f456  mov     r8d, 14Ch
0x18009f45c  cmp     cx, r8w
0x18009f460  cmovz   edx, r9d
0x18009f464  mov     [rsp+78h+var_47], dl
0x18009f468  test    r15b, r15b
0x18009f46b  jz      short loc_18009F475
0x18009f46d  movzx   eax, al
0x18009f470  test    dl, dl
0x18009f472  cmovnz  eax, edi
0x18009f475  test    al, al
0x18009f477  jz      short loc_18009F47F
0x18009f479  mov     [r13+0], dil
0x18009f47d  jmp     short loc_18009F4A5
0x18009f47f  test    r15b, r15b
0x18009f482  jz      short loc_18009F4A5
0x18009f484  mov     r9d, dword ptr [rsp+78h+Size]
0x18009f48c  mov     r8, [rsp+78h+BaseAddress]
0x18009f494  mov     edx, r12d
0x18009f497  mov     rcx, r14
0x18009f49a  call    CiHvciSetValidationContextForHvci
0x18009f49f  mov     esi, eax
0x18009f4a1  test    eax, eax
0x18009f4a3  js      short loc_18009F4E0
0x18009f4a5  bt      ebx, 13h
0x18009f4a9  jnb     short loc_18009F4C5
0x18009f4ab  lea     rdx, [r14+910h]
0x18009f4b2  mov     rcx, [rsp+78h+arg_10]
0x18009f4ba  call    CipGetCimContextIfPresent
0x18009f4bf  mov     esi, eax
0x18009f4c1  test    eax, eax
0x18009f4c3  js      short loc_18009F4E0
0x18009f4c5  mov     rax, [rsp+78h+arg_40]
0x18009f4cd  mov     [rax], r14
0x18009f4d0  mov     r14, rdi
0x18009f4d3  jmp     short loc_18009F4E0
0x18009f4d5  mov     esi, eax
0x18009f4d7  mov     [rsp+78h+var_44], eax
0x18009f4db  mov     r14, [rsp+78h+Entry]
0x18009f4e0  test    r14, r14
0x18009f4e3  jz      short loc_18009F4ED
0x18009f4e5  mov     rcx, r14; Entry
0x18009f4e8  call    CiFreeValidationContext
0x18009f4ed  mov     eax, esi
0x18009f4ef  lea     r11, [rsp+78h+var_28]
0x18009f4f4  mov     rbx, [r11+30h]
0x18009f4f8  mov     rsi, [r11+38h]
0x18009f4fc  mov     rsp, r11
0x18009f4ff  pop     r15
0x18009f501  pop     r14
0x18009f503  pop     r13
0x18009f505  pop     r12
0x18009f507  pop     rdi
0x18009f508  retn
```
