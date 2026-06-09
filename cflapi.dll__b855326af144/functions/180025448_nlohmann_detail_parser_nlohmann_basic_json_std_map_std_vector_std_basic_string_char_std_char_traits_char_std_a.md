# nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(bool,nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>> &)

- ea: `0x180025448`
- end: `0x180025884`
- name: `?parse@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAAX_NAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@3@@Z`
- size: `1084`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config`

## callers

- `0x1800178d0`

## callees

- `0x180002490`
- `0x180002e12`
- `0x180002f04`
- `0x180008a68`
- `0x180017b94`
- `0x180018df4`
- `0x180019fb8`
- `0x18001a674`
- `0x18001a80c`
- `0x18001ac5c`
- `0x18001b20c`
- `0x1800229d4`
- `0x180022cf4`
- `0x180024524`
- `0x180024a70`
- `0x180025448`
- `0x180025a34`
- `0x180025d30`
- `0x180030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::parse(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 (__fastcall ***v5)(_QWORD, _BYTE *); // rcx
  char v6; // si
  __int64 v7; // rdx
  _BYTE *v8; // rcx
  _BYTE *v9; // rdx
  __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  _QWORD *v13; // rax
  __int64 v14; // rdx
  const struct nlohmann::detail::parse_error *v15; // rdi
  unsigned __int8 v16; // dl
  __int64 v17; // rcx
  __int64 v19; // rsi
  int v20; // eax
  __int64 v21; // rdx
  _QWORD *v22; // rax
  __int64 v23; // rdx
  const struct nlohmann::detail::parse_error *v24; // rdi
  unsigned __int8 v25; // dl
  __int64 v26; // rcx
  char v27[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v28; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v29; // [rsp+38h] [rbp-C8h]
  _BYTE *v30; // [rsp+40h] [rbp-C0h]
  void **v31; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  char v34; // [rsp+70h] [rbp-90h] BYREF
  char v35; // [rsp+71h] [rbp-8Fh]
  _BYTE v36[56]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE *v37; // [rsp+C0h] [rbp-40h]
  void **v38; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v39[24]; // [rsp+D0h] [rbp-30h] BYREF
  void **v40; // [rsp+E8h] [rbp-18h]
  _BYTE v41[24]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v43[4]; // [rsp+148h] [rbp+48h] BYREF
  _QWORD v44[4]; // [rsp+168h] [rbp+68h] BYREF
  _QWORD v45[5]; // [rsp+188h] [rbp+88h] BYREF
  char *v46[2]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v47; // [rsp+1C0h] [rbp+C0h]
  _OWORD v48[4]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v49; // [rsp+210h] [rbp+110h]
  char v50; // [rsp+218h] [rbp+118h]
  _BYTE v51[56]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v52; // [rsp+258h] [rbp+158h]
  char v53; // [rsp+260h] [rbp+160h]
  char v54; // [rsp+268h] [rbp+168h]
  _BYTE v55[16]; // [rsp+270h] [rbp+170h] BYREF

  v5 = *(__int64 (__fastcall ****)(_QWORD, _BYTE *))(a1 + 56);
  v6 = *(_BYTE *)(a1 + 224);
  if ( v5 )
  {
    v30 = v36;
    v37 = 0;
    v8 = (_BYTE *)(**v5)(v5, v36);
    v37 = v8;
    v30 = v36;
    v46[0] = (char *)a3;
    v46[1] = 0;
    v47 = 0;
    memset(v48, 0, sizeof(v48));
    v49 = 0;
    v50 = 0;
    *(_QWORD *)&v28 = v51;
    v52 = 0;
    if ( v8 )
      v52 = (**(__int64 (__fastcall ***)(_BYTE *, _BYTE *))v8)(v8, v51);
    v53 = v6;
    v54 = 9;
    LOBYTE(v7) = 9;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      v55,
      v7);
    v27[0] = 1;
    std::vector<bool>::push_back(v48, v27);
    if ( v37 )
    {
      v9 = v36;
      LOBYTE(v9) = v37 != v36;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v37 + 32LL))(v37, v9);
      v37 = 0;
    }
    nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
      a1,
      v46);
    v10 = a1 + 72;
    v11 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
    *(_DWORD *)(a1 + 64) = v11;
    if ( v11 != 15 )
    {
      std::string::string(v43, "value");
      v13 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
              a1,
              v45,
              0xFu,
              v43);
      v28 = *(_OWORD *)(a1 + 104);
      v29 = *(_QWORD *)(a1 + 120);
      v15 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v31, v14, &v28, v13);
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        v10,
        v44);
      v50 = 1;
      if ( v53 )
      {
        nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v38, v15);
        throw (nlohmann::detail::parse_error *)&v38;
      }
      std::string::~string(v44);
      *((_QWORD *)&v33 + 1) = &std::exception::`vftable';
      o___std_exception_destroy_0(&v34);
      v31 = &std::exception::`vftable';
      o___std_exception_destroy_0(&v32);
      std::string::~string(v45);
      std::string::~string(v43);
    }
    if ( v50 )
    {
      LOBYTE(v28) = 9;
      LOBYTE(v12) = 9;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        (char *)&v28 + 8,
        v12);
    }
    else
    {
      if ( *(_BYTE *)a3 != 9 )
        return nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::~json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(v46);
      LOBYTE(v28) = 0;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        (char *)&v28 + 8,
        0);
    }
    v16 = *(_BYTE *)a3;
    *(_BYTE *)a3 = v28;
    LOBYTE(v28) = v16;
    v17 = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(a3 + 8) = *((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = v17;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)&v28 + 1,
      v16);
    return nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::~json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(v46);
  }
  v31 = (void **)a3;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = v6;
  nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
    a1,
    (char **)&v31);
  v19 = a1 + 72;
  v20 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
  *(_DWORD *)(a1 + 64) = v20;
  if ( v20 != 15 )
  {
    std::string::string(v43, "value");
    v22 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
            a1,
            v44,
            0xFu,
            v43);
    v28 = *(_OWORD *)(a1 + 104);
    v29 = *(_QWORD *)(a1 + 120);
    v24 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v38, v23, &v28, v22);
    nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
      v19,
      v45);
    v34 = 1;
    if ( v35 )
    {
      nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)pExceptionObject, v24);
      throw (nlohmann::detail::parse_error *)pExceptionObject;
    }
    std::string::~string(v45);
    v40 = &std::exception::`vftable';
    o___std_exception_destroy_0(v41);
    v38 = &std::exception::`vftable';
    o___std_exception_destroy_0(v39);
    std::string::~string(v44);
    std::string::~string(v43);
  }
  if ( v34 )
  {
    LOBYTE(v28) = 9;
    LOBYTE(v21) = 9;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      (char *)&v28 + 8,
      v21);
    v25 = *(_BYTE *)a3;
    *(_BYTE *)a3 = v28;
    LOBYTE(v28) = v25;
    v26 = *(_QWORD *)(a3 + 8);
    *(_QWORD *)(a3 + 8) = *((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = v26;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)&v28 + 1,
      v25);
  }
  return std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::~vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>(&v32);
}

```

## disassembly

```asm
0x180025448  mov     [rsp-8+arg_8], rbx
0x18002544d  mov     [rsp-8+arg_18], rsi
0x180025452  push    rbp
0x180025453  push    rdi
0x180025454  push    r14
0x180025456  lea     rbp, [rsp-190h]
0x18002545e  sub     rsp, 290h
0x180025465  mov     rax, cs:__security_cookie
0x18002546c  xor     rax, rsp
0x18002546f  mov     [rbp+1A0h+var_20], rax
0x180025476  mov     rbx, r8
0x180025479  mov     rdi, rcx
0x18002547c  mov     rcx, [rcx+38h]
0x180025480  mov     sil, [rdi+0E0h]
0x180025487  xor     r14d, r14d
0x18002548a  test    rcx, rcx
0x18002548d  jz      loc_1800256E0
0x180025493  lea     rax, [rbp+1A0h+var_218]
0x180025497  mov     [rsp+2A0h+var_260], rax
0x18002549c  mov     [rbp+1A0h+var_1E0], r14
0x1800254a0  mov     rax, [rcx]
0x1800254a3  lea     rdx, [rbp+1A0h+var_218]
0x1800254a7  mov     rax, [rax]
0x1800254aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254af  mov     rcx, rax
0x1800254b2  mov     [rbp+1A0h+var_1E0], rax
0x1800254b6  lea     rax, [rbp+1A0h+var_218]
0x1800254ba  mov     [rsp+2A0h+var_260], rax
0x1800254bf  mov     [rbp+1A0h+var_F0], rbx
0x1800254c6  mov     [rbp+1A0h+var_E8], r14
0x1800254cd  xorps   xmm0, xmm0
0x1800254d0  movdqa  [rbp+1A0h+var_E0], xmm0
0x1800254d8  movdqa  [rbp+1A0h+var_D0], xmm0
0x1800254e0  xorps   xmm1, xmm1
0x1800254e3  movdqa  [rbp+1A0h+var_C0], xmm1
0x1800254eb  movdqa  [rbp+1A0h+var_B0], xmm0
0x1800254f3  movdqa  [rbp+1A0h+var_A0], xmm1
0x1800254fb  mov     [rbp+1A0h+var_90], r14
0x180025502  mov     [rbp+1A0h+var_88], r14b
0x180025509  lea     rax, [rbp+1A0h+var_80]
0x180025510  mov     qword ptr [rsp+2A0h+var_278], rax
0x180025515  mov     [rbp+1A0h+var_48], r14
0x18002551c  test    rcx, rcx
0x18002551f  jz      short loc_18002553A
0x180025521  mov     rax, [rcx]
0x180025524  lea     rdx, [rbp+1A0h+var_80]
0x18002552b  mov     rax, [rax]
0x18002552e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025533  mov     [rbp+1A0h+var_48], rax
0x18002553a  mov     [rbp+1A0h+var_40], sil
0x180025541  mov     [rbp+1A0h+var_38], 9
0x180025548  mov     dl, 9
0x18002554a  lea     rcx, [rbp+1A0h+var_30]
0x180025551  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180025556  nop
0x180025557  mov     [rsp+2A0h+var_280], 1
0x18002555c  lea     rdx, [rsp+2A0h+var_280]
0x180025561  lea     rcx, [rbp+1A0h+var_D0]
0x180025568  call    ?push_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXAEB_N@Z; std::vector<bool>::push_back(bool const &)
0x18002556d  nop
0x18002556e  mov     rcx, [rbp+1A0h+var_1E0]
0x180025572  test    rcx, rcx
0x180025575  jz      short loc_180025591
0x180025577  mov     rax, [rcx]
0x18002557a  lea     rdx, [rbp+1A0h+var_218]
0x18002557e  cmp     rcx, rdx
0x180025581  setnz   dl
0x180025584  mov     rax, [rax+20h]
0x180025588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002558d  mov     [rbp+1A0h+var_1E0], r14
0x180025591  lea     rdx, [rbp+1A0h+var_F0]
0x180025598  mov     rcx, rdi
0x18002559b  call    ??$sax_parse_internal@V?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA_NPEAV?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@12@@Z; nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>(nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> *)
0x1800255a0  lea     rsi, [rdi+48h]
0x1800255a4  mov     rcx, rsi
0x1800255a7  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x1800255ac  mov     [rdi+40h], eax
0x1800255af  cmp     eax, 0Fh
0x1800255b2  jz      loc_180025673
0x1800255b8  lea     rdx, aValue; "value"
0x1800255bf  lea     rcx, [rbp+1A0h+var_158]
0x1800255c3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800255c8  nop
0x1800255c9  lea     r9, [rbp+1A0h+var_158]
0x1800255cd  mov     r8d, 0Fh
0x1800255d3  lea     rdx, [rbp+1A0h+var_118]
0x1800255da  mov     rcx, rdi
0x1800255dd  call    ?exception_message@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@AEBV45@@Z; nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type,std::string const &)
0x1800255e2  nop
0x1800255e3  movups  xmm0, xmmword ptr [rdi+68h]
0x1800255e7  movups  [rsp+2A0h+var_278], xmm0
0x1800255ec  movsd   xmm1, qword ptr [rdi+78h]
0x1800255f1  movsd   [rsp+2A0h+var_268], xmm1
0x1800255f7  mov     r9, rax
0x1800255fa  lea     r8, [rsp+2A0h+var_278]
0x1800255ff  lea     rcx, [rsp+2A0h+var_258]
0x180025604  call    ?create@parse_error@detail@nlohmann@@SA?AV123@HAEBUposition_t@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::parse_error::create(int,nlohmann::detail::position_t const &,std::string const &)
0x180025609  mov     rdi, rax
0x18002560c  lea     rdx, [rbp+1A0h+var_138]
0x180025610  mov     rcx, rsi
0x180025613  call    ?get_token_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(void)
0x180025618  nop
0x180025619  mov     [rbp+1A0h+var_88], 1
0x180025620  cmp     [rbp+1A0h+var_40], r14b
0x180025627  jnz     loc_180025867
0x18002562d  lea     rcx, [rbp+1A0h+var_138]
0x180025631  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025636  nop
0x180025637  lea     rdi, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18002563e  mov     [rsp+2A0h+var_238], rdi
0x180025643  lea     rcx, [rsp+2A0h+var_230]
0x180025648  call    _o___std_exception_destroy_0
0x18002564d  mov     [rsp+2A0h+var_258], rdi
0x180025652  lea     rcx, [rsp+2A0h+var_250]
0x180025657  call    _o___std_exception_destroy_0
0x18002565c  nop
0x18002565d  lea     rcx, [rbp+1A0h+var_118]
0x180025664  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025669  nop
0x18002566a  lea     rcx, [rbp+1A0h+var_158]
0x18002566e  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180025673  cmp     [rbp+1A0h+var_88], r14b
0x18002567a  jz      short loc_18002568F
0x18002567c  mov     byte ptr [rsp+2A0h+var_278], 9
0x180025681  mov     dl, 9
0x180025683  lea     rcx, [rsp+2A0h+var_278+8]
0x180025688  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x18002568d  jmp     short loc_1800256A6
0x18002568f  cmp     byte ptr [rbx], 9
0x180025692  jnz     short loc_1800256CF
0x180025694  mov     byte ptr [rsp+2A0h+var_278], r14b
0x180025699  xor     edx, edx
0x18002569b  lea     rcx, [rsp+2A0h+var_278+8]
0x1800256a0  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x1800256a5  nop
0x1800256a6  mov     dl, [rbx]
0x1800256a8  mov     al, byte ptr [rsp+2A0h+var_278]
0x1800256ac  mov     [rbx], al
0x1800256ae  mov     byte ptr [rsp+2A0h+var_278], dl
0x1800256b2  mov     rcx, [rbx+8]
0x1800256b6  mov     rax, qword ptr [rsp+2A0h+var_278+8]
0x1800256bb  mov     [rbx+8], rax
0x1800256bf  mov     qword ptr [rsp+2A0h+var_278+8], rcx
0x1800256c4  lea     rcx, [rsp+2A0h+var_278+8]
0x1800256c9  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800256ce  nop
0x1800256cf  lea     rcx, [rbp+1A0h+var_F0]
0x1800256d6  call    ??1?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAA@XZ; nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::~json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(void)
0x1800256db  jmp     loc_180025823
0x1800256e0  mov     [rsp+2A0h+var_258], rbx
0x1800256e5  xorps   xmm0, xmm0
0x1800256e8  movdqu  [rsp+2A0h+var_250], xmm0
0x1800256ee  xorps   xmm1, xmm1
0x1800256f1  movdqu  xmmword ptr [rsp+60h], xmm1
0x1800256f7  mov     [rsp+2A0h+var_230], r14b
0x1800256fc  mov     [rsp+2A0h+var_22F], sil
0x180025701  lea     rdx, [rsp+2A0h+var_258]
0x180025706  mov     rcx, rdi
0x180025709  call    ??$sax_parse_internal@V?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA_NPEAV?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@12@@Z; nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>(nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>> *)
0x18002570e  lea     rsi, [rdi+48h]
0x180025712  mov     rcx, rsi
0x180025715  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x18002571a  mov     [rdi+40h], eax
0x18002571d  cmp     eax, 0Fh
0x180025720  jz      loc_1800257D8
0x180025726  lea     rdx, aValue; "value"
0x18002572d  lea     rcx, [rbp+1A0h+var_158]
0x180025731  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180025736  nop
0x180025737  lea     r9, [rbp+1A0h+var_158]
0x18002573b  mov     r8d, 0Fh
0x180025741  lea     rdx, [rbp+1A0h+var_138]
0x180025745  mov     rcx, rdi
0x180025748  call    ?exception_message@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@AEBV45@@Z; nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type,std::string const &)
0x18002574d  nop
0x18002574e  movups  xmm0, xmmword ptr [rdi+68h]
0x180025752  movups  [rsp+2A0h+var_278], xmm0
0x180025757  movsd   xmm1, qword ptr [rdi+78h]
0x18002575c  movsd   [rsp+2A0h+var_268], xmm1
0x180025762  mov     r9, rax
0x180025765  lea     r8, [rsp+2A0h+var_278]
0x18002576a  lea     rcx, [rbp+1A0h+var_1D8]
0x18002576e  call    ?create@parse_error@detail@nlohmann@@SA?AV123@HAEBUposition_t@23@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::parse_error::create(int,nlohmann::detail::position_t const &,std::string const &)
0x180025773  mov     rdi, rax
0x180025776  lea     rdx, [rbp+1A0h+var_118]
0x18002577d  mov     rcx, rsi
0x180025780  call    ?get_token_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(void)
0x180025785  nop
0x180025786  mov     [rsp+2A0h+var_230], 1
0x18002578b  cmp     [rsp+2A0h+var_22F], r14b
0x180025790  jnz     loc_18002584A
0x180025796  lea     rcx, [rbp+1A0h+var_118]
0x18002579d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800257a2  nop
0x1800257a3  lea     rdi, ??_7exception@std@@6B@; const std::exception::`vftable'
0x1800257aa  mov     [rbp+1A0h+var_1B8], rdi
0x1800257ae  lea     rcx, [rbp+1A0h+var_1B0]
0x1800257b2  call    _o___std_exception_destroy_0
0x1800257b7  mov     [rbp+1A0h+var_1D8], rdi
0x1800257bb  lea     rcx, [rbp+1A0h+var_1D0]
0x1800257bf  call    _o___std_exception_destroy_0
0x1800257c4  nop
0x1800257c5  lea     rcx, [rbp+1A0h+var_138]
0x1800257c9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800257ce  nop
0x1800257cf  lea     rcx, [rbp+1A0h+var_158]
0x1800257d3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800257d8  cmp     [rsp+2A0h+var_230], r14b
0x1800257dd  jz      short loc_180025819
0x1800257df  mov     byte ptr [rsp+2A0h+var_278], 9
0x1800257e4  mov     dl, 9
0x1800257e6  lea     rcx, [rsp+2A0h+var_278+8]
0x1800257eb  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x1800257f0  mov     dl, [rbx]
0x1800257f2  mov     al, byte ptr [rsp+2A0h+var_278]
0x1800257f6  mov     [rbx], al
0x1800257f8  mov     byte ptr [rsp+2A0h+var_278], dl
0x1800257fc  mov     rcx, [rbx+8]
0x180025800  mov     rax, qword ptr [rsp+2A0h+var_278+8]
0x180025805  mov     [rbx+8], rax
0x180025809  mov     qword ptr [rsp+2A0h+var_278+8], rcx
0x18002580e  lea     rcx, [rsp+2A0h+var_278+8]
0x180025813  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180025818  nop
0x180025819  lea     rcx, [rsp+2A0h+var_250]
0x18002581e  call    ??1?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@QEAA@XZ; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *>>::~vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *>>(void)
0x180025823  mov     rcx, [rbp+1A0h+var_20]
0x18002582a  xor     rcx, rsp; StackCookie
0x18002582d  call    __security_check_cookie
0x180025832  lea     r11, [rsp+2A0h+var_10]
0x18002583a  mov     rbx, [r11+28h]
0x18002583e  mov     rsi, [r11+38h]
0x180025842  mov     rsp, r11
0x180025845  pop     r14
0x180025847  pop     rdi
0x180025848  pop     rbp
0x180025849  retn
0x18002584a  mov     rdx, rdi; struct nlohmann::detail::parse_error *
0x18002584d  lea     rcx, [rbp+1A0h+pExceptionObject]; this
0x180025851  call    ??0parse_error@detail@nlohmann@@QEAA@AEBV012@@Z; nlohmann::detail::parse_error::parse_error(nlohmann::detail::parse_error const &)
0x180025856  lea     rdx, _TI3?AVparse_error@detail@nlohmann@@; pThrowInfo
0x18002585d  lea     rcx, [rbp+1A0h+pExceptionObject]; pExceptionObject
0x180025861  call    _CxxThrowException_0
0x180025867  mov     rdx, rdi; struct nlohmann::detail::parse_error *
0x18002586a  lea     rcx, [rbp+1A0h+var_1D8]; this
0x18002586e  call    ??0parse_error@detail@nlohmann@@QEAA@AEBV012@@Z; nlohmann::detail::parse_error::parse_error(nlohmann::detail::parse_error const &)
0x180025873  lea     rdx, _TI3?AVparse_error@detail@nlohmann@@; pThrowInfo
0x18002587a  lea     rcx, [rbp+1A0h+var_1D8]; pExceptionObject
0x18002587e  call    _CxxThrowException_0
```
