# nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>>(nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>> *)

- ea: `0x180017b94`
- end: `0x180018deb`
- name: `??$sax_parse_internal@V?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA_NPEAV?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@12@@Z`
- size: `4695`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config`

## callers

- `0x180025448`

## callees

- `0x180002490`
- `0x180002e12`
- `0x180002f04`
- `0x180008a68`
- `0x180013070`
- `0x180013130`
- `0x18001479c`
- `0x180014e64`
- `0x1800171a0`
- `0x1800173a4`
- `0x180017598`
- `0x180017b94`
- `0x180019fb8`
- `0x18001a448`
- `0x18001a674`
- `0x18001a80c`
- `0x18001b19c`
- `0x18002258c`
- `0x1800228c8`
- `0x1800229d4`
- `0x180022cf4`
- `0x180024128`
- `0x180024220`
- `0x180024524`
- `0x180024a70`
- `0x1800250a0`
- `0x18002588c`
- `0x180025a34`
- `0x180025d30`
- `0x180030010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185d9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185e0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185e7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018795`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018942`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018949`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185d9`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185e0`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x1800185e7`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018795`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018942`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x180018949`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
char __fastcall nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::sax_parse_internal<nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>(
        __int64 a1,
        char **a2)
{
  __int64 v4; // r15
  char v5; // r14
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  __int64 v11; // rax
  char *v12; // rcx
  __int64 *v13; // rcx
  char *v14; // rcx
  char v15; // al
  __int64 v16; // r8
  char *v17; // rcx
  char v18; // dl
  __int64 v19; // rax
  __int64 *v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // ebx
  char v26; // al
  __int64 v27; // r8
  char *v28; // rcx
  char v29; // dl
  __int64 v30; // rax
  __int64 v31; // rax
  char *v32; // rcx
  char *v33; // rcx
  char v34; // al
  __int64 v35; // r8
  char *v36; // rcx
  char v37; // dl
  __int64 v38; // rax
  __int64 *v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rax
  int v44; // ebx
  char v45; // al
  __int64 v46; // r8
  char *v47; // rcx
  char v48; // dl
  __int64 v49; // rax
  _BYTE *v50; // rdx
  __int64 v51; // rax
  char *v52; // rcx
  char *v53; // rcx
  char v54; // al
  __int64 v55; // r8
  char *v56; // rcx
  char v57; // dl
  __int64 v58; // rax
  __int64 *v59; // rcx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rax
  int v64; // ebx
  char v65; // al
  __int64 v66; // r8
  char *v67; // rcx
  char v68; // dl
  __int64 v69; // rax
  int v70; // ecx
  int v71; // ecx
  int v72; // ecx
  char *v73; // rcx
  char *v74; // rdx
  int v75; // eax
  char v76; // al
  int v77; // eax
  char *v78; // rcx
  char *v79; // rdx
  int v80; // eax
  unsigned __int64 v81; // xmm0_8
  __int64 v82; // rax
  char *v83; // rcx
  char *v84; // rcx
  char v85; // al
  unsigned __int64 v86; // r8
  char *v87; // rcx
  char v88; // dl
  __int64 v89; // rax
  __int64 *v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  __int64 v93; // rdx
  __int64 v94; // rax
  int v95; // ebx
  char v96; // al
  unsigned __int64 v97; // r8
  char *v98; // rcx
  char v99; // dl
  __int64 v100; // rax
  __int64 v101; // rax
  int v102; // eax
  char v103; // al
  int v104; // eax
  int v105; // eax
  int v106; // eax
  _QWORD *v107; // rax
  __int64 v108; // rdx
  const struct nlohmann::detail::parse_error *v109; // rbx
  _QWORD *v110; // rax
  __int64 v111; // rdx
  const struct nlohmann::detail::parse_error *v112; // rbx
  _QWORD *v113; // rcx
  _QWORD *v114; // rax
  __int64 v115; // rdx
  const struct nlohmann::detail::parse_error *v116; // rbx
  _QWORD *v117; // rax
  __int64 v118; // rdx
  const struct nlohmann::detail::parse_error *v119; // rbx
  _QWORD *v120; // rax
  __int64 v121; // rdx
  const struct nlohmann::detail::parse_error *v122; // rbx
  _QWORD *v123; // rax
  __int64 v124; // rdx
  const struct nlohmann::detail::parse_error *v125; // rbx
  _QWORD *v126; // rax
  __int64 v127; // rdx
  const struct nlohmann::detail::parse_error *v128; // rbx
  _QWORD *v129; // rax
  __int64 v130; // rdx
  const struct nlohmann::detail::parse_error *v131; // rbx
  __int64 token_string; // rax
  __int64 v134; // rax
  __int64 v135; // rax
  const struct nlohmann::detail::out_of_range *v136; // rbx
  char v137[8]; // [rsp+30h] [rbp-D0h] BYREF
  int v138; // [rsp+38h] [rbp-C8h] BYREF
  char v139[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v140; // [rsp+48h] [rbp-B8h] BYREF
  char v141[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v142; // [rsp+58h] [rbp-A8h] BYREF
  char v143[8]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v144; // [rsp+68h] [rbp-98h] BYREF
  char v145[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v146; // [rsp+78h] [rbp-88h] BYREF
  __int128 v147; // [rsp+80h] [rbp-80h] BYREF
  __int64 v148; // [rsp+90h] [rbp-70h]
  __int64 v149; // [rsp+98h] [rbp-68h]
  void **v150; // [rsp+A0h] [rbp-60h] BYREF
  char v151[24]; // [rsp+A8h] [rbp-58h] BYREF
  void **v152; // [rsp+C0h] [rbp-40h]
  _BYTE v153[32]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v154; // [rsp+E8h] [rbp-18h] BYREF
  char v155; // [rsp+F0h] [rbp-10h]
  __int64 v156; // [rsp+F8h] [rbp-8h] BYREF
  char v157; // [rsp+100h] [rbp+0h]
  __int64 v158; // [rsp+108h] [rbp+8h] BYREF
  char v159; // [rsp+110h] [rbp+10h]
  __int64 v160; // [rsp+118h] [rbp+18h] BYREF
  char v161; // [rsp+120h] [rbp+20h]
  __int64 v162; // [rsp+128h] [rbp+28h] BYREF
  char v163; // [rsp+130h] [rbp+30h]
  __int64 v164; // [rsp+138h] [rbp+38h] BYREF
  char v165; // [rsp+140h] [rbp+40h]
  __int64 v166; // [rsp+148h] [rbp+48h] BYREF
  char v167; // [rsp+150h] [rbp+50h]
  __int64 v168; // [rsp+158h] [rbp+58h] BYREF
  char v169[8]; // [rsp+160h] [rbp+60h] BYREF
  __int64 v170; // [rsp+168h] [rbp+68h] BYREF
  char v171[8]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v172; // [rsp+178h] [rbp+78h] BYREF
  void **v173; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v174[24]; // [rsp+188h] [rbp+88h] BYREF
  void **v175; // [rsp+1A0h] [rbp+A0h]
  _BYTE v176[24]; // [rsp+1A8h] [rbp+A8h] BYREF
  void **v177; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v178[24]; // [rsp+1C8h] [rbp+C8h] BYREF
  void **v179; // [rsp+1E0h] [rbp+E0h]
  _BYTE v180[24]; // [rsp+1E8h] [rbp+E8h] BYREF
  void **v181; // [rsp+200h] [rbp+100h] BYREF
  char v182[24]; // [rsp+208h] [rbp+108h] BYREF
  void **v183; // [rsp+220h] [rbp+120h]
  char v184[24]; // [rsp+228h] [rbp+128h] BYREF
  char v185[16]; // [rsp+240h] [rbp+140h] BYREF
  char v186[16]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD v187[4]; // [rsp+260h] [rbp+160h] BYREF
  __int128 v188; // [rsp+280h] [rbp+180h] BYREF
  __int64 v189; // [rsp+290h] [rbp+190h]
  _QWORD v190[4]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v191[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  void **v192; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v193[24]; // [rsp+2E8h] [rbp+1E8h] BYREF
  void **v194; // [rsp+300h] [rbp+200h]
  _BYTE v195[24]; // [rsp+308h] [rbp+208h] BYREF
  _QWORD v196[4]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v197[32]; // [rsp+340h] [rbp+240h] BYREF
  _QWORD v198[4]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v199[32]; // [rsp+380h] [rbp+280h] BYREF
  _QWORD pExceptionObject[7]; // [rsp+3A0h] [rbp+2A0h] BYREF

  v147 = 0;
  v148 = 0;
  v149 = 0;
  v4 = a1 + 72;
  v5 = 1;
  while ( 1 )
  {
    v6 = *(_DWORD *)(a1 + 64);
    if ( v6 <= 6 )
    {
      if ( v6 != 6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              v10 = v9 - 1;
              if ( !v10 )
              {
                nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<std::string &>(
                  a2,
                  v196,
                  a1 + 152);
                goto LABEL_94;
              }
              if ( v10 == 1 )
              {
                v11 = std::vector<bool>::back(a2 + 4, v186);
                if ( ((1 << *(_QWORD *)(v11 + 8)) & **(_DWORD **)v11) == 0 )
                  goto LABEL_94;
                v139[0] = 6;
                v140 = *(_QWORD *)(a1 + 200);
                v137[0] = 5;
                v138 = (a2[2] - a2[1]) >> 3;
                v12 = a2[21];
                if ( v12 )
                {
                  if ( !(*(unsigned __int8 (__fastcall **)(char *, int *, char *, char *))(*(_QWORD *)v12 + 16LL))(
                          v12,
                          &v138,
                          v137,
                          v139) )
                    goto LABEL_12;
                  v14 = a2[2];
                  if ( a2[1] == v14 )
                  {
                    v15 = v139[0];
                    v16 = v140;
                    v139[0] = 0;
                    v140 = 0;
                    v17 = *a2;
                    v18 = **a2;
                    *v17 = v15;
                    v153[24] = v18;
                    v19 = *((_QWORD *)v17 + 1);
                    *((_QWORD *)v17 + 1) = v16;
                    v154 = v19;
                    v20 = &v154;
                  }
                  else
                  {
                    v21 = *((_QWORD *)v14 - 1);
                    if ( !v21 )
                      goto LABEL_12;
                    if ( *(_BYTE *)v21 == 2 )
                    {
                      v22 = *(_QWORD *)(v21 + 8);
                      v23 = *(_QWORD *)(v22 + 8);
                      if ( v23 == *(_QWORD *)(v22 + 16) )
                      {
                        std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
                          v22,
                          v23,
                          v139);
                      }
                      else
                      {
                        *(_BYTE *)v23 = v139[0];
                        *(_QWORD *)(v23 + 8) = v140;
                        v139[0] = 0;
                        v140 = 0;
                        *(_QWORD *)(v22 + 8) += 16LL;
                      }
                      goto LABEL_12;
                    }
                    v24 = std::vector<bool>::back(a2 + 8, v185);
                    v25 = **(_DWORD **)v24 & (1 << *(_QWORD *)(v24 + 8));
                    std::vector<bool>::pop_back(a2 + 8);
                    if ( !v25 )
                    {
LABEL_12:
                      v13 = &v140;
LABEL_93:
                      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v13);
                      goto LABEL_94;
                    }
                    v26 = v139[0];
                    v27 = v140;
                    v139[0] = 0;
                    v140 = 0;
                    v28 = a2[12];
                    v29 = *v28;
                    *v28 = v26;
                    v155 = v29;
                    v30 = *((_QWORD *)v28 + 1);
                    *((_QWORD *)v28 + 1) = v27;
                    v156 = v30;
                    v20 = &v156;
                  }
                  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v20);
                  goto LABEL_12;
                }
                std::_Xbad_function_call();
                goto LABEL_110;
              }
              goto LABEL_119;
            }
            v31 = std::vector<bool>::back(a2 + 4, v197);
            if ( ((1 << *(_QWORD *)(v31 + 8)) & **(_DWORD **)v31) == 0 )
              goto LABEL_94;
            v145[0] = 0;
            nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
              &v146,
              0);
            v137[0] = 5;
            v138 = (a2[2] - a2[1]) >> 3;
            v32 = a2[21];
            if ( !v32 )
            {
LABEL_110:
              std::_Xbad_function_call();
LABEL_111:
              std::_Xbad_function_call();
              goto LABEL_112;
            }
            if ( !(*(unsigned __int8 (__fastcall **)(char *, int *, char *, char *))(*(_QWORD *)v32 + 16LL))(
                    v32,
                    &v138,
                    v137,
                    v145) )
              goto LABEL_27;
            v33 = a2[2];
            if ( a2[1] == v33 )
            {
              v34 = v145[0];
              v35 = v146;
              v145[0] = 0;
              v146 = 0;
              v36 = *a2;
              v37 = **a2;
              *v36 = v34;
              v157 = v37;
              v38 = *((_QWORD *)v36 + 1);
              *((_QWORD *)v36 + 1) = v35;
              v158 = v38;
              v39 = &v158;
            }
            else
            {
              v40 = *((_QWORD *)v33 - 1);
              if ( !v40 )
                goto LABEL_27;
              if ( *(_BYTE *)v40 == 2 )
              {
                v41 = *(_QWORD *)(v40 + 8);
                v42 = *(_QWORD *)(v41 + 8);
                if ( v42 == *(_QWORD *)(v41 + 16) )
                {
                  std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
                    v41,
                    v42,
                    v145);
                }
                else
                {
                  *(_BYTE *)v42 = v145[0];
                  *(_QWORD *)(v42 + 8) = v146;
                  v145[0] = 0;
                  v146 = 0;
                  *(_QWORD *)(v41 + 8) += 16LL;
                }
                goto LABEL_27;
              }
              v43 = std::vector<bool>::back(a2 + 8, v198);
              v44 = **(_DWORD **)v43 & (1 << *(_QWORD *)(v43 + 8));
              std::vector<bool>::pop_back(a2 + 8);
              if ( !v44 )
              {
LABEL_27:
                v13 = &v146;
                goto LABEL_93;
              }
              v45 = v145[0];
              v46 = v146;
              v145[0] = 0;
              v146 = 0;
              v47 = a2[12];
              v48 = *v47;
              *v47 = v45;
              v159 = v48;
              v49 = *((_QWORD *)v47 + 1);
              *((_QWORD *)v47 + 1) = v46;
              v160 = v49;
              v39 = &v160;
            }
            nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v39);
            goto LABEL_27;
          }
          v137[0] = 0;
          v50 = v199;
        }
        else
        {
          v137[0] = 1;
          v50 = pExceptionObject;
        }
        nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<bool &>(
          a2,
          v50,
          v137);
        goto LABEL_94;
      }
      v51 = std::vector<bool>::back(a2 + 4, &v192);
      if ( ((1 << *(_QWORD *)(v51 + 8)) & **(_DWORD **)v51) == 0 )
        goto LABEL_94;
      v141[0] = 5;
      v142 = *(_QWORD *)(a1 + 192);
      v137[0] = 5;
      v138 = (a2[2] - a2[1]) >> 3;
      v52 = a2[21];
      if ( !v52 )
        goto LABEL_111;
      if ( !(*(unsigned __int8 (__fastcall **)(char *, int *, char *, char *))(*(_QWORD *)v52 + 16LL))(
              v52,
              &v138,
              v137,
              v141) )
        goto LABEL_44;
      v53 = a2[2];
      if ( a2[1] == v53 )
      {
        v54 = v141[0];
        v55 = v142;
        v141[0] = 0;
        v142 = 0;
        v56 = *a2;
        v57 = **a2;
        *v56 = v54;
        v161 = v57;
        v58 = *((_QWORD *)v56 + 1);
        *((_QWORD *)v56 + 1) = v55;
        v162 = v58;
        v59 = &v162;
      }
      else
      {
        v60 = *((_QWORD *)v53 - 1);
        if ( !v60 )
          goto LABEL_44;
        if ( *(_BYTE *)v60 == 2 )
        {
          v61 = *(_QWORD *)(v60 + 8);
          v62 = *(_QWORD *)(v61 + 8);
          if ( v62 == *(_QWORD *)(v61 + 16) )
          {
            std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
              v61,
              v62,
              v141);
          }
          else
          {
            *(_BYTE *)v62 = v141[0];
            *(_QWORD *)(v62 + 8) = v142;
            v141[0] = 0;
            v142 = 0;
            *(_QWORD *)(v61 + 8) += 16LL;
          }
          goto LABEL_44;
        }
        v63 = std::vector<bool>::back(a2 + 8, v190);
        v64 = **(_DWORD **)v63 & (1 << *(_QWORD *)(v63 + 8));
        std::vector<bool>::pop_back(a2 + 8);
        if ( !v64 )
        {
LABEL_44:
          v13 = &v142;
          goto LABEL_93;
        }
        v65 = v141[0];
        v66 = v142;
        v141[0] = 0;
        v142 = 0;
        v67 = a2[12];
        v68 = *v67;
        *v67 = v65;
        v163 = v68;
        v69 = *((_QWORD *)v67 + 1);
        *((_QWORD *)v67 + 1) = v66;
        v164 = v69;
        v59 = &v164;
      }
      nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v59);
      goto LABEL_44;
    }
    v70 = v6 - 7;
    if ( !v70 )
    {
      v81 = *(_QWORD *)(a1 + 208);
      if ( ((v81 >> 52) & 0x7FF) == 0x7FF )
      {
        token_string = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
                         v4,
                         v190);
        v134 = std::operator+<char>(v191, "number overflow parsing '", token_string);
        v135 = std::operator+<char>(v187, v134, "'");
        v136 = (const struct nlohmann::detail::out_of_range *)nlohmann::detail::out_of_range::create(&v192, 406, v135);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v4,
          &v188);
        *((_BYTE *)a2 + 104) = 1;
        if ( *((_BYTE *)a2 + 176) )
        {
          nlohmann::detail::out_of_range::out_of_range((nlohmann::detail::out_of_range *)pExceptionObject, v136);
          throw (nlohmann::detail::out_of_range *)pExceptionObject;
        }
        std::string::~string(&v188);
        v194 = &std::exception::`vftable';
        o___std_exception_destroy_0(v195);
        v192 = &std::exception::`vftable';
        o___std_exception_destroy_0(v193);
        std::string::~string(v187);
        std::string::~string(v191);
        v113 = v190;
        goto LABEL_136;
      }
      v82 = std::vector<bool>::back(a2 + 4, v191);
      if ( ((1 << *(_QWORD *)(v82 + 8)) & **(_DWORD **)v82) == 0 )
        goto LABEL_94;
      v143[0] = 7;
      v144 = v81;
      v137[0] = 5;
      v138 = (a2[2] - a2[1]) >> 3;
      v83 = a2[21];
      if ( !v83 )
      {
LABEL_124:
        std::_Xbad_function_call();
LABEL_125:
        std::string::string(v187, "array");
        v123 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                 a1,
                 pExceptionObject,
                 0xAu,
                 v187);
        v188 = *(_OWORD *)(a1 + 104);
        v189 = *(_QWORD *)(a1 + 120);
        v125 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                               &v177,
                                                               v124,
                                                               &v188,
                                                               v123);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v4,
          &v192);
        *((_BYTE *)a2 + 104) = 1;
        if ( *((_BYTE *)a2 + 176) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v125);
          throw (nlohmann::detail::parse_error *)&v150;
        }
        std::string::~string(&v192);
        v179 = &std::exception::`vftable';
        o___std_exception_destroy_0(v180);
        v177 = &std::exception::`vftable';
        o___std_exception_destroy_0(v178);
        std::string::~string(pExceptionObject);
        goto LABEL_131;
      }
      if ( (*(unsigned __int8 (__fastcall **)(char *, int *, char *, char *))(*(_QWORD *)v83 + 16LL))(
             v83,
             &v138,
             v137,
             v143) )
      {
        v84 = a2[2];
        if ( a2[1] == v84 )
        {
          v85 = v143[0];
          v86 = v144;
          v143[0] = 0;
          v144 = 0;
          v87 = *a2;
          v88 = **a2;
          *v87 = v85;
          v165 = v88;
          v89 = *((_QWORD *)v87 + 1);
          *((_QWORD *)v87 + 1) = v86;
          v166 = v89;
          v90 = &v166;
LABEL_91:
          nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(v90);
          goto LABEL_92;
        }
        v91 = *((_QWORD *)v84 - 1);
        if ( v91 )
        {
          if ( *(_BYTE *)v91 == 2 )
          {
            v92 = *(_QWORD *)(v91 + 8);
            v93 = *(_QWORD *)(v92 + 8);
            if ( v93 == *(_QWORD *)(v92 + 16) )
            {
              std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>(
                v92,
                v93,
                v143);
            }
            else
            {
              *(_BYTE *)v93 = v143[0];
              *(_QWORD *)(v93 + 8) = v144;
              v143[0] = 0;
              v144 = 0;
              *(_QWORD *)(v92 + 8) += 16LL;
            }
            goto LABEL_92;
          }
          v94 = std::vector<bool>::back(a2 + 8, v187);
          v95 = **(_DWORD **)v94 & (1 << *(_QWORD *)(v94 + 8));
          std::vector<bool>::pop_back(a2 + 8);
          if ( v95 )
          {
            v96 = v143[0];
            v97 = v144;
            v143[0] = 0;
            v144 = 0;
            v98 = a2[12];
            v99 = *v98;
            *v98 = v96;
            v167 = v99;
            v100 = *((_QWORD *)v98 + 1);
            *((_QWORD *)v98 + 1) = v97;
            v168 = v100;
            v90 = &v168;
            goto LABEL_91;
          }
        }
      }
LABEL_92:
      v13 = (__int64 *)&v144;
      goto LABEL_93;
    }
    v71 = v70 - 1;
    if ( v71 )
      break;
    v137[0] = 2;
    v138 = (a2[2] - a2[1]) >> 3;
    v78 = a2[21];
    if ( !v78 )
    {
      std::_Xbad_function_call();
      goto LABEL_124;
    }
    v137[0] = (*(__int64 (__fastcall **)(char *, int *, char *, char **))(*(_QWORD *)v78 + 16LL))(
                v78,
                &v138,
                v137,
                a2 + 23);
    std::vector<bool>::push_back(a2 + 4, v137);
    v137[0] = 2;
    nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<enum nlohmann::detail::value_t>(
      a2,
      v171,
      v137);
    v79 = a2[2];
    if ( v79 == a2[3] )
    {
      std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> * const &>(
        a2 + 1,
        v79,
        &v172);
    }
    else
    {
      *(_QWORD *)v79 = v172;
      a2[2] += 8;
    }
    v80 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
    *(_DWORD *)(a1 + 64) = v80;
    if ( v80 != 10 )
    {
      v137[0] = 1;
      std::vector<bool>::push_back(&v147, v137);
      continue;
    }
    v76 = nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::end_array(a2);
LABEL_64:
    if ( !v76 )
      goto LABEL_132;
    while ( 1 )
    {
LABEL_94:
      if ( !v149 )
        goto LABEL_133;
      v101 = std::vector<bool>::back(&v147, &v188);
      if ( ((1 << *(_QWORD *)(v101 + 8)) & **(_DWORD **)v101) != 0 )
      {
        v102 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
        *(_DWORD *)(a1 + 64) = v102;
        if ( v102 == 13 )
          goto LABEL_70;
        if ( v102 != 10 )
          goto LABEL_125;
        v103 = nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::end_array(a2);
        goto LABEL_102;
      }
      v104 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
      *(_DWORD *)(a1 + 64) = v104;
      if ( v104 == 13 )
        break;
      if ( v104 != 11 )
      {
        std::string::string(v187, "object");
        v126 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
                 a1,
                 v190,
                 0xBu,
                 v187);
        v188 = *(_OWORD *)(a1 + 104);
        v189 = *(_QWORD *)(a1 + 120);
        v128 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                               &v177,
                                                               v127,
                                                               &v188,
                                                               v126);
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
          v4,
          v191);
        *((_BYTE *)a2 + 104) = 1;
        if ( *((_BYTE *)a2 + 176) )
        {
          nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v128);
          throw (nlohmann::detail::parse_error *)&v150;
        }
        std::string::~string(v191);
        v179 = &std::exception::`vftable';
        o___std_exception_destroy_0(v180);
        v177 = &std::exception::`vftable';
        o___std_exception_destroy_0(v178);
        std::string::~string(v190);
        goto LABEL_114;
      }
      v103 = nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::end_object(a2);
LABEL_102:
      if ( !v103 )
        goto LABEL_132;
      std::vector<bool>::pop_back(&v147);
    }
    v105 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
    *(_DWORD *)(a1 + 64) = v105;
    if ( v105 != 4 )
    {
      std::string::string(v187, "object key");
      v129 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
               a1,
               v196,
               4u,
               v187);
      v188 = *(_OWORD *)(a1 + 104);
      v189 = *(_QWORD *)(a1 + 120);
      v131 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                             &v150,
                                                             v130,
                                                             &v188,
                                                             v129);
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        v4,
        v197);
      *((_BYTE *)a2 + 104) = 1;
      if ( *((_BYTE *)a2 + 176) )
      {
        nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v181, v131);
        throw (nlohmann::detail::parse_error *)&v181;
      }
      std::string::~string(v197);
      v152 = &std::exception::`vftable';
      o___std_exception_destroy_0(v153);
      v150 = &std::exception::`vftable';
      o___std_exception_destroy_0(v151);
      std::string::~string(v196);
LABEL_131:
      std::string::~string(v187);
      goto LABEL_132;
    }
    if ( !(unsigned __int8)nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::key(
                             a2,
                             a1 + 152) )
      goto LABEL_132;
    v106 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
    *(_DWORD *)(a1 + 64) = v106;
    if ( v106 != 12 )
    {
      std::string::string(v187, "object separator");
      v107 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
               a1,
               v198,
               0xCu,
               v187);
      v188 = *(_OWORD *)(a1 + 104);
      v189 = *(_QWORD *)(a1 + 120);
      v109 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                             &v181,
                                                             v108,
                                                             &v188,
                                                             v107);
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        v4,
        v199);
      *((_BYTE *)a2 + 104) = 1;
      if ( *((_BYTE *)a2 + 176) )
      {
        nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v109);
        throw (nlohmann::detail::parse_error *)&v150;
      }
      std::string::~string(v199);
      v183 = &std::exception::`vftable';
      o___std_exception_destroy_0(v184);
      v181 = &std::exception::`vftable';
      o___std_exception_destroy_0(v182);
      std::string::~string(v198);
      goto LABEL_131;
    }
LABEL_70:
    *(_DWORD *)(a1 + 64) = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
  }
  v72 = v71 - 1;
  if ( v72 )
  {
    if ( v72 != 5 )
    {
LABEL_119:
      std::string::string(v187, "value");
      v117 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
               a1,
               v190,
               0x10u,
               v187);
      v188 = *(_OWORD *)(a1 + 104);
      v189 = *(_QWORD *)(a1 + 120);
      v119 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(
                                                             &v173,
                                                             v118,
                                                             &v188,
                                                             v117);
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
        v4,
        v191);
      *((_BYTE *)a2 + 104) = 1;
      if ( *((_BYTE *)a2 + 176) )
      {
        nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v119);
        throw (nlohmann::detail::parse_error *)&v150;
      }
      std::string::~string(v191);
      v175 = &std::exception::`vftable';
      o___std_exception_destroy_0(v176);
      v173 = &std::exception::`vftable';
      o___std_exception_destroy_0(v174);
      std::string::~string(v190);
      goto LABEL_131;
    }
    std::string::string(v187, "value");
    v120 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
             a1,
             v190,
             0,
             v187);
    v188 = *(_OWORD *)(a1 + 104);
    v189 = *(_QWORD *)(a1 + 120);
    v122 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v173, v121, &v188, v120);
    nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
      v4,
      v191);
    *((_BYTE *)a2 + 104) = 1;
    if ( *((_BYTE *)a2 + 176) )
    {
      nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v122);
      throw (nlohmann::detail::parse_error *)&v150;
    }
    std::string::~string(v191);
    v175 = &std::exception::`vftable';
    o___std_exception_destroy_0(v176);
    v173 = &std::exception::`vftable';
    o___std_exception_destroy_0(v174);
    std::string::~string(v190);
LABEL_114:
    v113 = v187;
LABEL_136:
    std::string::~string(v113);
    std::vector<unsigned int>::~vector<unsigned int>(&v147);
    return 0;
  }
  v137[0] = 0;
  v138 = (a2[2] - a2[1]) >> 3;
  v73 = a2[21];
  if ( !v73 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v137[0] = (*(__int64 (__fastcall **)(char *, int *, char *, char **))(*(_QWORD *)v73 + 16LL))(
              v73,
              &v138,
              v137,
              a2 + 23);
  std::vector<bool>::push_back(a2 + 4, v137);
  v137[0] = 1;
  nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::handle_value<enum nlohmann::detail::value_t>(
    a2,
    v169,
    v137);
  v74 = a2[2];
  if ( v74 == a2[3] )
  {
    std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *,std::allocator<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> *>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>> * const &>(
      a2 + 1,
      v74,
      &v170);
  }
  else
  {
    *(_QWORD *)v74 = v170;
    a2[2] += 8;
  }
  v75 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
  *(_DWORD *)(a1 + 64) = v75;
  if ( v75 == 11 )
  {
    v76 = nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::end_object(a2);
    goto LABEL_64;
  }
  if ( v75 != 4 )
  {
    std::string::string(v187, "object key");
    v114 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
             a1,
             v190,
             4u,
             v187);
    v188 = *(_OWORD *)(a1 + 104);
    v189 = *(_QWORD *)(a1 + 120);
    v116 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v192, v115, &v188, v114);
    nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
      v4,
      v191);
    *((_BYTE *)a2 + 104) = 1;
    if ( *((_BYTE *)a2 + 176) )
    {
      nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v116);
      throw (nlohmann::detail::parse_error *)&v150;
    }
    goto LABEL_113;
  }
  if ( (unsigned __int8)nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::key(
                          a2,
                          a1 + 152) )
  {
    v77 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(v4);
    *(_DWORD *)(a1 + 64) = v77;
    if ( v77 == 12 )
    {
      v137[0] = 0;
      std::vector<bool>::push_back(&v147, v137);
      goto LABEL_70;
    }
LABEL_112:
    std::string::string(v187, "object separator");
    v110 = nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
             a1,
             v190,
             0xCu,
             v187);
    v188 = *(_OWORD *)(a1 + 104);
    v189 = *(_QWORD *)(a1 + 120);
    v112 = (const struct nlohmann::detail::parse_error *)nlohmann::detail::parse_error::create(&v192, v111, &v188, v110);
    nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
      v4,
      v191);
    *((_BYTE *)a2 + 104) = 1;
    if ( *((_BYTE *)a2 + 176) )
    {
      nlohmann::detail::parse_error::parse_error((nlohmann::detail::parse_error *)&v150, v112);
      throw (nlohmann::detail::parse_error *)&v150;
    }
LABEL_113:
    std::string::~string(v191);
    v194 = &std::exception::`vftable';
    o___std_exception_destroy_0(v195);
    v192 = &std::exception::`vftable';
    o___std_exception_destroy_0(v193);
    std::string::~string(v190);
    goto LABEL_114;
  }
LABEL_132:
  v5 = 0;
LABEL_133:
  std::vector<unsigned int>::~vector<unsigned int>(&v147);
  return v5;
}

```

## disassembly

```asm
0x180017b94  mov     [rsp-8+arg_10], rbx
0x180017b99  mov     [rsp-8+arg_18], rsi
0x180017b9e  push    rbp
0x180017b9f  push    rdi
0x180017ba0  push    r12
0x180017ba2  push    r14
0x180017ba4  push    r15
0x180017ba6  lea     rbp, [rsp-2E0h]
0x180017bae  sub     rsp, 3E0h
0x180017bb5  mov     rax, cs:__security_cookie
0x180017bbc  xor     rax, rsp
0x180017bbf  mov     [rbp+300h+var_28], rax
0x180017bc6  mov     rdi, rdx
0x180017bc9  mov     rsi, rcx
0x180017bcc  xorps   xmm0, xmm0
0x180017bcf  movdqu  [rbp+300h+var_380], xmm0
0x180017bd4  xor     r12d, r12d
0x180017bd7  mov     [rbp+300h+var_370], r12
0x180017bdb  mov     [rbp+300h+var_368], r12
0x180017bdf  lea     r15, [rcx+48h]
0x180017be3  lea     r14d, [r12+1]
0x180017be8  mov     ecx, [rsi+40h]
0x180017beb  cmp     ecx, 6
0x180017bee  jg      loc_1800180CE
0x180017bf4  jz      loc_180017F59
0x180017bfa  sub     ecx, 1
0x180017bfd  jz      loc_180017F4B
0x180017c03  sub     ecx, 1
0x180017c06  jz      loc_180017F2D
0x180017c0c  sub     ecx, 1
0x180017c0f  jz      loc_180017DB7
0x180017c15  sub     ecx, 1
0x180017c18  jz      loc_180017D9C
0x180017c1e  cmp     ecx, 1
0x180017c21  jnz     loc_1800187A5
0x180017c27  lea     rcx, [rdi+20h]
0x180017c2b  lea     rdx, [rbp+300h+var_1B0]
0x180017c32  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017c37  mov     rcx, [rax+8]
0x180017c3b  mov     edx, r14d
0x180017c3e  shl     edx, cl
0x180017c40  mov     rax, [rax]
0x180017c43  test    [rax], edx
0x180017c45  jz      loc_180018445
0x180017c4b  mov     [rsp+400h+var_3C0], 6
0x180017c50  mov     rax, [rsi+0C8h]
0x180017c57  mov     [rsp+400h+var_3B8], rax
0x180017c5c  mov     [rsp+400h+var_3D0], 5
0x180017c61  mov     rax, [rdi+10h]
0x180017c65  sub     rax, [rdi+8]
0x180017c69  sar     rax, 3
0x180017c6d  mov     [rsp+400h+var_3C8], eax
0x180017c71  mov     rcx, [rdi+0A8h]
0x180017c78  test    rcx, rcx
0x180017c7b  jz      loc_1800185D9
0x180017c81  mov     rax, [rcx]
0x180017c84  lea     r9, [rsp+400h+var_3C0]
0x180017c89  lea     r8, [rsp+400h+var_3D0]
0x180017c8e  lea     rdx, [rsp+400h+var_3C8]
0x180017c93  mov     rax, [rax+10h]
0x180017c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017c9c  test    al, al
0x180017c9e  jnz     short loc_180017CAE
0x180017ca0  mov     dl, [rsp+400h+var_3C0]
0x180017ca4  lea     rcx, [rsp+400h+var_3B8]
0x180017ca9  jmp     loc_180018440
0x180017cae  mov     rcx, [rdi+10h]
0x180017cb2  cmp     [rdi+8], rcx
0x180017cb6  jnz     short loc_180017CEC
0x180017cb8  mov     al, [rsp+400h+var_3C0]
0x180017cbc  mov     r8, [rsp+400h+var_3B8]
0x180017cc1  mov     [rsp+400h+var_3C0], r12b
0x180017cc6  mov     [rsp+400h+var_3B8], r12
0x180017ccb  mov     rcx, [rdi]
0x180017cce  mov     dl, [rcx]
0x180017cd0  mov     [rcx], al
0x180017cd2  mov     [rbp+300h+var_320], dl
0x180017cd5  mov     rax, [rcx+8]
0x180017cd9  mov     [rcx+8], r8
0x180017cdd  mov     [rbp+300h+var_318], rax
0x180017ce1  lea     rcx, [rbp+300h+var_318]
0x180017ce5  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180017cea  jmp     short loc_180017CA0
0x180017cec  mov     rcx, [rcx-8]
0x180017cf0  test    rcx, rcx
0x180017cf3  jz      short loc_180017CA0
0x180017cf5  cmp     byte ptr [rcx], 2
0x180017cf8  jnz     short loc_180017D3A
0x180017cfa  mov     rcx, [rcx+8]
0x180017cfe  mov     rdx, [rcx+8]
0x180017d02  cmp     rdx, [rcx+10h]
0x180017d06  jz      short loc_180017D2B
0x180017d08  mov     al, [rsp+400h+var_3C0]
0x180017d0c  mov     [rdx], al
0x180017d0e  mov     rax, [rsp+400h+var_3B8]
0x180017d13  mov     [rdx+8], rax
0x180017d17  mov     [rsp+400h+var_3C0], r12b
0x180017d1c  mov     [rsp+400h+var_3B8], r12
0x180017d21  add     qword ptr [rcx+8], 10h
0x180017d26  jmp     loc_180017CA0
0x180017d2b  lea     r8, [rsp+400h+var_3C0]
0x180017d30  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180017d35  jmp     loc_180017CA0
0x180017d3a  lea     rdx, [rbp+300h+var_1C0]
0x180017d41  lea     rcx, [rdi+40h]
0x180017d45  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017d4a  mov     rcx, [rax+8]
0x180017d4e  mov     ebx, r14d
0x180017d51  shl     ebx, cl
0x180017d53  mov     rax, [rax]
0x180017d56  and     ebx, [rax]
0x180017d58  lea     rcx, [rdi+40h]
0x180017d5c  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x180017d61  test    ebx, ebx
0x180017d63  jz      loc_180017CA0
0x180017d69  mov     al, [rsp+400h+var_3C0]
0x180017d6d  mov     r8, [rsp+400h+var_3B8]
0x180017d72  mov     [rsp+400h+var_3C0], r12b
0x180017d77  mov     [rsp+400h+var_3B8], r12
0x180017d7c  mov     rcx, [rdi+60h]
0x180017d80  mov     dl, [rcx]
0x180017d82  mov     [rcx], al
0x180017d84  mov     [rbp+300h+var_310], dl
0x180017d87  mov     rax, [rcx+8]
0x180017d8b  mov     [rcx+8], r8
0x180017d8f  mov     [rbp+300h+var_308], rax
0x180017d93  lea     rcx, [rbp+300h+var_308]
0x180017d97  jmp     loc_180017CE5
0x180017d9c  lea     r8, [rsi+98h]
0x180017da3  lea     rdx, [rbp+300h+var_E0]
0x180017daa  mov     rcx, rdi
0x180017dad  call    ??$handle_value@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAA?AU?$pair@_NPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@_N@Z; nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::handle_value<std::string &>(std::string &,bool)
0x180017db2  jmp     loc_180018445
0x180017db7  lea     rcx, [rdi+20h]
0x180017dbb  lea     rdx, [rbp+300h+var_C0]
0x180017dc2  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017dc7  mov     rcx, [rax+8]
0x180017dcb  mov     edx, r14d
0x180017dce  shl     edx, cl
0x180017dd0  mov     rax, [rax]
0x180017dd3  test    [rax], edx
0x180017dd5  jz      loc_180018445
0x180017ddb  mov     [rsp+400h+var_390], r12b
0x180017de0  xor     edx, edx
0x180017de2  lea     rcx, [rsp+400h+var_388]
0x180017de7  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180017dec  nop
0x180017ded  mov     [rsp+400h+var_3D0], 5
0x180017df2  mov     rax, [rdi+10h]
0x180017df6  sub     rax, [rdi+8]
0x180017dfa  sar     rax, 3
0x180017dfe  mov     [rsp+400h+var_3C8], eax
0x180017e02  mov     rcx, [rdi+0A8h]
0x180017e09  test    rcx, rcx
0x180017e0c  jz      loc_1800185E0
0x180017e12  mov     rax, [rcx]
0x180017e15  lea     r9, [rsp+400h+var_390]
0x180017e1a  lea     r8, [rsp+400h+var_3D0]
0x180017e1f  lea     rdx, [rsp+400h+var_3C8]
0x180017e24  mov     rax, [rax+10h]
0x180017e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017e2d  test    al, al
0x180017e2f  jnz     short loc_180017E3F
0x180017e31  mov     dl, [rsp+400h+var_390]
0x180017e35  lea     rcx, [rsp+400h+var_388]
0x180017e3a  jmp     loc_180018440
0x180017e3f  mov     rcx, [rdi+10h]
0x180017e43  cmp     [rdi+8], rcx
0x180017e47  jnz     short loc_180017E7D
0x180017e49  mov     al, [rsp+400h+var_390]
0x180017e4d  mov     r8, [rsp+400h+var_388]
0x180017e52  mov     [rsp+400h+var_390], r12b
0x180017e57  mov     [rsp+400h+var_388], r12
0x180017e5c  mov     rcx, [rdi]
0x180017e5f  mov     dl, [rcx]
0x180017e61  mov     [rcx], al
0x180017e63  mov     [rbp+300h+var_300], dl
0x180017e66  mov     rax, [rcx+8]
0x180017e6a  mov     [rcx+8], r8
0x180017e6e  mov     [rbp+300h+var_2F8], rax
0x180017e72  lea     rcx, [rbp+300h+var_2F8]
0x180017e76  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x180017e7b  jmp     short loc_180017E31
0x180017e7d  mov     rcx, [rcx-8]
0x180017e81  test    rcx, rcx
0x180017e84  jz      short loc_180017E31
0x180017e86  cmp     byte ptr [rcx], 2
0x180017e89  jnz     short loc_180017ECB
0x180017e8b  mov     rcx, [rcx+8]
0x180017e8f  mov     rdx, [rcx+8]
0x180017e93  cmp     rdx, [rcx+10h]
0x180017e97  jz      short loc_180017EBC
0x180017e99  mov     al, [rsp+400h+var_390]
0x180017e9d  mov     [rdx], al
0x180017e9f  mov     rax, [rsp+400h+var_388]
0x180017ea4  mov     [rdx+8], rax
0x180017ea8  mov     [rsp+400h+var_390], r12b
0x180017ead  mov     [rsp+400h+var_388], r12
0x180017eb2  add     qword ptr [rcx+8], 10h
0x180017eb7  jmp     loc_180017E31
0x180017ebc  lea     r8, [rsp+400h+var_390]
0x180017ec1  call    ??$_Emplace_reallocate@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@?$vector@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$allocator@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@std@@AEAAPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAV23@$$QEAV23@@Z; std::vector<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::_Emplace_reallocate<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> * const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> &&)
0x180017ec6  jmp     loc_180017E31
0x180017ecb  lea     rdx, [rbp+300h+var_A0]
0x180017ed2  lea     rcx, [rdi+40h]
0x180017ed6  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017edb  mov     rcx, [rax+8]
0x180017edf  mov     ebx, r14d
0x180017ee2  shl     ebx, cl
0x180017ee4  mov     rax, [rax]
0x180017ee7  and     ebx, [rax]
0x180017ee9  lea     rcx, [rdi+40h]
0x180017eed  call    ?pop_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXXZ; std::vector<bool>::pop_back(void)
0x180017ef2  test    ebx, ebx
0x180017ef4  jz      loc_180017E31
0x180017efa  mov     al, [rsp+400h+var_390]
0x180017efe  mov     r8, [rsp+400h+var_388]
0x180017f03  mov     [rsp+400h+var_390], r12b
0x180017f08  mov     [rsp+400h+var_388], r12
0x180017f0d  mov     rcx, [rdi+60h]
0x180017f11  mov     dl, [rcx]
0x180017f13  mov     [rcx], al
0x180017f15  mov     [rbp+300h+var_2F0], dl
0x180017f18  mov     rax, [rcx+8]
0x180017f1c  mov     [rcx+8], r8
0x180017f20  mov     [rbp+300h+var_2E8], rax
0x180017f24  lea     rcx, [rbp+300h+var_2E8]
0x180017f28  jmp     loc_180017E76
0x180017f2d  mov     [rsp+400h+var_3D0], r12b
0x180017f32  lea     rdx, [rbp+300h+var_80]
0x180017f39  lea     r8, [rsp+400h+var_3D0]
0x180017f3e  mov     rcx, rdi
0x180017f41  call    ??$handle_value@AEA_N@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@AEAA?AU?$pair@_NPEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@AEA_N_N@Z; nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::handle_value<bool &>(bool &,bool)
0x180017f46  jmp     loc_180018445
0x180017f4b  mov     [rsp+400h+var_3D0], r14b
0x180017f50  lea     rdx, [rbp+300h+pExceptionObject]
0x180017f57  jmp     short loc_180017F39
0x180017f59  lea     rcx, [rdi+20h]
0x180017f5d  lea     rdx, [rbp+300h+var_120]
0x180017f64  call    ?back@?$vector@_NV?$allocator@_N@std@@@std@@QEAA?AV?$_Vb_reference@U?$_Wrap_alloc@V?$allocator@I@std@@@std@@@2@XZ; std::vector<bool>::back(void)
0x180017f69  mov     rcx, [rax+8]
0x180017f6d  mov     edx, r14d
0x180017f70  shl     edx, cl
0x180017f72  mov     rax, [rax]
0x180017f75  test    [rax], edx
0x180017f77  jz      loc_180018445
0x180017f7d  mov     [rsp+400h+var_3B0], 5
0x180017f82  mov     rax, [rsi+0C0h]
0x180017f89  mov     [rsp+400h+var_3A8], rax
0x180017f8e  mov     [rsp+400h+var_3D0], 5
0x180017f93  mov     rax, [rdi+10h]
0x180017f97  sub     rax, [rdi+8]
0x180017f9b  sar     rax, 3
0x180017f9f  mov     [rsp+400h+var_3C8], eax
0x180017fa3  mov     rcx, [rdi+0A8h]
0x180017faa  test    rcx, rcx
0x180017fad  jz      loc_1800185E7
0x180017fb3  mov     rax, [rcx]
0x180017fb6  lea     r9, [rsp+400h+var_3B0]
0x180017fbb  lea     r8, [rsp+400h+var_3D0]
0x180017fc0  lea     rdx, [rsp+400h+var_3C8]
0x180017fc5  mov     rax, [rax+10h]
0x180017fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fce  test    al, al
0x180017fd0  jnz     short loc_180017FE0
0x180017fd2  mov     dl, [rsp+400h+var_3B0]
0x180017fd6  lea     rcx, [rsp+400h+var_3A8]
0x180017fdb  jmp     loc_180018440
0x180017fe0  mov     rcx, [rdi+10h]
0x180017fe4  cmp     [rdi+8], rcx
0x180017fe8  jnz     short loc_18001801E
0x180017fea  mov     al, [rsp+400h+var_3B0]
0x180017fee  mov     r8, [rsp+400h+var_3A8]
0x180017ff3  mov     [rsp+400h+var_3B0], r12b
0x180017ff8  mov     [rsp+400h+var_3A8], r12
0x180017ffd  mov     rcx, [rdi]
0x180018000  mov     dl, [rcx]
0x180018002  mov     [rcx], al
0x180018004  mov     [rbp+300h+var_2E0], dl
0x180018007  mov     rax, [rcx+8]
0x18001800b  mov     [rcx+8], r8
0x18001800f  mov     [rbp+300h+var_2D8], rax
0x180018013  lea     rcx, [rbp+300h+var_2D8]
0x180018017  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18001801c  jmp     short loc_180017FD2
0x18001801e  mov     rcx, [rcx-8]
0x180018022  test    rcx, rcx
0x180018025  jz      short loc_180017FD2
0x180018027  cmp     byte ptr [rcx], 2
0x18001802a  jnz     short loc_18001806C
0x18001802c  mov     rcx, [rcx+8]
0x180018030  mov     rdx, [rcx+8]
0x180018034  cmp     rdx, [rcx+10h]
0x180018038  jz      short loc_18001805D
0x18001803a  mov     al, [rsp+400h+var_3B0]
0x18001803e  mov     [rdx], al
0x180018040  mov     rax, [rsp+400h+var_3A8]
0x180018045  mov     [rdx+8], rax
0x180018049  mov     [rsp+400h+var_3B0], r12b
0x18001804e  mov     [rsp+400h+var_3A8], r12
  ... truncated ...
```
