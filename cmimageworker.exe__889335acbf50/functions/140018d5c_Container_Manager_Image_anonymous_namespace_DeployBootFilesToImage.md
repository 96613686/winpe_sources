# Container::Manager::Image::_anonymous_namespace_::DeployBootFilesToImage

- ea: `0x140018d5c`
- end: `0x1400194ca`
- name: `Container::Manager::Image::_anonymous_namespace_::DeployBootFilesToImage`
- size: `1902`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x140016da0`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140008f90`
- `0x14000a9b8`
- `0x14000aca8`
- `0x14000bebc`
- `0x14000c064`
- `0x14000c18c`
- `0x14000c70c`
- `0x14000cbb8`
- `0x14000cd84`
- `0x14000d1d4`
- `0x14000d81c`
- `0x140018d5c`

## import_xrefs

- `ntdll!RtlDoesFileExists_U` at `0x140018e20`
- `ntdll!RtlDoesFileExists_U` at `0x140018e20`

## string_xrefs

- `0x1400193e2`: `bcdboot.exe command line: %ws \noutput: %hs`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::DeployBootFilesToImage(const void **a1)
{
  __int64 v1; // r8
  const void *v3; // rdx
  __int64 v4; // rdx
  WCHAR *v5; // rcx
  const struct Path *v6; // rdx
  int v7; // eax
  unsigned int v8; // edi
  WCHAR *v9; // rcx
  int SystemDrivePath; // eax
  struct Path *v12; // rdx
  int WindowsDirectoryPath; // eax
  struct Path *v14; // rdx
  int SystemDirectoryPath; // eax
  _BYTE *v16; // rcx
  __int64 v17; // rbx
  const wchar_t *v18; // rax
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // esi
  __int64 v22; // r14
  unsigned __int64 v23; // rdi
  __int64 v24; // rcx
  const wchar_t *v25; // rax
  __int64 v26; // rcx
  unsigned __int64 v27; // r8
  __int64 v28; // rdx
  __int64 v29; // r8
  _WORD *v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r8
  int v33; // eax
  PCWSTR FileName[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v35[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  _WORD v37[8]; // [rsp+70h] [rbp-90h] BYREF
  void *v38[2]; // [rsp+80h] [rbp-80h] BYREF
  _WORD v39[8]; // [rsp+90h] [rbp-70h] BYREF
  char *v40[2]; // [rsp+A0h] [rbp-60h] BYREF
  _WORD v41[8]; // [rsp+B0h] [rbp-50h] BYREF
  void *v42[2]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v43[8]; // [rsp+D0h] [rbp-30h] BYREF
  void *v44[2]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v45[8]; // [rsp+F0h] [rbp-10h] BYREF
  __m128i si128; // [rsp+100h] [rbp+0h] BYREF
  __int64 v47; // [rsp+110h] [rbp+10h]
  const wchar_t *v48; // [rsp+118h] [rbp+18h] BYREF
  __int64 v49; // [rsp+120h] [rbp+20h]
  void *v50[2]; // [rsp+128h] [rbp+28h] BYREF
  _BYTE v51[24]; // [rsp+138h] [rbp+38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  char *v53; // [rsp+180h] [rbp+80h] BYREF

  v1 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v3 = *a1;
  FileName[0] = v35;
  FileName[1] = v35;
  v35[0] = 0;
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)FileName,
          v3,
          v1 >> 1) )
  {
    v4 = 1017;
    goto LABEL_3;
  }
  v49 = 3;
  v48 = L"EFI";
  if ( !Csl::Path::Append((Csl::Path *)FileName, &v48) )
  {
    v4 = 1018;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    v5 = (WCHAR *)FileName[0];
    if ( FileName[0] == v35 )
      return 2147942414LL;
LABEL_89:
    operator delete(v5, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  if ( RtlDoesFileExists_U(FileName[0]) )
  {
    v7 = Csl::DeletePath(FileName, v6);
    v8 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3FE,
        (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)(unsigned int)v7);
      v9 = (WCHAR *)FileName[0];
      if ( FileName[0] == v35 )
        return v8;
LABEL_10:
      operator delete(v9, (const struct std::nothrow_t *)&std::nothrow);
      return v8;
    }
  }
  v37[0] = 0;
  v36[0] = v37;
  v36[1] = v37;
  SystemDrivePath = Csl::GetSystemDrivePath((Csl *)v36, v6);
  v8 = SystemDrivePath;
  if ( SystemDrivePath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x403,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)SystemDrivePath);
    goto LABEL_14;
  }
  v39[0] = 0;
  v38[0] = v39;
  v38[1] = v39;
  WindowsDirectoryPath = Csl::GetWindowsDirectoryPath((Csl *)v38, v12);
  v8 = WindowsDirectoryPath;
  if ( WindowsDirectoryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x407,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)WindowsDirectoryPath);
LABEL_20:
    if ( v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_14:
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    v9 = (WCHAR *)FileName[0];
    if ( FileName[0] == v35 )
      return v8;
    goto LABEL_10;
  }
  v43[0] = 0;
  v42[0] = v43;
  v42[1] = v43;
  SystemDirectoryPath = Csl::GetSystemDirectoryPath((Csl *)v42, v14);
  v8 = SystemDirectoryPath;
  if ( SystemDirectoryPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40B,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)SystemDirectoryPath);
LABEL_24:
    if ( v42[0] != v43 )
      operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_20;
  }
  v49 = 11;
  v48 = L"bcdboot.exe";
  if ( !Csl::Path::Append((Csl::Path *)v42, &v48) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x40C,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    goto LABEL_82;
  }
  v16 = a1[1];
  v44[0] = v45;
  v17 = -1;
  v45[0] = 0;
  v44[1] = v45;
  v18 = (const wchar_t *)*a1;
  v19 = v16 - (_BYTE *)*a1;
  v47 = -1;
  v49 = v19 >> 1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v48 = v18;
  if ( !(unsigned __int8)Csl::StringSplit(&v48, 92, &si128) )
  {
    v20 = 1047;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
LABEL_80:
    if ( v44[0] != v45 )
      operator delete(v44[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_82:
    if ( v42[0] != v43 )
      operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    v5 = (WCHAR *)FileName[0];
    if ( FileName[0] == v35 )
      return 2147942414LL;
    goto LABEL_89;
  }
  v21 = 1;
  v22 = si128.m128i_i64[0];
  v23 = (si128.m128i_i64[1] - si128.m128i_i64[0]) >> 5;
  if ( v23 > 1 )
  {
    while ( 1 )
    {
      v24 = 32LL * v21;
      v25 = *(const wchar_t **)(v24 + v22);
      v26 = *(_QWORD *)(v24 + v22 + 8) - (_QWORD)v25;
      v48 = v25;
      v49 = v26 >> 1;
      if ( !Csl::Path::Append((Csl::Path *)v44, &v48) )
        break;
      if ( ++v21 >= v23 )
        goto LABEL_34;
    }
    v20 = 1051;
    goto LABEL_30;
  }
LABEL_34:
  v40[0] = (char *)v41;
  v40[1] = (char *)v41;
  v41[0] = 0;
  if ( v42[0] )
  {
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)v42[0] + v27) );
  }
  else
  {
    v27 = 0;
  }
  if ( !utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
          (__int64)v40,
          v42[0],
          v27) )
  {
    v28 = 1058;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL);
    if ( (_WORD *)v40[0] != v41 )
      operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
    goto LABEL_80;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           L" ",
                           1) )
  {
    v28 = 1059;
    goto LABEL_77;
  }
  if ( v38[0] )
  {
    v29 = -1;
    do
      ++v29;
    while ( *((_WORD *)v38[0] + v29) );
  }
  else
  {
    v29 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           v38[0],
                           v29) )
  {
    v28 = 1060;
    goto LABEL_77;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           L" /imageRoot ",
                           12) )
  {
    v28 = 1061;
    goto LABEL_77;
  }
  v30 = *a1;
  if ( *a1 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v30[v31] );
  }
  else
  {
    v31 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           v30,
                           v31) )
  {
    v28 = 1062;
    goto LABEL_77;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           L" /s ",
                           4) )
  {
    v28 = 1063;
    goto LABEL_77;
  }
  if ( v36[0] )
  {
    v32 = -1;
    do
      ++v32;
    while ( *((_WORD *)v36[0] + v32) );
  }
  else
  {
    v32 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           v36[0],
                           v32) )
  {
    v28 = 1064;
    goto LABEL_77;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           L" /f UEFI /t ",
                           12) )
  {
    v28 = 1065;
    goto LABEL_77;
  }
  if ( v44[0] )
  {
    do
      ++v17;
    while ( *((_WORD *)v44[0] + v17) );
  }
  else
  {
    v17 = 0;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           v40,
                           v44[0],
                           v17) )
  {
    v28 = 1066;
    goto LABEL_77;
  }
  LODWORD(v53) = 0;
  v50[0] = v51;
  v51[0] = 0;
  v50[1] = v51;
  v33 = Csl::ExecuteCommandLine((__int64)v40, (__int64)&v53, (__int64)v50);
  v8 = v33;
  if ( v33 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x430,
      (int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v33);
LABEL_93:
    if ( v50[0] != v51 )
      operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( (_WORD *)v40[0] != v41 )
      operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
    if ( v44[0] != v45 )
      operator delete(v44[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_24;
  }
  if ( (_DWORD)v53 )
  {
    v8 = wil::details::in1diag3::Return_Win32Msg(
           retaddr,
           (void *)0x438,
           (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
           (const char *)(unsigned int)v53,
           (unsigned int)"bcdboot.exe command line: %ws \noutput: %hs",
           v40[0],
           v50[0]);
    goto LABEL_93;
  }
  if ( v50[0] != v51 )
    operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( (_WORD *)v40[0] != v41 )
    operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit((__int64)&si128);
  if ( v44[0] != v45 )
    operator delete(v44[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v42[0] != v43 )
    operator delete(v42[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v38[0] != v39 )
    operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( FileName[0] != v35 )
    operator delete((void *)FileName[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x140018d5c  mov     [rsp-8+arg_8], rbx
0x140018d61  mov     [rsp-8+arg_10], rsi
0x140018d66  push    rbp
0x140018d67  push    rdi
0x140018d68  push    r12
0x140018d6a  push    r14
0x140018d6c  push    r15
0x140018d6e  lea     rbp, [rsp-50h]
0x140018d73  sub     rsp, 150h
0x140018d7a  mov     r8, [rcx+8]
0x140018d7e  lea     rax, [rsp+170h+var_120]
0x140018d83  sub     r8, [rcx]
0x140018d86  mov     r15, rcx
0x140018d89  mov     rdx, [rcx]
0x140018d8c  xor     r12d, r12d
0x140018d8f  mov     [rsp+170h+FileName], rax
0x140018d94  lea     rcx, [rsp+170h+FileName]
0x140018d99  lea     rax, [rsp+170h+var_120]
0x140018d9e  sar     r8, 1
0x140018da1  mov     [rsp+170h+var_128], rax
0x140018da6  mov     [rsp+170h+var_120], r12w
0x140018dac  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140018db1  test    al, al
0x140018db3  jnz     short loc_140018DEF
0x140018db5  mov     edx, 3F9h; void *
0x140018dba  mov     rcx, [rbp+78h]; this
0x140018dbe  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018dc5  mov     r9d, 8007000Eh; char *
0x140018dcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018dd0  mov     rcx, [rsp+170h+FileName]
0x140018dd5  lea     rax, [rsp+170h+var_120]
0x140018dda  cmp     rcx, rax
0x140018ddd  jz      loc_140019309
0x140018de3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140018dea  jmp     loc_140019304
0x140018def  lea     rax, aEfi; "EFI"
0x140018df6  mov     [rbp+70h+var_50], 3
0x140018dfe  lea     rdx, [rbp+70h+var_58]
0x140018e02  mov     [rbp+70h+var_58], rax
0x140018e06  lea     rcx, [rsp+170h+FileName]; this
0x140018e0b  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140018e10  test    al, al
0x140018e12  jnz     short loc_140018E1B
0x140018e14  mov     edx, 3FAh
0x140018e19  jmp     short loc_140018DBA
0x140018e1b  mov     rcx, [rsp+170h+FileName]; FileName
0x140018e20  call    cs:__imp_RtlDoesFileExists_U
0x140018e27  nop     dword ptr [rax+rax+00h]
0x140018e2c  test    al, al
0x140018e2e  jz      short loc_140018E7A
0x140018e30  lea     rcx, [rsp+170h+FileName]; this
0x140018e35  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x140018e3a  mov     edi, eax
0x140018e3c  test    eax, eax
0x140018e3e  jns     short loc_140018E7A
0x140018e40  mov     rcx, [rbp+78h]; this
0x140018e44  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018e4b  mov     r9d, eax; char *
0x140018e4e  mov     edx, 3FEh; void *
0x140018e53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018e58  mov     rcx, [rsp+170h+FileName]; void *
0x140018e5d  lea     rax, [rsp+170h+var_120]
0x140018e62  cmp     rcx, rax
0x140018e65  jz      short loc_140018E73
0x140018e67  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140018e6e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018e73  mov     eax, edi
0x140018e75  jmp     loc_1400194AD
0x140018e7a  lea     rax, [rsp+170h+var_100]
0x140018e7f  mov     [rsp+170h+var_100], r12w
0x140018e85  mov     [rsp+170h+var_110], rax
0x140018e8a  lea     rcx, [rsp+170h+var_110]; this
0x140018e8f  lea     rax, [rsp+170h+var_100]
0x140018e94  mov     [rsp+170h+var_108], rax
0x140018e99  call    ?GetSystemDrivePath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDrivePath(Csl::Path &)
0x140018e9e  mov     edi, eax
0x140018ea0  test    eax, eax
0x140018ea2  jns     short loc_140018EEE
0x140018ea4  mov     rcx, [rbp+78h]; this
0x140018ea8  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018eaf  mov     r9d, eax; char *
0x140018eb2  mov     edx, 403h; void *
0x140018eb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018ebc  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140018ec3  mov     rcx, [rsp+170h+var_110]; void *
0x140018ec8  lea     rax, [rsp+170h+var_100]
0x140018ecd  cmp     rcx, rax
0x140018ed0  jz      short loc_140018EDA
0x140018ed2  mov     rdx, rbx; struct std::nothrow_t *
0x140018ed5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018eda  mov     rcx, [rsp+170h+FileName]
0x140018edf  lea     rax, [rsp+170h+var_120]
0x140018ee4  cmp     rcx, rax
0x140018ee7  jz      short loc_140018E73
0x140018ee9  mov     rdx, rbx
0x140018eec  jmp     short loc_140018E6E
0x140018eee  lea     rax, [rbp+70h+var_E0]
0x140018ef2  mov     [rbp+70h+var_E0], r12w
0x140018ef7  mov     [rbp+70h+var_F0], rax
0x140018efb  lea     rcx, [rbp+70h+var_F0]; this
0x140018eff  lea     rax, [rbp+70h+var_E0]
0x140018f03  mov     [rbp+70h+var_E8], rax
0x140018f07  call    ?GetWindowsDirectoryPath@Csl@@YAJAEAVPath@1@@Z; Csl::GetWindowsDirectoryPath(Csl::Path &)
0x140018f0c  mov     edi, eax
0x140018f0e  test    eax, eax
0x140018f10  jns     short loc_140018F4B
0x140018f12  mov     rcx, [rbp+78h]; this
0x140018f16  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018f1d  mov     r9d, eax; char *
0x140018f20  mov     edx, 407h; void *
0x140018f25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018f2a  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140018f31  mov     rcx, [rbp+70h+var_F0]; void *
0x140018f35  lea     rax, [rbp+70h+var_E0]
0x140018f39  cmp     rcx, rax
0x140018f3c  jz      short loc_140018EC3
0x140018f3e  mov     rdx, rbx; struct std::nothrow_t *
0x140018f41  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018f46  jmp     loc_140018EC3
0x140018f4b  lea     rax, [rbp+70h+var_A0]
0x140018f4f  mov     [rbp+70h+var_A0], r12w
0x140018f54  mov     [rbp+70h+var_B0], rax
0x140018f58  lea     rcx, [rbp+70h+var_B0]; this
0x140018f5c  lea     rax, [rbp+70h+var_A0]
0x140018f60  mov     [rbp+70h+var_A8], rax
0x140018f64  call    ?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z; Csl::GetSystemDirectoryPath(Csl::Path &)
0x140018f69  mov     edi, eax
0x140018f6b  test    eax, eax
0x140018f6d  jns     short loc_140018FA5
0x140018f6f  mov     rcx, [rbp+78h]; this
0x140018f73  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018f7a  mov     r9d, eax; char *
0x140018f7d  mov     edx, 40Bh; void *
0x140018f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018f87  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140018f8e  mov     rcx, [rbp+70h+var_B0]; void *
0x140018f92  lea     rax, [rbp+70h+var_A0]
0x140018f96  cmp     rcx, rax
0x140018f99  jz      short loc_140018F31
0x140018f9b  mov     rdx, rbx; struct std::nothrow_t *
0x140018f9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140018fa3  jmp     short loc_140018F31
0x140018fa5  lea     rax, aBcdbootExe; "bcdboot.exe"
0x140018fac  mov     [rbp+70h+var_50], 0Bh
0x140018fb4  lea     rdx, [rbp+70h+var_58]
0x140018fb8  mov     [rbp+70h+var_58], rax
0x140018fbc  lea     rcx, [rbp+70h+var_B0]; this
0x140018fc0  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x140018fc5  test    al, al
0x140018fc7  jnz     short loc_140018FF0
0x140018fc9  mov     rcx, [rbp+78h]; this
0x140018fcd  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140018fd4  mov     r9d, 8007000Eh; char *
0x140018fda  mov     edx, 40Ch; void *
0x140018fdf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140018fe4  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x140018feb  jmp     loc_1400192B1
0x140018ff0  mov     rcx, [r15+8]
0x140018ff4  lea     rax, [rbp+70h+var_80]
0x140018ff8  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140019000  lea     r8, [rbp+70h+var_70]
0x140019004  mov     [rbp+70h+var_90], rax
0x140019008  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14001900c  lea     rax, [rbp+70h+var_80]
0x140019010  mov     [rbp+70h+var_80], r12w
0x140019015  mov     [rbp+70h+var_88], rax
0x140019019  mov     rax, [r15]
0x14001901c  sub     rcx, rax
0x14001901f  mov     [rbp+70h+var_60], rbx
0x140019023  sar     rcx, 1
0x140019026  lea     edx, [rbx+5Dh]
0x140019029  mov     [rbp+70h+var_50], rcx
0x14001902d  lea     rcx, [rbp+70h+var_58]
0x140019031  movdqu  [rbp+70h+var_70], xmm0
0x140019036  mov     [rbp+70h+var_58], rax
0x14001903a  call    ?StringSplit@Csl@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@GAEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@3@@Z; Csl::StringSplit(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &,ushort,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x14001903f  test    al, al
0x140019041  jnz     short loc_140019073
0x140019043  mov     edx, 417h; void *
0x140019048  mov     rcx, [rbp+78h]; this
0x14001904c  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x140019053  mov     r9d, 8007000Eh; char *
0x140019059  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001905e  lea     rcx, [rbp+70h+var_70]
0x140019062  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x140019067  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001906e  jmp     loc_14001929C
0x140019073  mov     rdi, qword ptr [rbp+70h+var_70+8]
0x140019077  mov     esi, 1
0x14001907c  mov     r14, qword ptr [rbp+70h+var_70]
0x140019080  sub     rdi, r14
0x140019083  sar     rdi, 5
0x140019087  cmp     rdi, rsi
0x14001908a  jbe     short loc_1400190C3
0x14001908c  mov     ecx, esi
0x14001908e  lea     rdx, [rbp+70h+var_58]
0x140019092  shl     rcx, 5
0x140019096  mov     rax, [rcx+r14]
0x14001909a  mov     rcx, [rcx+r14+8]
0x14001909f  sub     rcx, rax
0x1400190a2  mov     [rbp+70h+var_58], rax
0x1400190a6  sar     rcx, 1
0x1400190a9  mov     [rbp+70h+var_50], rcx
0x1400190ad  lea     rcx, [rbp+70h+var_90]; this
0x1400190b1  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1400190b6  test    al, al
0x1400190b8  jz      short loc_1400190F0
0x1400190ba  inc     esi
0x1400190bc  mov     eax, esi
0x1400190be  cmp     rax, rdi
0x1400190c1  jb      short loc_14001908C
0x1400190c3  mov     rdx, [rbp+70h+var_B0]
0x1400190c7  lea     rax, [rbp+70h+var_C0]
0x1400190cb  mov     [rbp+70h+var_D0], rax
0x1400190cf  lea     rax, [rbp+70h+var_C0]
0x1400190d3  mov     [rbp+70h+var_C8], rax
0x1400190d7  mov     [rbp+70h+var_C0], r12w
0x1400190dc  test    rdx, rdx
0x1400190df  jz      short loc_1400190FA
0x1400190e1  mov     r8, rbx
0x1400190e4  inc     r8
0x1400190e7  cmp     [rdx+r8*2], r12w
0x1400190ec  jnz     short loc_1400190E4
0x1400190ee  jmp     short loc_1400190FD
0x1400190f0  mov     edx, 41Bh
0x1400190f5  jmp     loc_140019048
0x1400190fa  mov     r8, r12
0x1400190fd  lea     rcx, [rbp+70h+var_D0]
0x140019101  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x140019106  test    al, al
0x140019108  jnz     short loc_140019114
0x14001910a  mov     edx, 422h
0x14001910f  jmp     loc_140019261
0x140019114  mov     r8d, 1
0x14001911a  lea     rdx, asc_1400377D0; " "
0x140019121  lea     rcx, [rbp+70h+var_D0]
0x140019125  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14001912a  test    al, al
0x14001912c  jnz     short loc_140019138
0x14001912e  mov     edx, 423h
0x140019133  jmp     loc_140019261
0x140019138  mov     rdx, [rbp+70h+var_F0]
0x14001913c  test    rdx, rdx
0x14001913f  jz      short loc_140019150
0x140019141  mov     r8, rbx
0x140019144  inc     r8
0x140019147  cmp     [rdx+r8*2], r12w
0x14001914c  jnz     short loc_140019144
0x14001914e  jmp     short loc_140019153
0x140019150  mov     r8, r12
0x140019153  lea     rcx, [rbp+70h+var_D0]
0x140019157  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x14001915c  test    al, al
0x14001915e  jnz     short loc_14001916A
0x140019160  mov     edx, 424h
0x140019165  jmp     loc_140019261
0x14001916a  mov     edi, 0Ch
0x14001916f  lea     rdx, aImageroot_0; " /imageRoot "
0x140019176  mov     r8d, edi
0x140019179  lea     rcx, [rbp+70h+var_D0]
0x14001917d  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140019182  test    al, al
0x140019184  jnz     short loc_140019190
0x140019186  mov     edx, 425h
0x14001918b  jmp     loc_140019261
0x140019190  mov     rdx, [r15]
0x140019193  test    rdx, rdx
0x140019196  jz      short loc_1400191A7
0x140019198  mov     r8, rbx
0x14001919b  inc     r8
0x14001919e  cmp     [rdx+r8*2], r12w
0x1400191a3  jnz     short loc_14001919B
0x1400191a5  jmp     short loc_1400191AA
0x1400191a7  mov     r8, r12
0x1400191aa  lea     rcx, [rbp+70h+var_D0]
0x1400191ae  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1400191b3  test    al, al
0x1400191b5  jnz     short loc_1400191C1
0x1400191b7  mov     edx, 426h
0x1400191bc  jmp     loc_140019261
0x1400191c1  mov     r8d, 4
0x1400191c7  lea     rdx, aS; " /s "
0x1400191ce  lea     rcx, [rbp+70h+var_D0]
0x1400191d2  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x1400191d7  test    al, al
0x1400191d9  jnz     short loc_1400191E2
0x1400191db  mov     edx, 427h
0x1400191e0  jmp     short loc_140019261
0x1400191e2  mov     rdx, [rsp+170h+var_110]
0x1400191e7  test    rdx, rdx
0x1400191ea  jz      short loc_1400191FB
0x1400191ec  mov     r8, rbx
0x1400191ef  inc     r8
0x1400191f2  cmp     [rdx+r8*2], r12w
0x1400191f7  jnz     short loc_1400191EF
0x1400191f9  jmp     short loc_1400191FE
0x1400191fb  mov     r8, r12
0x1400191fe  lea     rcx, [rbp+70h+var_D0]
0x140019202  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x140019207  test    al, al
  ... truncated ...
```
