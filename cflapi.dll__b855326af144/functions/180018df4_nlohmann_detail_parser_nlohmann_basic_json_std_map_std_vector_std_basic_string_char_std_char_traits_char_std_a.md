# nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>(nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>> *)

- ea: `0x180018df4`
- end: `0x180019cff`
- name: `??$sax_parse_internal@V?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA_NPEAV?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@12@@Z`
- size: `3851`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config`

## callers

- `0x180025448`

## callees

- `0x180002490`
- `0x18000289c`
- `0x180002e12`
- `0x180002f04`
- `0x180008a68`
- `0x180013070`
- `0x180013130`
- `0x180013e58`
- `0x180013fec`
- `0x180014170`
- `0x18001432c`
- `0x18001449c`
- `0x18001479c`
- `0x180017730`
- `0x180018df4`
- `0x180019eac`
- `0x180019fb8`
- `0x18001a448`
- `0x18001a674`
- `0x18001a80c`
- `0x18001b19c`
- `0x18001b694`
- `0x18002258c`
- `0x180022608`
- `0x1800228c8`
- `0x1800229d4`
- `0x180022cf4`
- `0x180024524`
- `0x180024a70`
- `0x18002588c`
- `0x180025a34`
- `0x180025d30`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
char __fastcall nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
        __int64 a1,
        char **a2)
{
  char **v2; // rdi
  __int64 v4; // r15
  __int64 v5; // rbx
  char v6; // r14
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  __int64 v12; // r8
  char *v13; // rax
  char *v14; // rcx
  char v15; // dl
  __int64 v16; // rax
  __int64 *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rdx
  char *v21; // rcx
  char v22; // dl
  __int64 v23; // rax
  char *v24; // rax
  void *v25; // rbx
  char *v26; // rcx
  char v27; // dl
  __int64 v28; // rax
  __int64 v29; // r15
  __int64 v30; // r15
  __int64 v31; // r12
  void *v32; // rbx
  void *v33; // rbx
  char *v34; // rcx
  char v35; // dl
  __int64 v36; // rax
  char *v37; // rax
  char *v38; // r8
  char v39; // dl
  __int64 v40; // rcx
  __int64 v41; // rbx
  __int64 v42; // rbx
  _BYTE *v43; // rdx
  char *v44; // r8
  char v45; // dl
  __int64 v46; // rcx
  char *v47; // rax
  char *v48; // rcx
  char v49; // dl
  __int64 v50; // rax
  __int64 v51; // rcx
  char *v52; // rcx
  char v53; // dl
  __int64 v54; // rax
  int v55; // ecx
  int v56; // ecx
  int v57; // ecx
  __int64 v58; // rax
  __int64 *v59; // rdx
  int v60; // eax
  int v61; // eax
  __int64 v62; // rax
  __int64 *v63; // rdx
  int v64; // eax
  unsigned __int64 v65; // xmm0_8
  char *v66; // rax
  char *v67; // r8
  char v68; // dl
  __int64 v69; // rcx
  __int64 v70; // rdx
  char v71; // dl
  __int64 v72; // rax
  __int64 v73; // rcx
  int v74; // eax
  _QWORD *v75; // rax
  __int64 v76; // rdx
  const struct nlohmann::detail::parse_error *v77; // rsi
  int v78; // eax
  int v79; // eax
  int v80; // eax
  _QWORD *v81; // rax
  __int64 v82; // rdx
  const struct nlohmann::detail::parse_error *v83; // rsi
  _QWORD *v84; // rax
  __int64 v85; // rdx
  const struct nlohmann::detail::parse_error *v86; // rsi
  char **v87; // rcx
  _QWORD *v88; // rax
  __int64 v89; // rdx
  const struct nlohmann::detail::parse_error *v90; // rsi
  _QWORD *v91; // rax
  __int64 v92; // rdx
  const struct nlohmann::detail::parse_error *v93; // rsi
  _QWORD *v94; // rax
  __int64 v95; // rdx
  const struct nlohmann::detail::parse_error *v96; // rbx
  _QWORD *v97; // rax
  __int64 v98; // rdx
  const struct nlohmann::detail::parse_error *v99; // rsi
  _QWORD *v100; // rax
  __int64 v101; // rdx
  const struct nlohmann::detail::parse_error *v102; // rsi
  __int64 token_string; // rax
  __int64 v105; // rax
  __int64 v106; // rax
  const struct nlohmann::detail::out_of_range *v107; // rbx
  char v108[8]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v109; // [rsp+28h] [rbp-D8h] BYREF
  char v110; // [rsp+30h] [rbp-D0h] BYREF
  char v111; // [rsp+31h] [rbp-CFh] BYREF
  char v112; // [rsp+32h] [rbp-CEh] BYREF
  char v113; // [rsp+38h] [rbp-C8h]
  __int64 v114; // [rsp+40h] [rbp-C0h] BYREF
  char v115; // [rsp+48h] [rbp-B8h]
  __int64 v116; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v117; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v118; // [rsp+68h] [rbp-98h]
  __int64 v119; // [rsp+70h] [rbp-90h]
  char v120; // [rsp+78h] [rbp-88h]
  __int64 v121; // [rsp+80h] [rbp-80h] BYREF
  char v122; // [rsp+88h] [rbp-78h]
  __int64 v123; // [rsp+90h] [rbp-70h] BYREF
  void **v124; // [rsp+98h] [rbp-68h] BYREF
  char v125[24]; // [rsp+A0h] [rbp-60h] BYREF
  void **v126; // [rsp+B8h] [rbp-48h]
  char v127[24]; // [rsp+C0h] [rbp-40h] BYREF
  void **v128; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v129[24]; // [rsp+E0h] [rbp-20h] BYREF
  void **v130; // [rsp+F8h] [rbp-8h]
  _BYTE v131[24]; // [rsp+100h] [rbp+0h] BYREF
  void **v132; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v133[24]; // [rsp+120h] [rbp+20h] BYREF
  void **v134; // [rsp+138h] [rbp+38h]
  _BYTE v135[24]; // [rsp+140h] [rbp+40h] BYREF
  void **v136; // [rsp+158h] [rbp+58h] BYREF
  char v137[24]; // [rsp+160h] [rbp+60h] BYREF
  void **v138; // [rsp+178h] [rbp+78h]
  char v139[24]; // [rsp+180h] [rbp+80h] BYREF
  char *v140; // [rsp+198h] [rbp+98h] BYREF
  void *v141; // [rsp+1A0h] [rbp+A0h]
  __int128 v142; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v143; // [rsp+1C8h] [rbp+C8h]
  char *v144; // [rsp+1D8h] [rbp+D8h] BYREF
  void *v145; // [rsp+1E0h] [rbp+E0h]
  char *v146; // [rsp+1F8h] [rbp+F8h] BYREF
  void *v147; // [rsp+200h] [rbp+100h]
  void **v148; // [rsp+218h] [rbp+118h] BYREF
  _QWORD v149[3]; // [rsp+220h] [rbp+120h] BYREF
  void **v150; // [rsp+238h] [rbp+138h]
  _BYTE v151[24]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v152; // [rsp+258h] [rbp+158h] BYREF
  __int64 v153; // [rsp+260h] [rbp+160h] BYREF
  char v154[8]; // [rsp+278h] [rbp+178h] BYREF
  __int64 v155[3]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v156; // [rsp+298h] [rbp+198h] BYREF
  __int64 v157; // [rsp+2A0h] [rbp+1A0h] BYREF
  char v158[8]; // [rsp+2B8h] [rbp+1B8h] BYREF
  __int64 v159; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 pExceptionObject; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int64 v161; // [rsp+2E0h] [rbp+1E0h] BYREF

  v2 = a2;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v4 = a1 + 72;
  v5 = a1 + 72;
  v6 = 1;
LABEL_2:
  while ( 1 )
  {
    v7 = *(_DWORD *)(a1 + 64);
    if ( v7 <= 6 )
      break;
    v55 = v7 - 7;
    if ( !v55 )
    {
      v65 = *(_QWORD *)(a1 + 208);
      if ( ((v65 >> 52) & 0x7FF) == 2047 )
      {
        token_string = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
                         v4,
                         &v144);
        v105 = std::operator+<char>(&v146, "number overflow parsing '", token_string);
        v106 = std::operator+<char>(&v140, v105, "'");
        v107 = (const struct nlohmann::detail::out_of_range *)nlohmann::detail::out_of_range::create(&v148, 406, v106);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v4,
          &v142);
        *((_BYTE *)v2 + 40) = 1;
        if ( *((_BYTE *)v2 + 41) )
        {
          nlohmann::detail::out_of_range::out_of_range((nlohmann::detail::out_of_range *)&pExceptionObject, v107);
          throw (nlohmann::detail::out_of_range *)&pExceptionObject;
        }
        std::string::~string(&v142);
        v150 = &std::exception::`vftable';
        o___std_exception_destroy_0(v151);
        v148 = &std::exception::`vftable';
        o___std_exception_destroy_0(v149);
        std::string::~string(&v140);
        std::string::~string(&v146);
        v87 = &v144;
        goto LABEL_104;
      }
      v109 = *(_QWORD *)(a1 + 208);
      v66 = v2[2];
      if ( v2[1] == v66 )
      {
        v67 = *v2;
        v68 = **v2;
        *v67 = 7;
        LOBYTE(pExceptionObject) = v68;
        v161 = *((_QWORD *)v67 + 1);
        v17 = &v161;
      }
      else
      {
        v69 = *((_QWORD *)v66 - 1);
        if ( *(_BYTE *)v69 == 2 )
        {
          v19 = *(_QWORD *)(v69 + 8);
          v70 = *(_QWORD *)(v19 + 8);
          if ( v70 == *(_QWORD *)(v19 + 16) )
          {
            std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<double &>(
              v19,
              v70,
              &v109);
            goto LABEL_72;
          }
          *(_BYTE *)v70 = 7;
          v109 = v65;
          *(_QWORD *)(v70 + 8) = v65;
          goto LABEL_15;
        }
        v67 = v2[4];
        v71 = *v67;
        *v67 = 7;
        LOBYTE(v148) = v71;
        v149[0] = *((_QWORD *)v67 + 1);
        v17 = v149;
      }
      *((_QWORD *)v67 + 1) = v65;
      goto LABEL_71;
    }
    v56 = v55 - 1;
    if ( v56 )
    {
      v57 = v56 - 1;
      if ( v57 )
      {
        if ( v57 == 5 )
        {
          std::string::string(&v140, "value");
          v94 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                  a1,
                  &v144,
                  0,
                  &v140);
          v142 = *(_OWORD *)(v4 + 32);
          v143 = *(_QWORD *)(v4 + 48);
          v96 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                                &v128,
                                                                v95,
                                                                &v142,
                                                                v94);
          nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
            v4,
            &v146);
          *((_BYTE *)v2 + 40) = 1;
          if ( *((_BYTE *)v2 + 41) )
          {
            nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v96);
            throw (nlohmann::detail::parse_error *)&v124;
          }
          std::string::~string(&v146);
          v130 = &std::exception::`vftable';
          o___std_exception_destroy_0(v131);
          v128 = &std::exception::`vftable';
          o___std_exception_destroy_0(v129);
          std::string::~string(&v144);
          goto LABEL_88;
        }
        goto LABEL_92;
      }
      v108[0] = 1;
      v58 = nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<enum nlohmann::detail::value_t>(
              v2,
              v108);
      v109 = v58;
      v59 = (__int64 *)v2[2];
      if ( v59 == (__int64 *)v2[3] )
      {
        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> * const &>(
          v2 + 1,
          v59,
          &v109);
      }
      else
      {
        *v59 = v58;
        v2[2] += 8;
      }
      v5 = a1 + 72;
      v60 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      *(_DWORD *)(a1 + 64) = v60;
      if ( v60 == 11 )
        goto LABEL_51;
      if ( v60 != 4 )
      {
        std::string::string(&v140, "object key");
        v88 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                a1,
                &v144,
                4u,
                &v140);
        v142 = *(_OWORD *)(a1 + 104);
        v143 = *(_QWORD *)(a1 + 120);
        v90 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                              &v148,
                                                              v89,
                                                              &v142,
                                                              v88);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v5,
          &v146);
        *((_BYTE *)v2 + 40) = 1;
        if ( *((_BYTE *)v2 + 41) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v90);
          throw (nlohmann::detail::parse_error *)&v124;
        }
LABEL_87:
        std::string::~string(&v146);
        v150 = &std::exception::`vftable';
        o___std_exception_destroy_0(v151);
        v148 = &std::exception::`vftable';
        o___std_exception_destroy_0(v149);
        std::string::~string(&v144);
LABEL_88:
        v87 = &v140;
LABEL_104:
        std::string::~string(v87);
LABEL_105:
        std::vector<unsigned int>::~vector<unsigned int>(&v117);
        return 0;
      }
      v2[4] = (char *)std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::operator[](
                        *(_QWORD *)(*((_QWORD *)v2[2] - 1) + 8LL),
                        a1 + 152);
      v61 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      *(_DWORD *)(a1 + 64) = v61;
      if ( v61 != 12 )
      {
        std::string::string(&v140, "object separator");
        v84 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                a1,
                &v144,
                0xCu,
                &v140);
        v142 = *(_OWORD *)(a1 + 104);
        v143 = *(_QWORD *)(a1 + 120);
        v86 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                              &v148,
                                                              v85,
                                                              &v142,
                                                              v84);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v5,
          &v146);
        *((_BYTE *)v2 + 40) = 1;
        if ( *((_BYTE *)v2 + 41) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v86);
          throw (nlohmann::detail::parse_error *)&v124;
        }
        goto LABEL_87;
      }
      v108[0] = 0;
      std::vector<bool>::push_back(&v117, v108);
      *(_DWORD *)(a1 + 64) = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
    }
    else
    {
      v108[0] = 2;
      v62 = nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<enum nlohmann::detail::value_t>(
              v2,
              v108);
      v109 = v62;
      v63 = (__int64 *)v2[2];
      if ( v63 == (__int64 *)v2[3] )
      {
        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> * const &>(
          v2 + 1,
          v63,
          &v109);
      }
      else
      {
        *v63 = v62;
        v2[2] += 8;
      }
      v5 = a1 + 72;
      v64 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      *(_DWORD *)(a1 + 64) = v64;
      if ( v64 == 10 )
      {
LABEL_51:
        v2[2] -= 8;
        goto LABEL_52;
      }
      v108[0] = 1;
      std::vector<bool>::push_back(&v117, v108);
    }
    v4 = a1 + 72;
  }
  if ( v7 == 6 )
  {
    v12 = *(_QWORD *)(a1 + 192);
    v109 = v12;
    v47 = v2[2];
    if ( v2[1] == v47 )
    {
      v48 = *v2;
      v49 = **v2;
      *v48 = 5;
      LOBYTE(v156) = v49;
      v50 = *((_QWORD *)v48 + 1);
      *((_QWORD *)v48 + 1) = v12;
      v157 = v50;
      v17 = &v157;
      goto LABEL_71;
    }
    v51 = *((_QWORD *)v47 - 1);
    if ( *(_BYTE *)v51 != 2 )
    {
      v52 = v2[4];
      v53 = *v52;
      *v52 = 5;
      v158[0] = v53;
      v54 = *((_QWORD *)v52 + 1);
      *((_QWORD *)v52 + 1) = v12;
      v159 = v54;
      v17 = &v159;
      goto LABEL_71;
    }
    v19 = *(_QWORD *)(v51 + 8);
    v20 = *(_QWORD *)(v19 + 8);
    if ( v20 == *(_QWORD *)(v19 + 16) )
    {
      std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<__int64 &>(
        v19,
        v20,
        &v109);
      goto LABEL_72;
    }
    *(_BYTE *)v20 = 5;
    goto LABEL_14;
  }
  v5 = v4;
  v8 = v7 - 1;
  if ( !v8 )
  {
    LOBYTE(a2) = 1;
LABEL_34:
    if ( (unsigned __int8)nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::boolean(
                            v2,
                            a2) )
      goto LABEL_72;
    goto LABEL_105;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    a2 = 0;
    goto LABEL_34;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v37 = v2[2];
    if ( v2[1] == v37 )
    {
      v113 = 0;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        &v114,
        0);
      v38 = *v2;
      v39 = **v2;
      *v38 = v113;
      v113 = v39;
      v40 = *((_QWORD *)v38 + 1);
      *((_QWORD *)v38 + 1) = v114;
      v114 = v40;
      v17 = &v114;
    }
    else
    {
      v41 = *((_QWORD *)v37 - 1);
      if ( *(_BYTE *)v41 == 2 )
      {
        v42 = *(_QWORD *)(v41 + 8);
        v43 = *(_BYTE **)(v42 + 8);
        if ( v43 == *(_BYTE **)(v42 + 16) )
        {
          std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<std::nullptr_t>(v42);
        }
        else
        {
          *v43 = 0;
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
            v43 + 8,
            0);
          *(_QWORD *)(v42 + 8) += 16LL;
        }
        goto LABEL_72;
      }
      v115 = 0;
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
        &v116,
        0);
      v44 = v2[4];
      v45 = *v44;
      *v44 = v115;
      v115 = v45;
      v46 = *((_QWORD *)v44 + 1);
      *((_QWORD *)v44 + 1) = v116;
      v116 = v46;
      v17 = &v116;
    }
LABEL_71:
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v17);
    goto LABEL_72;
  }
  v11 = v10 - 1;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      v12 = *(_QWORD *)(a1 + 200);
      v109 = v12;
      v13 = v2[2];
      if ( v2[1] == v13 )
      {
        v14 = *v2;
        v15 = **v2;
        *v14 = 6;
        v120 = v15;
        v16 = *((_QWORD *)v14 + 1);
        *((_QWORD *)v14 + 1) = v12;
        v121 = v16;
        v17 = &v121;
        goto LABEL_71;
      }
      v18 = *((_QWORD *)v13 - 1);
      if ( *(_BYTE *)v18 != 2 )
      {
        v21 = v2[4];
        v22 = *v21;
        *v21 = 6;
        v122 = v22;
        v23 = *((_QWORD *)v21 + 1);
        *((_QWORD *)v21 + 1) = v12;
        v123 = v23;
        v17 = &v123;
        goto LABEL_71;
      }
      v19 = *(_QWORD *)(v18 + 8);
      v20 = *(_QWORD *)(v19 + 8);
      if ( v20 == *(_QWORD *)(v19 + 16) )
      {
        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<unsigned __int64 &>(
          v19,
          v20,
          &v109);
        goto LABEL_72;
      }
      *(_BYTE *)v20 = 6;
LABEL_14:
      *(_QWORD *)(v20 + 8) = v12;
LABEL_15:
      *(_QWORD *)(v19 + 8) += 16LL;
      goto LABEL_72;
    }
LABEL_92:
    std::string::string(&v140, "value");
    v91 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
            a1,
            &v144,
            0x10u,
            &v140);
    v142 = *(_OWORD *)(v5 + 32);
    v143 = *(_QWORD *)(v5 + 48);
    v93 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v128, v92, &v142, v91);
    nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
      v5,
      &v146);
    *((_BYTE *)v2 + 40) = 1;
    if ( *((_BYTE *)v2 + 41) )
    {
      nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v93);
      throw (nlohmann::detail::parse_error *)&v124;
    }
    std::string::~string(&v146);
    v130 = &std::exception::`vftable';
    o___std_exception_destroy_0(v131);
    v128 = &std::exception::`vftable';
    o___std_exception_destroy_0(v129);
    std::string::~string(&v144);
    goto LABEL_100;
  }
  v24 = v2[2];
  if ( v2[1] == v24 )
  {
    v25 = operator new(0x20u);
    v144 = &v110;
    v145 = v25;
    std::string::string(v25, a1 + 152);
    v145 = 0;
    v26 = *v2;
    v27 = **v2;
    *v26 = 3;
    LOBYTE(v152) = v27;
    v28 = *((_QWORD *)v26 + 1);
    *((_QWORD *)v26 + 1) = v25;
    v153 = v28;
    v17 = &v153;
    goto LABEL_71;
  }
  v29 = *((_QWORD *)v24 - 1);
  if ( *(_BYTE *)v29 != 2 )
  {
    v33 = operator new(0x20u);
    v140 = &v112;
    v141 = v33;
    std::string::string(v33, a1 + 152);
    v141 = 0;
    v34 = v2[4];
    v35 = *v34;
    *v34 = 3;
    v154[0] = v35;
    v36 = *((_QWORD *)v34 + 1);
    *((_QWORD *)v34 + 1) = v33;
    v155[0] = v36;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v155);
LABEL_52:
    v4 = a1 + 72;
    goto LABEL_72;
  }
  v30 = *(_QWORD *)(v29 + 8);
  v31 = *(_QWORD *)(v30 + 8);
  if ( v31 == *(_QWORD *)(v30 + 16) )
  {
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<std::string &>(
      v30,
      *(_QWORD *)(v30 + 8),
      a1 + 152);
  }
  else
  {
    *(_QWORD *)(v31 + 8) = 0;
    *(_BYTE *)v31 = 3;
    v32 = operator new(0x20u);
    v146 = &v111;
    v147 = v32;
    std::string::string(v32, a1 + 152);
    v147 = 0;
    *(_QWORD *)(v31 + 8) = v32;
    *(_QWORD *)(v30 + 8) += 16LL;
  }
  v4 = a1 + 72;
  while ( 1 )
  {
LABEL_72:
    if ( !v119 )
      goto LABEL_101;
    v72 = std::vector<bool>::back(&v117, &v142);
    v5 = a1 + 72;
    v73 = a1 + 72;
    if ( ((1 << *(_QWORD *)(v72 + 8)) & **(_DWORD **)v72) != 0 )
      break;
    v78 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v73);
    *(_DWORD *)(a1 + 64) = v78;
    if ( v78 == 13 )
    {
      v79 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      *(_DWORD *)(a1 + 64) = v79;
      if ( v79 != 4 )
      {
        std::string::string(&v140, "object key");
        v100 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                 a1,
                 &v152,
                 4u,
                 &v140);
        v142 = *(_OWORD *)(a1 + 104);
        v143 = *(_QWORD *)(a1 + 120);
        v102 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                               &v124,
                                                               v101,
                                                               &v142,
                                                               v100);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v5,
          v154);
        *((_BYTE *)v2 + 40) = 1;
        if ( *((_BYTE *)v2 + 41) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v136, v102);
          throw (nlohmann::detail::parse_error *)&v136;
        }
        std::string::~string(v154);
        v126 = &std::exception::`vftable';
        o___std_exception_destroy_0(v127);
        v124 = &std::exception::`vftable';
        o___std_exception_destroy_0(v125);
        std::string::~string(&v152);
        goto LABEL_100;
      }
      v2[4] = (char *)std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::operator[](
                        *(_QWORD *)(*((_QWORD *)v2[2] - 1) + 8LL),
                        a1 + 152);
      v80 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      *(_DWORD *)(a1 + 64) = v80;
      if ( v80 != 12 )
      {
        std::string::string(&v140, "object separator");
        v81 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                a1,
                &v156,
                0xCu,
                &v140);
        v142 = *(_OWORD *)(a1 + 104);
        v143 = *(_QWORD *)(a1 + 120);
        v83 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                              &v136,
                                                              v82,
                                                              &v142,
                                                              v81);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v5,
          v158);
        *((_BYTE *)v2 + 40) = 1;
        if ( *((_BYTE *)v2 + 41) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v83);
          throw (nlohmann::detail::parse_error *)&v124;
        }
        std::string::~string(v158);
        v138 = &std::exception::`vftable';
        o___std_exception_destroy_0(v139);
        v136 = &std::exception::`vftable';
        o___std_exception_destroy_0(v137);
        std::string::~string(&v156);
        goto LABEL_100;
      }
LABEL_81:
      *(_DWORD *)(a1 + 64) = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(a1 + 72);
      goto LABEL_2;
    }
    if ( v78 != 11 )
    {
      std::string::string(&v140, "object");
      v97 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
              a1,
              &v144,
              0xBu,
              &v140);
      v142 = *(_OWORD *)(a1 + 104);
      v143 = *(_QWORD *)(a1 + 120);
      v99 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v132, v98, &v142, v97);
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        v5,
        &v146);
      *((_BYTE *)v2 + 40) = 1;
      if ( *((_BYTE *)v2 + 41) )
      {
        nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v99);
        throw (nlohmann::detail::parse_error *)&v124;
      }
      std::string::~string(&v146);
      v134 = &std::exception::`vftable';
      o___std_exception_destroy_0(v135);
      v132 = &std::exception::`vftable';
      o___std_exception_destroy_0(v133);
      std::string::~string(&v144);
      goto LABEL_88;
    }
LABEL_80:
    v2[2] -= 8;
    std::vector<bool>::pop_back(&v117);
  }
  v74 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v73);
  *(_DWORD *)(a1 + 64) = v74;
  if ( v74 == 13 )
    goto LABEL_81;
  if ( v74 == 10 )
    goto LABEL_80;
  std::string::string(&v140, "array");
  v75 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
          a1,
          &pExceptionObject,
          0xAu,
          &v140);
  v142 = *(_OWORD *)(a1 + 104);
  v143 = *(_QWORD *)(a1 + 120);
  v77 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v132, v76, &v142, v75);
  nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
    v5,
    &v148);
  *((_BYTE *)v2 + 40) = 1;
  if ( *((_BYTE *)v2 + 41) )
  {
    nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v124, v77);
    throw (nlohmann::detail::parse_error *)&v124;
  }
  std::string::~string(&v148);
  v134 = &std::exception::`vftable';
  o___std_exception_destroy_0(v135);
  v132 = &std::exception::`vftable';
  o___std_exception_destroy_0(v133);
  std::string::~string(&pExceptionObject);
LABEL_100:
  std::string::~string(&v140);
  v6 = 0;
LABEL_101:
  std::vector<unsigned int>::~vector<unsigned int>(&v117);
  return v6;
}

```

## disassembly

```asm
0x180018df4  mov     [rsp-8+arg_10], rbx
0x180018df9  push    rbp
0x180018dfa  push    rsi
0x180018dfb  push    rdi
0x180018dfc  push    r12
0x180018dfe  push    r13
0x180018e00  push    r14
0x180018e02  push    r15
0x180018e04  lea     rbp, [rsp-220h]
0x180018e0c  sub     rsp, 320h
0x180018e13  mov     rax, cs:__security_cookie
0x180018e1a  xor     rax, rsp
0x180018e1d  mov     [rbp+250h+var_40], rax
0x180018e24  mov     rdi, rdx
0x180018e27  mov     rsi, rcx
0x180018e2a  xorps   xmm0, xmm0
0x180018e2d  movdqu  [rsp+350h+var_2F8], xmm0
0x180018e33  xor     r12d, r12d
0x180018e36  mov     [rsp+350h+var_2E8], r12
0x180018e3b  mov     [rsp+350h+var_2E0], r12
0x180018e40  lea     r15, [rcx+48h]
0x180018e44  mov     rbx, r15
0x180018e47  lea     r14d, [r12+1]
0x180018e4c  mov     ecx, [rsi+40h]
0x180018e4f  cmp     ecx, 6
0x180018e52  jg      loc_1800191E1
0x180018e58  jz      loc_18001914A
0x180018e5e  mov     rbx, r15
0x180018e61  sub     ecx, 1
0x180018e64  jz      loc_180019145
0x180018e6a  sub     ecx, 1
0x180018e6d  jz      loc_18001912E
0x180018e73  sub     ecx, 1
0x180018e76  jz      loc_180019068
0x180018e7c  sub     ecx, 1
0x180018e7f  jz      loc_180018F1D
0x180018e85  cmp     ecx, 1
0x180018e88  jnz     loc_1800197D6
0x180018e8e  mov     r8, [rsi+0C8h]
0x180018e95  mov     [rsp+350h+var_328], r8
0x180018e9a  mov     rax, [rdi+10h]
0x180018e9e  cmp     [rdi+8], rax
0x180018ea2  jnz     short loc_180018EC5
0x180018ea4  mov     rcx, [rdi]
0x180018ea7  mov     dl, [rcx]
0x180018ea9  mov     byte ptr [rcx], 6
0x180018eac  mov     [rsp+350h+var_2D8], dl
0x180018eb0  mov     rax, [rcx+8]
0x180018eb4  mov     [rcx+8], r8
0x180018eb8  mov     [rbp+250h+var_2D0], rax
0x180018ebc  lea     rcx, [rbp+250h+var_2D0]
0x180018ec0  jmp     loc_1800193DD
0x180018ec5  mov     rcx, [rax-8]
0x180018ec9  cmp     byte ptr [rcx], 2
0x180018ecc  jnz     short loc_180018EFC
0x180018ece  mov     rcx, [rcx+8]
0x180018ed2  mov     rdx, [rcx+8]
0x180018ed6  cmp     rdx, [rcx+10h]
0x180018eda  jz      short loc_180018EED
0x180018edc  mov     byte ptr [rdx], 6
0x180018edf  mov     [rdx+8], r8
0x180018ee3  add     qword ptr [rcx+8], 10h
0x180018ee8  jmp     loc_1800193E2
0x180018eed  lea     r8, [rsp+350h+var_328]
0x180018ef2  call    ??$_Emplace_reallocate@AEA_K@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@AEA_K@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<unsigned __int64 &>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,unsigned __int64 &)
0x180018ef7  jmp     loc_1800193E2
0x180018efc  mov     rcx, [rdi+20h]
0x180018f00  mov     dl, [rcx]
0x180018f02  mov     byte ptr [rcx], 6
0x180018f05  mov     [rbp+250h+var_2C8], dl
0x180018f08  mov     rax, [rcx+8]
0x180018f0c  mov     [rcx+8], r8
0x180018f10  mov     [rbp+250h+var_2C0], rax
0x180018f14  lea     rcx, [rbp+250h+var_2C0]
0x180018f18  jmp     loc_1800193DD
0x180018f1d  lea     r13, [rsi+98h]
0x180018f24  mov     rax, [rdi+10h]
0x180018f28  cmp     [rdi+8], rax
0x180018f2c  jnz     short loc_180018F89
0x180018f2e  mov     ecx, 20h ; ' '; Size
0x180018f33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018f38  mov     rbx, rax
0x180018f3b  lea     rax, [rsp+350h+var_320]
0x180018f40  mov     [rbp+250h+var_178], rax
0x180018f47  mov     [rbp+250h+var_170], rbx
0x180018f4e  mov     rdx, r13
0x180018f51  mov     rcx, rbx
0x180018f54  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180018f59  mov     [rbp+250h+var_170], r12
0x180018f60  mov     rcx, [rdi]
0x180018f63  mov     dl, [rcx]
0x180018f65  mov     byte ptr [rcx], 3
0x180018f68  mov     byte ptr [rbp+250h+var_F8], dl
0x180018f6e  mov     rax, [rcx+8]
0x180018f72  mov     [rcx+8], rbx
0x180018f76  mov     [rbp+250h+var_F0], rax
0x180018f7d  lea     rcx, [rbp+250h+var_F0]
0x180018f84  jmp     loc_1800193DD
0x180018f89  mov     r15, [rax-8]
0x180018f8d  cmp     byte ptr [r15], 2
0x180018f91  jnz     short loc_180019007
0x180018f93  mov     r15, [r15+8]
0x180018f97  mov     r12, [r15+8]
0x180018f9b  cmp     r12, [r15+10h]
0x180018f9f  jz      short loc_180018FF7
0x180018fa1  xor     eax, eax
0x180018fa3  mov     [r12+8], rax
0x180018fa8  mov     byte ptr [r12], 3
0x180018fad  lea     ecx, [rax+20h]; Size
0x180018fb0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018fb5  mov     rbx, rax
0x180018fb8  lea     rax, [rsp+350h+var_31F]
0x180018fbd  mov     [rbp+250h+var_158], rax
0x180018fc4  mov     [rbp+250h+var_150], rbx
0x180018fcb  mov     rdx, r13
0x180018fce  mov     rcx, rbx
0x180018fd1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180018fd6  mov     [rbp+250h+var_150], 0
0x180018fe1  mov     [r12+8], rbx
0x180018fe6  add     qword ptr [r15+8], 10h
0x180018feb  lea     r15, [rsi+48h]
0x180018fef  xor     r12d, r12d
0x180018ff2  jmp     loc_1800193E2
0x180018ff7  mov     r8, r13
0x180018ffa  mov     rdx, r12
0x180018ffd  mov     rcx, r15
0x180019000  call    ??$_Emplace_reallocate@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<std::string &>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,std::string &)
0x180019005  jmp     short loc_180018FEB
0x180019007  mov     ecx, 20h ; ' '; Size
0x18001900c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180019011  mov     rbx, rax
0x180019014  lea     rax, [rsp+350h+var_31E]
0x180019019  mov     [rbp+250h+var_1B8], rax
0x180019020  mov     [rbp+250h+var_1B0], rbx
0x180019027  mov     rdx, r13
0x18001902a  mov     rcx, rbx
0x18001902d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180019032  mov     [rbp+250h+var_1B0], r12
0x180019039  mov     rcx, [rdi+20h]
0x18001903d  mov     dl, [rcx]
0x18001903f  mov     byte ptr [rcx], 3
0x180019042  mov     [rbp+250h+var_D8], dl
0x180019048  mov     rax, [rcx+8]
0x18001904c  mov     [rcx+8], rbx
0x180019050  mov     [rbp+250h+var_D0], rax
0x180019057  lea     rcx, [rbp+250h+var_D0]
0x18001905e  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180019063  jmp     loc_18001924E
0x180019068  mov     rax, [rdi+10h]
0x18001906c  cmp     [rdi+8], rax
0x180019070  jnz     short loc_1800190B1
0x180019072  mov     [rsp+350h+var_318], r12b
0x180019077  xor     edx, edx
0x180019079  lea     rcx, [rsp+350h+var_310]
0x18001907e  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180019083  nop
0x180019084  mov     r8, [rdi]
0x180019087  mov     dl, [r8]
0x18001908a  mov     al, [rsp+350h+var_318]
0x18001908e  mov     [r8], al
0x180019091  mov     [rsp+350h+var_318], dl
0x180019095  mov     rcx, [r8+8]
0x180019099  mov     rax, [rsp+350h+var_310]
0x18001909e  mov     [r8+8], rax
0x1800190a2  mov     [rsp+350h+var_310], rcx
0x1800190a7  lea     rcx, [rsp+350h+var_310]
0x1800190ac  jmp     loc_1800193DD
0x1800190b1  mov     rbx, [rax-8]
0x1800190b5  cmp     byte ptr [rbx], 2
0x1800190b8  jnz     short loc_1800190EE
0x1800190ba  mov     rbx, [rbx+8]
0x1800190be  mov     rdx, [rbx+8]
0x1800190c2  cmp     rdx, [rbx+10h]
0x1800190c6  jz      short loc_1800190E1
0x1800190c8  mov     [rdx], r12b
0x1800190cb  lea     rcx, [rdx+8]
0x1800190cf  xor     edx, edx
0x1800190d1  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x1800190d6  nop
0x1800190d7  add     qword ptr [rbx+8], 10h
0x1800190dc  jmp     loc_1800193E2
0x1800190e1  mov     rcx, rbx
0x1800190e4  call    ??$_Emplace_reallocate@$$T@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEA$$T@Z
0x1800190e9  jmp     loc_1800193E2
0x1800190ee  mov     [rsp+350h+var_308], r12b
0x1800190f3  xor     edx, edx
0x1800190f5  lea     rcx, [rsp+350h+var_300]
0x1800190fa  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x1800190ff  nop
0x180019100  mov     r8, [rdi+20h]
0x180019104  mov     dl, [r8]
0x180019107  mov     al, [rsp+350h+var_308]
0x18001910b  mov     [r8], al
0x18001910e  mov     [rsp+350h+var_308], dl
0x180019112  mov     rcx, [r8+8]
0x180019116  mov     rax, [rsp+350h+var_300]
0x18001911b  mov     [r8+8], rax
0x18001911f  mov     [rsp+350h+var_300], rcx
0x180019124  lea     rcx, [rsp+350h+var_300]
0x180019129  jmp     loc_1800193DD
0x18001912e  xor     edx, edx
0x180019130  mov     rcx, rdi
0x180019133  call    ?boolean@?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAA_N_N@Z; nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::boolean(bool)
0x180019138  test    al, al
0x18001913a  jz      loc_180019BBE
0x180019140  jmp     loc_1800193E2
0x180019145  mov     dl, r14b
0x180019148  jmp     short loc_180019130
0x18001914a  mov     r8, [rsi+0C0h]
0x180019151  mov     [rsp+350h+var_328], r8
0x180019156  mov     rax, [rdi+10h]
0x18001915a  cmp     [rdi+8], rax
0x18001915e  jnz     short loc_180019189
0x180019160  mov     rcx, [rdi]
0x180019163  mov     dl, [rcx]
0x180019165  mov     byte ptr [rcx], 5
0x180019168  mov     byte ptr [rbp+250h+var_B8], dl
0x18001916e  mov     rax, [rcx+8]
0x180019172  mov     [rcx+8], r8
0x180019176  mov     [rbp+250h+var_B0], rax
0x18001917d  lea     rcx, [rbp+250h+var_B0]
0x180019184  jmp     loc_1800193DD
0x180019189  mov     rcx, [rax-8]
0x18001918d  cmp     byte ptr [rcx], 2
0x180019190  jnz     short loc_1800191B7
0x180019192  mov     rcx, [rcx+8]
0x180019196  mov     rdx, [rcx+8]
0x18001919a  cmp     rdx, [rcx+10h]
0x18001919e  jz      short loc_1800191A8
0x1800191a0  mov     byte ptr [rdx], 5
0x1800191a3  jmp     loc_180018EDF
0x1800191a8  lea     r8, [rsp+350h+var_328]
0x1800191ad  call    ??$_Emplace_reallocate@AEA_J@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@AEA_J@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<__int64 &>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,__int64 &)
0x1800191b2  jmp     loc_1800193E2
0x1800191b7  mov     rcx, [rdi+20h]
0x1800191bb  mov     dl, [rcx]
0x1800191bd  mov     byte ptr [rcx], 5
0x1800191c0  mov     [rbp+250h+var_98], dl
0x1800191c6  mov     rax, [rcx+8]
0x1800191ca  mov     [rcx+8], r8
0x1800191ce  mov     [rbp+250h+var_90], rax
0x1800191d5  lea     rcx, [rbp+250h+var_90]
0x1800191dc  jmp     loc_1800193DD
0x1800191e1  sub     ecx, 7
0x1800191e4  jz      loc_18001931F
0x1800191ea  sub     ecx, 1
0x1800191ed  jz      loc_1800192B8
0x1800191f3  sub     ecx, 1
0x1800191f6  jnz     loc_1800197CD
0x1800191fc  mov     [rsp+350h+var_330], r14b
0x180019201  lea     rdx, [rsp+350h+var_330]
0x180019206  mov     rcx, rdi
0x180019209  call    ??$handle_value@W4value_t@detail@nlohmann@@@?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@2@$$QEAW4value_t@12@@Z; nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::handle_value<nlohmann::detail::value_t>(nlohmann::detail::value_t &&)
0x18001920e  mov     [rsp+350h+var_328], rax
0x180019213  mov     rdx, [rdi+10h]
0x180019217  cmp     rdx, [rdi+18h]
0x18001921b  jz      short loc_180019227
0x18001921d  mov     [rdx], rax
0x180019220  add     qword ptr [rdi+10h], 8
0x180019225  jmp     short loc_180019235
0x180019227  lea     r8, [rsp+350h+var_328]
0x18001922c  lea     rcx, [rdi+8]
0x180019230  call    ??$_Emplace_reallocate@AEBQEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@PEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAPEAV23@AEBQEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const &>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const &)
0x180019235  lea     rbx, [rsi+48h]
0x180019239  mov     rcx, rbx
0x18001923c  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x180019241  mov     [rsi+40h], eax
0x180019244  cmp     eax, 0Bh
0x180019247  jnz     short loc_180019257
0x180019249  add     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFF8h
0x18001924e  lea     r15, [rsi+48h]
0x180019252  jmp     loc_1800193E2
0x180019257  cmp     eax, 4
0x18001925a  jnz     loc_180019700
0x180019260  lea     rdx, [rsi+98h]
0x180019267  mov     rax, [rdi+10h]
0x18001926b  mov     rcx, [rax-8]
0x18001926f  mov     rcx, [rcx+8]
0x180019273  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@QEAAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::operator[](std::string const &)
0x180019278  mov     [rdi+20h], rax
0x18001927c  mov     rcx, rbx
0x18001927f  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x180019284  mov     [rsi+40h], eax
0x180019287  cmp     eax, 0Ch
0x18001928a  jnz     loc_18001962C
0x180019290  mov     [rsp+350h+var_330], r12b
0x180019295  lea     rdx, [rsp+350h+var_330]
0x18001929a  lea     rcx, [rsp+350h+var_2F8]
0x18001929f  call    ?push_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXAEB_N@Z; std::vector<bool>::push_back(bool const &)
0x1800192a4  mov     rcx, rbx
0x1800192a7  call    ?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)
0x1800192ac  mov     [rsi+40h], eax
0x1800192af  lea     r15, [rsi+48h]
0x1800192b3  jmp     loc_180018E4C
0x1800192b8  mov     [rsp+350h+var_330], 2
0x1800192bd  lea     rdx, [rsp+350h+var_330]
0x1800192c2  mov     rcx, rdi
0x1800192c5  call    ??$handle_value@W4value_t@detail@nlohmann@@@?$json_sax_dom_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@2@$$QEAW4value_t@12@@Z; nlohmann::detail::json_sax_dom_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::handle_value<nlohmann::detail::value_t>(nlohmann::detail::value_t &&)
0x1800192ca  mov     [rsp+350h+var_328], rax
0x1800192cf  mov     rdx, [rdi+10h]
  ... truncated ...
```
