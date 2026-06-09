# Csl::EnumerateDirectory(Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)

- ea: `0x14000ad64`
- end: `0x14000ae0b`
- name: `?EnumerateDirectory@Csl@@YAJAEBVPath@1@W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z`
- size: `167`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x140006188`
- `0x1400187e4`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000ad64`
- `0x14000b2ec`

## pseudocode

```c
__int64 __fastcall Csl::EnumerateDirectory(__int64 *a1, int a2, __m128i *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-38h]
  void *v7[2]; // [rsp+30h] [rbp-28h] BYREF
  _WORD v8[12]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( (a2 & 0xA) == 0 )
    a2 |= 0xAu;
  v7[0] = v8;
  v7[1] = v8;
  v8[0] = 0;
  v3 = Csl::EnumerateDirectoryInternal(a1, (__int64)v7, a2, a3, L"*");
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( v7[0] != v8 )
      operator delete(v7[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)(unsigned int)v3,
      v6);
    if ( v7[0] != v8 )
      operator delete(v7[0], (const struct std::nothrow_t *)&std::nothrow);
    return v4;
  }
}

```

## disassembly

```asm
0x14000ad64  push    rbx
0x14000ad66  sub     rsp, 50h
0x14000ad6a  test    dl, 0Ah
0x14000ad6d  jnz     short loc_14000AD72
0x14000ad6f  or      edx, 0Ah
0x14000ad72  lea     rax, [rsp+58h+var_18]
0x14000ad77  mov     r9, r8
0x14000ad7a  mov     [rsp+58h+var_28], rax
0x14000ad7f  mov     r8d, edx
0x14000ad82  lea     rax, [rsp+58h+var_18]
0x14000ad87  mov     [rsp+58h+var_20], rax
0x14000ad8c  lea     rdx, [rsp+58h+var_28]
0x14000ad91  xor     eax, eax
0x14000ad93  mov     [rsp+58h+var_18], ax
0x14000ad98  lea     rax, asc_14003692C; "*"
0x14000ad9f  mov     qword ptr [rsp+58h+var_38], rax; int
0x14000ada4  call    ?EnumerateDirectoryInternal@Csl@@YAJAEBVPath@1@0W4EnumerateDirectoryOption@1@AEAV?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@PEBG@Z; Csl::EnumerateDirectoryInternal(Csl::Path const &,Csl::Path const &,Csl::EnumerateDirectoryOption,utl::vector<Csl::Path,utl::allocator<Csl::Path>> &,ushort const *)
0x14000ada9  mov     ebx, eax
0x14000adab  test    eax, eax
0x14000adad  jns     short loc_14000ADE7
0x14000adaf  mov     rcx, [rsp+58h]; this
0x14000adb4  lea     r8, aOnecoreBaseGen_0; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14000adbb  mov     r9d, eax; char *
0x14000adbe  mov     edx, 30Fh; void *
0x14000adc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000adc8  mov     rcx, [rsp+58h+var_28]; void *
0x14000adcd  lea     rax, [rsp+58h+var_18]
0x14000add2  cmp     rcx, rax
0x14000add5  jz      short loc_14000ADE3
0x14000add7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000adde  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ade3  mov     eax, ebx
0x14000ade5  jmp     short loc_14000AE04
0x14000ade7  mov     rcx, [rsp+58h+var_28]; void *
0x14000adec  lea     rax, [rsp+58h+var_18]
0x14000adf1  cmp     rcx, rax
0x14000adf4  jz      short loc_14000AE02
0x14000adf6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000adfd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000ae02  xor     eax, eax
0x14000ae04  add     rsp, 50h
0x14000ae08  pop     rbx
0x14000ae09  retn
```
