# CflApi::SerializeSessionContext(_GUID const *,ushort const *,uchar const *,ulong,ushort const *,ushort * *)

- ea: `0x18001fb28`
- end: `0x180020037`
- name: `?SerializeSessionContext@CflApi@@YAJPEBU_GUID@@PEBGPEBEK1PEAPEAG@Z`
- size: `1295`
- prototype: `int(CflApi *__hidden this, const struct _GUID *, const unsigned __int16 *, const unsigned __int8 *, unsigned int, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `23`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180011230`

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
- `0x18001fb28`
- `0x180021000`
- `0x180021184`
- `0x180021420`
- `0x180022cf4`
- `0x1800230a8`
- `0x18002e008`

## string_xrefs

- `0x18001fe69`: `userSid`
- `0x18001fece`: `userSid`
- `0x18001ff75`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x18001ffc4`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`
- `0x180020005`: `onecore\ds\security\cfl\api\lib\cflapiimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CflApi::SerializeSessionContext(
        CflApi *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const unsigned __int8 *a4,
        __int64 a5,
        unsigned __int16 *a6)
{
  size_t v6; // rdi
  unsigned int v10; // ebx
  __int64 v11; // rdx
  char *v12; // rbx
  __int64 v13; // rax
  char v14; // r8
  __int64 v15; // r9
  __int64 v16; // rbx
  _QWORD *v17; // rax
  __int64 v18; // rax
  char v19; // dl
  _QWORD *v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  char *v23; // rbx
  __int64 v24; // rbx
  __int64 v25; // rax
  char v26; // dl
  __int64 v27; // r8
  __int64 v28; // rax
  char v29; // dl
  _QWORD *v30; // r8
  __int64 v31; // rbx
  _QWORD *v32; // rax
  __int64 v33; // rax
  char v34; // dl
  _QWORD *v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rax
  char v39; // dl
  _QWORD *v40; // rdx
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rdi
  int v46; // eax
  __int64 v47; // rdx
  __int64 v48; // r8
  const unsigned __int16 *v49; // r8
  HLOCAL v50; // rbx
  int v51; // eax
  unsigned int v52; // edi
  int v54; // [rsp+20h] [rbp-A9h]
  HLOCAL hMem; // [rsp+30h] [rbp-99h] BYREF
  _QWORD *v56; // [rsp+38h] [rbp-91h] BYREF
  HLOCAL *p_hMem; // [rsp+40h] [rbp-89h] BYREF
  _QWORD *v58; // [rsp+48h] [rbp-81h] BYREF
  char v59[8]; // [rsp+50h] [rbp-79h] BYREF
  char v60[8]; // [rsp+58h] [rbp-71h] BYREF
  void *v61[2]; // [rsp+60h] [rbp-69h] BYREF
  __int64 v62; // [rsp+70h] [rbp-59h]
  unsigned __int16 *v63[2]; // [rsp+80h] [rbp-49h] BYREF
  __int64 v64; // [rsp+90h] [rbp-39h]
  unsigned __int64 v65; // [rsp+98h] [rbp-31h]
  _BYTE v66[32]; // [rsp+A0h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+4Fh]

  v6 = (unsigned int)a4;
  if ( !this || !a2 || !a6 )
  {
    v10 = -2147467261;
    v11 = 563;
    goto LABEL_30;
  }
  if ( !*(_QWORD *)this && *((_QWORD *)this + 1) == _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0] )
  {
LABEL_8:
    v10 = -2147024809;
    v11 = 565;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)v10,
      v54);
    return v10;
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
  *(_QWORD *)a6 = 0;
  *(_OWORD *)v63 = 0;
  v64 = 0;
  v65 = 7;
  LOWORD(v63[0]) = 0;
  v59[0] = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
    v60,
    0);
  hMem = &p_hMem;
  v12 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
          (char *)&p_hMem,
          (const IID *)this);
  v13 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
          v59,
          "providerId");
  v14 = *(_BYTE *)v13;
  *(_BYTE *)v13 = *v12;
  *v12 = v14;
  v15 = *(_QWORD *)(v13 + 8);
  *(_QWORD *)(v13 + 8) = *((_QWORD *)v12 + 1);
  *((_QWORD *)v12 + 1) = v15;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v12 + 8);
  hMem = &p_hMem;
  std::wstring::wstring(v61, a2);
  v16 = anonymous_namespace_::Utf16ToUtf8(v66, v61);
  v58 = 0;
  LOBYTE(p_hMem) = 3;
  v17 = operator new(0x20u);
  *(_OWORD *)v17 = 0;
  v17[2] = 0;
  v17[3] = 0;
  *(_OWORD *)v17 = *(_OWORD *)v16;
  *((_OWORD *)v17 + 1) = *(_OWORD *)(v16 + 16);
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 15;
  *(_BYTE *)v16 = 0;
  v58 = v17;
  v18 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
          v59,
          "scenarioId");
  v19 = *(_BYTE *)v18;
  *(_BYTE *)v18 = (_BYTE)p_hMem;
  LOBYTE(p_hMem) = v19;
  v20 = *(_QWORD **)(v18 + 8);
  *(_QWORD *)(v18 + 8) = v58;
  v58 = v20;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v58);
  std::string::~string(v66);
  std::wstring::~wstring(v61, v21, v22);
  if ( a3 )
  {
    p_hMem = (HLOCAL *)v66;
    *(_OWORD *)v61 = 0;
    v62 = 0;
    if ( v6 )
    {
      std::vector<unsigned char>::_Buy_nonzero(v61, v6);
      v23 = (char *)v61[0];
      memmove_0(v61[0], a3, v6);
      v61[1] = &v23[v6];
      hMem = 0;
      std::_Tidy_guard<std::vector<unsigned char>>::~_Tidy_guard<std::vector<unsigned char>>(&hMem);
    }
    v24 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
            v66,
            v61);
    v25 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v59,
            "scenarioContext");
    v26 = *(_BYTE *)v25;
    *(_BYTE *)v25 = *(_BYTE *)v24;
    *(_BYTE *)v24 = v26;
    v27 = *(_QWORD *)(v25 + 8);
    *(_QWORD *)(v25 + 8) = *(_QWORD *)(v24 + 8);
    *(_QWORD *)(v24 + 8) = v27;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v24 + 8);
    std::vector<char>::~vector<char>(v61);
  }
  else
  {
    p_hMem = &hMem;
    LOBYTE(hMem) = 0;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v56,
      0);
    v28 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v59,
            "scenarioContext");
    v29 = *(_BYTE *)v28;
    *(_BYTE *)v28 = (_BYTE)hMem;
    LOBYTE(hMem) = v29;
    v30 = *(_QWORD **)(v28 + 8);
    *(_QWORD *)(v28 + 8) = v56;
    v56 = v30;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v56);
  }
  p_hMem = &hMem;
  if ( a5 )
  {
    std::wstring::wstring(v61, a5);
    v31 = anonymous_namespace_::Utf16ToUtf8(v66, v61);
    v56 = 0;
    LOBYTE(hMem) = 3;
    v32 = operator new(0x20u);
    *(_OWORD *)v32 = 0;
    v32[2] = 0;
    v32[3] = 0;
    *(_OWORD *)v32 = *(_OWORD *)v31;
    *((_OWORD *)v32 + 1) = *(_OWORD *)(v31 + 16);
    *(_QWORD *)(v31 + 16) = 0;
    *(_QWORD *)(v31 + 24) = 15;
    *(_BYTE *)v31 = 0;
    v56 = v32;
    v33 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v59,
            "userSid");
    v34 = *(_BYTE *)v33;
    *(_BYTE *)v33 = (_BYTE)hMem;
    LOBYTE(hMem) = v34;
    v35 = *(_QWORD **)(v33 + 8);
    *(_QWORD *)(v33 + 8) = v56;
    v56 = v35;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v56);
    std::string::~string(v66);
    std::wstring::~wstring(v61, v36, v37);
  }
  else
  {
    LOBYTE(hMem) = 0;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v56,
      0);
    v38 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
            v59,
            "userSid");
    v39 = *(_BYTE *)v38;
    *(_BYTE *)v38 = (_BYTE)hMem;
    LOBYTE(hMem) = v39;
    v40 = *(_QWORD **)(v38 + 8);
    *(_QWORD *)(v38 + 8) = v56;
    v56 = v40;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(&v56);
  }
  v41 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::dump(
          v59,
          v66);
  v42 = anonymous_namespace_::Utf8ToUtf16(v61, v41);
  std::wstring::operator=(v63, v42);
  std::wstring::~wstring(v61, v43, v44);
  std::string::~string(v66);
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v60);
  v45 = v64;
  hMem = 0;
  v46 = CflApiNew::AllocBuffer_unsigned_short_(v64 + 1, &hMem);
  v10 = v46;
  if ( v46 >= 0 )
  {
    v49 = (const unsigned __int16 *)v63;
    if ( v65 > 7 )
      v49 = v63[0];
    v50 = hMem;
    v51 = StringCchCopyW((unsigned __int16 *)hMem, v45 + 1, v49);
    v52 = v51;
    if ( v51 >= 0 )
    {
      *(_QWORD *)a6 = v50;
      v10 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
        (const char *)(unsigned int)v51,
        v54);
      if ( v50 )
        CflFreeBuffer(v50);
      v10 = v52;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x255,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimpl.cpp",
      (const char *)(unsigned int)v46,
      v54);
    if ( hMem )
      CflFreeBuffer(hMem);
  }
  std::wstring::~wstring(v63, v47, v48);
  return v10;
}

```

## disassembly

```asm
0x18001fb28  push    rbp
0x18001fb2a  push    rbx
0x18001fb2b  push    rsi
0x18001fb2c  push    rdi
0x18001fb2d  push    r12
0x18001fb2f  push    r13
0x18001fb31  push    r14
0x18001fb33  push    r15
0x18001fb35  lea     rbp, [rsp-0Fh]
0x18001fb3a  sub     rsp, 0D8h
0x18001fb41  mov     rax, cs:__security_cookie
0x18001fb48  xor     rax, rsp
0x18001fb4b  mov     [rbp+47h+var_50], rax
0x18001fb4f  mov     edi, r9d
0x18001fb52  mov     rsi, r8
0x18001fb55  mov     r12, rdx
0x18001fb58  mov     rbx, rcx
0x18001fb5b  mov     r15, [rbp+47h+arg_20]
0x18001fb5f  mov     r14, [rbp+47h+arg_28]
0x18001fb63  xor     r13d, r13d
0x18001fb66  test    rcx, rcx
0x18001fb69  jz      loc_18001FFF8
0x18001fb6f  test    rdx, rdx
0x18001fb72  jz      loc_18001FFF8
0x18001fb78  test    r14, r14
0x18001fb7b  jz      loc_18001FFF8
0x18001fb81  xorps   xmm0, xmm0
0x18001fb84  movq    rax, xmm0
0x18001fb89  cmp     [rcx], rax
0x18001fb8c  jnz     short loc_18001FB9E
0x18001fb8e  psrldq  xmm0, 8
0x18001fb93  movq    rax, xmm0
0x18001fb98  cmp     [rcx+8], rax
0x18001fb9c  jz      short loc_18001FBA8
0x18001fb9e  test    rsi, rsi
0x18001fba1  jz      short loc_18001FBB7
0x18001fba3  test    r9d, r9d
0x18001fba6  jnz     short loc_18001FBBC
0x18001fba8  mov     ebx, 80070057h
0x18001fbad  mov     edx, 235h
0x18001fbb2  jmp     loc_180020002
0x18001fbb7  test    r9d, r9d
0x18001fbba  jnz     short loc_18001FBA8
0x18001fbbc  mov     [r14], r13
0x18001fbbf  xorps   xmm0, xmm0
0x18001fbc2  movups  xmmword ptr [rbp+47h+var_90], xmm0
0x18001fbc6  mov     [rbp+47h+var_80], r13
0x18001fbca  mov     [rbp+47h+var_78], 7
0x18001fbd2  mov     word ptr [rbp+47h+var_90], r13w
0x18001fbd7  mov     [rbp+47h+var_C0], r13b
0x18001fbdb  xor     edx, edx
0x18001fbdd  lea     rcx, [rbp+47h+var_B8]
0x18001fbe1  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18001fbe6  nop
0x18001fbe7  lea     rax, [rsp+110h+var_D0]
0x18001fbec  mov     [rsp+110h+hMem], rax
0x18001fbf1  mov     rdx, rbx
0x18001fbf4  lea     rcx, [rsp+110h+var_D0]
0x18001fbf9  call    ??$?0AEBU_GUID@@U0@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBU_GUID@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(_GUID const &)
0x18001fbfe  mov     rbx, rax
0x18001fc01  lea     rdx, aProviderid_0; "providerId"
0x18001fc08  lea     rcx, [rbp+47h+var_C0]
0x18001fc0c  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fc11  nop
0x18001fc12  mov     r8b, [rax]
0x18001fc15  mov     cl, [rbx]
0x18001fc17  mov     [rax], cl
0x18001fc19  mov     [rbx], r8b
0x18001fc1c  lea     rcx, [rbx+8]
0x18001fc20  mov     r9, [rax+8]
0x18001fc24  mov     r8, [rcx]
0x18001fc27  mov     [rax+8], r8
0x18001fc2b  mov     [rcx], r9
0x18001fc2e  mov     dl, [rbx]
0x18001fc30  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001fc35  lea     rax, [rsp+110h+var_D0]
0x18001fc3a  mov     [rsp+110h+hMem], rax
0x18001fc3f  mov     rdx, r12
0x18001fc42  lea     rcx, [rbp+47h+var_B0]
0x18001fc46  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001fc4b  nop
0x18001fc4c  lea     rdx, [rbp+47h+var_B0]
0x18001fc50  lea     rcx, [rbp+47h+var_70]
0x18001fc54  call    _anonymous_namespace___Utf16ToUtf8
0x18001fc59  mov     rbx, rax
0x18001fc5c  xor     eax, eax
0x18001fc5e  mov     [rsp+110h+var_C8], rax
0x18001fc63  mov     byte ptr [rsp+110h+var_D0], 3
0x18001fc68  lea     r12d, [rax+20h]
0x18001fc6c  mov     ecx, r12d; Size
0x18001fc6f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fc74  xorps   xmm0, xmm0
0x18001fc77  movups  xmmword ptr [rax], xmm0
0x18001fc7a  mov     [rax+10h], r13
0x18001fc7e  mov     [rax+18h], r13
0x18001fc82  movups  xmm0, xmmword ptr [rbx]
0x18001fc85  movups  xmmword ptr [rax], xmm0
0x18001fc88  movups  xmm1, xmmword ptr [rbx+10h]
0x18001fc8c  movups  xmmword ptr [rax+10h], xmm1
0x18001fc90  mov     [rbx+10h], r13
0x18001fc94  mov     qword ptr [rbx+18h], 0Fh
0x18001fc9c  mov     [rbx], r13b
0x18001fc9f  mov     [rsp+110h+var_C8], rax
0x18001fca4  lea     rdx, aScenarioid_0; "scenarioId"
0x18001fcab  lea     rcx, [rbp+47h+var_C0]
0x18001fcaf  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fcb4  nop
0x18001fcb5  mov     dl, [rax]
0x18001fcb7  mov     cl, byte ptr [rsp+110h+var_D0]
0x18001fcbb  mov     [rax], cl
0x18001fcbd  mov     byte ptr [rsp+110h+var_D0], dl
0x18001fcc1  mov     rdx, [rax+8]
0x18001fcc5  mov     rcx, [rsp+110h+var_C8]
0x18001fcca  mov     [rax+8], rcx
0x18001fcce  mov     [rsp+110h+var_C8], rdx
0x18001fcd3  mov     dl, byte ptr [rsp+110h+var_D0]
0x18001fcd7  lea     rcx, [rsp+110h+var_C8]
0x18001fcdc  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001fce1  nop
0x18001fce2  lea     rcx, [rbp+47h+var_70]
0x18001fce6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001fceb  nop
0x18001fcec  lea     rcx, [rbp+47h+var_B0]
0x18001fcf0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fcf5  test    rsi, rsi
0x18001fcf8  jz      loc_18001FD9C
0x18001fcfe  lea     rax, [rbp+47h+var_70]
0x18001fd02  mov     [rsp+110h+var_D0], rax
0x18001fd07  xorps   xmm0, xmm0
0x18001fd0a  movdqu  xmmword ptr [rbp+47h+var_B0], xmm0
0x18001fd0f  mov     [rbp+47h+var_A0], r13
0x18001fd13  test    rdi, rdi
0x18001fd16  jz      short loc_18001FD4E
0x18001fd18  mov     rdx, rdi
0x18001fd1b  lea     rcx, [rbp+47h+var_B0]
0x18001fd1f  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x18001fd24  mov     rbx, [rbp+47h+var_B0]
0x18001fd28  mov     r8, rdi; Size
0x18001fd2b  mov     rdx, rsi; Src
0x18001fd2e  mov     rcx, rbx; void *
0x18001fd31  call    memmove_0
0x18001fd36  lea     rax, [rdi+rbx]
0x18001fd3a  mov     [rbp+47h+var_B0+8], rax
0x18001fd3e  mov     [rsp+110h+hMem], r13
0x18001fd43  lea     rcx, [rsp+110h+hMem]
0x18001fd48  call    ??1?$_Tidy_guard@V?$vector@EV?$allocator@E@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uchar>>::~_Tidy_guard<std::vector<uchar>>(void)
0x18001fd4d  nop
0x18001fd4e  lea     rdx, [rbp+47h+var_B0]
0x18001fd52  lea     rcx, [rbp+47h+var_70]
0x18001fd56  call    ??$?0V?$vector@EV?$allocator@E@std@@@std@@V01@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@$$QEAV?$vector@EV?$allocator@E@std@@@std@@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(std::vector<uchar> &&)
0x18001fd5b  mov     rbx, rax
0x18001fd5e  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18001fd65  lea     rcx, [rbp+47h+var_C0]
0x18001fd69  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fd6e  nop
0x18001fd6f  mov     dl, [rax]
0x18001fd71  mov     cl, [rbx]
0x18001fd73  mov     [rax], cl
0x18001fd75  mov     [rbx], dl
0x18001fd77  lea     rcx, [rbx+8]
0x18001fd7b  mov     r8, [rax+8]
0x18001fd7f  mov     rdx, [rcx]
0x18001fd82  mov     [rax+8], rdx
0x18001fd86  mov     [rcx], r8
0x18001fd89  mov     dl, [rbx]
0x18001fd8b  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001fd90  nop
0x18001fd91  lea     rcx, [rbp+47h+var_B0]
0x18001fd95  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001fd9a  jmp     short loc_18001FDF5
0x18001fd9c  lea     rax, [rsp+110h+hMem]
0x18001fda1  mov     [rsp+110h+var_D0], rax
0x18001fda6  mov     byte ptr [rsp+110h+hMem], r13b
0x18001fdab  xor     edx, edx
0x18001fdad  lea     rcx, [rsp+110h+var_D8]
0x18001fdb2  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18001fdb7  nop
0x18001fdb8  lea     rdx, aScenariocontex_0; "scenarioContext"
0x18001fdbf  lea     rcx, [rbp+47h+var_C0]
0x18001fdc3  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fdc8  nop
0x18001fdc9  mov     dl, [rax]
0x18001fdcb  mov     cl, byte ptr [rsp+110h+hMem]
0x18001fdcf  mov     [rax], cl
0x18001fdd1  mov     byte ptr [rsp+110h+hMem], dl
0x18001fdd5  mov     r8, [rax+8]
0x18001fdd9  mov     rcx, [rsp+110h+var_D8]
0x18001fdde  mov     [rax+8], rcx
0x18001fde2  mov     [rsp+110h+var_D8], r8
0x18001fde7  mov     dl, byte ptr [rsp+110h+hMem]
0x18001fdeb  lea     rcx, [rsp+110h+var_D8]
0x18001fdf0  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001fdf5  lea     rax, [rsp+110h+hMem]
0x18001fdfa  mov     [rsp+110h+var_D0], rax
0x18001fdff  test    r15, r15
0x18001fe02  jz      loc_18001FEBC
0x18001fe08  mov     rdx, r15
0x18001fe0b  lea     rcx, [rbp+47h+var_B0]
0x18001fe0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001fe14  nop
0x18001fe15  lea     rdx, [rbp+47h+var_B0]
0x18001fe19  lea     rcx, [rbp+47h+var_70]
0x18001fe1d  call    _anonymous_namespace___Utf16ToUtf8
0x18001fe22  mov     rbx, rax
0x18001fe25  xor     eax, eax
0x18001fe27  mov     [rsp+110h+var_D8], rax
0x18001fe2c  mov     byte ptr [rsp+110h+hMem], 3
0x18001fe31  mov     rcx, r12; Size
0x18001fe34  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001fe39  xorps   xmm0, xmm0
0x18001fe3c  movups  xmmword ptr [rax], xmm0
0x18001fe3f  mov     [rax+10h], r13
0x18001fe43  mov     [rax+18h], r13
0x18001fe47  movups  xmm0, xmmword ptr [rbx]
0x18001fe4a  movups  xmmword ptr [rax], xmm0
0x18001fe4d  movups  xmm1, xmmword ptr [rbx+10h]
0x18001fe51  movups  xmmword ptr [rax+10h], xmm1
0x18001fe55  mov     [rbx+10h], r13
0x18001fe59  mov     qword ptr [rbx+18h], 0Fh
0x18001fe61  mov     [rbx], r13b
0x18001fe64  mov     [rsp+110h+var_D8], rax
0x18001fe69  lea     rdx, aUsersid; "userSid"
0x18001fe70  lea     rcx, [rbp+47h+var_C0]
0x18001fe74  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fe79  nop
0x18001fe7a  mov     dl, [rax]
0x18001fe7c  mov     cl, byte ptr [rsp+110h+hMem]
0x18001fe80  mov     [rax], cl
0x18001fe82  mov     byte ptr [rsp+110h+hMem], dl
0x18001fe86  mov     rdx, [rax+8]
0x18001fe8a  mov     rcx, [rsp+110h+var_D8]
0x18001fe8f  mov     [rax+8], rcx
0x18001fe93  mov     [rsp+110h+var_D8], rdx
0x18001fe98  mov     dl, byte ptr [rsp+110h+hMem]
0x18001fe9c  lea     rcx, [rsp+110h+var_D8]
0x18001fea1  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001fea6  nop
0x18001fea7  lea     rcx, [rbp+47h+var_70]
0x18001feab  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001feb0  nop
0x18001feb1  lea     rcx, [rbp+47h+var_B0]
0x18001feb5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001feba  jmp     short loc_18001FF0B
0x18001febc  mov     byte ptr [rsp+110h+hMem], r13b
0x18001fec1  xor     edx, edx
0x18001fec3  lea     rcx, [rsp+110h+var_D8]
0x18001fec8  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18001fecd  nop
0x18001fece  lea     rdx, aUsersid; "userSid"
0x18001fed5  lea     rcx, [rbp+47h+var_C0]
0x18001fed9  call    ??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::operator[]<char const>(char const *)
0x18001fede  nop
0x18001fedf  mov     dl, [rax]
0x18001fee1  mov     cl, byte ptr [rsp+110h+hMem]
0x18001fee5  mov     [rax], cl
0x18001fee7  mov     byte ptr [rsp+110h+hMem], dl
0x18001feeb  mov     rdx, [rax+8]
0x18001feef  mov     rcx, [rsp+110h+var_D8]
0x18001fef4  mov     [rax+8], rcx
0x18001fef8  mov     [rsp+110h+var_D8], rdx
0x18001fefd  mov     dl, byte ptr [rsp+110h+hMem]
0x18001ff01  lea     rcx, [rsp+110h+var_D8]
0x18001ff06  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001ff0b  lea     rdx, [rbp+47h+var_70]
0x18001ff0f  lea     rcx, [rbp+47h+var_C0]
0x18001ff13  call    ?dump@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@HD_NW4error_handler_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::dump(int,char,bool,nlohmann::detail::error_handler_t)
0x18001ff18  nop
0x18001ff19  mov     rdx, rax
0x18001ff1c  lea     rcx, [rbp+47h+var_B0]
0x18001ff20  call    _anonymous_namespace___Utf8ToUtf16
0x18001ff25  mov     rdx, rax
0x18001ff28  lea     rcx, [rbp+47h+var_90]
0x18001ff2c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001ff31  lea     rcx, [rbp+47h+var_B0]
0x18001ff35  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ff3a  nop
0x18001ff3b  lea     rcx, [rbp+47h+var_70]
0x18001ff3f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001ff44  nop
0x18001ff45  mov     dl, [rbp+47h+var_C0]
0x18001ff48  lea     rcx, [rbp+47h+var_B8]
0x18001ff4c  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001ff51  mov     rdi, [rbp+47h+var_80]
0x18001ff55  mov     [rsp+110h+hMem], r13
0x18001ff5a  lea     rdx, [rsp+110h+hMem]
0x18001ff5f  lea     rcx, [rdi+1]
0x18001ff63  call    CflApiNew__AllocBuffer_unsigned_short_
0x18001ff68  mov     ebx, eax
0x18001ff6a  test    eax, eax
0x18001ff6c  jns     short loc_18001FF98
0x18001ff6e  mov     rcx, [rbp+4Fh]; this
0x18001ff72  mov     r9d, eax; char *
0x18001ff75  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18001ff7c  mov     edx, 255h; void *
0x18001ff81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ff86  nop
0x18001ff87  mov     rcx, [rsp+110h+hMem]; hMem
0x18001ff8c  test    rcx, rcx
0x18001ff8f  jz      short loc_18001FFED
0x18001ff91  call    CflFreeBuffer
  ... truncated ...
```
