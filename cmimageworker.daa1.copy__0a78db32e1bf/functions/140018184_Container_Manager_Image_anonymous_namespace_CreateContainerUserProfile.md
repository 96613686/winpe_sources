# Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile

- ea: `0x140018184`
- end: `0x14001831a`
- name: `Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000a9b8`
- `0x14000cd84`
- `0x140018184`
- `0x1400187e4`
- `0x140019e40`
- `0x14001d310`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x140018265`
- `ntdll!RtlDoesFileExists_U` at `0x140018265`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::CreateContainerUserProfile(
        __int64 *a1,
        __int64 *a2,
        __int64 a3)
{
  __int64 v5; // r8
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int UserProfileFromDefaultUserProfile; // ebx
  __int64 v12; // rdx
  const wchar_t *v13; // [rsp+20h] [rbp-30h] BYREF
  __int64 v14; // [rsp+28h] [rbp-28h]
  PCWSTR FileName[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v16[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  v5 = a1[1] - *a1;
  v7 = *a1;
  FileName[0] = v16;
  FileName[1] = v16;
  v16[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           FileName,
                           v7,
                           v5 >> 1) )
  {
    v8 = 970;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      (int)v13);
    if ( FileName[0] != v16 )
      operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v14 = 5;
  v13 = L"Users";
  if ( !Csl::Path::Append((Csl::Path *)FileName, &v13) )
  {
    v8 = 971;
    goto LABEL_7;
  }
  v9 = *(_QWORD *)(a3 + 8) - *(_QWORD *)a3;
  v13 = *(const wchar_t **)a3;
  v14 = v9 >> 1;
  if ( !Csl::Path::Append((Csl::Path *)FileName, &v13) )
  {
    v8 = 972;
    goto LABEL_7;
  }
  if ( !RtlDoesFileExists_U(FileName[0]) )
  {
    UserProfileFromDefaultUserProfile = Container::Manager::Image::_anonymous_namespace_::CreateUserProfileFromDefaultUserProfile(
                                          (__int64)a1,
                                          a2,
                                          FileName);
    if ( UserProfileFromDefaultUserProfile < 0 )
    {
      v12 = 981;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)UserProfileFromDefaultUserProfile,
        (int)v13);
      if ( FileName[0] != v16 )
        operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)UserProfileFromDefaultUserProfile;
    }
    UserProfileFromDefaultUserProfile = Container::Manager::Image::_anonymous_namespace_::InitializeUserHive(
                                          a2,
                                          (__int64 *)FileName);
    if ( UserProfileFromDefaultUserProfile < 0 )
    {
      v12 = 984;
      goto LABEL_13;
    }
    UserProfileFromDefaultUserProfile = Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage(
                                          a1,
                                          (unsigned __int8 **)a2,
                                          (unsigned __int8 **)a3);
    if ( UserProfileFromDefaultUserProfile < 0 )
    {
      v12 = 987;
      goto LABEL_13;
    }
  }
  if ( FileName[0] != v16 )
    operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x140018184  push    rbp
0x140018186  push    rbx
0x140018187  push    rsi
0x140018188  push    rdi
0x140018189  push    r14
0x14001818b  mov     rbp, rsp
0x14001818e  sub     rsp, 50h
0x140018192  mov     rsi, r8
0x140018195  lea     rax, [rbp+var_10]
0x140018199  mov     r8, [rcx+8]
0x14001819d  mov     rdi, rdx
0x1400181a0  sub     r8, [rcx]
0x1400181a3  mov     r14, rcx
0x1400181a6  mov     rdx, [rcx]
0x1400181a9  lea     rcx, [rbp+FileName]
0x1400181ad  mov     [rbp+FileName], rax
0x1400181b1  lea     rax, [rbp+var_10]
0x1400181b5  mov     [rbp+var_18], rax
0x1400181b9  xor     eax, eax
0x1400181bb  sar     r8, 1
0x1400181be  mov     [rbp+var_10], ax
0x1400181c2  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400181c7  test    al, al
0x1400181c9  jnz     short loc_1400181D2
0x1400181cb  mov     edx, 3CAh
0x1400181d0  jmp     short loc_140018228
0x1400181d2  lea     rax, aUsers; "Users"
0x1400181d9  mov     [rbp+var_28], 5
0x1400181e1  lea     rdx, [rbp+var_30]
0x1400181e5  mov     [rbp+var_30], rax
0x1400181e9  lea     rcx, [rbp+FileName]; this
0x1400181ed  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1400181f2  test    al, al
0x1400181f4  jnz     short loc_1400181FD
0x1400181f6  mov     edx, 3CBh
0x1400181fb  jmp     short loc_140018228
0x1400181fd  mov     rax, [rsi]
0x140018200  lea     rdx, [rbp+var_30]
0x140018204  mov     rcx, [rsi+8]
0x140018208  sub     rcx, rax
0x14001820b  mov     [rbp+var_30], rax
0x14001820f  sar     rcx, 1
0x140018212  mov     [rbp+var_28], rcx
0x140018216  lea     rcx, [rbp+FileName]; this
0x14001821a  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001821f  test    al, al
0x140018221  jnz     short loc_140018261
0x140018223  mov     edx, 3CCh; void *
0x140018228  mov     rcx, [rbp+28h]; this
0x14001822c  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018233  mov     r9d, 8007000Eh; char *
0x140018239  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001823e  mov     rcx, [rbp+FileName]; void *
0x140018242  lea     rax, [rbp+var_10]
0x140018246  cmp     rcx, rax
0x140018249  jz      short loc_140018257
0x14001824b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018252  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018257  mov     eax, 8007000Eh
0x14001825c  jmp     loc_14001830E
0x140018261  mov     rcx, [rbp+FileName]; FileName
0x140018265  call    cs:__imp_RtlDoesFileExists_U
0x14001826c  nop     dword ptr [rax+rax+00h]
0x140018271  test    al, al
0x140018273  jnz     short loc_1400182F3
0x140018275  lea     r8, [rbp+FileName]
0x140018279  mov     rdx, rdi
0x14001827c  mov     rcx, r14
0x14001827f  call    Container__Manager__Image___anonymous_namespace___CreateUserProfileFromDefaultUserProfile
0x140018284  mov     ebx, eax
0x140018286  test    eax, eax
0x140018288  jns     short loc_1400182BF
0x14001828a  mov     edx, 3D5h; void *
0x14001828f  mov     rcx, [rbp+28h]; this
0x140018293  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001829a  mov     r9d, ebx; char *
0x14001829d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400182a2  mov     rcx, [rbp+FileName]; void *
0x1400182a6  lea     rax, [rbp+var_10]
0x1400182aa  cmp     rcx, rax
0x1400182ad  jz      short loc_1400182BB
0x1400182af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400182b6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400182bb  mov     eax, ebx
0x1400182bd  jmp     short loc_14001830E
0x1400182bf  lea     rdx, [rbp+FileName]
0x1400182c3  mov     rcx, rdi
0x1400182c6  call    Container__Manager__Image___anonymous_namespace___InitializeUserHive
0x1400182cb  mov     ebx, eax
0x1400182cd  test    eax, eax
0x1400182cf  jns     short loc_1400182D8
0x1400182d1  mov     edx, 3D8h
0x1400182d6  jmp     short loc_14001828F
0x1400182d8  mov     r8, rsi
0x1400182db  mov     rdx, rdi
0x1400182de  mov     rcx, r14
0x1400182e1  call    Container__Manager__Image___anonymous_namespace___RegisterUserHiveInImage
0x1400182e6  mov     ebx, eax
0x1400182e8  test    eax, eax
0x1400182ea  jns     short loc_1400182F3
0x1400182ec  mov     edx, 3DBh
0x1400182f1  jmp     short loc_14001828F
0x1400182f3  mov     rcx, [rbp+FileName]; void *
0x1400182f7  lea     rax, [rbp+var_10]
0x1400182fb  cmp     rcx, rax
0x1400182fe  jz      short loc_14001830C
0x140018300  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018307  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001830c  xor     eax, eax
0x14001830e  add     rsp, 50h
0x140018312  pop     r14
0x140018314  pop     rdi
0x140018315  pop     rsi
0x140018316  pop     rbx
0x140018317  pop     rbp
0x140018318  retn
```
