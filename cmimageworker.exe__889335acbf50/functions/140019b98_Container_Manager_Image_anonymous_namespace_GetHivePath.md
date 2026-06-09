# Container::Manager::Image::_anonymous_namespace_::GetHivePath

- ea: `0x140019b98`
- end: `0x140019dc2`
- name: `Container::Manager::Image::_anonymous_namespace_::GetHivePath`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001b938`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000a7a4`
- `0x14000a9b8`
- `0x14000cd84`
- `0x14000d7bc`
- `0x140019b98`

## string_xrefs

- `0x140019c20`: `Windows\System32\Config`
- `0x140019d00`: `SECURITY`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::GetHivePath(const void **a1, int a2, __int64 a3)
{
  __int64 v5; // r8
  const void *v6; // rdx
  __int64 v7; // rdx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  unsigned int v11; // ebx
  const wchar_t *v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h]
  void *v15[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v16[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  v5 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v6 = *a1;
  v15[0] = v16;
  v15[1] = v16;
  v16[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v15,
          v6,
          v5 >> 1) )
  {
    v7 = 196;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    if ( v15[0] != v16 )
      operator delete(v15[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( a2 == 1 )
  {
    v14 = 24;
    v13 = L"Users\\Default\\ntuser.dat";
    if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
    {
      v7 = 201;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v14 = 23;
  v13 = L"Windows\\System32\\Config";
  if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
  {
    v7 = 205;
    goto LABEL_23;
  }
  v8 = a2 - 2;
  if ( !v8 )
  {
    v14 = 3;
    v13 = L"SAM";
    if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
    {
      v7 = 211;
      goto LABEL_23;
    }
LABEL_26:
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
      a3,
      (__int64)v15);
    if ( v15[0] != v16 )
      operator delete(v15[0], (const struct std::nothrow_t *)&std::nothrow);
    return 0;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v14 = 8;
    v13 = L"SECURITY";
    if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
    {
      v7 = 217;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v14 = 8;
    v13 = L"SOFTWARE";
    if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
    {
      v7 = 223;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  if ( v10 == 1 )
  {
    v14 = 6;
    v13 = L"SYSTEM";
    if ( !Csl::Path::Append((Csl::Path *)v15, &v13) )
    {
      v7 = 229;
      goto LABEL_23;
    }
    goto LABEL_26;
  }
  v11 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xED,
          (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
          (const char *)0x32);
  if ( v15[0] != v16 )
    operator delete(v15[0], (const struct std::nothrow_t *)&std::nothrow);
  return v11;
}

```

## disassembly

```asm
0x140019b98  mov     [rsp-8+arg_0], rbx
0x140019b9d  mov     [rsp-8+arg_8], rdi
0x140019ba2  push    rbp
0x140019ba3  mov     rbp, rsp
0x140019ba6  sub     rsp, 50h
0x140019baa  mov     rdi, r8
0x140019bad  lea     rax, [rbp+var_10]
0x140019bb1  mov     r8, [rcx+8]
0x140019bb5  mov     ebx, edx
0x140019bb7  sub     r8, [rcx]
0x140019bba  mov     rdx, [rcx]
0x140019bbd  lea     rcx, [rbp+var_20]
0x140019bc1  mov     [rbp+var_20], rax
0x140019bc5  lea     rax, [rbp+var_10]
0x140019bc9  mov     [rbp+var_18], rax
0x140019bcd  xor     eax, eax
0x140019bcf  sar     r8, 1
0x140019bd2  mov     [rbp+var_10], ax
0x140019bd6  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140019bdb  test    al, al
0x140019bdd  jnz     short loc_140019BE9
0x140019bdf  mov     edx, 0C4h
0x140019be4  jmp     loc_140019D54
0x140019be9  lea     rdx, [rbp+var_30]
0x140019bed  lea     rcx, [rbp+var_20]; this
0x140019bf1  cmp     ebx, 1
0x140019bf4  jnz     short loc_140019C20
0x140019bf6  lea     rax, aUsersDefaultNt; "Users\\Default\\ntuser.dat"
0x140019bfd  mov     [rbp+var_28], 18h
0x140019c05  mov     [rbp+var_30], rax
0x140019c09  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019c0e  test    al, al
0x140019c10  jnz     loc_140019D8A
0x140019c16  mov     edx, 0C9h
0x140019c1b  jmp     loc_140019D54
0x140019c20  lea     rax, aWindowsSystem3; "Windows\\System32\\Config"
0x140019c27  mov     [rbp+var_28], 17h
0x140019c2f  mov     [rbp+var_30], rax
0x140019c33  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019c38  test    al, al
0x140019c3a  jnz     short loc_140019C46
0x140019c3c  mov     edx, 0CDh
0x140019c41  jmp     loc_140019D54
0x140019c46  sub     ebx, 2
0x140019c49  jz      loc_140019D2B
0x140019c4f  sub     ebx, 1
0x140019c52  jz      loc_140019D00
0x140019c58  sub     ebx, 1
0x140019c5b  jz      short loc_140019CD1
0x140019c5d  cmp     ebx, 1
0x140019c60  jz      short loc_140019C9F
0x140019c62  mov     rcx, [rbp+8]; this
0x140019c66  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019c6d  mov     r9d, 32h ; '2'; char *
0x140019c73  mov     edx, 0EDh; void *
0x140019c78  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x140019c7d  mov     rcx, [rbp+var_20]; void *
0x140019c81  mov     ebx, eax
0x140019c83  lea     rax, [rbp+var_10]
0x140019c87  cmp     rcx, rax
0x140019c8a  jz      short loc_140019C98
0x140019c8c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019c93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019c98  mov     eax, ebx
0x140019c9a  jmp     loc_140019DB1
0x140019c9f  lea     rax, aSystem; "SYSTEM"
0x140019ca6  mov     [rbp+var_28], 6
0x140019cae  lea     rdx, [rbp+var_30]
0x140019cb2  mov     [rbp+var_30], rax
0x140019cb6  lea     rcx, [rbp+var_20]; this
0x140019cba  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019cbf  test    al, al
0x140019cc1  jnz     loc_140019D8A
0x140019cc7  mov     edx, 0E5h
0x140019ccc  jmp     loc_140019D54
0x140019cd1  lea     rax, aSoftware; "SOFTWARE"
0x140019cd8  mov     [rbp+var_28], 8
0x140019ce0  lea     rdx, [rbp+var_30]
0x140019ce4  mov     [rbp+var_30], rax
0x140019ce8  lea     rcx, [rbp+var_20]; this
0x140019cec  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019cf1  test    al, al
0x140019cf3  jnz     loc_140019D8A
0x140019cf9  mov     edx, 0DFh
0x140019cfe  jmp     short loc_140019D54
0x140019d00  lea     rax, aSecurity; "SECURITY"
0x140019d07  mov     [rbp+var_28], 8
0x140019d0f  lea     rdx, [rbp+var_30]
0x140019d13  mov     [rbp+var_30], rax
0x140019d17  lea     rcx, [rbp+var_20]; this
0x140019d1b  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019d20  test    al, al
0x140019d22  jnz     short loc_140019D8A
0x140019d24  mov     edx, 0D9h
0x140019d29  jmp     short loc_140019D54
0x140019d2b  lea     rax, aSam; "SAM"
0x140019d32  mov     [rbp+var_28], 3
0x140019d3a  lea     rdx, [rbp+var_30]
0x140019d3e  mov     [rbp+var_30], rax
0x140019d42  lea     rcx, [rbp+var_20]; this
0x140019d46  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140019d4b  test    al, al
0x140019d4d  jnz     short loc_140019D8A
0x140019d4f  mov     edx, 0D3h; void *
0x140019d54  mov     rcx, [rbp+8]; this
0x140019d58  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019d5f  mov     r9d, 8007000Eh; char *
0x140019d65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140019d6a  mov     rcx, [rbp+var_20]; void *
0x140019d6e  lea     rax, [rbp+var_10]
0x140019d72  cmp     rcx, rax
0x140019d75  jz      short loc_140019D83
0x140019d77  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019d7e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019d83  mov     eax, 8007000Eh
0x140019d88  jmp     short loc_140019DB1
0x140019d8a  lea     rdx, [rbp+var_20]
0x140019d8e  mov     rcx, rdi
0x140019d91  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x140019d96  mov     rcx, [rbp+var_20]; void *
0x140019d9a  lea     rax, [rbp+var_10]
0x140019d9e  cmp     rcx, rax
0x140019da1  jz      short loc_140019DAF
0x140019da3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140019daa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140019daf  xor     eax, eax
0x140019db1  mov     rbx, [rsp+50h+arg_0]
0x140019db6  mov     rdi, [rsp+50h+arg_8]
0x140019dbb  add     rsp, 50h
0x140019dbf  pop     rbp
0x140019dc0  retn
```
