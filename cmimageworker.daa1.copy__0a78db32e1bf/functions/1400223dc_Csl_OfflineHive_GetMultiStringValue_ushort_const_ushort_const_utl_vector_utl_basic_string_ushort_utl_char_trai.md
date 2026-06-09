# Csl::OfflineHive::GetMultiStringValue(ushort const *,ushort const *,utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)

- ea: `0x1400223dc`
- end: `0x140022609`
- name: `?GetMultiStringValue@OfflineHive@Csl@@QEBAJPEBG0AEAV?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x14001bb2c`

## callees

- `0x140002344`
- `0x140006fe4`
- `0x140008f90`
- `0x14000cd84`
- `0x14000d0a4`
- `0x14000d7bc`
- `0x1400223dc`
- `0x140022610`

## string_xrefs

- `0x140022424`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x140022577`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x1400225c3`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
__int64 __fastcall Csl::OfflineHive::GetMultiStringValue(__int64 a1, int a2, int a3, __int64 a4)
{
  int WideStringValueCommon; // eax
  unsigned int v6; // ebx
  const struct std::nothrow_t *v7; // rdx
  void *v8; // rcx
  char *v9; // r14
  char *v10; // rbx
  __int64 v11; // rax
  char *v12; // rsi
  __int64 v13; // r13
  __int64 v14; // r8
  __int64 v15; // rdi
  __int64 v16; // rsi
  __m128i v17; // kr00_16
  const struct std::nothrow_t *v18; // rdx
  __int64 v20; // rdx
  const struct std::nothrow_t *v21; // rdx
  unsigned int v22; // [rsp+20h] [rbp-49h]
  unsigned int v23; // [rsp+30h] [rbp-39h] BYREF
  void *v24; // [rsp+38h] [rbp-31h] BYREF
  __m128i si128; // [rsp+40h] [rbp-29h] BYREF
  __int64 v26; // [rsp+50h] [rbp-19h]
  void *v27; // [rsp+58h] [rbp-11h] BYREF
  char *v28; // [rsp+60h] [rbp-9h]
  _WORD v29[44]; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v24 = 0;
  v23 = 0;
  WideStringValueCommon = Csl::OfflineHive::GetWideStringValueCommon(a1, a2, a3, a4, &v24, &v23);
  v6 = WideStringValueCommon;
  if ( WideStringValueCommon < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x302,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
      (const char *)(unsigned int)WideStringValueCommon,
      v22);
    v8 = v24;
    if ( v24 )
      goto LABEL_27;
    return v6;
  }
  v9 = (char *)v24;
  v10 = (char *)v24;
  v11 = v23 & 0xFFFFFFFE;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v26 = -1;
  v12 = (char *)v24 + v11;
  v13 = v11 - 2;
  if ( v24 >= (char *)v24 + v11 )
  {
LABEL_25:
    v6 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x31E,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
           (const char *)0xD,
           v22);
    utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
    if ( v9 )
    {
      v8 = v9;
LABEL_27:
      operator delete(v8, v7);
    }
    return v6;
  }
  while ( *(_WORD *)v10 || v10 != &v9[v13] )
  {
    v29[0] = 0;
    v27 = v29;
    v14 = -1;
    v28 = (char *)v29;
    do
      ++v14;
    while ( *(_WORD *)&v10[2 * v14] );
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v27,
                             v10,
                             v14) )
    {
      v20 = 787;
      goto LABEL_20;
    }
    v15 = v28 - (_BYTE *)v27;
    if ( !(unsigned __int8)utl::vector<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::emplace_back<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,0>(
                             &si128,
                             &v27) )
    {
      v20 = 793;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)0x8007000ELL,
        v22);
      if ( v27 != v29 )
        operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
      utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
      if ( v9 )
        operator delete(v9, v21);
      return 2147942414LL;
    }
    v10 += 2 * (v15 >> 1) + 2;
    if ( v27 != v29 )
      operator delete(v27, (const struct std::nothrow_t *)&std::nothrow);
    if ( v10 >= v12 )
      goto LABEL_25;
  }
  v16 = v26;
  v17 = si128;
  v26 = -1;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(a4);
  *(__m128i *)a4 = v17;
  *(_QWORD *)(a4 + 16) = v16;
  utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(&si128);
  if ( v9 )
    operator delete(v9, v18);
  return 0;
}

```

## disassembly

```asm
0x1400223dc  push    rbp
0x1400223de  push    rbx
0x1400223df  push    rsi
0x1400223e0  push    rdi
0x1400223e1  push    r12
0x1400223e3  push    r13
0x1400223e5  push    r14
0x1400223e7  push    r15
0x1400223e9  lea     rbp, [rsp-1Fh]
0x1400223ee  sub     rsp, 88h
0x1400223f5  lea     rax, [rbp+57h+var_90]
0x1400223f9  xor     r12d, r12d
0x1400223fc  mov     [rsp+0C0h+var_98], rax
0x140022401  mov     r15, r9
0x140022404  lea     rax, [rbp+57h+var_88]
0x140022408  mov     [rbp+57h+var_88], r12
0x14002240c  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x140022411  mov     [rbp+57h+var_90], r12d
0x140022415  call    ?GetWideStringValueCommon@OfflineHive@Csl@@QEBAJQEBG0KAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@AEAK@Z; Csl::OfflineHive::GetWideStringValueCommon(ushort const * const,ushort const * const,ulong,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong &)
0x14002241a  mov     ebx, eax
0x14002241c  test    eax, eax
0x14002241e  jns     short loc_14002244A
0x140022420  mov     rcx, [rbp+5Fh]; this
0x140022424  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002242b  mov     r9d, eax; char *
0x14002242e  mov     edx, 302h; void *
0x140022433  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022438  mov     rcx, [rbp+57h+var_88]
0x14002243c  test    rcx, rcx
0x14002243f  jz      loc_1400225F2
0x140022445  jmp     loc_1400225ED
0x14002244a  mov     r14, [rbp+57h+var_88]
0x14002244e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140022452  mov     eax, [rbp+57h+var_90]
0x140022455  mov     rbx, r14
0x140022458  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140022460  and     rax, 0FFFFFFFFFFFFFFFEh
0x140022464  movdqu  [rbp+57h+var_80], xmm0
0x140022469  mov     [rbp+57h+var_70], rcx
0x14002246d  lea     rsi, [rax+r14]
0x140022471  lea     r13, [rax-2]
0x140022475  cmp     r14, rsi
0x140022478  jnb     loc_1400225BF
0x14002247e  cmp     [rbx], r12w
0x140022482  jnz     short loc_140022491
0x140022484  lea     rax, [r14+r13]
0x140022488  cmp     rbx, rax
0x14002248b  jz      loc_14002251A
0x140022491  lea     rax, [rbp+57h+var_58]
0x140022495  mov     [rbp+57h+var_58], r12w
0x14002249a  mov     [rbp+57h+var_68], rax
0x14002249e  mov     r8, rcx
0x1400224a1  lea     rax, [rbp+57h+var_58]
0x1400224a5  mov     [rbp+57h+var_60], rax
0x1400224a9  inc     r8
0x1400224ac  cmp     [rbx+r8*2], r12w
0x1400224b1  jnz     short loc_1400224A9
0x1400224b3  mov     rdx, rbx
0x1400224b6  lea     rcx, [rbp+57h+var_68]
0x1400224ba  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1400224bf  test    al, al
0x1400224c1  jz      loc_14002256E
0x1400224c7  mov     rdi, [rbp+57h+var_60]
0x1400224cb  lea     rdx, [rbp+57h+var_68]
0x1400224cf  sub     rdi, [rbp+57h+var_68]
0x1400224d3  lea     rcx, [rbp+57h+var_80]
0x1400224d7  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_N$$QEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@1@@Z; utl::vector<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::emplace_back<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,0>(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x1400224dc  test    al, al
0x1400224de  jz      loc_140022567
0x1400224e4  mov     rcx, [rbp+57h+var_68]; void *
0x1400224e8  lea     rax, [rbp+57h+var_58]
0x1400224ec  sar     rdi, 1
0x1400224ef  lea     rbx, [rbx+rdi*2]
0x1400224f3  add     rbx, 2
0x1400224f7  cmp     rcx, rax
0x1400224fa  jz      short loc_140022508
0x1400224fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140022503  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022508  cmp     rbx, rsi
0x14002250b  jnb     loc_1400225BF
0x140022511  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140022515  jmp     loc_14002247E
0x14002251a  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140022522  mov     rsi, [rbp+57h+var_70]
0x140022526  mov     rbx, qword ptr [rbp+57h+var_80]
0x14002252a  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x14002252e  mov     [rbp+57h+var_70], rcx
0x140022532  mov     rcx, r15
0x140022535  movdqu  [rbp+57h+var_80], xmm0
0x14002253a  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x14002253f  lea     rcx, [rbp+57h+var_80]
0x140022543  mov     [r15], rbx
0x140022546  mov     [r15+8], rdi
0x14002254a  mov     [r15+10h], rsi
0x14002254e  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x140022553  test    r14, r14
0x140022556  jz      short loc_140022560
0x140022558  mov     rcx, r14; void *
0x14002255b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140022560  xor     eax, eax
0x140022562  jmp     loc_1400225F4
0x140022567  mov     edx, 319h
0x14002256c  jmp     short loc_140022573
0x14002256e  mov     edx, 313h; void *
0x140022573  mov     rcx, [rbp+5Fh]; this
0x140022577  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x14002257e  mov     r9d, 8007000Eh; char *
0x140022584  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140022589  mov     rcx, [rbp+57h+var_68]; void *
0x14002258d  lea     rax, [rbp+57h+var_58]
0x140022591  cmp     rcx, rax
0x140022594  jz      short loc_1400225A2
0x140022596  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14002259d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400225a2  lea     rcx, [rbp+57h+var_80]
0x1400225a6  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x1400225ab  test    r14, r14
0x1400225ae  jz      short loc_1400225B8
0x1400225b0  mov     rcx, r14; void *
0x1400225b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400225b8  mov     eax, 8007000Eh
0x1400225bd  jmp     short loc_1400225F4
0x1400225bf  mov     rcx, [rbp+5Fh]; this
0x1400225c3  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1400225ca  mov     r9d, 0Dh; char *
0x1400225d0  mov     edx, 31Eh; void *
0x1400225d5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1400225da  lea     rcx, [rbp+57h+var_80]
0x1400225de  mov     ebx, eax
0x1400225e0  call    ?_Uninit@?$vector@VPath@Csl@@V?$allocator@VPath@Csl@@@utl@@@utl@@AEAAXXZ; utl::vector<Csl::Path,utl::allocator<Csl::Path>>::_Uninit(void)
0x1400225e5  test    r14, r14
0x1400225e8  jz      short loc_1400225F2
0x1400225ea  mov     rcx, r14; void *
0x1400225ed  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400225f2  mov     eax, ebx
0x1400225f4  add     rsp, 88h
0x1400225fb  pop     r15
0x1400225fd  pop     r14
0x1400225ff  pop     r13
0x140022601  pop     r12
0x140022603  pop     rdi
0x140022604  pop     rsi
0x140022605  pop     rbx
0x140022606  pop     rbp
0x140022607  retn
```
