# ReplaceAnonymousIdentity(ushort const *,ushort const *,ushort * *)

- ea: `0x1800282f4`
- end: `0x180028712`
- name: `?ReplaceAnonymousIdentity@@YAJPEBG0PEAPEAG@Z`
- size: `1054`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180076954`

## callees

- `0x1800273fc`
- `0x18002756c`
- `0x18002813c`
- `0x1800281f4`
- `0x1800282f4`
- `0x180028718`
- `0x180028728`
- `0x180028768`
- `0x180028810`
- `0x18002885c`
- `0x1800288f4`
- `0x180028aa8`
- `0x180028f5c`
- `0x180029014`
- `0x180029094`
- `0x18002b7b4`
- `0x18003225c`
- `0x180032f2c`
- `0x1800333f0`
- `0x180035680`
- `0x180047e00`
- `0x1800751c0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002867f`

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
  std::wstring::_Construct<1,unsigned short const *>(&v35, a2, v6);
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
    std::wstring::_Construct<1,unsigned short const *>(&Src, L"$01", 3);
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
0x1800282f4  push    rbx
0x1800282f6  push    rsi
0x1800282f7  push    rdi
0x1800282f8  push    r12
0x1800282fa  push    r13
0x1800282fc  push    r14
0x1800282fe  push    r15
0x180028300  sub     rsp, 280h
0x180028307  mov     rax, cs:__security_cookie
0x18002830e  xor     rax, rsp
0x180028311  mov     [rsp+2B8h+var_48], rax
0x180028319  mov     r12, r8
0x18002831c  mov     rdi, rdx
0x18002831f  mov     r15, rcx
0x180028322  xor     r13d, r13d
0x180028325  mov     [r8], r13
0x180028328  xorps   xmm0, xmm0
0x18002832b  movups  [rsp+2B8h+var_A8], xmm0
0x180028333  mov     [rsp+2B8h+var_98], r13
0x18002833b  mov     [rsp+2B8h+var_90], r13
0x180028343  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180028347  mov     r8, rsi
0x18002834a  inc     r8
0x18002834d  cmp     [rdx+r8*2], r13w
0x180028352  jnz     short loc_18002834A
0x180028354  lea     rcx, [rsp+2B8h+var_A8]
0x18002835c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180028361  nop
0x180028362  mov     rbx, r13
0x180028365  mov     [rsp+2B8h+var_270], rbx
0x18002836a  lea     rcx, [rsp+2B8h+var_A8]
0x180028372  cmp     [rsp+2B8h+var_90], 7
0x18002837b  cmova   rcx, qword ptr [rsp+2B8h+var_A8]
0x180028384  mov     r9d, 5Ch ; '\'
0x18002838a  mov     rdx, [rsp+2B8h+var_98]
0x180028392  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x180028397  cmp     rax, rsi
0x18002839a  jnz     loc_180028641
0x1800283a0  lea     rcx, [rsp+2B8h+var_A8]
0x1800283a8  cmp     [rsp+2B8h+var_90], 7
0x1800283b1  cmova   rcx, qword ptr [rsp+2B8h+var_A8]
0x1800283ba  mov     r9d, 40h ; '@'
0x1800283c0  mov     rdx, [rsp+2B8h+var_98]
0x1800283c8  call    ??$_Traits_find_ch@U?$char_traits@G@std@@@std@@YA_KQEBG_K1G@Z; std::_Traits_find_ch<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort)
0x1800283cd  cmp     rax, rsi
0x1800283d0  jnz     loc_180028641
0x1800283d6  mov     r14b, r13b
0x1800283d9  xorps   xmm0, xmm0
0x1800283dc  movups  [rsp+2B8h+Src], xmm0
0x1800283e4  xorps   xmm1, xmm1
0x1800283e7  movdqu  [rsp+2B8h+var_78], xmm1
0x1800283f0  mov     r8d, 3
0x1800283f6  lea     rdx, a01; "$01"
0x1800283fd  lea     rcx, [rsp+2B8h+Src]
0x180028405  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002840a  nop
0x18002840b  mov     r8, rsi
0x18002840e  inc     r8
0x180028411  cmp     [rdi+r8*2], r13w
0x180028416  jnz     short loc_18002840E
0x180028418  mov     rdx, rdi
0x18002841b  lea     rcx, [rsp+2B8h+Src]; Src
0x180028423  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180028428  mov     r8d, 3
0x18002842e  lea     rdx, a03; "$03"
0x180028435  lea     rcx, [rsp+2B8h+Src]; Src
0x18002843d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180028442  mov     esi, r13d
0x180028445  cmp     esi, 7
0x180028448  jnb     loc_1800285D7
0x18002844e  mov     eax, esi
0x180028450  lea     rdi, ?idPrivacyPatterns@@3PAPEBGA; ushort const * near * idPrivacyPatterns
0x180028457  mov     rdi, [rdi+rax*8]
0x18002845b  mov     [rsp+2B8h+var_268], r13
0x180028460  lea     rcx, [rsp+2B8h+var_260]
0x180028465  call    ??0?$regex_traits@G@std@@QEAA@XZ; std::regex_traits<ushort>::regex_traits<ushort>(void)
0x18002846a  nop
0x18002846b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002846f  inc     rax
0x180028472  cmp     [rdi+rax*2], r13w
0x180028477  jnz     short loc_18002846F
0x180028479  lea     r9, [rdi+rax*2]
0x18002847d  mov     r8, rdi
0x180028480  lea     rdx, [rsp+2B8h+var_260]
0x180028485  lea     rcx, [rsp+2B8h+var_238]
0x18002848d  call    ??0?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAA@AEBV?$regex_traits@G@1@PEBG1W4syntax_option_type@regex_constants@1@@Z; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>(std::regex_traits<ushort> const &,ushort const *,ushort const *,std::regex_constants::syntax_option_type)
0x180028492  nop
0x180028493  lea     rcx, [rsp+2B8h+var_238]
0x18002849b  call    ?_Compile@?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAAPEAV_Root_node@2@XZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::_Compile(void)
0x1800284a0  mov     rdi, rax
0x1800284a3  test    rax, rax
0x1800284a6  jz      short loc_1800284AC
0x1800284a8  lock inc dword ptr [rax+2Ch]
0x1800284ac  mov     rcx, [rsp+2B8h+var_268]
0x1800284b1  test    rcx, rcx
0x1800284b4  jz      short loc_1800284CF
0x1800284b6  or      eax, 0FFFFFFFFh
0x1800284b9  lock xadd [rcx+2Ch], eax
0x1800284be  cmp     eax, 1
0x1800284c1  jnz     short loc_1800284CF
0x1800284c3  xor     edx, edx; struct std::_Node_base *
0x1800284c5  mov     rcx, [rsp+2B8h+var_268]; struct std::_Node_base *
0x1800284ca  call    ?_Destroy_node@std@@YAXPEAV_Node_base@1@0@Z; std::_Destroy_node(std::_Node_base *,std::_Node_base *)
0x1800284cf  mov     [rsp+2B8h+var_268], rdi
0x1800284d4  lea     rcx, [rsp+2B8h+var_238]
0x1800284dc  call    ??1?$_Parser2@PEBGGV?$regex_traits@G@std@@@std@@QEAA@XZ; std::_Parser2<ushort const *,ushort,std::regex_traits<ushort>>::~_Parser2<ushort const *,ushort,std::regex_traits<ushort>>(void)
0x1800284e1  nop
0x1800284e2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800284e6  inc     rax
0x1800284e9  cmp     [r15+rax*2], r13w
0x1800284ee  jnz     short loc_1800284E6
0x1800284f0  mov     rcx, [rsp+2B8h+var_268]
0x1800284f5  test    rcx, rcx
0x1800284f8  jz      loc_1800286DC
0x1800284fe  lea     r8, [r15+rax*2]
0x180028502  mov     [rsp+2B8h+var_280], 10h
0x18002850a  mov     eax, [rcx+20h]
0x18002850d  mov     [rsp+2B8h+var_288], eax
0x180028511  mov     eax, [rcx+28h]
0x180028514  mov     [rsp+2B8h+var_290], eax
0x180028518  mov     qword ptr [rsp+2B8h+var_298], rcx; int
0x18002851d  lea     r9, [rsp+2B8h+var_260]
0x180028522  mov     rdx, r15
0x180028525  lea     rcx, [rsp+2B8h+var_1B8]
0x18002852d  call    ??0?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA@PEBG0AEBV?$regex_traits@G@1@PEAV_Root_node@1@IW4syntax_option_type@regex_constants@1@W4match_flag_type@51@@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>(ushort const *,ushort const *,std::regex_traits<ushort> const &,std::_Root_node *,uint,std::regex_constants::syntax_option_type,std::regex_constants::match_flag_type)
0x180028532  nop
0x180028533  mov     r8b, 1
0x180028536  xor     edx, edx
0x180028538  lea     rcx, [rsp+2B8h+var_1B8]
0x180028540  call    ??$_Match@V?$allocator@V?$sub_match@PEBG@std@@@std@@@?$_Matcher2@PEBGGV?$regex_traits@G@std@@PEBGX@std@@QEAA_NPEAV?$match_results@PEBGV?$allocator@V?$sub_match@PEBG@std@@@std@@@1@_N@Z; std::_Matcher2<ushort const *,ushort,std::regex_traits<ushort>,ushort const *,void>::_Match<std::allocator<std::sub_match<ushort const *>>>(std::match_results<ushort const *> *,bool)
0x180028545  mov     dil, al
0x180028548  lea     rcx, [rsp+2B8h+var_1B8]
0x180028550  call    ??1?$_Matcher2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@GV?$regex_traits@G@2@V12@X@std@@QEAA@XZ; std::_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>::~_Matcher2<std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort,std::regex_traits<ushort>,std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>,void>(void)
0x180028555  test    dil, dil
0x180028558  jz      loc_1800286D7
0x18002855e  lea     r9, [rsp+2B8h+Src]
0x180028566  lea     r8, [rsp+2B8h+var_268]
0x18002856b  mov     rdx, r15
0x18002856e  lea     rcx, [rsp+2B8h+var_68]
0x180028576  call    ??$regex_replace@V?$regex_traits@G@std@@GU?$char_traits@G@2@V?$allocator@G@2@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@PEBGAEBV?$basic_regex@GV?$regex_traits@G@std@@@0@AEBV10@W4match_flag_type@regex_constants@0@@Z; std::regex_replace<std::regex_traits<ushort>,ushort,std::char_traits<ushort>,std::allocator<ushort>>(ushort const *,std::basic_regex<ushort,std::regex_traits<ushort>> const &,std::wstring const &,std::regex_constants::match_flag_type)
0x18002857b  nop
0x18002857c  lea     rdx, [rsp+2B8h+var_68]
0x180028584  cmp     [rsp+2B8h+var_50], 7
0x18002858d  cmova   rdx, [rsp+2B8h+var_68]
0x180028596  lea     rcx, [rsp+2B8h+hMem]
0x18002859b  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800285a0  mov     rdx, rax
0x1800285a3  lea     rcx, [rsp+2B8h+var_270]
0x1800285a8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x1800285ad  lea     rcx, [rsp+2B8h+hMem]
0x1800285b2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800285b7  mov     r14b, 1
0x1800285ba  lea     rcx, [rsp+2B8h+var_68]
0x1800285c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800285c7  nop
0x1800285c8  lea     rcx, [rsp+2B8h+var_268]
0x1800285cd  call    ??1?$basic_regex@GV?$regex_traits@G@std@@@std@@QEAA@XZ; std::basic_regex<ushort,std::regex_traits<ushort>>::~basic_regex<ushort,std::regex_traits<ushort>>(void)
0x1800285d2  mov     rbx, [rsp+2B8h+var_270]
0x1800285d7  mov     rdx, qword ptr [rsp+2B8h+var_78+8]
0x1800285df  cmp     rdx, 7
0x1800285e3  jbe     short loc_1800285FA
0x1800285e5  lea     rdx, ds:2[rdx*2]
0x1800285ed  mov     rcx, qword ptr [rsp+2B8h+Src]
0x1800285f5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800285fa  test    r14b, r14b
0x1800285fd  jnz     loc_180028685
0x180028603  mov     rcx, [rsp+2B8h]; this
0x18002860b  mov     ebx, 80070057h
0x180028610  mov     r9d, ebx; char *
0x180028613  lea     r8, aOnecoreuapNetR_2; "onecoreuap\\net\\rras\\ras\\ppp\\eaptls"...
0x18002861a  mov     edx, 75h ; 'u'; void *
0x18002861f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028624  nop
0x180028625  lea     rcx, [rsp+2B8h+var_270]
0x18002862a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002862f  nop
0x180028630  lea     rcx, [rsp+2B8h+var_A8]
0x180028638  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002863d  mov     eax, ebx
0x18002863f  jmp     short loc_1800286B4
0x180028641  lea     rdx, [rsp+2B8h+var_A8]
0x180028649  cmp     [rsp+2B8h+var_90], 7
0x180028652  cmova   rdx, qword ptr [rsp+2B8h+var_A8]
0x18002865b  lea     rcx, [rsp+2B8h+hMem]
0x180028660  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180028665  lea     rcx, [rsp+2B8h+var_270]
0x18002866a  cmp     rcx, rax
0x18002866d  jz      short loc_180028675
0x18002866f  mov     rbx, [rax]
0x180028672  mov     [rax], r13
0x180028675  mov     rcx, [rsp+2B8h+hMem]; hMem
0x18002867a  test    rcx, rcx
0x18002867d  jz      short loc_180028685
0x18002867f  call    cs:__imp_LocalFree
0x180028685  mov     [r12], rbx
0x180028689  mov     rdx, [rsp+2B8h+var_90]
0x180028691  cmp     rdx, 7
0x180028695  jbe     short loc_1800286AC
0x180028697  lea     rdx, ds:2[rdx*2]
0x18002869f  mov     rcx, qword ptr [rsp+2B8h+var_A8]
0x1800286a7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800286ac  xor     eax, eax
0x1800286ae  jmp     short loc_1800286B4
0x1800286b0  mov     eax, dword ptr [rsp+2B8h+hMem]
0x1800286b4  mov     rcx, [rsp+2B8h+var_48]
0x1800286bc  xor     rcx, rsp; StackCookie
0x1800286bf  call    __security_check_cookie
0x1800286c4  add     rsp, 280h
0x1800286cb  pop     r15
0x1800286cd  pop     r14
0x1800286cf  pop     r13
0x1800286d1  pop     r12
0x1800286d3  pop     rdi
0x1800286d4  pop     rsi
0x1800286d5  pop     rbx
0x1800286d6  retn
0x1800286d7  mov     rcx, [rsp+2B8h+var_268]
0x1800286dc  test    rcx, rcx
0x1800286df  jz      short loc_1800286FA
0x1800286e1  or      eax, 0FFFFFFFFh
0x1800286e4  lock xadd [rcx+2Ch], eax
0x1800286e9  cmp     eax, 1
0x1800286ec  jnz     short loc_1800286FA
0x1800286ee  xor     edx, edx; struct std::_Node_base *
0x1800286f0  mov     rcx, [rsp+2B8h+var_268]; struct std::_Node_base *
0x1800286f5  call    ?_Destroy_node@std@@YAXPEAV_Node_base@1@0@Z; std::_Destroy_node(std::_Node_base *,std::_Node_base *)
0x1800286fa  mov     [rsp+2B8h+var_268], r13
0x1800286ff  lea     rcx, [rsp+2B8h+var_250]; this
0x180028704  call    ??1locale@std@@QEAA@XZ; std::locale::~locale(void)
0x180028709  inc     esi
0x18002870b  jmp     loc_180028445
```
