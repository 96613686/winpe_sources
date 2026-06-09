# ReplaceAnonymousIdentity(ushort const *,ushort const *,ushort * *)

- ea: `0x18002a25c`
- end: `0x18002a681`
- name: `?ReplaceAnonymousIdentity@@YAJPEBG0PEAPEAG@Z`
- size: `1061`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18007bc7c`

## callees

- `0x180028f98`
- `0x180029110`
- `0x18002a0a4`
- `0x18002a15c`
- `0x18002a25c`
- `0x18002a688`
- `0x18002a698`
- `0x18002a6d8`
- `0x18002a784`
- `0x18002a7d8`
- `0x18002a870`
- `0x18002aa24`
- `0x18002af1c`
- `0x18002afd4`
- `0x18002b058`
- `0x18002dc28`
- `0x180034bb0`
- `0x180035880`
- `0x180035d24`
- `0x180038270`
- `0x18004a618`
- `0x18007a4ac`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002a5e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ReplaceAnonymousIdentity(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  __int64 v6; // r8
  __int64 v7; // r8
  unsigned __int16 *v8; // rbx
  __int128 *v9; // rcx
  __int64 v10; // r8
  __int128 *v11; // rcx
  char v12; // r14
  __int64 v13; // r8
  unsigned int i; // esi
  const unsigned __int16 * near *v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  struct std::_Node_base *v19; // rcx
  __int64 v20; // r8
  char v21; // di
  _QWORD *v22; // rdx
  __int64 v23; // rax
  __int128 *v25; // rdx
  unsigned __int16 **v26; // rax
  int v27; // [rsp+20h] [rbp-298h]
  HLOCAL hMem; // [rsp+40h] [rbp-278h] BYREF
  unsigned __int16 *v29; // [rsp+48h] [rbp-270h] BYREF
  struct std::_Node_base *v30; // [rsp+50h] [rbp-268h] BYREF
  _BYTE v31[16]; // [rsp+58h] [rbp-260h] BYREF
  _BYTE v32[24]; // [rsp+68h] [rbp-250h] BYREF
  _BYTE v33[128]; // [rsp+80h] [rbp-238h] BYREF
  _BYTE v34[272]; // [rsp+100h] [rbp-1B8h] BYREF
  __int128 v35; // [rsp+210h] [rbp-A8h] BYREF
  __int64 v36; // [rsp+220h] [rbp-98h]
  unsigned __int64 v37; // [rsp+228h] [rbp-90h]
  __int128 Src; // [rsp+230h] [rbp-88h] BYREF
  __int128 v39; // [rsp+240h] [rbp-78h]
  _QWORD v40[4]; // [rsp+250h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+0h]

  *a3 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  std::wstring::_Construct<1,unsigned short const *>(&v35);
  v8 = 0;
  v29 = 0;
  v9 = &v35;
  if ( v37 > 7 )
    v9 = (__int128 *)v35;
  if ( std::_Traits_find_ch<std::char_traits<unsigned short>>(v9, v36, v7, 92) != -1 )
    goto LABEL_28;
  v11 = &v35;
  if ( v37 > 7 )
    v11 = (__int128 *)v35;
  if ( std::_Traits_find_ch<std::char_traits<unsigned short>>(v11, v36, v10, 64) == -1 )
  {
    v12 = 0;
    Src = 0;
    v39 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&Src);
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    std::wstring::_Append<unsigned short>(&Src);
    std::wstring::_Append<unsigned short>(&Src);
    for ( i = 0; i < 7; ++i )
    {
      v15 = (&idPrivacyPatterns)[i];
      v30 = 0;
      std::regex_traits<unsigned short>::regex_traits<unsigned short>(v31);
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)v15 + v16) );
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>(
        v33,
        v31,
        v15,
        (char *)v15 + 2 * v16);
      v17 = std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::_Compile(v33);
      if ( v17 )
        _InterlockedIncrement((volatile signed __int32 *)(v17 + 44));
      v30 = (struct std::_Node_base *)v17;
      std::_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>::~_Parser2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>>(v33);
      v18 = -1;
      do
        ++v18;
      while ( a1[v18] );
      v19 = v30;
      if ( v30 )
      {
        std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>(
          (unsigned int)v34,
          (_DWORD)a1,
          (_DWORD)a1 + 2 * v18,
          (unsigned int)v31,
          (__int64)v30,
          *((_DWORD *)v30 + 10),
          *((_DWORD *)v30 + 8),
          16);
        LOBYTE(v20) = 1;
        v21 = std::_Matcher2<unsigned short const *,unsigned short,std::regex_traits<unsigned short>,unsigned short const *,void>::_Match<std::allocator<std::sub_match<unsigned short const *>>>(
                v34,
                0,
                v20);
        std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,void>::~_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short,std::regex_traits<unsigned short>,std::_String_const_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,void>(v34);
        if ( v21 )
        {
          std::regex_replace<std::regex_traits<unsigned short>,unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
            v40,
            a1,
            &v30,
            &Src);
          v22 = v40;
          if ( v40[3] > 7u )
            v22 = (_QWORD *)v40[0];
          v23 = wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  &hMem,
                  v22);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &v29,
            v23);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
          v12 = 1;
          std::wstring::_Tidy_deallocate(v40);
          std::basic_regex<unsigned short,std::regex_traits<unsigned short>>::~basic_regex<unsigned short,std::regex_traits<unsigned short>>(&v30);
          v8 = v29;
          break;
        }
        v19 = v30;
      }
      if ( v19 && _InterlockedExchangeAdd((volatile signed __int32 *)v19 + 11, 0xFFFFFFFF) == 1 )
        std::_Destroy_node(v30, 0);
      v30 = 0;
      std::locale::~locale((std::locale *)v32);
    }
    if ( *((_QWORD *)&v39 + 1) > 7u )
      std::_Deallocate<16>(Src, 2LL * *((_QWORD *)&v39 + 1) + 2);
    if ( !v12 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x75,
        (unsigned int)"onecoreuap\\net\\rras\\ras\\ppp\\eaptlsdata\\regex.cpp",
        (const char *)0x80070057LL,
        v27);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
      std::wstring::_Tidy_deallocate(&v35);
      return 2147942487LL;
    }
  }
  else
  {
LABEL_28:
    v25 = &v35;
    if ( v37 > 7 )
      v25 = (__int128 *)v35;
    v26 = (unsigned __int16 **)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                                 &hMem,
                                 v25);
    if ( &v29 != v26 )
    {
      v8 = *v26;
      *v26 = 0;
    }
    if ( hMem )
      LocalFree(hMem);
  }
  *a3 = v8;
  if ( v37 > 7 )
    std::_Deallocate<16>(v35, 2 * v37 + 2);
  return 0;
}

```

## disassembly

```asm
0x18002a25c  push    rbx
0x18002a25e  push    rsi
0x18002a25f  push    rdi
0x18002a260  push    r12
0x18002a262  push    r13
0x18002a264  push    r14
0x18002a266  push    r15
0x18002a268  sub     rsp, 280h
0x18002a26f  mov     rax, cs:__security_cookie
0x18002a276  xor     rax, rsp
0x18002a279  mov     [rsp+2B8h+var_48], rax
0x18002a281  mov     r12, r8
0x18002a284  mov     rdi, rdx
0x18002a287  mov     r15, rcx
0x18002a28a  xor     r13d, r13d
0x18002a28d  mov     [r8], r13
0x18002a290  xorps   xmm0, xmm0
0x18002a293  movups  [rsp+2B8h+var_A8], xmm0
0x18002a29b  mov     [rsp+2B8h+var_98], r13
0x18002a2a3  mov     [rsp+2B8h+var_90], r13
0x18002a2ab  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002a2af  mov     r8, rsi
0x18002a2b2  inc     r8
0x18002a2b5  cmp     [rdx+r8*2], r13w
0x18002a2ba  jnz     short loc_18002A2B2
0x18002a2bc  lea     rcx, [rsp+2B8h+var_A8]
0x18002a2c4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a2c9  nop
0x18002a2ca  mov     rbx, r13
0x18002a2cd  mov     [rsp+2B8h+var_270], rbx
0x18002a2d2  lea     rcx, [rsp+2B8h+var_A8]
0x18002a2da  cmp     [rsp+2B8h+var_90], 7
0x18002a2e3  cmova   rcx, qword ptr [rsp+2B8h+var_A8]
0x18002a2ec  mov     r9d, 5Ch ; '\'
0x18002a2f2  mov     rdx, [rsp+2B8h+var_98]
0x18002a2fa  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18002a2ff  cmp     rax, rsi
0x18002a302  jnz     loc_18002A5A9
0x18002a308  lea     rcx, [rsp+2B8h+var_A8]
0x18002a310  cmp     [rsp+2B8h+var_90], 7
0x18002a319  cmova   rcx, qword ptr [rsp+2B8h+var_A8]
0x18002a322  mov     r9d, 40h ; '@'
0x18002a328  mov     rdx, [rsp+2B8h+var_98]
0x18002a330  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x18002a335  cmp     rax, rsi
0x18002a338  jnz     loc_18002A5A9
0x18002a33e  mov     r14b, r13b
0x18002a341  xorps   xmm0, xmm0
0x18002a344  movups  [rsp+2B8h+Src], xmm0
0x18002a34c  xorps   xmm1, xmm1
0x18002a34f  movdqu  [rsp+2B8h+var_78], xmm1
0x18002a358  mov     r8d, 3
0x18002a35e  lea     rdx, a01; "$01"
0x18002a365  lea     rcx, [rsp+2B8h+Src]
0x18002a36d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002a372  nop
0x18002a373  mov     r8, rsi
0x18002a376  inc     r8
0x18002a379  cmp     [rdi+r8*2], r13w
0x18002a37e  jnz     short loc_18002A376
0x18002a380  mov     rdx, rdi
0x18002a383  lea     rcx, [rsp+2B8h+Src]; Src
0x18002a38b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002a390  mov     r8d, 3
0x18002a396  lea     rdx, a03; "$03"
0x18002a39d  lea     rcx, [rsp+2B8h+Src]; Src
0x18002a3a5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18002a3aa  mov     esi, r13d
0x18002a3ad  cmp     esi, 7
0x18002a3b0  jnb     loc_18002A53F
0x18002a3b6  mov     eax, esi
0x18002a3b8  lea     rdi, ?idPrivacyPatterns@@3PAPEBGA; ushort const * near * idPrivacyPatterns
0x18002a3bf  mov     rdi, [rdi+rax*8]
0x18002a3c3  mov     [rsp+2B8h+var_268], r13
0x18002a3c8  lea     rcx, [rsp+2B8h+var_260]
0x18002a3cd  call    ??0?$regex_traits@G@std@@QEAA@XZ; std::regex_traits<ushort>::regex_traits<ushort>(void)
0x18002a3d2  nop
0x18002a3d3  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a3d7  inc     rax
0x18002a3da  cmp     [rdi+rax*2], r13w
0x18002a3df  jnz     short loc_18002A3D7
0x18002a3e1  lea     r9, [rdi+rax*2]
0x18002a3e5  mov     r8, rdi
0x18002a3e8  lea     rdx, [rsp+2B8h+var_260]
0x18002a3ed  lea     rcx, [rsp+2B8h+var_238]
0x18002a3f5  call    ??0?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAA@AEBV?$regex_traits@G@1@PEBG1W4syntax_option_type@regex_constants@1@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>(std::regex_traits<ushort> const &,ushort const *,ushort const *,std::regex_constants::syntax_option_type)
0x18002a3fa  nop
0x18002a3fb  lea     rcx, [rsp+2B8h+var_238]
0x18002a403  call    ?_Compile@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Root_node@2@XZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Compile(void)
0x18002a408  mov     rdi, rax
0x18002a40b  test    rax, rax
0x18002a40e  jz      short loc_18002A414
0x18002a410  lock inc dword ptr [rax+2Ch]
0x18002a414  mov     rcx, [rsp+2B8h+var_268]
0x18002a419  test    rcx, rcx
0x18002a41c  jz      short loc_18002A437
0x18002a41e  or      eax, 0FFFFFFFFh
0x18002a421  lock xadd [rcx+2Ch], eax
0x18002a426  cmp     eax, 1
0x18002a429  jnz     short loc_18002A437
0x18002a42b  xor     edx, edx; struct std::_Node_base *
0x18002a42d  mov     rcx, [rsp+2B8h+var_268]; struct std::_Node_base *
0x18002a432  call    ?_Destroy_node@std@@YAXPEAV_Node_base@1@0@Z; std::_Destroy_node(std::_Node_base *,std::_Node_base *)
0x18002a437  mov     [rsp+2B8h+var_268], rdi
0x18002a43c  lea     rcx, [rsp+2B8h+var_238]
0x18002a444  call    ??1?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAA@XZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::~_Parser2<ushort const *,ushort,std::regex_traits<ushort>>(void)
0x18002a449  nop
0x18002a44a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a44e  inc     rax
0x18002a451  cmp     [r15+rax*2], r13w
0x18002a456  jnz     short loc_18002A44E
0x18002a458  mov     rcx, [rsp+2B8h+var_268]
0x18002a45d  test    rcx, rcx
0x18002a460  jz      loc_18002A64B
0x18002a466  lea     r8, [r15+rax*2]
0x18002a46a  mov     [rsp+2B8h+var_280], 10h
0x18002a472  mov     eax, [rcx+20h]
0x18002a475  mov     [rsp+2B8h+var_288], eax
0x18002a479  mov     eax, [rcx+28h]
0x18002a47c  mov     [rsp+2B8h+var_290], eax
0x18002a480  mov     qword ptr [rsp+2B8h+var_298], rcx; int
0x18002a485  lea     r9, [rsp+2B8h+var_260]
0x18002a48a  mov     rdx, r15
0x18002a48d  lea     rcx, [rsp+2B8h+var_1B8]
0x18002a495  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x18002a49a  nop
0x18002a49b  mov     r8b, 1
0x18002a49e  xor     edx, edx
0x18002a4a0  lea     rcx, [rsp+2B8h+var_1B8]
0x18002a4a8  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x18002a4ad  mov     dil, al
0x18002a4b0  lea     rcx, [rsp+2B8h+var_1B8]
0x18002a4b8  call    ??1?$_Matcher2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@V12@X@std@@QEAA@XZ; std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>::~_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>(void)
0x18002a4bd  test    dil, dil
0x18002a4c0  jz      loc_18002A646
0x18002a4c6  lea     r9, [rsp+2B8h+Src]
0x18002a4ce  lea     r8, [rsp+2B8h+var_268]
0x18002a4d3  mov     rdx, r15
0x18002a4d6  lea     rcx, [rsp+2B8h+var_68]
0x18002a4de  call    ??$regex_replace@V?$regex_traits@G@std@@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV10@W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::wstring const &,std::regex_constants::match_flag_type)
0x18002a4e3  nop
0x18002a4e4  lea     rdx, [rsp+2B8h+var_68]
0x18002a4ec  cmp     [rsp+2B8h+var_50], 7
0x18002a4f5  cmova   rdx, [rsp+2B8h+var_68]
0x18002a4fe  lea     rcx, [rsp+2B8h+hMem]
0x18002a503  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a508  mov     rdx, rax
0x18002a50b  lea     rcx, [rsp+2B8h+var_270]
0x18002a510  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18002a515  lea     rcx, [rsp+2B8h+hMem]
0x18002a51a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a51f  mov     r14b, 1
0x18002a522  lea     rcx, [rsp+2B8h+var_68]
0x18002a52a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a52f  nop
0x18002a530  lea     rcx, [rsp+2B8h+var_268]
0x18002a535  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x18002a53a  mov     rbx, [rsp+2B8h+var_270]
0x18002a53f  mov     rdx, qword ptr [rsp+2B8h+var_78+8]
0x18002a547  cmp     rdx, 7
0x18002a54b  jbe     short loc_18002A562
0x18002a54d  lea     rdx, ds:2[rdx*2]
0x18002a555  mov     rcx, qword ptr [rsp+2B8h+Src]
0x18002a55d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a562  test    r14b, r14b
0x18002a565  jnz     loc_18002A5F3
0x18002a56b  mov     rcx, [rsp+2B8h]; this
0x18002a573  mov     ebx, 80070057h
0x18002a578  mov     r9d, ebx; char *
0x18002a57b  lea     r8, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x18002a582  mov     edx, 75h ; 'u'; void *
0x18002a587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002a58c  nop
0x18002a58d  lea     rcx, [rsp+2B8h+var_270]
0x18002a592  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002a597  nop
0x18002a598  lea     rcx, [rsp+2B8h+var_A8]
0x18002a5a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a5a5  mov     eax, ebx
0x18002a5a7  jmp     short loc_18002A622
0x18002a5a9  lea     rdx, [rsp+2B8h+var_A8]
0x18002a5b1  cmp     [rsp+2B8h+var_90], 7
0x18002a5ba  cmova   rdx, qword ptr [rsp+2B8h+var_A8]
0x18002a5c3  lea     rcx, [rsp+2B8h+hMem]
0x18002a5c8  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002a5cd  lea     rcx, [rsp+2B8h+var_270]
0x18002a5d2  cmp     rcx, rax
0x18002a5d5  jz      short loc_18002A5DD
0x18002a5d7  mov     rbx, [rax]
0x18002a5da  mov     [rax], r13
0x18002a5dd  mov     rcx, [rsp+2B8h+hMem]; hMem
0x18002a5e2  test    rcx, rcx
0x18002a5e5  jz      short loc_18002A5F3
0x18002a5e7  call    cs:__imp_LocalFree
0x18002a5ee  nop     dword ptr [rax+rax+00h]
0x18002a5f3  mov     [r12], rbx
0x18002a5f7  mov     rdx, [rsp+2B8h+var_90]
0x18002a5ff  cmp     rdx, 7
0x18002a603  jbe     short loc_18002A61A
0x18002a605  lea     rdx, ds:2[rdx*2]
0x18002a60d  mov     rcx, qword ptr [rsp+2B8h+var_A8]
0x18002a615  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002a61a  xor     eax, eax
0x18002a61c  jmp     short loc_18002A622
0x18002a61e  mov     eax, dword ptr [rsp+2B8h+hMem]
0x18002a622  mov     rcx, [rsp+2B8h+var_48]
0x18002a62a  xor     rcx, rsp; StackCookie
0x18002a62d  call    __security_check_cookie
0x18002a632  add     rsp, 280h
0x18002a639  pop     r15
0x18002a63b  pop     r14
0x18002a63d  pop     r13
0x18002a63f  pop     r12
0x18002a641  pop     rdi
0x18002a642  pop     rsi
0x18002a643  pop     rbx
0x18002a644  retn
0x18002a646  mov     rcx, [rsp+2B8h+var_268]
0x18002a64b  test    rcx, rcx
0x18002a64e  jz      short loc_18002A669
0x18002a650  or      eax, 0FFFFFFFFh
0x18002a653  lock xadd [rcx+2Ch], eax
0x18002a658  cmp     eax, 1
0x18002a65b  jnz     short loc_18002A669
0x18002a65d  xor     edx, edx; struct std::_Node_base *
0x18002a65f  mov     rcx, [rsp+2B8h+var_268]; struct std::_Node_base *
0x18002a664  call    ?_Destroy_node@std@@YAXPEAV_Node_base@1@0@Z; std::_Destroy_node(std::_Node_base *,std::_Node_base *)
0x18002a669  mov     [rsp+2B8h+var_268], r13
0x18002a66e  lea     rcx, [rsp+2B8h+var_250]; this
0x18002a673  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x18002a678  inc     esi
0x18002a67a  jmp     loc_18002A3AD
```
