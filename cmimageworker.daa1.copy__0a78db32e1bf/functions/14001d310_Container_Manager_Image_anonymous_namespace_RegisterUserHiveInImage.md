# Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage

- ea: `0x14001d310`
- end: `0x14001d8da`
- name: `Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage`
- size: `1482`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140018184`

## callees

- `0x140002344`
- `0x140002b2c`
- `0x140006fe4`
- `0x14000a9b8`
- `0x14000aa58`
- `0x14000aca8`
- `0x14000cd84`
- `0x14000ce58`
- `0x14001adb0`
- `0x14001d310`
- `0x140021914`
- `0x140021a0c`
- `0x1400228fc`
- `0x140022d64`
- `0x14002e8cc`

## string_xrefs

- `0x14001d395`: `Windows\System32\config\SOFTWARE`
- `0x14001d5cf`: `ProfileImagePath`

## pseudocode

```c
__int64 __fastcall Container::Manager::Image::_anonymous_namespace_::RegisterUserHiveInImage(
        __int64 *a1,
        unsigned __int8 **a2,
        unsigned __int8 **a3)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  __int64 v7; // rdx
  void *v8; // rcx
  int v9; // eax
  int v10; // edi
  void *v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  int Key; // eax
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  unsigned __int8 *v20; // r8
  unsigned __int8 *v21; // rdx
  __int64 v22; // rax
  size_t v23; // rbx
  unsigned __int8 *v24; // rdi
  int v25; // ebx
  const struct Path *v26; // rdx
  int v27; // esi
  __int64 v28; // rdx
  unsigned int v29; // [rsp+20h] [rbp-79h]
  unsigned int v30; // [rsp+20h] [rbp-79h]
  unsigned int v31; // [rsp+20h] [rbp-79h]
  const wchar_t *v32; // [rsp+30h] [rbp-69h] BYREF
  __int64 v33; // [rsp+38h] [rbp-61h]
  void *v34[2]; // [rsp+40h] [rbp-59h] BYREF
  _WORD v35[8]; // [rsp+50h] [rbp-49h] BYREF
  unsigned __int16 *v36[2]; // [rsp+60h] [rbp-39h] BYREF
  _WORD v37[8]; // [rsp+70h] [rbp-29h] BYREF
  unsigned __int8 *v38[2]; // [rsp+80h] [rbp-19h] BYREF
  _WORD v39[8]; // [rsp+90h] [rbp-9h] BYREF
  unsigned __int8 *v40[2]; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v41; // [rsp+B0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  int v43; // [rsp+100h] [rbp+67h] BYREF

  v5 = a1[1] - *a1;
  v6 = *a1;
  v34[0] = v35;
  v34[1] = v35;
  v35[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v34,
                           v6,
                           v5 >> 1) )
  {
    v7 = 892;
    goto LABEL_3;
  }
  v33 = 32;
  v32 = L"Windows\\System32\\config\\SOFTWARE";
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v34) )
  {
    v7 = 893;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
    v8 = v34[0];
    if ( v34[0] == v35 )
      return 2147942414LL;
LABEL_72:
    operator delete(v8, (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  LOBYTE(v32) = 0;
  v33 = 0;
  v9 = Csl::OfflineHive::Open((Csl::OfflineHive *)&v32, (LPCWSTR *)v34);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x381,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v9,
      v29);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v11 = v34[0];
    if ( v34[0] == v35 )
      return (unsigned int)v10;
LABEL_9:
    operator delete(v11, (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v10;
  }
  v37[0] = 0;
  v36[0] = v37;
  v40[1] = (unsigned __int8 *)47;
  v36[1] = v37;
  v40[0] = (unsigned __int8 *)L"Microsoft\\Windows NT\\CurrentVersion\\ProfileList";
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v36) )
  {
    v13 = 901;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
    goto LABEL_69;
  }
  v14 = a2[1] - *a2;
  v40[0] = *a2;
  v40[1] = (unsigned __int8 *)(v14 >> 1);
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v36) )
  {
    v13 = 902;
    goto LABEL_13;
  }
  LOBYTE(v43) = 0;
  Key = Csl::OfflineHive::CreateKey((Csl::OfflineHive *)&v32, v36[0], (bool *)&v43);
  v10 = Key;
  if ( Key < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x388,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)Key,
      v29);
    goto LABEL_18;
  }
  v39[0] = 0;
  v38[0] = (unsigned __int8 *)v39;
  v40[1] = (unsigned __int8 *)8;
  v38[1] = (unsigned __int8 *)v39;
  v40[0] = (unsigned __int8 *)L"C:\\Users";
  if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v38) )
  {
    v16 = 910;
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)0x8007000ELL,
      v29);
LABEL_67:
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_69:
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v8 = v34[0];
    if ( v34[0] == v35 )
      return 2147942414LL;
    goto LABEL_72;
  }
  v17 = a3[1] - *a3;
  v40[0] = *a3;
  v40[1] = (unsigned __int8 *)(v17 >> 1);
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v38) )
  {
    v16 = 911;
    goto LABEL_24;
  }
  v18 = -1;
  do
    ++v18;
  while ( *(_WORD *)&v38[0][2 * v18] );
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"ProfileImagePath", v38[0], 2 * (int)v18 + 2, 2u);
  if ( v10 < 0 )
  {
    v19 = 915;
    goto LABEL_31;
  }
  v43 = 0;
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"Flags", (const unsigned __int8 *)&v43, 4u, 4u);
  if ( v10 < 0 )
  {
    v19 = 918;
    goto LABEL_31;
  }
  v43 = 0;
  v10 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"State", (const unsigned __int8 *)&v43, 4u, 4u);
  if ( v10 < 0 )
  {
    v19 = 919;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v10,
      v30);
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_18:
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    v11 = v34[0];
    if ( v34[0] == v35 )
      return (unsigned int)v10;
    goto LABEL_9;
  }
  v20 = a2[1];
  v21 = *a2;
  v22 = (v20 - *a2) >> 1;
  *(__m128i *)v40 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v41 = -1;
  v23 = 2 * v22;
  if ( 2 * v22 )
  {
    if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(v40, 2 * v22) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x39B,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
        (const char *)0x8007000ELL,
        v30);
      if ( v40[0] != (unsigned __int8 *)-1LL )
        operator delete(v40[0], (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_67;
    }
    memset_0(v40[1], 0, v23);
    v24 = v40[0];
    v21 = *a2;
    v25 = LODWORD(v40[0]) + v23;
    v20 = a2[1];
  }
  else
  {
    v24 = v40[0];
    v25 = -1;
  }
  memcpy_0(v24, v21, 2 * ((v20 - v21) >> 1));
  v27 = Csl::OfflineHive::SetValue((Csl::OfflineHive *)&v32, v36[0], L"Sid", v24, v25 - (int)v24, 3u);
  if ( v27 < 0 )
  {
    v28 = 929;
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v28,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\image\\cmimage\\lib\\adjustments.cpp",
      (const char *)(unsigned int)v27,
      v31);
    if ( v24 != (unsigned __int8 *)-1LL )
      operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
    if ( (_WORD *)v38[0] != v39 )
      operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v36[0] != v37 )
      operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
    if ( v34[0] != v35 )
      operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
    return (unsigned int)v27;
  }
  v27 = Csl::DeletePath((LPCWSTR *)v34, v26);
  if ( v27 < 0 )
  {
    v28 = 932;
    goto LABEL_43;
  }
  v27 = Csl::OfflineHive::Save((Csl::OfflineHive *)&v32, (LPCWSTR *)v34);
  if ( v27 < 0 )
  {
    v28 = 935;
    goto LABEL_43;
  }
  if ( v24 != (unsigned __int8 *)-1LL )
    operator delete(v24, (const struct std::nothrow_t *)&std::nothrow);
  if ( (_WORD *)v38[0] != v39 )
    operator delete(v38[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v36[0] != v37 )
    operator delete(v36[0], (const struct std::nothrow_t *)&std::nothrow);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v32);
  if ( v34[0] != v35 )
    operator delete(v34[0], (const struct std::nothrow_t *)&std::nothrow);
  return 0;
}

```

## disassembly

```asm
0x14001d310  push    rbp
0x14001d312  push    rbx
0x14001d313  push    rsi
0x14001d314  push    rdi
0x14001d315  push    r14
0x14001d317  push    r15
0x14001d319  lea     rbp, [rsp-2Fh]
0x14001d31e  sub     rsp, 0C8h
0x14001d325  mov     rbx, r8
0x14001d328  lea     rax, [rbp+57h+var_A0]
0x14001d32c  mov     r8, [rcx+8]
0x14001d330  mov     rsi, rdx
0x14001d333  sub     r8, [rcx]
0x14001d336  xor     r14d, r14d
0x14001d339  mov     rdx, [rcx]
0x14001d33c  lea     rcx, [rbp+57h+var_B0]
0x14001d340  mov     [rbp+57h+var_B0], rax
0x14001d344  lea     rax, [rbp+57h+var_A0]
0x14001d348  sar     r8, 1
0x14001d34b  mov     [rbp+57h+var_A8], rax
0x14001d34f  mov     [rbp+57h+var_A0], r14w
0x14001d354  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x14001d359  test    al, al
0x14001d35b  jnz     short loc_14001D395
0x14001d35d  mov     edx, 37Ch; void *
0x14001d362  mov     rcx, [rbp+5Fh]; this
0x14001d366  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d36d  mov     r9d, 8007000Eh; char *
0x14001d373  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d378  mov     rcx, [rbp+57h+var_B0]
0x14001d37c  lea     rax, [rbp+57h+var_A0]
0x14001d380  cmp     rcx, rax
0x14001d383  jz      loc_14001D8C4
0x14001d389  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d390  jmp     loc_14001D8BF
0x14001d395  lea     rax, aWindowsSystem3_1; "Windows\\System32\\config\\SOFTWARE"
0x14001d39c  mov     [rbp+57h+var_B8], 20h ; ' '
0x14001d3a4  lea     rdx, [rbp+57h+var_C0]
0x14001d3a8  mov     [rbp+57h+var_C0], rax
0x14001d3ac  lea     rcx, [rbp+57h+var_B0]; this
0x14001d3b0  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001d3b5  test    al, al
0x14001d3b7  jnz     short loc_14001D3C0
0x14001d3b9  mov     edx, 37Dh
0x14001d3be  jmp     short loc_14001D362
0x14001d3c0  lea     rdx, [rbp+57h+var_B0]; struct Path *
0x14001d3c4  mov     byte ptr [rbp+57h+var_C0], r14b
0x14001d3c8  lea     rcx, [rbp+57h+var_C0]; this
0x14001d3cc  mov     [rbp+57h+var_B8], r14
0x14001d3d0  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x14001d3d5  mov     edi, eax
0x14001d3d7  test    eax, eax
0x14001d3d9  jns     short loc_14001D41C
0x14001d3db  mov     rcx, [rbp+5Fh]; this
0x14001d3df  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d3e6  mov     r9d, eax; char *
0x14001d3e9  mov     edx, 381h; void *
0x14001d3ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d3f3  lea     rcx, [rbp+57h+var_C0]; this
0x14001d3f7  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001d3fc  mov     rcx, [rbp+57h+var_B0]; void *
0x14001d400  lea     rax, [rbp+57h+var_A0]
0x14001d404  cmp     rcx, rax
0x14001d407  jz      short loc_14001D415
0x14001d409  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14001d410  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d415  mov     eax, edi
0x14001d417  jmp     loc_14001D8C9
0x14001d41c  lea     rax, [rbp+57h+var_80]
0x14001d420  mov     [rbp+57h+var_80], r14w
0x14001d425  mov     [rbp+57h+var_90], rax
0x14001d429  lea     rdx, [rbp+57h+var_50]
0x14001d42d  lea     rax, [rbp+57h+var_80]
0x14001d431  mov     [rbp+57h+var_50+8], 2Fh ; '/'
0x14001d439  mov     [rbp+57h+var_88], rax
0x14001d43d  lea     rcx, [rbp+57h+var_90]; this
0x14001d441  lea     rax, aMicrosoftWindo; "Microsoft\\Windows NT\\CurrentVersion\\"...
0x14001d448  mov     [rbp+57h+var_50], rax
0x14001d44c  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001d451  test    al, al
0x14001d453  jnz     short loc_14001D47C
0x14001d455  mov     edx, 385h; void *
0x14001d45a  mov     rcx, [rbp+5Fh]; this
0x14001d45e  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d465  mov     r9d, 8007000Eh; char *
0x14001d46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d470  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d477  jmp     loc_14001D891
0x14001d47c  mov     rax, [rsi]
0x14001d47f  lea     rdx, [rbp+57h+var_50]
0x14001d483  mov     rcx, [rsi+8]
0x14001d487  sub     rcx, rax
0x14001d48a  mov     [rbp+57h+var_50], rax
0x14001d48e  sar     rcx, 1
0x14001d491  mov     [rbp+57h+var_50+8], rcx
0x14001d495  lea     rcx, [rbp+57h+var_90]; this
0x14001d499  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001d49e  test    al, al
0x14001d4a0  jnz     short loc_14001D4A9
0x14001d4a2  mov     edx, 386h
0x14001d4a7  jmp     short loc_14001D45A
0x14001d4a9  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001d4ad  lea     r8, [rbp+57h+arg_0]; bool *
0x14001d4b1  lea     rcx, [rbp+57h+var_C0]; this
0x14001d4b5  mov     byte ptr [rbp+57h+arg_0], r14b
0x14001d4b9  call    ?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z; Csl::OfflineHive::CreateKey(ushort const * const,bool &)
0x14001d4be  mov     edi, eax
0x14001d4c0  test    eax, eax
0x14001d4c2  jns     short loc_14001D51A
0x14001d4c4  mov     rcx, [rbp+5Fh]; this
0x14001d4c8  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d4cf  mov     r9d, eax; char *
0x14001d4d2  mov     edx, 388h; void *
0x14001d4d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d4dc  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d4e3  mov     rcx, [rbp+57h+var_90]; void *
0x14001d4e7  lea     rax, [rbp+57h+var_80]
0x14001d4eb  cmp     rcx, rax
0x14001d4ee  jz      short loc_14001D4F8
0x14001d4f0  mov     rdx, rbx; struct std::nothrow_t *
0x14001d4f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d4f8  lea     rcx, [rbp+57h+var_C0]; this
0x14001d4fc  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001d501  mov     rcx, [rbp+57h+var_B0]
0x14001d505  lea     rax, [rbp+57h+var_A0]
0x14001d509  cmp     rcx, rax
0x14001d50c  jz      loc_14001D415
0x14001d512  mov     rdx, rbx
0x14001d515  jmp     loc_14001D410
0x14001d51a  lea     rax, [rbp+57h+var_60]
0x14001d51e  mov     [rbp+57h+var_60], r14w
0x14001d523  mov     [rbp+57h+var_70], rax
0x14001d527  lea     rdx, [rbp+57h+var_50]
0x14001d52b  lea     rax, [rbp+57h+var_60]
0x14001d52f  mov     [rbp+57h+var_50+8], 8
0x14001d537  mov     [rbp+57h+var_68], rax
0x14001d53b  lea     rcx, [rbp+57h+var_70]; this
0x14001d53f  lea     rax, aCUsers; "C:\\Users"
0x14001d546  mov     [rbp+57h+var_50], rax
0x14001d54a  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001d54f  test    al, al
0x14001d551  jnz     short loc_14001D57A
0x14001d553  mov     edx, 38Eh; void *
0x14001d558  mov     rcx, [rbp+5Fh]; this
0x14001d55c  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d563  mov     r9d, 8007000Eh; char *
0x14001d569  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d56e  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d575  jmp     loc_14001D87C
0x14001d57a  mov     rax, [rbx]
0x14001d57d  lea     rdx, [rbp+57h+var_50]
0x14001d581  mov     rcx, [rbx+8]
0x14001d585  sub     rcx, rax
0x14001d588  mov     [rbp+57h+var_50], rax
0x14001d58c  sar     rcx, 1
0x14001d58f  mov     [rbp+57h+var_50+8], rcx
0x14001d593  lea     rcx, [rbp+57h+var_70]; this
0x14001d597  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x14001d59c  test    al, al
0x14001d59e  jnz     short loc_14001D5A7
0x14001d5a0  mov     edx, 38Fh
0x14001d5a5  jmp     short loc_14001D558
0x14001d5a7  mov     r9, [rbp+57h+var_70]; unsigned __int8 *
0x14001d5ab  or      r15, 0FFFFFFFFFFFFFFFFh
0x14001d5af  mov     rax, r15
0x14001d5b2  inc     rax
0x14001d5b5  cmp     [r9+rax*2], r14w
0x14001d5ba  jnz     short loc_14001D5B2
0x14001d5bc  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001d5c0  lea     eax, ds:2[rax*2]
0x14001d5c7  mov     [rsp+0F0h+var_C8], 2; unsigned int
0x14001d5cf  lea     r8, aProfileimagepa; "ProfileImagePath"
0x14001d5d6  lea     rcx, [rbp+57h+var_C0]; this
0x14001d5da  mov     [rsp+0F0h+var_D0], eax; int
0x14001d5de  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x14001d5e3  mov     edi, eax
0x14001d5e5  test    eax, eax
0x14001d5e7  jns     short loc_14001D626
0x14001d5e9  mov     edx, 393h; void *
0x14001d5ee  mov     rcx, [rbp+5Fh]; this
0x14001d5f2  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d5f9  mov     r9d, edi; char *
0x14001d5fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d601  mov     rcx, [rbp+57h+var_70]; void *
0x14001d605  lea     rax, [rbp+57h+var_60]
0x14001d609  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d610  cmp     rcx, rax
0x14001d613  jz      loc_14001D4E3
0x14001d619  mov     rdx, rbx; struct std::nothrow_t *
0x14001d61c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d621  jmp     loc_14001D4E3
0x14001d626  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001d62a  lea     r9, [rbp+57h+arg_0]; unsigned __int8 *
0x14001d62e  mov     ebx, 4
0x14001d633  mov     [rbp+57h+arg_0], r14d
0x14001d637  mov     [rsp+0F0h+var_C8], ebx; unsigned int
0x14001d63b  lea     r8, aFlags; "Flags"
0x14001d642  lea     rcx, [rbp+57h+var_C0]; this
0x14001d646  mov     [rsp+0F0h+var_D0], ebx; unsigned int
0x14001d64a  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x14001d64f  mov     edi, eax
0x14001d651  test    eax, eax
0x14001d653  jns     short loc_14001D65C
0x14001d655  mov     edx, 396h
0x14001d65a  jmp     short loc_14001D5EE
0x14001d65c  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001d660  lea     r9, [rbp+57h+arg_0]; unsigned __int8 *
0x14001d664  mov     [rsp+0F0h+var_C8], ebx; unsigned int
0x14001d668  lea     r8, aState; "State"
0x14001d66f  lea     rcx, [rbp+57h+var_C0]; this
0x14001d673  mov     [rsp+0F0h+var_D0], ebx; int
0x14001d677  mov     [rbp+57h+arg_0], r14d
0x14001d67b  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x14001d680  mov     edi, eax
0x14001d682  test    eax, eax
0x14001d684  jns     short loc_14001D690
0x14001d686  mov     edx, 397h
0x14001d68b  jmp     loc_14001D5EE
0x14001d690  mov     r8, [rsi+8]
0x14001d694  mov     rdx, [rsi]
0x14001d697  mov     rax, r8
0x14001d69a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14001d6a2  sub     rax, rdx
0x14001d6a5  sar     rax, 1
0x14001d6a8  movdqu  xmmword ptr [rbp+57h+var_50], xmm0
0x14001d6ad  mov     [rbp+57h+var_40], r15
0x14001d6b1  lea     rbx, [rax+rax]
0x14001d6b5  test    rbx, rbx
0x14001d6b8  jnz     short loc_14001D6C3
0x14001d6ba  mov     rdi, [rbp+57h+var_50]
0x14001d6be  dec     rbx
0x14001d6c1  jmp     short loc_14001D6F3
0x14001d6c3  mov     rdx, rbx
0x14001d6c6  lea     rcx, [rbp+57h+var_50]
0x14001d6ca  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14001d6cf  test    al, al
0x14001d6d1  jz      loc_14001D849
0x14001d6d7  mov     rcx, [rbp+57h+var_50+8]; void *
0x14001d6db  mov     r8, rbx; Size
0x14001d6de  xor     edx, edx; Val
0x14001d6e0  call    memset_0
0x14001d6e5  mov     rdi, [rbp+57h+var_50]
0x14001d6e9  mov     rdx, [rsi]; Src
0x14001d6ec  add     rbx, rdi
0x14001d6ef  mov     r8, [rsi+8]
0x14001d6f3  sub     r8, rdx
0x14001d6f6  mov     rcx, rdi; void *
0x14001d6f9  sar     r8, 1
0x14001d6fc  add     r8, r8; Size
0x14001d6ff  call    memcpy_0
0x14001d704  mov     rdx, [rbp+57h+var_90]; unsigned __int16 *
0x14001d708  lea     r8, aSid; "Sid"
0x14001d70f  sub     ebx, edi
0x14001d711  mov     [rsp+0F0h+var_C8], 3; unsigned int
0x14001d719  mov     r9, rdi; unsigned __int8 *
0x14001d71c  mov     [rsp+0F0h+var_D0], ebx; int
0x14001d720  lea     rcx, [rbp+57h+var_C0]; this
0x14001d724  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x14001d729  mov     esi, eax
0x14001d72b  test    eax, eax
0x14001d72d  jns     short loc_14001D7AD
0x14001d72f  mov     edx, 3A1h; void *
0x14001d734  mov     rcx, [rbp+5Fh]; this
0x14001d738  lea     r8, aOnecoreBaseGen_2; "onecore\\base\\gendrv\\silos\\clem\\ima"...
0x14001d73f  mov     r9d, esi; char *
0x14001d742  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001d747  lea     rbx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x14001d74e  cmp     rdi, r15
0x14001d751  jz      short loc_14001D75E
0x14001d753  mov     rdx, rbx; struct std::nothrow_t *
0x14001d756  mov     rcx, rdi; void *
0x14001d759  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d75e  mov     rcx, [rbp+57h+var_70]; void *
0x14001d762  lea     rax, [rbp+57h+var_60]
0x14001d766  cmp     rcx, rax
0x14001d769  jz      short loc_14001D773
0x14001d76b  mov     rdx, rbx; struct std::nothrow_t *
0x14001d76e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d773  mov     rcx, [rbp+57h+var_90]; void *
0x14001d777  lea     rax, [rbp+57h+var_80]
0x14001d77b  cmp     rcx, rax
0x14001d77e  jz      short loc_14001D788
0x14001d780  mov     rdx, rbx; struct std::nothrow_t *
0x14001d783  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d788  lea     rcx, [rbp+57h+var_C0]; this
0x14001d78c  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x14001d791  mov     rcx, [rbp+57h+var_B0]; void *
0x14001d795  lea     rax, [rbp+57h+var_A0]
0x14001d799  cmp     rcx, rax
0x14001d79c  jz      short loc_14001D7A6
0x14001d79e  mov     rdx, rbx; struct std::nothrow_t *
0x14001d7a1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001d7a6  mov     eax, esi
0x14001d7a8  jmp     loc_14001D8C9
0x14001d7ad  lea     rcx, [rbp+57h+var_B0]; this
0x14001d7b1  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x14001d7b6  mov     esi, eax
0x14001d7b8  test    eax, eax
0x14001d7ba  jns     short loc_14001D7C6
0x14001d7bc  mov     edx, 3A4h
  ... truncated ...
```
