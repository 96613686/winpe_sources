# CflApiNew::SerializeSessionContext(_GUID const *,ushort const *,uchar const *,ulong,ushort const *,ulong,ushort * *)

- ea: `0x18002b264`
- end: `0x18002b7d1`
- name: `?SerializeSessionContext@CflApiNew@@YAJPEBU_GUID@@PEBGPEBEK1KPEAPEAG@Z`
- size: `1389`
- prototype: `int(CflApiNew *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned int, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800113b0`

## callees

- `0x180002490`
- `0x18000289c`
- `0x1800067c4`
- `0x1800071b4`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180010700`
- `0x180012910`
- `0x180012b38`
- `0x180012cec`
- `0x18001332c`
- `0x18001a674`
- `0x18001aa1c`
- `0x18001b0bc`
- `0x18001b3fc`
- `0x180021420`
- `0x180022cf4`
- `0x1800230a8`
- `0x18002b264`
- `0x18002c4a4`
- `0x18002c628`
- `0x18002e008`

## string_xrefs

- `0x18002b5aa`: `userSid`
- `0x18002b610`: `userSid`
- `0x18002b70f`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002b75e`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002b79f`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CflApiNew::SerializeSessionContext(
        CflApiNew *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        __int64 a5,
        const unsigned __int16 *a6,
        _QWORD *a7)
{
  size_t v7; // rdi
  unsigned int v11; // ebx
  __int64 v12; // rdx
  char *v13; // rbx
  __int64 v14; // rax
  char v15; // r8
  __int64 v16; // r9
  __int64 v17; // rbx
  _QWORD *v18; // rax
  __int64 v19; // rax
  char v20; // dl
  _QWORD *v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r8
  char *v24; // rbx
  __int64 v25; // rbx
  __int64 v26; // rax
  char v27; // dl
  __int64 v28; // r8
  __int64 v29; // rax
  char v30; // dl
  _QWORD *v31; // r8
  __int64 v32; // rbx
  _QWORD *v33; // rax
  __int64 v34; // rax
  char v35; // dl
  _QWORD *v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rax
  char v40; // dl
  _QWORD *v41; // rdx
  __int64 v42; // rax
  char v43; // dl
  _QWORD *v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // rdi
  int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // r8
  const unsigned __int16 *v53; // r8
  HLOCAL v54; // rbx
  int v55; // eax
  unsigned int v56; // edi
  int v58; // [rsp+20h] [rbp-B1h]
  HLOCAL hMem; // [rsp+30h] [rbp-A1h] BYREF
  unsigned __int64 v60; // [rsp+38h] [rbp-99h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-91h] BYREF
  _QWORD *v62; // [rsp+48h] [rbp-89h] BYREF
  char v63[8]; // [rsp+50h] [rbp-81h] BYREF
  char v64[8]; // [rsp+58h] [rbp-79h] BYREF
  void *v65[2]; // [rsp+60h] [rbp-71h] BYREF
  __int64 v66; // [rsp+70h] [rbp-61h]
  unsigned __int16 *v67[2]; // [rsp+80h] [rbp-51h] BYREF
  __int64 v68; // [rsp+90h] [rbp-41h]
  unsigned __int64 v69; // [rsp+98h] [rbp-39h]
  _BYTE v70[32]; // [rsp+A0h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v7 = (unsigned int)a4;
  if ( !this || !a2 || !a7 )
  {
    v11 = -2147467261;
    v12 = 277;
    goto LABEL_30;
  }
  if ( !*(_QWORD *)this && *((_QWORD *)this + 1) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
  {
LABEL_8:
    v11 = -2147024809;
    v12 = 279;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)v11,
      v58);
    return v11;
  }
  if ( a3 )
  {
    if ( !(_DWORD)a4 )
      goto LABEL_8;
  }
  else if ( (_DWORD)a4 )
  {
    goto LABEL_8;
  }
  *a7 = 0;
  *(_OWORD *)v67 = 0;
  v68 = 0;
  v69 = 7;
  LOWORD(v67[0]) = 0;
  v63[0] = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
    v64,
    0);
  hMem = &p_hMem;
  v13 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
          (char *)&p_hMem,
          (const IID *)this);
  v14 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
          v63,
          "providerId");
  v15 = *(_BYTE *)v14;
  *(_BYTE *)v14 = *v13;
  *v13 = v15;
  v16 = *(_QWORD *)(v14 + 8);
  *(_QWORD *)(v14 + 8) = *((_QWORD *)v13 + 1);
  *((_QWORD *)v13 + 1) = v16;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v13 + 8);
  hMem = &p_hMem;
  std::wstring::wstring(v65, a2);
  v17 = anonymous_namespace_::Utf16ToUtf8_0(v70, v65);
  v62 = 0;
  LOBYTE(p_hMem) = 3;
  v18 = operator new(0x20u);
  *(_OWORD *)v18 = 0;
  v18[2] = 0;
  v18[3] = 0;
  *(_OWORD *)v18 = *(_OWORD *)v17;
  *((_OWORD *)v18 + 1) = *(_OWORD *)(v17 + 16);
  *(_QWORD *)(v17 + 16) = 0;
  *(_QWORD *)(v17 + 24) = 15;
  *(_BYTE *)v17 = 0;
  v62 = v18;
  v19 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
          v63,
          "scenarioId");
  v20 = *(_BYTE *)v19;
  *(_BYTE *)v19 = (_BYTE)p_hMem;
  LOBYTE(p_hMem) = v20;
  v21 = *(_QWORD **)(v19 + 8);
  *(_QWORD *)(v19 + 8) = v62;
  v62 = v21;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v62);
  std::string::~string(v70);
  std::wstring::~wstring(v65, v22, v23);
  if ( a3 )
  {
    p_hMem = (HLOCAL *)v70;
    *(_OWORD *)v65 = 0;
    v66 = 0;
    if ( v7 )
    {
      std::vector<unsigned char>::_Buy_nonzero(v65, v7);
      v24 = (char *)v65[0];
      memmove_0(v65[0], a3, v7);
      v65[1] = &v24[v7];
      hMem = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&hMem);
    }
    v25 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
            v70,
            v65);
    v26 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v63,
            "scenarioContext");
    v27 = *(_BYTE *)v26;
    *(_BYTE *)v26 = *(_BYTE *)v25;
    *(_BYTE *)v25 = v27;
    v28 = *(_QWORD *)(v26 + 8);
    *(_QWORD *)(v26 + 8) = *(_QWORD *)(v25 + 8);
    *(_QWORD *)(v25 + 8) = v28;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v25 + 8);
    std::vector<char>::~vector<char>(v65);
  }
  else
  {
    p_hMem = &hMem;
    LOBYTE(hMem) = 0;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v60,
      0);
    v29 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v63,
            "scenarioContext");
    v30 = *(_BYTE *)v29;
    *(_BYTE *)v29 = (_BYTE)hMem;
    LOBYTE(hMem) = v30;
    v31 = *(_QWORD **)(v29 + 8);
    *(_QWORD *)(v29 + 8) = v60;
    v60 = (unsigned __int64)v31;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v60);
  }
  p_hMem = &hMem;
  if ( a5 )
  {
    std::wstring::wstring(v65, a5);
    v32 = anonymous_namespace_::Utf16ToUtf8_0(v70, v65);
    v60 = 0;
    LOBYTE(hMem) = 3;
    v33 = operator new(0x20u);
    *(_OWORD *)v33 = 0;
    v33[2] = 0;
    v33[3] = 0;
    *(_OWORD *)v33 = *(_OWORD *)v32;
    *((_OWORD *)v33 + 1) = *(_OWORD *)(v32 + 16);
    *(_QWORD *)(v32 + 16) = 0;
    *(_QWORD *)(v32 + 24) = 15;
    *(_BYTE *)v32 = 0;
    v60 = (unsigned __int64)v33;
    v34 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v63,
            "userSid");
    v35 = *(_BYTE *)v34;
    *(_BYTE *)v34 = (_BYTE)hMem;
    LOBYTE(hMem) = v35;
    v36 = *(_QWORD **)(v34 + 8);
    *(_QWORD *)(v34 + 8) = v60;
    v60 = (unsigned __int64)v36;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v60);
    std::string::~string(v70);
    std::wstring::~wstring(v65, v37, v38);
  }
  else
  {
    LOBYTE(hMem) = 0;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v60,
      0);
    v39 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v63,
            "userSid");
    v40 = *(_BYTE *)v39;
    *(_BYTE *)v39 = (_BYTE)hMem;
    LOBYTE(hMem) = v40;
    v41 = *(_QWORD **)(v39 + 8);
    *(_QWORD *)(v39 + 8) = v60;
    v60 = (unsigned __int64)v41;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v60);
  }
  p_hMem = &hMem;
  LOBYTE(hMem) = 6;
  v60 = (unsigned int)a6;
  v42 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
          v63,
          "currentSessionId");
  v43 = *(_BYTE *)v42;
  *(_BYTE *)v42 = (_BYTE)hMem;
  LOBYTE(hMem) = v43;
  v44 = *(_QWORD **)(v42 + 8);
  *(_QWORD *)(v42 + 8) = v60;
  v60 = (unsigned __int64)v44;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v60);
  v45 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::dump(
          v63,
          v70);
  v46 = anonymous_namespace_::Utf8ToUtf16_0(v65, v45);
  std::wstring::operator=(v67, v46);
  std::wstring::~wstring(v65, v47, v48);
  std::string::~string(v70);
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v64);
  v49 = v68;
  hMem = 0;
  v50 = CflApiNew::AllocBuffer_unsigned_short_(v68 + 1, &hMem);
  v11 = v50;
  if ( v50 >= 0 )
  {
    v53 = (const unsigned __int16 *)v67;
    if ( v69 > 7 )
      v53 = v67[0];
    v54 = hMem;
    v55 = StringCchCopyW((unsigned __int16 *)hMem, v49 + 1, v53);
    v56 = v55;
    if ( v55 >= 0 )
    {
      *a7 = v54;
      v11 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)(unsigned int)v55,
        v58);
      if ( v54 )
        CflFreeBuffer(v54);
      v11 = v56;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)v50,
      v58);
    if ( hMem )
      CflFreeBuffer(hMem);
  }
  std::wstring::~wstring(v67, v51, v52);
  return v11;
}

```

## disassembly

```asm
0x18002b264  push    rbp
0x18002b266  push    rbx
0x18002b267  push    rsi
0x18002b268  push    rdi
0x18002b269  push    r12
0x18002b26b  push    r13
0x18002b26d  push    r14
0x18002b26f  push    r15
0x18002b271  lea     rbp, [rsp-7]
0x18002b276  sub     rsp, 0D8h
0x18002b27d  mov     rax, cs:__security_cookie
0x18002b284  xor     rax, rsp
0x18002b287  mov     [rbp+3Fh+var_50], rax
0x18002b28b  mov     edi, r9d
0x18002b28e  mov     rsi, r8
0x18002b291  mov     r12, rdx
0x18002b294  mov     rbx, rcx
0x18002b297  mov     r15, [rbp+3Fh+arg_20]
0x18002b29b  mov     r14, qword ptr [rbp+3Fh+arg_30]
0x18002b29f  xor     r13d, r13d
0x18002b2a2  test    rcx, rcx
0x18002b2a5  jz      loc_18002B792
0x18002b2ab  test    rdx, rdx
0x18002b2ae  jz      loc_18002B792
0x18002b2b4  test    r14, r14
0x18002b2b7  jz      loc_18002B792
0x18002b2bd  xorps   xmm0, xmm0
0x18002b2c0  movq    rax, xmm0
0x18002b2c5  cmp     [rcx], rax
0x18002b2c8  jnz     short loc_18002B2DA
0x18002b2ca  psrldq  xmm0, 8
0x18002b2cf  movq    rax, xmm0
0x18002b2d4  cmp     [rcx+8], rax
0x18002b2d8  jz      short loc_18002B2E4
0x18002b2da  test    rsi, rsi
0x18002b2dd  jz      short loc_18002B2F3
0x18002b2df  test    r9d, r9d
0x18002b2e2  jnz     short loc_18002B2F8
0x18002b2e4  mov     ebx, 80070057h
0x18002b2e9  mov     edx, 117h
0x18002b2ee  jmp     loc_18002B79C
0x18002b2f3  test    r9d, r9d
0x18002b2f6  jnz     short loc_18002B2E4
0x18002b2f8  mov     [r14], r13
0x18002b2fb  xorps   xmm0, xmm0
0x18002b2fe  movups  xmmword ptr [rbp+3Fh+var_90], xmm0
0x18002b302  mov     [rbp+3Fh+var_80], r13
0x18002b306  mov     [rbp+3Fh+var_78], 7
0x18002b30e  mov     word ptr [rbp+3Fh+var_90], r13w
0x18002b313  mov     [rsp+110h+var_C0], r13b
0x18002b318  xor     edx, edx
0x18002b31a  lea     rcx, [rbp+3Fh+var_B8]
0x18002b31e  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18002b323  nop
0x18002b324  lea     rax, [rsp+110h+var_D0]
0x18002b329  mov     [rsp+110h+hMem], rax
0x18002b32e  mov     rdx, rbx
0x18002b331  lea     rcx, [rsp+110h+var_D0]
0x18002b336  call    ??$?0AEBU_GUID@@U0@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBU_GUID@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(_GUID const &)
0x18002b33b  mov     rbx, rax
0x18002b33e  lea     rdx, aProviderid_0; "providerId"
0x18002b345  lea     rcx, [rsp+110h+var_C0]
0x18002b34a  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b34f  nop
0x18002b350  mov     r8b, [rax]
0x18002b353  mov     cl, [rbx]
0x18002b355  mov     [rax], cl
0x18002b357  mov     [rbx], r8b
0x18002b35a  lea     rcx, [rbx+8]
0x18002b35e  mov     r9, [rax+8]
0x18002b362  mov     r8, [rcx]
0x18002b365  mov     [rax+8], r8
0x18002b369  mov     [rcx], r9
0x18002b36c  mov     dl, [rbx]
0x18002b36e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b373  lea     rax, [rsp+110h+var_D0]
0x18002b378  mov     [rsp+110h+hMem], rax
0x18002b37d  mov     rdx, r12
0x18002b380  lea     rcx, [rbp+3Fh+var_B0]
0x18002b384  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b389  nop
0x18002b38a  lea     rdx, [rbp+3Fh+var_B0]
0x18002b38e  lea     rcx, [rbp+3Fh+var_70]
0x18002b392  call    _anonymous_namespace___Utf16ToUtf8_0
0x18002b397  mov     rbx, rax
0x18002b39a  xor     eax, eax
0x18002b39c  mov     [rsp+110h+var_C8], rax
0x18002b3a1  mov     byte ptr [rsp+110h+var_D0], 3
0x18002b3a6  lea     r12d, [rax+20h]
0x18002b3aa  mov     ecx, r12d; Size
0x18002b3ad  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b3b2  xorps   xmm0, xmm0
0x18002b3b5  movups  xmmword ptr [rax], xmm0
0x18002b3b8  mov     [rax+10h], r13
0x18002b3bc  mov     [rax+18h], r13
0x18002b3c0  movups  xmm0, xmmword ptr [rbx]
0x18002b3c3  movups  xmmword ptr [rax], xmm0
0x18002b3c6  movups  xmm1, xmmword ptr [rbx+10h]
0x18002b3ca  movups  xmmword ptr [rax+10h], xmm1
0x18002b3ce  mov     [rbx+10h], r13
0x18002b3d2  mov     qword ptr [rbx+18h], 0Fh
0x18002b3da  mov     [rbx], r13b
0x18002b3dd  mov     [rsp+110h+var_C8], rax
0x18002b3e2  lea     rdx, aScenarioid_0; "scenarioId"
0x18002b3e9  lea     rcx, [rsp+110h+var_C0]
0x18002b3ee  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b3f3  nop
0x18002b3f4  mov     dl, [rax]
0x18002b3f6  mov     cl, byte ptr [rsp+110h+var_D0]
0x18002b3fa  mov     [rax], cl
0x18002b3fc  mov     byte ptr [rsp+110h+var_D0], dl
0x18002b400  mov     rdx, [rax+8]
0x18002b404  mov     rcx, [rsp+110h+var_C8]
0x18002b409  mov     [rax+8], rcx
0x18002b40d  mov     [rsp+110h+var_C8], rdx
0x18002b412  mov     dl, byte ptr [rsp+110h+var_D0]
0x18002b416  lea     rcx, [rsp+110h+var_C8]
0x18002b41b  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b420  nop
0x18002b421  lea     rcx, [rbp+3Fh+var_70]
0x18002b425  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b42a  nop
0x18002b42b  lea     rcx, [rbp+3Fh+var_B0]
0x18002b42f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b434  test    rsi, rsi
0x18002b437  jz      loc_18002B4DC
0x18002b43d  lea     rax, [rbp+3Fh+var_70]
0x18002b441  mov     [rsp+110h+var_D0], rax
0x18002b446  xorps   xmm0, xmm0
0x18002b449  movdqu  xmmword ptr [rbp+3Fh+var_B0], xmm0
0x18002b44e  mov     [rbp+3Fh+var_A0], r13
0x18002b452  test    rdi, rdi
0x18002b455  jz      short loc_18002B48D
0x18002b457  mov     rdx, rdi
0x18002b45a  lea     rcx, [rbp+3Fh+var_B0]
0x18002b45e  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18002b463  mov     rbx, [rbp+3Fh+var_B0]
0x18002b467  mov     r8, rdi; Size
0x18002b46a  mov     rdx, rsi; Src
0x18002b46d  mov     rcx, rbx; void *
0x18002b470  call    memmove_0
0x18002b475  lea     rax, [rdi+rbx]
0x18002b479  mov     [rbp+3Fh+var_B0+8], rax
0x18002b47d  mov     [rsp+110h+hMem], r13
0x18002b482  lea     rcx, [rsp+110h+hMem]
0x18002b487  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18002b48c  nop
0x18002b48d  lea     rdx, [rbp+3Fh+var_B0]
0x18002b491  lea     rcx, [rbp+3Fh+var_70]
0x18002b495  call    ??$?0V?$vector@EV?$allocator@E@std@@@std@@V01@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(std::vector<uchar> &&)
0x18002b49a  mov     rbx, rax
0x18002b49d  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18002b4a4  lea     rcx, [rsp+110h+var_C0]
0x18002b4a9  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b4ae  nop
0x18002b4af  mov     dl, [rax]
0x18002b4b1  mov     cl, [rbx]
0x18002b4b3  mov     [rax], cl
0x18002b4b5  mov     [rbx], dl
0x18002b4b7  lea     rcx, [rbx+8]
0x18002b4bb  mov     r8, [rax+8]
0x18002b4bf  mov     rdx, [rcx]
0x18002b4c2  mov     [rax+8], rdx
0x18002b4c6  mov     [rcx], r8
0x18002b4c9  mov     dl, [rbx]
0x18002b4cb  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b4d0  nop
0x18002b4d1  lea     rcx, [rbp+3Fh+var_B0]
0x18002b4d5  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18002b4da  jmp     short loc_18002B536
0x18002b4dc  lea     rax, [rsp+110h+hMem]
0x18002b4e1  mov     [rsp+110h+var_D0], rax
0x18002b4e6  mov     byte ptr [rsp+110h+hMem], r13b
0x18002b4eb  xor     edx, edx
0x18002b4ed  lea     rcx, [rsp+110h+var_D8]
0x18002b4f2  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18002b4f7  nop
0x18002b4f8  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18002b4ff  lea     rcx, [rsp+110h+var_C0]
0x18002b504  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b509  nop
0x18002b50a  mov     dl, [rax]
0x18002b50c  mov     cl, byte ptr [rsp+110h+hMem]
0x18002b510  mov     [rax], cl
0x18002b512  mov     byte ptr [rsp+110h+hMem], dl
0x18002b516  mov     r8, [rax+8]
0x18002b51a  mov     rcx, [rsp+110h+var_D8]
0x18002b51f  mov     [rax+8], rcx
0x18002b523  mov     [rsp+110h+var_D8], r8
0x18002b528  mov     dl, byte ptr [rsp+110h+hMem]
0x18002b52c  lea     rcx, [rsp+110h+var_D8]
0x18002b531  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b536  lea     rax, [rsp+110h+hMem]
0x18002b53b  mov     [rsp+110h+var_D0], rax
0x18002b540  test    r15, r15
0x18002b543  jz      loc_18002B5FE
0x18002b549  mov     rdx, r15
0x18002b54c  lea     rcx, [rbp+3Fh+var_B0]
0x18002b550  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b555  nop
0x18002b556  lea     rdx, [rbp+3Fh+var_B0]
0x18002b55a  lea     rcx, [rbp+3Fh+var_70]
0x18002b55e  call    _anonymous_namespace___Utf16ToUtf8_0
0x18002b563  mov     rbx, rax
0x18002b566  xor     eax, eax
0x18002b568  mov     [rsp+110h+var_D8], rax
0x18002b56d  mov     byte ptr [rsp+110h+hMem], 3
0x18002b572  mov     rcx, r12; Size
0x18002b575  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b57a  xorps   xmm0, xmm0
0x18002b57d  movups  xmmword ptr [rax], xmm0
0x18002b580  mov     [rax+10h], r13
0x18002b584  mov     [rax+18h], r13
0x18002b588  movups  xmm0, xmmword ptr [rbx]
0x18002b58b  movups  xmmword ptr [rax], xmm0
0x18002b58e  movups  xmm1, xmmword ptr [rbx+10h]
0x18002b592  movups  xmmword ptr [rax+10h], xmm1
0x18002b596  mov     [rbx+10h], r13
0x18002b59a  mov     qword ptr [rbx+18h], 0Fh
0x18002b5a2  mov     [rbx], r13b
0x18002b5a5  mov     [rsp+110h+var_D8], rax
0x18002b5aa  lea     rdx, aUsersid; "userSid"
0x18002b5b1  lea     rcx, [rsp+110h+var_C0]
0x18002b5b6  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b5bb  nop
0x18002b5bc  mov     dl, [rax]
0x18002b5be  mov     cl, byte ptr [rsp+110h+hMem]
0x18002b5c2  mov     [rax], cl
0x18002b5c4  mov     byte ptr [rsp+110h+hMem], dl
0x18002b5c8  mov     rdx, [rax+8]
0x18002b5cc  mov     rcx, [rsp+110h+var_D8]
0x18002b5d1  mov     [rax+8], rcx
0x18002b5d5  mov     [rsp+110h+var_D8], rdx
0x18002b5da  mov     dl, byte ptr [rsp+110h+hMem]
0x18002b5de  lea     rcx, [rsp+110h+var_D8]
0x18002b5e3  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b5e8  nop
0x18002b5e9  lea     rcx, [rbp+3Fh+var_70]
0x18002b5ed  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b5f2  nop
0x18002b5f3  lea     rcx, [rbp+3Fh+var_B0]
0x18002b5f7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b5fc  jmp     short loc_18002B64E
0x18002b5fe  mov     byte ptr [rsp+110h+hMem], r13b
0x18002b603  xor     edx, edx
0x18002b605  lea     rcx, [rsp+110h+var_D8]
0x18002b60a  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18002b60f  nop
0x18002b610  lea     rdx, aUsersid; "userSid"
0x18002b617  lea     rcx, [rsp+110h+var_C0]
0x18002b61c  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b621  nop
0x18002b622  mov     dl, [rax]
0x18002b624  mov     cl, byte ptr [rsp+110h+hMem]
0x18002b628  mov     [rax], cl
0x18002b62a  mov     byte ptr [rsp+110h+hMem], dl
0x18002b62e  mov     rdx, [rax+8]
0x18002b632  mov     rcx, [rsp+110h+var_D8]
0x18002b637  mov     [rax+8], rcx
0x18002b63b  mov     [rsp+110h+var_D8], rdx
0x18002b640  mov     dl, byte ptr [rsp+110h+hMem]
0x18002b644  lea     rcx, [rsp+110h+var_D8]
0x18002b649  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b64e  lea     rax, [rsp+110h+hMem]
0x18002b653  mov     [rsp+110h+var_D0], rax
0x18002b658  mov     byte ptr [rsp+110h+hMem], 6
0x18002b65d  mov     eax, dword ptr [rbp+3Fh+arg_28]
0x18002b660  mov     [rsp+110h+var_D8], rax
0x18002b665  lea     rdx, aCurrentsession; "currentSessionId"
0x18002b66c  lea     rcx, [rsp+110h+var_C0]
0x18002b671  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18002b676  nop
0x18002b677  mov     dl, [rax]
0x18002b679  mov     cl, byte ptr [rsp+110h+hMem]
0x18002b67d  mov     [rax], cl
0x18002b67f  mov     byte ptr [rsp+110h+hMem], dl
0x18002b683  mov     rdx, [rax+8]
0x18002b687  mov     rcx, [rsp+110h+var_D8]
0x18002b68c  mov     [rax+8], rcx
0x18002b690  mov     [rsp+110h+var_D8], rdx
0x18002b695  mov     dl, byte ptr [rsp+110h+hMem]
0x18002b699  lea     rcx, [rsp+110h+var_D8]
0x18002b69e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002b6a3  lea     rdx, [rbp+3Fh+var_70]
0x18002b6a7  lea     rcx, [rsp+110h+var_C0]
0x18002b6ac  call    ?dump@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HD_NW4error_handler_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::dump(int,char,bool,nlohmann::detail::error_handler_t)
0x18002b6b1  nop
0x18002b6b2  mov     rdx, rax
0x18002b6b5  lea     rcx, [rbp+3Fh+var_B0]
0x18002b6b9  call    _anonymous_namespace___Utf8ToUtf16_0
0x18002b6be  mov     rdx, rax
0x18002b6c1  lea     rcx, [rbp+3Fh+var_90]
0x18002b6c5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002b6ca  lea     rcx, [rbp+3Fh+var_B0]
0x18002b6ce  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b6d3  nop
0x18002b6d4  lea     rcx, [rbp+3Fh+var_70]
0x18002b6d8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b6dd  nop
0x18002b6de  mov     dl, [rsp+110h+var_C0]
  ... truncated ...
```
