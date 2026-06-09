# CflApiNew::DeserializeSessionContext(_GUID const *,ushort const *,ushort * *,uchar * *,ulong *,ushort * *,ulong *)

- ea: `0x180028cc4`
- end: `0x180029455`
- name: `?DeserializeSessionContext@CflApiNew@@YAJPEBU_GUID@@PEBGPEAPEAGPEAPEAEPEAK24@Z`
- size: `1937`
- prototype: `__int64 __fastcall(CflApiNew *__hidden this, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int16 **, unsigned int *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180010470`

## callees

- `0x180002490`
- `0x1800067c4`
- `0x1800071b4`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180010700`
- `0x1800132a8`
- `0x18001332c`
- `0x180016e28`
- `0x180016ed4`
- `0x180016fe0`
- `0x1800178d0`
- `0x180019fb8`
- `0x18001b0bc`
- `0x18001b3fc`
- `0x18001b49c`
- `0x180022448`
- `0x180022cf4`
- `0x180028034`
- `0x180028cc4`
- `0x18002c4a4`
- `0x18002c628`
- `0x18002dffc`

## string_xrefs

- `0x180028fb6`: `userSid`
- `0x180028ff4`: `userSid`
- `0x180029112`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180029178`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x1800291dc`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180029252`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x1800292d8`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180029394`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x180029414`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CflApiNew::DeserializeSessionContext(
        CflApiNew *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        unsigned __int16 **a7)
{
  unsigned __int8 **v9; // r15
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // rax
  __m128i v14; // xmm6
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rdx
  __int64 v19; // r8
  char v20; // bl
  __int64 v21; // rax
  __int64 v22; // rax
  char v23; // bl
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rax
  int v30; // r12d
  __int64 v31; // rdi
  int v32; // eax
  unsigned int v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // r8
  const unsigned __int16 *v36; // r8
  HLOCAL v37; // rbx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // r8
  unsigned int v41; // edi
  const void *v42; // rsi
  size_t v43; // r14
  HLOCAL v44; // rdi
  int v45; // eax
  HLOCAL v46; // rsi
  unsigned __int64 v47; // r15
  int v48; // eax
  unsigned int v49; // esi
  const unsigned __int16 *v50; // r8
  int v51; // eax
  unsigned int v52; // r15d
  unsigned __int16 *v53; // rax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // rdx
  __int64 v62; // rdx
  __int64 v63; // r8
  int v64; // [rsp+20h] [rbp-1D8h]
  int v65; // [rsp+20h] [rbp-1D8h]
  HLOCAL hMem; // [rsp+30h] [rbp-1C8h] BYREF
  _BYTE v67[8]; // [rsp+38h] [rbp-1C0h] BYREF
  HLOCAL v68; // [rsp+40h] [rbp-1B8h]
  void *Src[2]; // [rsp+48h] [rbp-1B0h] BYREF
  __int64 v70; // [rsp+58h] [rbp-1A0h]
  unsigned __int8 **v71; // [rsp+60h] [rbp-198h]
  unsigned __int16 **v72; // [rsp+68h] [rbp-190h]
  unsigned int *v73; // [rsp+70h] [rbp-188h]
  unsigned __int16 **v74; // [rsp+78h] [rbp-180h]
  _BYTE v75[56]; // [rsp+80h] [rbp-178h] BYREF
  __int64 v76; // [rsp+B8h] [rbp-140h]
  _BYTE v77[32]; // [rsp+C0h] [rbp-138h] BYREF
  HLOCAL v78[4]; // [rsp+E0h] [rbp-118h] BYREF
  unsigned __int16 *v79[2]; // [rsp+100h] [rbp-F8h] BYREF
  __int64 v80; // [rsp+110h] [rbp-E8h]
  unsigned __int64 v81; // [rsp+118h] [rbp-E0h]
  unsigned __int16 *v82[2]; // [rsp+120h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+130h] [rbp-C8h]
  _BYTE v84[32]; // [rsp+140h] [rbp-B8h] BYREF
  _BYTE v85[32]; // [rsp+160h] [rbp-98h] BYREF
  _BYTE v86[32]; // [rsp+180h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+0h]

  v72 = a4;
  v9 = a5;
  v71 = a5;
  v73 = a6;
  v74 = a7;
  if ( !this || !a2 || !a3 || !a6 )
  {
    v33 = -2147467261;
    v61 = 331;
    goto LABEL_63;
  }
  if ( !*(_QWORD *)this && *((_QWORD *)this + 1) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    goto LABEL_61;
  if ( a4 )
  {
    if ( a5 )
    {
      *(_QWORD *)a3 = 0;
      *a4 = 0;
      *(_DWORD *)a5 = 0;
      goto LABEL_67;
    }
    goto LABEL_61;
  }
  if ( a5 )
  {
LABEL_61:
    v33 = -2147024809;
    v61 = 333;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v61,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)v33,
      v65);
    return v33;
  }
  *(_QWORD *)a3 = 0;
LABEL_67:
  try
  {
    *(_QWORD *)a6 = 0;
    *(_DWORD *)a7 = 0;
    *(_OWORD *)v82 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v82[0]) = 0;
    *(_OWORD *)Src = 0;
    v70 = 0;
    *(_OWORD *)v79 = 0;
    v80 = 0;
    v81 = 7;
    LOWORD(v79[0]) = 0;
    v78[0] = v75;
    v76 = 0;
    std::wstring::wstring(v85, a2);
    v10 = anonymous_namespace_::Utf16ToUtf8_0(v86, v85);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::parse<std::string>(
      &hMem,
      v10,
      v75);
    std::string::~string(v86);
    std::wstring::~wstring(v85, v11, v12);
    std::string::string(v77, "providerId");
    v13 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
            &hMem,
            v77);
    v14 = *(__m128i *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<_GUID,_GUID,0>(
                        v13,
                        v78);
    std::string::~string(v77);
    std::string::string(v77, "scenarioId");
    v15 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
            &hMem,
            v77);
    v16 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
            v15,
            v84);
    v17 = anonymous_namespace_::Utf8ToUtf16_0(v78, v16);
    std::wstring::operator=(v82, v17);
    std::wstring::~wstring(v78, v18, v19);
    std::string::~string(v84);
    std::string::~string(v77);
    std::string::string(v77, "scenarioContext");
    v20 = *(_BYTE *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
                      &hMem,
                      v77);
    std::string::~string(v77);
    if ( v20 )
    {
      std::string::string(v77, "scenarioContext");
      v21 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
              &hMem,
              v77);
      v22 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::vector<unsigned char>,std::vector<unsigned char>,0>(
              v21,
              v78);
      std::vector<unsigned char>::operator=(Src, v22);
      std::vector<char>::~vector<char>(v78);
      std::string::~string(v77);
    }
    std::string::string(v77, "userSid");
    v23 = *(_BYTE *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
                      &hMem,
                      v77);
    std::string::~string(v77);
    if ( v23 )
    {
      std::string::string(v77, "userSid");
      v24 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
              &hMem,
              v77);
      v25 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
              v24,
              v78);
      v26 = anonymous_namespace_::Utf8ToUtf16_0(v84, v25);
      std::wstring::operator=(v79, v26);
      std::wstring::~wstring(v84, v27, v28);
      std::string::~string(v78);
      std::string::~string(v77);
    }
    std::string::string(v77, "currentSessionId");
    v29 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
            &hMem,
            v77);
    v30 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<unsigned long,unsigned long,0>(v29);
    std::string::~string(v77);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v67);
  }
  catch ( nlohmann::detail::out_of_range )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16E,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)0x80090005LL,
      v64);
    std::wstring::~wstring(v79, v62, v63);
    std::vector<char>::~vector<char>(Src);
    std::wstring::~wstring(v82, v59, v60);
    return 2148073477LL;
  }
  if ( *(_QWORD *)this != v14.m128i_i64[0] || *((_QWORD *)this + 1) != _mm_srli_si128(v14, 8).m128i_u64[0] )
  {
    v33 = -2147024894;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x171,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)0x80070002LL,
      v65);
LABEL_60:
    std::wstring::~wstring(v79, v34, v35);
    std::vector<char>::~vector<char>(Src);
    std::wstring::~wstring(v82, v57, v58);
    return v33;
  }
  v31 = si128.m128i_i64[0];
  hMem = 0;
  v32 = CflApiNew::AllocBuffer_unsigned_short_(si128.m128i_i64[0] + 1, &hMem);
  v33 = v32;
  if ( v32 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v32,
      v65);
    if ( hMem )
      CflFreeBuffer(hMem);
    goto LABEL_60;
  }
  v36 = (const unsigned __int16 *)v82;
  if ( si128.m128i_i64[1] > 7uLL )
    v36 = v82[0];
  v37 = hMem;
  v38 = StringCchCopyW((unsigned __int16 *)hMem, v31 + 1, v36);
  v41 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v38,
      v65);
LABEL_26:
    if ( v37 )
      CflFreeBuffer(v37);
    v33 = v41;
    goto LABEL_60;
  }
  v42 = Src[0];
  v43 = (char *)Src[1] - (char *)Src[0];
  v44 = 0;
  v68 = 0;
  if ( Src[0] != Src[1] )
  {
    v68 = 0;
    v45 = CflApiNew::AllocBuffer_unsigned_char_((char *)Src[1] - (char *)Src[0]);
    v41 = v45;
    if ( v45 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x17D,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v45,
        v65);
      if ( v68 )
        CflFreeBuffer(v68);
      goto LABEL_26;
    }
    v44 = v68;
    memcpy_0(v68, v42, v43);
  }
  v46 = 0;
  if ( v80 )
  {
    v47 = v80 + 1;
    v78[0] = 0;
    v48 = CflApiNew::AllocBuffer_unsigned_short_(v80 + 1, v78);
    v49 = v48;
    if ( v48 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v48,
        v65);
      if ( v78[0] )
        CflFreeBuffer(v78[0]);
      if ( v44 )
        CflFreeBuffer(v44);
      if ( v37 )
        CflFreeBuffer(v37);
      v33 = v49;
      goto LABEL_60;
    }
    v50 = (const unsigned __int16 *)v79;
    if ( v81 > 7 )
      v50 = v79[0];
    v46 = v78[0];
    v51 = StringCchCopyW((unsigned __int16 *)v78[0], v47, v50);
    v52 = v51;
    if ( v51 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x186,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v51,
        v65);
      if ( v46 )
        CflFreeBuffer(v46);
      if ( v44 )
        CflFreeBuffer(v44);
      if ( v37 )
        CflFreeBuffer(v37);
      v33 = v52;
      goto LABEL_60;
    }
    v9 = v71;
  }
  *(_QWORD *)a3 = v37;
  if ( v72 )
  {
    v53 = (unsigned __int16 *)v44;
    v44 = 0;
    *v72 = v53;
    *(_DWORD *)v9 = v43;
  }
  *(_QWORD *)v73 = v46;
  *(_DWORD *)v74 = v30;
  if ( v44 )
    CflFreeBuffer(v44);
  std::wstring::~wstring(v79, v39, v40);
  std::vector<char>::~vector<char>(Src);
  std::wstring::~wstring(v82, v54, v55);
  return 0;
}

```

## disassembly

```asm
0x180028cc4  mov     rax, rsp
0x180028cc7  push    rbx
0x180028cc8  push    rsi
0x180028cc9  push    rdi
0x180028cca  push    r12
0x180028ccc  push    r13
0x180028cce  push    r14
0x180028cd0  push    r15
0x180028cd2  sub     rsp, 1C0h
0x180028cd9  movaps  xmmword ptr [rax-48h], xmm6
0x180028cdd  mov     rax, cs:__security_cookie
0x180028ce4  xor     rax, rsp
0x180028ce7  mov     [rsp+1F8h+var_58], rax
0x180028cef  mov     [rsp+1F8h+var_190], r9
0x180028cf4  mov     r13, r8
0x180028cf7  mov     rdi, rcx
0x180028cfa  mov     r15, [rsp+1F8h+arg_20]
0x180028d02  mov     [rsp+1F8h+var_198], r15
0x180028d07  mov     rcx, [rsp+1F8h+arg_28]
0x180028d0f  mov     [rsp+1F8h+var_188], rcx
0x180028d14  mov     r8, [rsp+1F8h+arg_30]
0x180028d1c  mov     [rsp+1F8h+var_180], r8
0x180028d21  xor     esi, esi
0x180028d23  test    rdi, rdi
0x180028d26  jz      loc_180029407
0x180028d2c  test    rdx, rdx
0x180028d2f  jz      loc_180029407
0x180028d35  test    r13, r13
0x180028d38  jz      loc_180029407
0x180028d3e  test    rcx, rcx
0x180028d41  jz      loc_180029407
0x180028d47  xorps   xmm0, xmm0
0x180028d4a  movq    rax, xmm0
0x180028d4f  cmp     [rdi], rax
0x180028d52  jnz     short loc_180028D68
0x180028d54  psrldq  xmm0, 8
0x180028d59  movq    rax, xmm0
0x180028d5e  cmp     [rdi+8], rax
0x180028d62  jz      loc_1800293FB
0x180028d68  test    r9, r9
0x180028d6b  jz      short loc_180028D82
0x180028d6d  test    r15, r15
0x180028d70  jz      loc_1800293FB
0x180028d76  mov     [r13+0], rsi
0x180028d7a  mov     [r9], rsi
0x180028d7d  mov     [r15], esi
0x180028d80  jmp     short loc_180028D8F
0x180028d82  test    r15, r15
0x180028d85  jnz     loc_1800293FB
0x180028d8b  mov     [r13+0], rsi
0x180028d8f  mov     [rcx], rsi
0x180028d92  mov     [r8], esi
0x180028d95  xorps   xmm0, xmm0
0x180028d98  movups  xmmword ptr [rsp+1F8h+var_D8], xmm0
0x180028da0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180028da8  movdqu  [rsp+1F8h+var_C8], xmm1
0x180028db1  mov     word ptr [rsp+1F8h+var_D8], si
0x180028db9  movdqu  xmmword ptr [rsp+1F8h+Src], xmm0
0x180028dbf  mov     [rsp+1F8h+var_1A0], rsi
0x180028dc4  movups  xmmword ptr [rsp+1F8h+var_F8], xmm0
0x180028dcc  mov     [rsp+1F8h+var_E8], rsi
0x180028dd4  mov     [rsp+1F8h+var_E0], 7
0x180028de0  mov     word ptr [rsp+1F8h+var_F8], si
0x180028de8  lea     rax, [rsp+1F8h+var_178]
0x180028df0  mov     [rsp+1F8h+var_118], rax
0x180028df8  mov     [rsp+1F8h+var_140], rsi
0x180028e00  lea     rcx, [rsp+1F8h+var_98]
0x180028e08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180028e0d  nop
0x180028e0e  lea     rdx, [rsp+1F8h+var_98]
0x180028e16  lea     rcx, [rsp+1F8h+var_78]
0x180028e1e  call    _anonymous_namespace___Utf16ToUtf8_0
0x180028e23  nop
0x180028e24  lea     r8, [rsp+1F8h+var_178]
0x180028e2c  mov     rdx, rax
0x180028e2f  lea     rcx, [rsp+1F8h+hMem]
0x180028e34  call    ??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@SA?AV01@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z@3@_N2@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::parse<std::string>(std::string &&,std::function<bool (int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x180028e39  nop
0x180028e3a  lea     rcx, [rsp+1F8h+var_78]
0x180028e42  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028e47  nop
0x180028e48  lea     rcx, [rsp+1F8h+var_98]
0x180028e50  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028e55  lea     rdx, aProviderid_0; "providerId"
0x180028e5c  lea     rcx, [rsp+1F8h+var_138]
0x180028e64  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028e69  nop
0x180028e6a  lea     rdx, [rsp+1F8h+var_138]
0x180028e72  lea     rcx, [rsp+1F8h+hMem]
0x180028e77  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x180028e7c  lea     rdx, [rsp+1F8h+var_118]
0x180028e84  mov     rcx, rax
0x180028e87  call    ??$get@U_GUID@@U1@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AU_GUID@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<_GUID,_GUID,0>(void)
0x180028e8c  movups  xmm6, xmmword ptr [rax]
0x180028e8f  lea     rcx, [rsp+1F8h+var_138]
0x180028e97  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028e9c  lea     rdx, aScenarioid_0; "scenarioId"
0x180028ea3  lea     rcx, [rsp+1F8h+var_138]
0x180028eab  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028eb0  nop
0x180028eb1  lea     rdx, [rsp+1F8h+var_138]
0x180028eb9  lea     rcx, [rsp+1F8h+hMem]
0x180028ebe  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x180028ec3  lea     rdx, [rsp+1F8h+var_B8]
0x180028ecb  mov     rcx, rax
0x180028ece  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x180028ed3  nop
0x180028ed4  mov     rdx, rax
0x180028ed7  lea     rcx, [rsp+1F8h+var_118]
0x180028edf  call    _anonymous_namespace___Utf8ToUtf16_0
0x180028ee4  mov     rdx, rax
0x180028ee7  lea     rcx, [rsp+1F8h+var_D8]
0x180028eef  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180028ef4  lea     rcx, [rsp+1F8h+var_118]
0x180028efc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028f01  nop
0x180028f02  lea     rcx, [rsp+1F8h+var_B8]
0x180028f0a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028f0f  nop
0x180028f10  lea     rcx, [rsp+1F8h+var_138]
0x180028f18  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028f1d  lea     rdx, aScenariocontex_0; "scenarioContext"
0x180028f24  lea     rcx, [rsp+1F8h+var_138]
0x180028f2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028f31  nop
0x180028f32  lea     rdx, [rsp+1F8h+var_138]
0x180028f3a  lea     rcx, [rsp+1F8h+hMem]
0x180028f3f  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x180028f44  mov     bl, [rax]
0x180028f46  lea     rcx, [rsp+1F8h+var_138]
0x180028f4e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028f53  test    bl, bl
0x180028f55  jz      short loc_180028FB6
0x180028f57  lea     rdx, aScenariocontex_0; "scenarioContext"
0x180028f5e  lea     rcx, [rsp+1F8h+var_138]
0x180028f66  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028f6b  nop
0x180028f6c  lea     rdx, [rsp+1F8h+var_138]
0x180028f74  lea     rcx, [rsp+1F8h+hMem]
0x180028f79  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x180028f7e  lea     rdx, [rsp+1F8h+var_118]
0x180028f86  mov     rcx, rax
0x180028f89  call    ??$get@V?$vector@EV?$allocator@E@std@@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::vector<uchar>,std::vector<uchar>,0>(void)
0x180028f8e  mov     rdx, rax
0x180028f91  lea     rcx, [rsp+1F8h+Src]
0x180028f96  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180028f9b  lea     rcx, [rsp+1F8h+var_118]
0x180028fa3  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x180028fa8  nop
0x180028fa9  lea     rcx, [rsp+1F8h+var_138]
0x180028fb1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028fb6  lea     rdx, aUsersid; "userSid"
0x180028fbd  lea     rcx, [rsp+1F8h+var_138]
0x180028fc5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180028fca  nop
0x180028fcb  lea     rdx, [rsp+1F8h+var_138]
0x180028fd3  lea     rcx, [rsp+1F8h+hMem]
0x180028fd8  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x180028fdd  mov     bl, [rax]
0x180028fdf  lea     rcx, [rsp+1F8h+var_138]
0x180028fe7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180028fec  test    bl, bl
0x180028fee  jz      loc_180029075
0x180028ff4  lea     rdx, aUsersid; "userSid"
0x180028ffb  lea     rcx, [rsp+1F8h+var_138]
0x180029003  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180029008  nop
0x180029009  lea     rdx, [rsp+1F8h+var_138]
0x180029011  lea     rcx, [rsp+1F8h+hMem]
0x180029016  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18002901b  lea     rdx, [rsp+1F8h+var_118]
0x180029023  mov     rcx, rax
0x180029026  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x18002902b  nop
0x18002902c  mov     rdx, rax
0x18002902f  lea     rcx, [rsp+1F8h+var_B8]
0x180029037  call    _anonymous_namespace___Utf8ToUtf16_0
0x18002903c  mov     rdx, rax
0x18002903f  lea     rcx, [rsp+1F8h+var_F8]
0x180029047  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002904c  lea     rcx, [rsp+1F8h+var_B8]
0x180029054  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029059  nop
0x18002905a  lea     rcx, [rsp+1F8h+var_118]
0x180029062  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180029067  nop
0x180029068  lea     rcx, [rsp+1F8h+var_138]
0x180029070  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180029075  lea     rdx, aCurrentsession; "currentSessionId"
0x18002907c  lea     rcx, [rsp+1F8h+var_138]
0x180029084  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180029089  nop
0x18002908a  lea     rdx, [rsp+1F8h+var_138]
0x180029092  lea     rcx, [rsp+1F8h+hMem]
0x180029097  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18002909c  mov     rcx, rax
0x18002909f  call    ??$get@KK$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBAKXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<ulong,ulong,0>(void)
0x1800290a4  mov     r12d, eax
0x1800290a7  lea     rcx, [rsp+1F8h+var_138]
0x1800290af  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800290b4  nop
0x1800290b5  mov     dl, byte ptr [rsp+1F8h+hMem]
0x1800290b9  lea     rcx, [rsp+1F8h+var_1C0]
0x1800290be  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800290c3  nop
0x1800290c4  movq    rax, xmm6
0x1800290c9  cmp     [rdi], rax
0x1800290cc  jnz     loc_180029384
0x1800290d2  psrldq  xmm6, 8
0x1800290d7  movq    rax, xmm6
0x1800290dc  cmp     [rdi+8], rax
0x1800290e0  jnz     loc_180029384
0x1800290e6  mov     rdi, qword ptr [rsp+1F8h+var_C8]
0x1800290ee  mov     [rsp+1F8h+hMem], rsi
0x1800290f3  lea     rdx, [rsp+1F8h+hMem]
0x1800290f8  lea     rcx, [rdi+1]
0x1800290fc  call    CflApiNew__AllocBuffer_unsigned_short_
0x180029101  mov     ebx, eax
0x180029103  test    eax, eax
0x180029105  jns     short loc_18002913C
0x180029107  mov     rcx, [rsp+1F8h]; this
0x18002910f  mov     r9d, eax; char *
0x180029112  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180029119  mov     edx, 176h; void *
0x18002911e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029123  nop
0x180029124  mov     rcx, [rsp+1F8h+hMem]; hMem
0x180029129  test    rcx, rcx
0x18002912c  jz      loc_1800293A6
0x180029132  call    CflFreeBuffer
0x180029137  jmp     loc_1800293A6
0x18002913c  lea     r8, [rsp+1F8h+var_D8]
0x180029144  cmp     qword ptr [rsp+1F8h+var_C8+8], 7
0x18002914d  cmova   r8, [rsp+1F8h+var_D8]; unsigned __int16 *
0x180029156  lea     rdx, [rdi+1]; unsigned __int64
0x18002915a  mov     rbx, [rsp+1F8h+hMem]
0x18002915f  mov     rcx, rbx; unsigned __int16 *
0x180029162  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180029167  mov     edi, eax
0x180029169  test    eax, eax
0x18002916b  jns     short loc_18002919E
0x18002916d  mov     rcx, [rsp+1F8h]; this
0x180029175  mov     r9d, eax; char *
0x180029178  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002917f  mov     edx, 177h; void *
0x180029184  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029189  nop
0x18002918a  test    rbx, rbx
0x18002918d  jz      short loc_180029197
0x18002918f  mov     rcx, rbx; hMem
0x180029192  call    CflFreeBuffer
0x180029197  mov     ebx, edi
0x180029199  jmp     loc_1800293A6
0x18002919e  mov     rsi, [rsp+1F8h+Src]
0x1800291a3  mov     r14, [rsp+1F8h+Src+8]
0x1800291a8  sub     r14, rsi
0x1800291ab  xor     edi, edi
0x1800291ad  mov     [rsp+1F8h+var_1B8], rdi
0x1800291b2  cmp     rsi, [rsp+1F8h+Src+8]
0x1800291b7  jz      short loc_180029212
0x1800291b9  mov     [rsp+1F8h+var_1B8], rdi
0x1800291be  lea     rdx, [rsp+1F8h+var_1B8]
0x1800291c3  mov     rcx, r14; uBytes
0x1800291c6  call    CflApiNew__AllocBuffer_unsigned_char_
0x1800291cb  mov     edi, eax
0x1800291cd  test    eax, eax
0x1800291cf  jns     short loc_1800291FF
0x1800291d1  mov     rcx, [rsp+1F8h]; this
0x1800291d9  mov     r9d, eax; char *
0x1800291dc  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x1800291e3  mov     edx, 17Dh; void *
0x1800291e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800291ed  nop
0x1800291ee  mov     rcx, [rsp+1F8h+var_1B8]; hMem
0x1800291f3  test    rcx, rcx
0x1800291f6  jz      short loc_18002918A
0x1800291f8  call    CflFreeBuffer
0x1800291fd  jmp     short loc_18002918A
0x1800291ff  mov     r8, r14; Size
0x180029202  mov     rdx, rsi; Src
0x180029205  mov     rdi, [rsp+1F8h+var_1B8]
0x18002920a  mov     rcx, rdi; void *
0x18002920d  call    memcpy_0
0x180029212  xor     esi, esi
0x180029214  mov     rax, [rsp+1F8h+var_E8]
0x18002921c  test    rax, rax
0x18002921f  jz      loc_180029320
0x180029225  lea     r15, [rax+1]
0x180029229  mov     [rsp+1F8h+var_118], rsi
0x180029231  lea     rdx, [rsp+1F8h+var_118]
0x180029239  mov     rcx, r15
0x18002923c  call    CflApiNew__AllocBuffer_unsigned_short_
0x180029241  mov     esi, eax
0x180029243  test    eax, eax
0x180029245  jns     short loc_180029299
0x180029247  mov     rcx, [rsp+1F8h]; this
0x18002924f  mov     r9d, eax; char *
0x180029252  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x180029259  mov     edx, 185h; void *
0x18002925e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
