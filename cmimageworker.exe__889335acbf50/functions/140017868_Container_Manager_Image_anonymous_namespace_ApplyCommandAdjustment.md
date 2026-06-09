# Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment

- ea: `0x140017868`
- end: `0x140017c80`
- name: `Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment`
- size: `1048`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x14000a9b8`
- `0x14000bebc`
- `0x14000c70c`
- `0x14000cbb8`
- `0x14000cd84`
- `0x14000d1d4`
- `0x14000d7bc`
- `0x140017868`

## string_xrefs

- `0x140017be8`: `bcdedit.exe command line: %ws \noutput: %hs`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::ApplyCommandAdjustment(
        const void **a1,
        struct Path *a2)
{
  int SystemDirectoryPath; // eax
  unsigned int v6; // edi
  void *v7; // rcx
  void *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8
  const void *v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // eax
  void *v15; // [rsp+40h] [rbp-49h] BYREF
  char *v16; // [rsp+48h] [rbp-41h]
  _WORD v17[8]; // [rsp+50h] [rbp-39h] BYREF
  char *v18[2]; // [rsp+60h] [rbp-29h] BYREF
  _WORD v19[8]; // [rsp+70h] [rbp-19h] BYREF
  void *v20[2]; // [rsp+80h] [rbp-9h] BYREF
  _WORD v21[8]; // [rsp+90h] [rbp+7h] BYREF
  void *v22[2]; // [rsp+A0h] [rbp+17h] BYREF
  _BYTE v23[16]; // [rsp+B0h] [rbp+27h] BYREF
  const wchar_t *v24; // [rsp+C0h] [rbp+37h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+3Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  char *v27; // [rsp+F8h] [rbp+6Fh] BYREF

  if ( *(_DWORD *)a2 != 1 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x27D,
             (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
             (const char *)0x32);
  v15 = v17;
  v17[0] = 0;
  v16 = (char *)v17;
  SystemDirectoryPath = Csl::GetSystemDirectoryPath((Csl *)&v15, a2);
  v6 = SystemDirectoryPath;
  if ( SystemDirectoryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24E,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)SystemDirectoryPath);
    v7 = v15;
    if ( v15 == v17 )
      return v6;
LABEL_5:
    operator delete(v7, (const struct std::nothrow_t *)&std::nothrow);
    return v6;
  }
  v25 = 11;
  v24 = L"bcdedit.exe";
  if ( !Csl::Path::Append((Csl::Path *)&v15, &v24) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24F,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    v8 = v15;
    if ( v15 == v17 )
      return 2147942414LL;
LABEL_35:
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v18[0] = (char *)v19;
  v18[1] = (char *)v19;
  v19[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v18,
          v15,
          (v16 - (_BYTE *)v15) >> 1) )
  {
    v9 = 594;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    goto LABEL_32;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v18,
                           L" /store ",
                           8) )
  {
    v9 = 595;
    goto LABEL_12;
  }
  v10 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v11 = *a1;
  v20[0] = v21;
  v20[1] = v21;
  v21[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v20,
          v11,
          v10 >> 1) )
  {
    v12 = 603;
    goto LABEL_30;
  }
  v25 = 22;
  v24 = L"EFI\\Microsoft\\Boot\\BCD";
  if ( !Csl::Path::Append((Csl::Path *)v20, &v24) )
  {
    v12 = 604;
    goto LABEL_30;
  }
  if ( v20[0] )
  {
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v20[0] + v13) );
  }
  else
  {
    v13 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v18,
                           v20[0],
                           v13) )
  {
    v12 = 606;
    goto LABEL_30;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v18,
                           L" ",
                           1) )
  {
    v12 = 608;
    goto LABEL_30;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v18,
                           *((_QWORD *)a2 + 1),
                           (__int64)(*((_QWORD *)a2 + 2) - *((_QWORD *)a2 + 1)) >> 1) )
  {
    v12 = 609;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    if ( v20[0] != v21 )
      operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_32:
    if ( (_WORD *)v18[0] != v19 )
      operator delete(v18[0], (const struct std::nothrow_t *)&std::nothrow);
    v8 = v15;
    if ( v15 == v17 )
      return 2147942414LL;
    goto LABEL_35;
  }
  LODWORD(v27) = 0;
  v22[0] = v23;
  v23[0] = 0;
  v22[1] = v23;
  v14 = Csl::ExecuteCommandLine((__int64)v18, (__int64)&v27, (__int64)v22);
  v6 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26B,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v14);
    goto LABEL_39;
  }
  if ( (_DWORD)v27 )
  {
    v6 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x273,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
           (const char *)(unsigned int)v27,
           (unsigned int)"bcdedit.exe command line: %ws \noutput: %hs",
           v18[0],
           v22[0]);
LABEL_39:
    if ( v22[0] != v23 )
      operator delete(v22[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v20[0] != v21 )
      operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( (_WORD *)v18[0] != v19 )
      operator delete(v18[0], (const struct std::nothrow_t *)&std::nothrow);
    v7 = v15;
    if ( v15 == v17 )
      return v6;
    goto LABEL_5;
  }
  if ( v22[0] != v23 )
    operator delete(v22[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v20[0] != v21 )
    operator delete(v20[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (_WORD *)v18[0] != v19 )
    operator delete(v18[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v15 != v17 )
    operator delete(v15, (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x140017868  mov     [rsp-8+arg_0], rbx
0x14001786d  mov     [rsp-8+arg_10], rsi
0x140017872  push    rbp
0x140017873  push    rdi
0x140017874  push    r14
0x140017876  lea     rbp, [rsp-47h]
0x14001787b  sub     rsp, 0D0h
0x140017882  cmp     dword ptr [rdx], 1
0x140017885  mov     rbx, rdx
0x140017888  mov     rsi, rcx
0x14001788b  jz      short loc_1400178AD
0x14001788d  mov     rcx, [rbp+5Fh]; this
0x140017891  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140017898  mov     r9d, 32h ; '2'; char *
0x14001789e  mov     edx, 27Dh; void *
0x1400178a3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400178a8  jmp     loc_140017C67
0x1400178ad  lea     rax, [rbp+57h+var_90]
0x1400178b1  xor     r14d, r14d
0x1400178b4  mov     [rbp+57h+var_A0], rax
0x1400178b8  lea     rcx, [rbp+57h+var_A0]; this
0x1400178bc  lea     rax, [rbp+57h+var_90]
0x1400178c0  mov     [rbp+57h+var_90], r14w
0x1400178c5  mov     [rbp+57h+var_98], rax
0x1400178c9  call    ?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDirectoryPath(Csl::Path &)
0x1400178ce  mov     edi, eax
0x1400178d0  test    eax, eax
0x1400178d2  jns     short loc_14001790C
0x1400178d4  mov     rcx, [rbp+5Fh]; this
0x1400178d8  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400178df  mov     r9d, eax; char *
0x1400178e2  mov     edx, 24Eh; void *
0x1400178e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400178ec  mov     rcx, [rbp+57h+var_A0]; void *
0x1400178f0  lea     rax, [rbp+57h+var_90]
0x1400178f4  cmp     rcx, rax
0x1400178f7  jz      short loc_140017905
0x1400178f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140017900  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017905  mov     eax, edi
0x140017907  jmp     loc_140017C67
0x14001790c  lea     rax, aBcdeditExe; "bcdedit.exe"
0x140017913  mov     [rbp+57h+var_18], 0Bh
0x14001791b  lea     rdx, [rbp+57h+var_20]
0x14001791f  mov     [rbp+57h+var_20], rax
0x140017923  lea     rcx, [rbp+57h+var_A0]; this
0x140017927  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001792c  test    al, al
0x14001792e  jnz     short loc_140017968
0x140017930  mov     rcx, [rbp+5Fh]; this
0x140017934  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001793b  mov     r9d, 8007000Eh; char *
0x140017941  mov     edx, 24Fh; void *
0x140017946  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001794b  mov     rcx, [rbp+57h+var_A0]
0x14001794f  lea     rax, [rbp+57h+var_90]
0x140017953  cmp     rcx, rax
0x140017956  jz      loc_140017B11
0x14001795c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140017963  jmp     loc_140017B0C
0x140017968  mov     r8, [rbp+57h+var_98]
0x14001796c  lea     rax, [rbp+57h+var_70]
0x140017970  mov     rdx, [rbp+57h+var_A0]
0x140017974  lea     rcx, [rbp+57h+var_80]
0x140017978  mov     [rbp+57h+var_80], rax
0x14001797c  sub     r8, rdx
0x14001797f  lea     rax, [rbp+57h+var_70]
0x140017983  sar     r8, 1
0x140017986  mov     [rbp+57h+var_78], rax
0x14001798a  mov     [rbp+57h+var_70], r14w
0x14001798f  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140017994  test    al, al
0x140017996  jnz     short loc_1400179BF
0x140017998  mov     edx, 252h; void *
0x14001799d  mov     rcx, [rbp+5Fh]; this
0x1400179a1  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x1400179a8  mov     r9d, 8007000Eh; char *
0x1400179ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400179b3  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x1400179ba  jmp     loc_140017AE7
0x1400179bf  mov     r8d, 8
0x1400179c5  lea     rdx, aStore; " /store "
0x1400179cc  lea     rcx, [rbp+57h+var_80]
0x1400179d0  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1400179d5  test    al, al
0x1400179d7  jnz     short loc_1400179E0
0x1400179d9  mov     edx, 253h
0x1400179de  jmp     short loc_14001799D
0x1400179e0  mov     r8, [rsi+8]
0x1400179e4  lea     rax, [rbp+57h+var_50]
0x1400179e8  sub     r8, [rsi]
0x1400179eb  lea     rcx, [rbp+57h+var_60]
0x1400179ef  mov     rdx, [rsi]
0x1400179f2  mov     [rbp+57h+var_60], rax
0x1400179f6  lea     rax, [rbp+57h+var_50]
0x1400179fa  sar     r8, 1
0x1400179fd  mov     [rbp+57h+var_58], rax
0x140017a01  mov     [rbp+57h+var_50], r14w
0x140017a06  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140017a0b  test    al, al
0x140017a0d  jnz     short loc_140017A19
0x140017a0f  mov     edx, 25Bh
0x140017a14  jmp     loc_140017AB5
0x140017a19  lea     rax, aEfiMicrosoftBo; "EFI\\Microsoft\\Boot\\BCD"
0x140017a20  mov     [rbp+57h+var_18], 16h
0x140017a28  lea     rdx, [rbp+57h+var_20]
0x140017a2c  mov     [rbp+57h+var_20], rax
0x140017a30  lea     rcx, [rbp+57h+var_60]; this
0x140017a34  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140017a39  test    al, al
0x140017a3b  jnz     short loc_140017A44
0x140017a3d  mov     edx, 25Ch
0x140017a42  jmp     short loc_140017AB5
0x140017a44  mov     rdx, [rbp+57h+var_60]
0x140017a48  test    rdx, rdx
0x140017a4b  jz      short loc_140017A5D
0x140017a4d  or      r8, 0FFFFFFFFFFFFFFFFh
0x140017a51  inc     r8
0x140017a54  cmp     [rdx+r8*2], r14w
0x140017a59  jnz     short loc_140017A51
0x140017a5b  jmp     short loc_140017A60
0x140017a5d  mov     r8, r14
0x140017a60  lea     rcx, [rbp+57h+var_80]
0x140017a64  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140017a69  test    al, al
0x140017a6b  jnz     short loc_140017A74
0x140017a6d  mov     edx, 25Eh
0x140017a72  jmp     short loc_140017AB5
0x140017a74  mov     r8d, 1
0x140017a7a  lea     rdx, asc_1400377D0; " "
0x140017a81  lea     rcx, [rbp+57h+var_80]
0x140017a85  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140017a8a  test    al, al
0x140017a8c  jnz     short loc_140017A95
0x140017a8e  mov     edx, 260h
0x140017a93  jmp     short loc_140017AB5
0x140017a95  mov     rdx, [rbx+8]
0x140017a99  lea     rcx, [rbp+57h+var_80]
0x140017a9d  mov     r8, [rbx+10h]
0x140017aa1  sub     r8, rdx
0x140017aa4  sar     r8, 1
0x140017aa7  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140017aac  test    al, al
0x140017aae  jnz     short loc_140017B1B
0x140017ab0  mov     edx, 261h; void *
0x140017ab5  mov     rcx, [rbp+5Fh]; this
0x140017ab9  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140017ac0  mov     r9d, 8007000Eh; char *
0x140017ac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017acb  mov     rcx, [rbp+57h+var_60]; void *
0x140017acf  lea     rax, [rbp+57h+var_50]
0x140017ad3  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140017ada  cmp     rcx, rax
0x140017add  jz      short loc_140017AE7
0x140017adf  mov     rdx, rbx; struct std::nothrow_t *
0x140017ae2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017ae7  mov     rcx, [rbp+57h+var_80]; void *
0x140017aeb  lea     rax, [rbp+57h+var_70]
0x140017aef  cmp     rcx, rax
0x140017af2  jz      short loc_140017AFC
0x140017af4  mov     rdx, rbx; struct std::nothrow_t *
0x140017af7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017afc  mov     rcx, [rbp+57h+var_A0]; void *
0x140017b00  lea     rax, [rbp+57h+var_90]
0x140017b04  cmp     rcx, rax
0x140017b07  jz      short loc_140017B11
0x140017b09  mov     rdx, rbx; struct std::nothrow_t *
0x140017b0c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017b11  mov     eax, 8007000Eh
0x140017b16  jmp     loc_140017C67
0x140017b1b  lea     rax, [rbp+57h+var_30]
0x140017b1f  mov     dword ptr [rbp+57h+arg_8], r14d
0x140017b23  mov     [rbp+57h+var_40], rax
0x140017b27  lea     r8, [rbp+57h+var_40]
0x140017b2b  lea     rax, [rbp+57h+var_30]
0x140017b2f  mov     [rbp+57h+var_30], r14b
0x140017b33  mov     r9d, 7530h
0x140017b39  mov     [rbp+57h+var_38], rax
0x140017b3d  lea     rdx, [rbp+57h+arg_8]
0x140017b41  lea     rcx, [rbp+57h+var_80]
0x140017b45  call    ?ExecuteCommandLine@Csl@@YAJAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAKAEAV?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@3@K@Z; Csl::ExecuteCommandLine(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &,ulong &,utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>> &,ulong)
0x140017b4a  mov     edi, eax
0x140017b4c  test    eax, eax
0x140017b4e  jns     short loc_140017BC7
0x140017b50  mov     rcx, [rbp+5Fh]; this
0x140017b54  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140017b5b  mov     r9d, eax; char *
0x140017b5e  mov     edx, 26Bh; void *
0x140017b63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140017b68  mov     rcx, [rbp+57h+var_40]; void *
0x140017b6c  lea     rax, [rbp+57h+var_30]
0x140017b70  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140017b77  cmp     rcx, rax
0x140017b7a  jz      short loc_140017B84
0x140017b7c  mov     rdx, rbx; struct std::nothrow_t *
0x140017b7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017b84  mov     rcx, [rbp+57h+var_60]; void *
0x140017b88  lea     rax, [rbp+57h+var_50]
0x140017b8c  cmp     rcx, rax
0x140017b8f  jz      short loc_140017B99
0x140017b91  mov     rdx, rbx; struct std::nothrow_t *
0x140017b94  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017b99  mov     rcx, [rbp+57h+var_80]; void *
0x140017b9d  lea     rax, [rbp+57h+var_70]
0x140017ba1  cmp     rcx, rax
0x140017ba4  jz      short loc_140017BAE
0x140017ba6  mov     rdx, rbx; struct std::nothrow_t *
0x140017ba9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017bae  mov     rcx, [rbp+57h+var_A0]
0x140017bb2  lea     rax, [rbp+57h+var_90]
0x140017bb6  cmp     rcx, rax
0x140017bb9  jz      loc_140017905
0x140017bbf  mov     rdx, rbx
0x140017bc2  jmp     loc_140017900
0x140017bc7  mov     r9d, dword ptr [rbp+57h+arg_8]; char *
0x140017bcb  test    r9d, r9d
0x140017bce  jz      short loc_140017C0A
0x140017bd0  mov     rax, [rbp+57h+var_40]
0x140017bd4  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140017bdb  mov     rdx, [rbp+57h+var_80]
0x140017bdf  mov     rcx, [rbp+5Fh]; this
0x140017be3  mov     [rsp+0E0h+var_B0], rax
0x140017be8  lea     rax, aBcdeditExeComm; "bcdedit.exe command line: %ws \noutput:"...
0x140017bef  mov     [rsp+0E0h+var_B8], rdx; char *
0x140017bf4  mov     edx, 273h; void *
0x140017bf9  mov     qword ptr [rsp+0E0h+var_C0], rax; unsigned int
0x140017bfe  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x140017c03  mov     edi, eax
0x140017c05  jmp     loc_140017B68
0x140017c0a  mov     rcx, [rbp+57h+var_40]; void *
0x140017c0e  lea     rax, [rbp+57h+var_30]
0x140017c12  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140017c19  cmp     rcx, rax
0x140017c1c  jz      short loc_140017C26
0x140017c1e  mov     rdx, rbx; struct std::nothrow_t *
0x140017c21  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017c26  mov     rcx, [rbp+57h+var_60]; void *
0x140017c2a  lea     rax, [rbp+57h+var_50]
0x140017c2e  cmp     rcx, rax
0x140017c31  jz      short loc_140017C3B
0x140017c33  mov     rdx, rbx; struct std::nothrow_t *
0x140017c36  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017c3b  mov     rcx, [rbp+57h+var_80]; void *
0x140017c3f  lea     rax, [rbp+57h+var_70]
0x140017c43  cmp     rcx, rax
0x140017c46  jz      short loc_140017C50
0x140017c48  mov     rdx, rbx; struct std::nothrow_t *
0x140017c4b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017c50  mov     rcx, [rbp+57h+var_A0]; void *
0x140017c54  lea     rax, [rbp+57h+var_90]
0x140017c58  cmp     rcx, rax
0x140017c5b  jz      short loc_140017C65
0x140017c5d  mov     rdx, rbx; struct std::nothrow_t *
0x140017c60  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140017c65  xor     eax, eax
0x140017c67  lea     r11, [rsp+0E0h+var_10]
0x140017c6f  mov     rbx, [r11+20h]
0x140017c73  mov     rsi, [r11+30h]
0x140017c77  mov     rsp, r11
0x140017c7a  pop     r14
0x140017c7c  pop     rdi
0x140017c7d  pop     rbp
0x140017c7e  retn
```
