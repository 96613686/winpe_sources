# CflApi::DeserializeSessionContext(_GUID const *,ushort const *,ushort * *,uchar * *,ulong *,ushort * *)

- ea: `0x18001cb44`
- end: `0x18001d268`
- name: `?DeserializeSessionContext@CflApi@@YAJPEBU_GUID@@PEBGPEAPEAGPEAPEAEPEAK2@Z`
- size: `1828`
- prototype: `__int64 __fastcall(CflApi *__hidden this, const struct _GUID *, const unsigned __int16 *, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800102f0`

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
- `0x18001cb44`
- `0x180021000`
- `0x180021184`
- `0x180022448`
- `0x180022cf4`
- `0x18002dffc`

## string_xrefs

- `0x18001ce1d`: `userSid`
- `0x18001ce5b`: `userSid`
- `0x18001cf3a`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001cfa0`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001cffe`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001d074`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001d0fa`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001d1a7`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001d227`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
__int64 __fastcall CflApi::DeserializeSessionContext(
        CflApi *this,
        const struct _GUID *a2,
        unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned __int16 **v6; // r15
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rax
  __m128i v13; // xmm6
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  char v19; // bl
  __int64 v20; // rax
  __int64 v21; // rax
  char v22; // bl
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rdi
  int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  HLOCAL v33; // rcx
  const unsigned __int16 *v34; // r8
  unsigned __int64 v35; // rdx
  HLOCAL v36; // rdi
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // r8
  const void *v40; // rsi
  size_t v41; // r14
  HLOCAL v42; // rbx
  int v43; // eax
  HLOCAL v44; // rsi
  unsigned __int64 v45; // r15
  int v46; // eax
  unsigned int v47; // esi
  const unsigned __int16 *v48; // r8
  int v49; // eax
  unsigned int v50; // r15d
  unsigned __int16 *v51; // rax
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // r8
  int v62; // [rsp+20h] [rbp-1C8h]
  int v63; // [rsp+20h] [rbp-1C8h]
  HLOCAL hMem; // [rsp+30h] [rbp-1B8h] BYREF
  _BYTE v65[8]; // [rsp+38h] [rbp-1B0h] BYREF
  HLOCAL v66; // [rsp+40h] [rbp-1A8h]
  void *Src[2]; // [rsp+48h] [rbp-1A0h] BYREF
  __int64 v68; // [rsp+58h] [rbp-190h]
  unsigned __int16 **v69; // [rsp+60h] [rbp-188h]
  unsigned int *v70; // [rsp+68h] [rbp-180h]
  _BYTE v71[56]; // [rsp+70h] [rbp-178h] BYREF
  __int64 v72; // [rsp+A8h] [rbp-140h]
  _BYTE v73[32]; // [rsp+B0h] [rbp-138h] BYREF
  HLOCAL v74[4]; // [rsp+D0h] [rbp-118h] BYREF
  unsigned __int16 *v75[2]; // [rsp+F0h] [rbp-F8h] BYREF
  __int64 v76; // [rsp+100h] [rbp-E8h]
  unsigned __int64 v77; // [rsp+108h] [rbp-E0h]
  unsigned __int16 *v78[2]; // [rsp+110h] [rbp-D8h] BYREF
  __m128i si128; // [rsp+120h] [rbp-C8h]
  _BYTE v80[32]; // [rsp+130h] [rbp-B8h] BYREF
  _BYTE v81[32]; // [rsp+150h] [rbp-98h] BYREF
  _BYTE v82[32]; // [rsp+170h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+0h]

  v6 = a4;
  v69 = a4;
  v70 = a6;
  if ( !this || !a2 || !a3 || !a6 )
  {
    v30 = -2147467261;
    v59 = 614;
    goto LABEL_62;
  }
  if ( !*(_QWORD *)this && *((_QWORD *)this + 1) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
    goto LABEL_60;
  if ( a4 )
  {
    if ( a5 )
    {
      *(_QWORD *)a3 = 0;
      *a4 = 0;
      *(_DWORD *)a5 = 0;
      goto LABEL_66;
    }
    goto LABEL_60;
  }
  if ( a5 )
  {
LABEL_60:
    v30 = -2147024809;
    v59 = 616;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v59,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)v30,
      v63);
    return v30;
  }
  *(_QWORD *)a3 = 0;
LABEL_66:
  try
  {
    *(_QWORD *)a6 = 0;
    *(_OWORD *)v78 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v78[0]) = 0;
    *(_OWORD *)Src = 0;
    v68 = 0;
    *(_OWORD *)v75 = 0;
    v76 = 0;
    v77 = 7;
    LOWORD(v75[0]) = 0;
    v74[0] = v71;
    v72 = 0;
    std::wstring::wstring(v81, a2);
    v9 = anonymous_namespace_::Utf16ToUtf8(v82, v81);
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::parse<std::string>(
      &hMem,
      v9,
      v71);
    std::string::~string(v82);
    std::wstring::~wstring(v81, v10, v11);
    std::string::string(v73, "providerId");
    v12 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
            &hMem,
            v73);
    v13 = *(__m128i *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<_GUID,_GUID,0>(
                        v12,
                        v74);
    std::string::~string(v73);
    std::string::string(v73, "scenarioId");
    v14 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
            &hMem,
            v73);
    v15 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
            v14,
            v80);
    v16 = anonymous_namespace_::Utf8ToUtf16(v74, v15);
    std::wstring::operator=(v78, v16);
    std::wstring::~wstring(v74, v17, v18);
    std::string::~string(v80);
    std::string::~string(v73);
    std::string::string(v73, "scenarioContext");
    v19 = *(_BYTE *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
                      &hMem,
                      v73);
    std::string::~string(v73);
    if ( v19 )
    {
      std::string::string(v73, "scenarioContext");
      v20 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
              &hMem,
              v73);
      v21 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::vector<unsigned char>,std::vector<unsigned char>,0>(
              v20,
              v74);
      std::vector<unsigned char>::operator=(Src, v21);
      std::vector<char>::~vector<char>(v74);
      std::string::~string(v73);
    }
    std::string::string(v73, "userSid");
    v22 = *(_BYTE *)nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
                      &hMem,
                      v73);
    std::string::~string(v73);
    if ( v22 )
    {
      std::string::string(v73, "userSid");
      v23 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
              &hMem,
              v73);
      v24 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
              v23,
              v74);
      v25 = anonymous_namespace_::Utf8ToUtf16(v80, v24);
      std::wstring::operator=(v75, v25);
      std::wstring::~wstring(v80, v26, v27);
      std::string::~string(v74);
      std::string::~string(v73);
    }
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v65);
  }
  catch ( nlohmann::detail::out_of_range )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80090005LL,
      v62);
    std::wstring::~wstring(v75, v60, v61);
    std::vector<char>::~vector<char>(Src);
    std::wstring::~wstring(v78, v57, v58);
    return 2148073477LL;
  }
  if ( *(_QWORD *)this != v13.m128i_i64[0] || *((_QWORD *)this + 1) != _mm_srli_si128(v13, 8).m128i_u64[0] )
  {
    v30 = -2147024894;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x289,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)0x80070002LL,
      v63);
    goto LABEL_59;
  }
  v28 = si128.m128i_i64[0];
  hMem = 0;
  v29 = CflApiNew::AllocBuffer_unsigned_short_(si128.m128i_i64[0] + 1, &hMem);
  v30 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28E,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v29,
      v63);
    v33 = hMem;
    if ( !hMem )
    {
LABEL_59:
      std::wstring::~wstring(v75, v31, v32);
      std::vector<char>::~vector<char>(Src);
      std::wstring::~wstring(v78, v55, v56);
      return v30;
    }
LABEL_21:
    CflFreeBuffer(v33);
    goto LABEL_59;
  }
  v34 = (const unsigned __int16 *)v78;
  if ( si128.m128i_i64[1] > 7uLL )
    v34 = v78[0];
  v35 = v28 + 1;
  v36 = hMem;
  v37 = StringCchCopyW((unsigned __int16 *)hMem, v35, v34);
  v30 = v37;
  if ( v37 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x28F,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v37,
      v63);
LABEL_26:
    if ( !v36 )
      goto LABEL_59;
    v33 = v36;
    goto LABEL_21;
  }
  v40 = Src[0];
  v41 = (char *)Src[1] - (char *)Src[0];
  v42 = 0;
  v66 = 0;
  if ( Src[0] != Src[1] )
  {
    v66 = 0;
    v43 = CflApiNew::AllocBuffer_unsigned_char_((char *)Src[1] - (char *)Src[0]);
    v30 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x295,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v43,
        v63);
      if ( v66 )
        CflFreeBuffer(v66);
      goto LABEL_26;
    }
    v42 = v66;
    memcpy_0(v66, v40, v41);
  }
  v44 = 0;
  if ( v76 )
  {
    v45 = v76 + 1;
    v74[0] = 0;
    v46 = CflApiNew::AllocBuffer_unsigned_short_(v76 + 1, v74);
    v47 = v46;
    if ( v46 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29D,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v46,
        v63);
      if ( v74[0] )
        CflFreeBuffer(v74[0]);
      if ( v42 )
        CflFreeBuffer(v42);
      if ( v36 )
        CflFreeBuffer(v36);
      v30 = v47;
      goto LABEL_59;
    }
    v48 = (const unsigned __int16 *)v75;
    if ( v77 > 7 )
      v48 = v75[0];
    v44 = v74[0];
    v49 = StringCchCopyW((unsigned __int16 *)v74[0], v45, v48);
    v50 = v49;
    if ( v49 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29E,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v49,
        v63);
      if ( v44 )
        CflFreeBuffer(v44);
      if ( v42 )
        CflFreeBuffer(v42);
      if ( v36 )
        CflFreeBuffer(v36);
      v30 = v50;
      goto LABEL_59;
    }
    v6 = v69;
  }
  *(_QWORD *)a3 = v36;
  if ( v6 )
  {
    v51 = (unsigned __int16 *)v42;
    v42 = 0;
    *v6 = v51;
    *(_DWORD *)a5 = v41;
  }
  *(_QWORD *)v70 = v44;
  if ( v42 )
    CflFreeBuffer(v42);
  std::wstring::~wstring(v75, v38, v39);
  std::vector<char>::~vector<char>(Src);
  std::wstring::~wstring(v78, v52, v53);
  return 0;
}

```

## disassembly

```asm
0x18001cb44  mov     rax, rsp
0x18001cb47  push    rbx
0x18001cb48  push    rsi
0x18001cb49  push    rdi
0x18001cb4a  push    r12
0x18001cb4c  push    r13
0x18001cb4e  push    r14
0x18001cb50  push    r15
0x18001cb52  sub     rsp, 1B0h
0x18001cb59  movaps  xmmword ptr [rax-48h], xmm6
0x18001cb5d  mov     rax, cs:__security_cookie
0x18001cb64  xor     rax, rsp
0x18001cb67  mov     [rsp+1E8h+var_58], rax
0x18001cb6f  mov     r15, r9
0x18001cb72  mov     [rsp+1E8h+var_188], r9
0x18001cb77  mov     r12, r8
0x18001cb7a  mov     rdi, rcx
0x18001cb7d  mov     r13, [rsp+1E8h+arg_20]
0x18001cb85  mov     rcx, [rsp+1E8h+arg_28]
0x18001cb8d  mov     [rsp+1E8h+var_180], rcx
0x18001cb92  xor     esi, esi
0x18001cb94  test    rdi, rdi
0x18001cb97  jz      loc_18001D21A
0x18001cb9d  test    rdx, rdx
0x18001cba0  jz      loc_18001D21A
0x18001cba6  test    r8, r8
0x18001cba9  jz      loc_18001D21A
0x18001cbaf  test    rcx, rcx
0x18001cbb2  jz      loc_18001D21A
0x18001cbb8  xorps   xmm0, xmm0
0x18001cbbb  movq    rax, xmm0
0x18001cbc0  cmp     [rdi], rax
0x18001cbc3  jnz     short loc_18001CBD9
0x18001cbc5  psrldq  xmm0, 8
0x18001cbca  movq    rax, xmm0
0x18001cbcf  cmp     [rdi+8], rax
0x18001cbd3  jz      loc_18001D20E
0x18001cbd9  test    r9, r9
0x18001cbdc  jz      short loc_18001CBF3
0x18001cbde  test    r13, r13
0x18001cbe1  jz      loc_18001D20E
0x18001cbe7  mov     [r8], rsi
0x18001cbea  mov     [r9], rsi
0x18001cbed  mov     [r13+0], esi
0x18001cbf1  jmp     short loc_18001CBFF
0x18001cbf3  test    r13, r13
0x18001cbf6  jnz     loc_18001D20E
0x18001cbfc  mov     [r8], rsi
0x18001cbff  mov     [rcx], rsi
0x18001cc02  xorps   xmm0, xmm0
0x18001cc05  movups  xmmword ptr [rsp+1E8h+var_D8], xmm0
0x18001cc0d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001cc15  movdqu  [rsp+1E8h+var_C8], xmm1
0x18001cc1e  mov     word ptr [rsp+1E8h+var_D8], si
0x18001cc26  movdqu  xmmword ptr [rsp+1E8h+Src], xmm0
0x18001cc2c  mov     [rsp+1E8h+var_190], rsi
0x18001cc31  movups  xmmword ptr [rsp+1E8h+var_F8], xmm0
0x18001cc39  mov     [rsp+1E8h+var_E8], rsi
0x18001cc41  mov     [rsp+1E8h+var_E0], 7
0x18001cc4d  mov     word ptr [rsp+1E8h+var_F8], si
0x18001cc55  lea     rax, [rsp+1E8h+var_178]
0x18001cc5a  mov     [rsp+1E8h+var_118], rax
0x18001cc62  mov     [rsp+1E8h+var_140], rsi
0x18001cc6a  lea     rcx, [rsp+1E8h+var_98]
0x18001cc72  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001cc77  nop
0x18001cc78  lea     rdx, [rsp+1E8h+var_98]
0x18001cc80  lea     rcx, [rsp+1E8h+var_78]
0x18001cc88  call    _anonymous_namespace___Utf16ToUtf8
0x18001cc8d  nop
0x18001cc8e  lea     r8, [rsp+1E8h+var_178]
0x18001cc93  mov     rdx, rax
0x18001cc96  lea     rcx, [rsp+1E8h+hMem]
0x18001cc9b  call    ??$parse@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@SA?AV01@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$function@$$A6A_NHW4parse_event_t@detail@nlohmann@@AEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z@3@_N2@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::parse<std::string>(std::string &&,std::function<bool (int,nlohmann::detail::parse_event_t,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &)>,bool,bool)
0x18001cca0  nop
0x18001cca1  lea     rcx, [rsp+1E8h+var_78]
0x18001cca9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ccae  nop
0x18001ccaf  lea     rcx, [rsp+1E8h+var_98]
0x18001ccb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ccbc  lea     rdx, aProviderid_0; "providerId"
0x18001ccc3  lea     rcx, [rsp+1E8h+var_138]
0x18001cccb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001ccd0  nop
0x18001ccd1  lea     rdx, [rsp+1E8h+var_138]
0x18001ccd9  lea     rcx, [rsp+1E8h+hMem]
0x18001ccde  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001cce3  lea     rdx, [rsp+1E8h+var_118]
0x18001cceb  mov     rcx, rax
0x18001ccee  call    ??$get@U_GUID@@U1@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AU_GUID@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<_GUID,_GUID,0>(void)
0x18001ccf3  movups  xmm6, xmmword ptr [rax]
0x18001ccf6  lea     rcx, [rsp+1E8h+var_138]
0x18001ccfe  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cd03  lea     rdx, aScenarioid_0; "scenarioId"
0x18001cd0a  lea     rcx, [rsp+1E8h+var_138]
0x18001cd12  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001cd17  nop
0x18001cd18  lea     rdx, [rsp+1E8h+var_138]
0x18001cd20  lea     rcx, [rsp+1E8h+hMem]
0x18001cd25  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001cd2a  lea     rdx, [rsp+1E8h+var_B8]
0x18001cd32  mov     rcx, rax
0x18001cd35  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x18001cd3a  nop
0x18001cd3b  mov     rdx, rax
0x18001cd3e  lea     rcx, [rsp+1E8h+var_118]
0x18001cd46  call    _anonymous_namespace___Utf8ToUtf16
0x18001cd4b  mov     rdx, rax
0x18001cd4e  lea     rcx, [rsp+1E8h+var_D8]
0x18001cd56  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001cd5b  lea     rcx, [rsp+1E8h+var_118]
0x18001cd63  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cd68  nop
0x18001cd69  lea     rcx, [rsp+1E8h+var_B8]
0x18001cd71  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cd76  nop
0x18001cd77  lea     rcx, [rsp+1E8h+var_138]
0x18001cd7f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cd84  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18001cd8b  lea     rcx, [rsp+1E8h+var_138]
0x18001cd93  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001cd98  nop
0x18001cd99  lea     rdx, [rsp+1E8h+var_138]
0x18001cda1  lea     rcx, [rsp+1E8h+hMem]
0x18001cda6  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001cdab  mov     bl, [rax]
0x18001cdad  lea     rcx, [rsp+1E8h+var_138]
0x18001cdb5  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cdba  test    bl, bl
0x18001cdbc  jz      short loc_18001CE1D
0x18001cdbe  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18001cdc5  lea     rcx, [rsp+1E8h+var_138]
0x18001cdcd  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001cdd2  nop
0x18001cdd3  lea     rdx, [rsp+1E8h+var_138]
0x18001cddb  lea     rcx, [rsp+1E8h+hMem]
0x18001cde0  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001cde5  lea     rdx, [rsp+1E8h+var_118]
0x18001cded  mov     rcx, rax
0x18001cdf0  call    ??$get@V?$vector@EV?$allocator@E@std@@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::vector<uchar>,std::vector<uchar>,0>(void)
0x18001cdf5  mov     rdx, rax
0x18001cdf8  lea     rcx, [rsp+1E8h+Src]
0x18001cdfd  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18001ce02  lea     rcx, [rsp+1E8h+var_118]
0x18001ce0a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001ce0f  nop
0x18001ce10  lea     rcx, [rsp+1E8h+var_138]
0x18001ce18  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ce1d  lea     rdx, aUsersid; "userSid"
0x18001ce24  lea     rcx, [rsp+1E8h+var_138]
0x18001ce2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001ce31  nop
0x18001ce32  lea     rdx, [rsp+1E8h+var_138]
0x18001ce3a  lea     rcx, [rsp+1E8h+hMem]
0x18001ce3f  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001ce44  mov     bl, [rax]
0x18001ce46  lea     rcx, [rsp+1E8h+var_138]
0x18001ce4e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ce53  test    bl, bl
0x18001ce55  jz      loc_18001CEDD
0x18001ce5b  lea     rdx, aUsersid; "userSid"
0x18001ce62  lea     rcx, [rsp+1E8h+var_138]
0x18001ce6a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18001ce6f  nop
0x18001ce70  lea     rdx, [rsp+1E8h+var_138]
0x18001ce78  lea     rcx, [rsp+1E8h+hMem]
0x18001ce7d  call    ?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::at(std::string const &)
0x18001ce82  lea     rdx, [rsp+1E8h+var_118]
0x18001ce8a  mov     rcx, rax
0x18001ce8d  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x18001ce92  nop
0x18001ce93  mov     rdx, rax
0x18001ce96  lea     rcx, [rsp+1E8h+var_B8]
0x18001ce9e  call    _anonymous_namespace___Utf8ToUtf16
0x18001cea3  mov     rdx, rax
0x18001cea6  lea     rcx, [rsp+1E8h+var_F8]
0x18001ceae  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ceb3  lea     rcx, [rsp+1E8h+var_B8]
0x18001cebb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001cec0  nop
0x18001cec1  lea     rcx, [rsp+1E8h+var_118]
0x18001cec9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cece  nop
0x18001cecf  lea     rcx, [rsp+1E8h+var_138]
0x18001ced7  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001cedc  nop
0x18001cedd  mov     dl, byte ptr [rsp+1E8h+hMem]
0x18001cee1  lea     rcx, [rsp+1E8h+var_1B0]
0x18001cee6  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001ceeb  nop
0x18001ceec  movq    rax, xmm6
0x18001cef1  cmp     [rdi], rax
0x18001cef4  jnz     loc_18001D197
0x18001cefa  psrldq  xmm6, 8
0x18001ceff  movq    rax, xmm6
0x18001cf04  cmp     [rdi+8], rax
0x18001cf08  jnz     loc_18001D197
0x18001cf0e  mov     rdi, qword ptr [rsp+1E8h+var_C8]
0x18001cf16  mov     [rsp+1E8h+hMem], rsi
0x18001cf1b  lea     rdx, [rsp+1E8h+hMem]
0x18001cf20  lea     rcx, [rdi+1]
0x18001cf24  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001cf29  mov     ebx, eax
0x18001cf2b  test    eax, eax
0x18001cf2d  jns     short loc_18001CF64
0x18001cf2f  mov     rcx, [rsp+1E8h]; this
0x18001cf37  mov     r9d, eax; char *
0x18001cf3a  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001cf41  mov     edx, 28Eh; void *
0x18001cf46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cf4b  nop
0x18001cf4c  mov     rcx, [rsp+1E8h+hMem]; hMem
0x18001cf51  test    rcx, rcx
0x18001cf54  jz      loc_18001D1B9
0x18001cf5a  call    CflFreeBuffer
0x18001cf5f  jmp     loc_18001D1B9
0x18001cf64  lea     r8, [rsp+1E8h+var_D8]
0x18001cf6c  cmp     qword ptr [rsp+1E8h+var_C8+8], 7
0x18001cf75  cmova   r8, [rsp+1E8h+var_D8]; unsigned __int16 *
0x18001cf7e  lea     rdx, [rdi+1]; unsigned __int64
0x18001cf82  mov     rdi, [rsp+1E8h+hMem]
0x18001cf87  mov     rcx, rdi; unsigned __int16 *
0x18001cf8a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001cf8f  mov     ebx, eax
0x18001cf91  test    eax, eax
0x18001cf93  jns     short loc_18001CFC0
0x18001cf95  mov     rcx, [rsp+1E8h]; this
0x18001cf9d  mov     r9d, eax; char *
0x18001cfa0  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001cfa7  mov     edx, 28Fh; void *
0x18001cfac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfb1  nop
0x18001cfb2  test    rdi, rdi
0x18001cfb5  jz      loc_18001D1B9
0x18001cfbb  mov     rcx, rdi
0x18001cfbe  jmp     short loc_18001CF5A
0x18001cfc0  mov     rsi, [rsp+1E8h+Src]
0x18001cfc5  mov     r14, [rsp+1E8h+Src+8]
0x18001cfca  sub     r14, rsi
0x18001cfcd  xor     ebx, ebx
0x18001cfcf  mov     [rsp+1E8h+var_1A8], rbx
0x18001cfd4  cmp     rsi, [rsp+1E8h+Src+8]
0x18001cfd9  jz      short loc_18001D034
0x18001cfdb  mov     [rsp+1E8h+var_1A8], rbx
0x18001cfe0  lea     rdx, [rsp+1E8h+var_1A8]
0x18001cfe5  mov     rcx, r14; uBytes
0x18001cfe8  call    CflApiNew__AllocBuffer_unsigned_char_
0x18001cfed  mov     ebx, eax
0x18001cfef  test    eax, eax
0x18001cff1  jns     short loc_18001D021
0x18001cff3  mov     rcx, [rsp+1E8h]; this
0x18001cffb  mov     r9d, eax; char *
0x18001cffe  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001d005  mov     edx, 295h; void *
0x18001d00a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d00f  nop
0x18001d010  mov     rcx, [rsp+1E8h+var_1A8]; hMem
0x18001d015  test    rcx, rcx
0x18001d018  jz      short loc_18001CFB2
0x18001d01a  call    CflFreeBuffer
0x18001d01f  jmp     short loc_18001CFB2
0x18001d021  mov     r8, r14; Size
0x18001d024  mov     rdx, rsi; Src
0x18001d027  mov     rbx, [rsp+1E8h+var_1A8]
0x18001d02c  mov     rcx, rbx; void *
0x18001d02f  call    memcpy_0
0x18001d034  xor     esi, esi
0x18001d036  mov     rax, [rsp+1E8h+var_E8]
0x18001d03e  test    rax, rax
0x18001d041  jz      loc_18001D13F
0x18001d047  lea     r15, [rax+1]
0x18001d04b  mov     [rsp+1E8h+var_118], rsi
0x18001d053  lea     rdx, [rsp+1E8h+var_118]
0x18001d05b  mov     rcx, r15
0x18001d05e  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001d063  mov     esi, eax
0x18001d065  test    eax, eax
0x18001d067  jns     short loc_18001D0BB
0x18001d069  mov     rcx, [rsp+1E8h]; this
0x18001d071  mov     r9d, eax; char *
0x18001d074  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001d07b  mov     edx, 29Dh; void *
0x18001d080  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d085  nop
0x18001d086  mov     rcx, [rsp+1E8h+var_118]; hMem
0x18001d08e  test    rcx, rcx
0x18001d091  jz      short loc_18001D099
0x18001d093  call    CflFreeBuffer
0x18001d098  nop
0x18001d099  test    rbx, rbx
0x18001d09c  jz      short loc_18001D0A7
0x18001d09e  mov     rcx, rbx; hMem
0x18001d0a1  call    CflFreeBuffer
0x18001d0a6  nop
0x18001d0a7  test    rdi, rdi
0x18001d0aa  jz      short loc_18001D0B4
0x18001d0ac  mov     rcx, rdi; hMem
0x18001d0af  call    CflFreeBuffer
0x18001d0b4  mov     ebx, esi
0x18001d0b6  jmp     loc_18001D1B9
  ... truncated ...
```
