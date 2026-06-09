# nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(void)

- ea: `0x180026060`
- end: `0x1800266a9`
- name: `?scan_number@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ`
- size: `1609`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025d30`

## callees

- `0x180014b74`
- `0x1800159b0`
- `0x180024948`
- `0x180026060`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800265ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002661e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002665d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800265ef`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002661e`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002665d`
- `api-ms-win-crt-private-l1-1-0!_o_strtod` at `0x180026683`
- `api-ms-win-crt-private-l1-1-0!_o_strtod` at `0x180026683`
- `api-ms-win-crt-private-l1-1-0!_o_strtoll` at `0x180026654`
- `api-ms-win-crt-private-l1-1-0!_o_strtoll` at `0x180026654`
- `api-ms-win-crt-private-l1-1-0!_o_strtoull` at `0x180026615`
- `api-ms-win-crt-private-l1-1-0!_o_strtoull` at `0x180026615`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(
        __int64 a1)
{
  _QWORD *v2; // rbx
  _BYTE *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rdx
  char v6; // al
  int v7; // esi
  int v8; // r9d
  int v9; // ecx
  unsigned __int64 v10; // rcx
  _BYTE *v11; // rax
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  bool v16; // zf
  unsigned __int64 v17; // rcx
  _BYTE *v18; // rax
  int v19; // ecx
  int v20; // eax
  bool v21; // zf
  int v22; // ecx
  char v23; // r9
  unsigned __int64 v24; // rcx
  _BYTE *v25; // rax
  int v26; // ecx
  const char *v27; // rax
  unsigned __int64 v29; // rcx
  _BYTE *v30; // rax
  bool v31; // zf
  int v32; // ecx
  int v33; // ecx
  char v34; // r9
  unsigned __int64 v35; // rcx
  _BYTE *v36; // rax
  int v37; // eax
  char v38; // r9
  unsigned __int64 v39; // rcx
  _BYTE *v40; // rax
  char v41; // r9
  unsigned __int64 v42; // rcx
  _BYTE *v43; // rax
  int v44; // eax
  bool v45; // zf
  int v46; // ecx
  int v47; // ecx
  char v48; // r9
  unsigned __int64 v49; // rcx
  bool v50; // cc
  int v51; // eax
  _BYTE *v52; // rax
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // eax
  bool v56; // zf
  int v57; // ecx
  char v58; // r9
  unsigned __int64 v59; // rcx
  _BYTE *v60; // rax
  int v61; // eax
  bool v62; // zf
  int v63; // ecx
  int v64; // ecx
  int v65; // ecx
  char v66; // r9
  unsigned __int64 v67; // rcx
  _BYTE *v68; // rax
  int v69; // eax
  bool v70; // zf
  int v71; // ecx
  int v72; // ecx
  char v73; // r9
  unsigned __int64 v74; // rcx
  _BYTE *v75; // rax
  const char *v76; // rcx
  unsigned __int64 v77; // rsi
  __int64 v78; // rdx
  __int64 v79; // rcx
  __int64 v80; // r8
  const char *v81; // rcx
  __int64 v82; // rsi
  __int64 v83; // rdx
  __int64 v84; // rcx
  __int64 v85; // r8
  char v86; // [rsp+40h] [rbp+8h] BYREF
  char *EndPtr; // [rsp+48h] [rbp+10h] BYREF

  v2 = (_QWORD *)(a1 + 80);
  *(_QWORD *)(a1 + 96) = 0;
  if ( *(_QWORD *)(a1 + 104) <= 0xFu )
    v3 = (_BYTE *)(a1 + 80);
  else
    v3 = (_BYTE *)*v2;
  *v3 = 0;
  v4 = a1 + 56;
  v5 = *(_BYTE **)v4;
  if ( *(_QWORD *)v4 == *(_QWORD *)(v4 + 8) )
    v5 = *(_BYTE **)(v4 + 8);
  else
    *(_QWORD *)(v4 + 8) = v5;
  v6 = *(_BYTE *)(a1 + 20);
  v86 = v6;
  if ( v5 == *(_BYTE **)(v4 + 16) )
  {
    std::vector<char>::_Emplace_reallocate<char>(v4, v5, &v86);
  }
  else
  {
    *v5 = v6;
    ++*(_QWORD *)(v4 + 8);
  }
  v7 = 5;
  v8 = *(_DWORD *)(a1 + 20);
  if ( v8 > 52 )
  {
    if ( v8 == 53 )
      goto LABEL_48;
    v9 = v8 - 54;
    if ( v8 == 54 )
      goto LABEL_48;
    goto LABEL_30;
  }
  if ( v8 != 52 )
  {
    if ( v8 == 45 )
    {
      v17 = v2[2];
      if ( v17 >= v2[3] )
      {
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
      }
      else
      {
        v2[2] = v17 + 1;
        if ( v2[3] <= 0xFu )
          v18 = v2;
        else
          v18 = (_BYTE *)*v2;
        *(_WORD *)&v18[v17] = 45;
      }
      goto LABEL_32;
    }
    v9 = v8 - 48;
    if ( v8 == 48 )
    {
      v10 = v2[2];
      if ( v10 < v2[3] )
      {
        v2[2] = v10 + 1;
        if ( v2[3] <= 0xFu )
          v11 = v2;
        else
          v11 = (_BYTE *)*v2;
        *(_WORD *)&v11[v10] = 48;
        goto LABEL_20;
      }
      goto LABEL_19;
    }
LABEL_30:
    v19 = v9 - 1;
    if ( !v19 || (unsigned int)(v19 - 1) < 2 )
      goto LABEL_48;
LABEL_32:
    v7 = 6;
    v20 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
    if ( v20 > 53 )
    {
      v22 = v20 - 54;
      v21 = v20 == 54;
    }
    else
    {
      if ( v20 == 53 )
      {
LABEL_47:
        LOBYTE(v8) = *(_BYTE *)(a1 + 20);
        goto LABEL_48;
      }
      if ( v20 == 48 )
      {
        v23 = *(_BYTE *)(a1 + 20);
        v24 = v2[2];
        if ( v24 < v2[3] )
        {
          v2[2] = v24 + 1;
          if ( v2[3] <= 0xFu )
            v25 = v2;
          else
            v25 = (_BYTE *)*v2;
          v25[v24] = v23;
          v25[v24 + 1] = 0;
LABEL_20:
          v12 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
          if ( v12 != 46 )
          {
            v16 = ((v12 - 69) & 0xFFFFFFDF) == 0;
            goto LABEL_71;
          }
LABEL_75:
          v41 = *(_BYTE *)(a1 + 144);
          v42 = v2[2];
          if ( v42 >= v2[3] )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
          }
          else
          {
            v2[2] = v42 + 1;
            if ( v2[3] <= 0xFu )
              v43 = v2;
            else
              v43 = (_BYTE *)*v2;
            v43[v42 + 1] = 0;
            v43[v42] = v41;
          }
          v44 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
          if ( v44 > 53 )
          {
            v46 = v44 - 54;
            v45 = v44 == 54;
          }
          else
          {
            if ( v44 == 53 || v44 == 48 )
            {
LABEL_90:
              v48 = *(_BYTE *)(a1 + 20);
              v49 = v2[2];
              if ( v49 >= v2[3] )
                goto LABEL_92;
              v50 = v2[3] <= 0xFu;
LABEL_106:
              v2[2] = v49 + 1;
              if ( v50 )
                v52 = v2;
              else
                v52 = (_BYTE *)*v2;
              v52[v49] = v48;
              v52[v49 + 1] = 0;
              while ( 1 )
              {
                v51 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
                if ( v51 > 54 )
                {
                  if ( v51 != 55 && v51 != 56 && v51 != 57 )
                  {
                    v14 = (unsigned int)(v51 - 69);
                    if ( v51 != 69 && v51 != 101 )
                    {
LABEL_112:
                      v7 = 7;
                      goto LABEL_113;
                    }
LABEL_72:
                    v38 = *(_BYTE *)(a1 + 20);
                    v39 = v2[2];
                    if ( v39 >= v2[3] )
                    {
                      std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                    }
                    else
                    {
                      v2[2] = v39 + 1;
                      if ( v2[3] <= 0xFu )
                        v40 = v2;
                      else
                        v40 = (_BYTE *)*v2;
                      v40[v39 + 1] = 0;
                      v40[v39] = v38;
                    }
                    v55 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
                    if ( v55 > 52 )
                    {
                      if ( v55 != 53 )
                      {
                        v57 = v55 - 54;
                        v56 = v55 == 54;
                        goto LABEL_141;
                      }
                    }
                    else
                    {
                      if ( v55 == 52 )
                        goto LABEL_145;
                      if ( v55 == 43 || v55 == 45 )
                      {
                        v58 = *(_BYTE *)(a1 + 20);
                        v59 = v2[2];
                        if ( v59 >= v2[3] )
                        {
                          std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                        }
                        else
                        {
                          v2[2] = v59 + 1;
                          if ( v2[3] <= 0xFu )
                            v60 = v2;
                          else
                            v60 = (_BYTE *)*v2;
                          v60[v59] = v58;
                          v60[v59 + 1] = 0;
                        }
                        v61 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
                        if ( v61 > 53 )
                        {
                          v63 = v61 - 54;
                          v62 = v61 == 54;
                        }
                        else
                        {
                          if ( v61 == 53 || v61 == 48 )
                            goto LABEL_145;
                          v63 = v61 - 49;
                          v62 = v61 == 49;
                        }
                        if ( !v62 )
                        {
                          v64 = v63 - 1;
                          if ( v64 )
                          {
                            if ( (unsigned int)(v64 - 1) >= 2 )
                            {
                              v27 = "invalid number; expected digit after exponent sign";
                              goto LABEL_46;
                            }
                          }
                        }
                      }
                      else
                      {
                        v57 = v55 - 48;
                        v56 = v55 == 48;
LABEL_141:
                        if ( !v56 )
                        {
                          v65 = v57 - 1;
                          if ( v65 )
                          {
                            if ( (unsigned int)(v65 - 1) >= 2 )
                            {
                              v27 = "invalid number; expected '+', '-', or digit after exponent";
LABEL_46:
                              *(_QWORD *)(a1 + 112) = v27;
                              return 14;
                            }
                          }
                        }
                      }
                    }
LABEL_145:
                    v66 = *(_BYTE *)(a1 + 20);
                    v67 = v2[2];
                    if ( v67 >= v2[3] )
                    {
                      std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                    }
                    else
                    {
                      v2[2] = v67 + 1;
                      if ( v2[3] <= 0xFu )
                        v68 = v2;
                      else
                        v68 = (_BYTE *)*v2;
                      v68[v67 + 1] = 0;
                      v68[v67] = v66;
                    }
                    v7 = 7;
                    while ( 2 )
                    {
                      v69 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
                      if ( v69 > 53 )
                      {
                        v71 = v69 - 54;
                        v70 = v69 == 54;
LABEL_157:
                        if ( !v70 )
                        {
                          v72 = v71 - 1;
                          if ( v72 )
                          {
                            v14 = (unsigned int)(v72 - 1);
                            if ( (unsigned int)v14 > 1 )
                              goto LABEL_113;
                          }
                        }
                      }
                      else if ( v69 != 53 && v69 != 48 )
                      {
                        v71 = v69 - 49;
                        v70 = v69 == 49;
                        goto LABEL_157;
                      }
                      v73 = *(_BYTE *)(a1 + 20);
                      v74 = *(_QWORD *)(a1 + 96);
                      if ( v74 >= *(_QWORD *)(a1 + 104) )
                      {
                        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                      }
                      else
                      {
                        v2[2] = v74 + 1;
                        if ( *(_QWORD *)(a1 + 104) <= 0xFu )
                          v75 = v2;
                        else
                          v75 = (_BYTE *)*v2;
                        v75[v74] = v73;
                        v75[v74 + 1] = 0;
                      }
                      continue;
                    }
                  }
                }
                else if ( v51 != 54 && v51 != 48 && v51 != 49 && v51 != 50 && v51 != 51 )
                {
                  v14 = (unsigned int)(v51 - 52);
                  if ( (unsigned int)v14 > 1 )
                    goto LABEL_112;
                }
                v48 = *(_BYTE *)(a1 + 20);
                v49 = *(_QWORD *)(a1 + 96);
                if ( v49 < *(_QWORD *)(a1 + 104) )
                {
                  v50 = *(_QWORD *)(a1 + 104) <= 0xFu;
                  goto LABEL_106;
                }
LABEL_92:
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
              }
            }
            v46 = v44 - 49;
            v45 = v44 == 49;
          }
          if ( !v45 )
          {
            v47 = v46 - 1;
            if ( v47 )
            {
              if ( (unsigned int)(v47 - 1) >= 2 )
              {
                v27 = "invalid number; expected digit after '.'";
                goto LABEL_46;
              }
            }
          }
          goto LABEL_90;
        }
LABEL_19:
        std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
        goto LABEL_20;
      }
      v22 = v20 - 49;
      v21 = v20 == 49;
    }
    if ( !v21 )
    {
      v26 = v22 - 1;
      if ( v26 )
      {
        if ( (unsigned int)(v26 - 1) >= 2 )
        {
          v27 = "invalid number; expected digit after '-'";
          goto LABEL_46;
        }
      }
    }
    goto LABEL_47;
  }
LABEL_48:
  v29 = v2[2];
  if ( v29 >= v2[3] )
    goto LABEL_68;
  v2[2] = v29 + 1;
  if ( v2[3] <= 0xFu )
    v30 = v2;
  else
    v30 = (_BYTE *)*v2;
  v30[v29 + 1] = 0;
  v30[v29] = v8;
  while ( 1 )
  {
    v37 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
    v14 = (unsigned int)v37;
    if ( v37 > 69 )
    {
      v16 = v37 == 101;
LABEL_71:
      if ( !v16 )
        goto LABEL_113;
      goto LABEL_72;
    }
    if ( v37 == 69 )
      goto LABEL_72;
    if ( v37 <= 52 )
      break;
    if ( v37 != 53 )
    {
      v32 = v37 - 54;
      v31 = v37 == 54;
      goto LABEL_60;
    }
LABEL_63:
    v34 = *(_BYTE *)(a1 + 20);
    v35 = *(_QWORD *)(a1 + 96);
    if ( v35 >= *(_QWORD *)(a1 + 104) )
    {
LABEL_68:
      std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
    }
    else
    {
      v2[2] = v35 + 1;
      if ( *(_QWORD *)(a1 + 104) <= 0xFu )
        v36 = v2;
      else
        v36 = (_BYTE *)*v2;
      v36[v35] = v34;
      v36[v35 + 1] = 0;
    }
  }
  if ( v37 == 52 )
    goto LABEL_63;
  if ( v37 == 46 )
    goto LABEL_75;
  v32 = v37 - 48;
  v31 = v37 == 48;
LABEL_60:
  if ( v31 )
    goto LABEL_63;
  v33 = v32 - 1;
  if ( !v33 )
    goto LABEL_63;
  v14 = (unsigned int)(v33 - 1);
  if ( (unsigned int)v14 <= 1 )
    goto LABEL_63;
LABEL_113:
  *(_BYTE *)(a1 + 24) = 1;
  --*(_QWORD *)(a1 + 32);
  v53 = *(_QWORD *)(a1 + 40);
  if ( v53 )
  {
    *(_QWORD *)(a1 + 40) = v53 - 1;
  }
  else
  {
    v54 = *(_QWORD *)(a1 + 48);
    if ( v54 )
      *(_QWORD *)(a1 + 48) = v54 - 1;
  }
  if ( *(_DWORD *)(a1 + 20) != -1 )
    --*(_QWORD *)(a1 + 64);
  EndPtr = 0;
  *(_DWORD *)_o__errno(v14, v13, v15) = 0;
  if ( v7 == 5 )
  {
    if ( v2[3] <= 0xFu )
      v76 = (const char *)v2;
    else
      v76 = (const char *)*v2;
    v77 = strtoull(v76, &EndPtr, 10);
    if ( !*(_DWORD *)_o__errno(v79, v78, v80) )
    {
      *(_QWORD *)(a1 + 128) = v77;
      return 5;
    }
  }
  else if ( v7 == 6 )
  {
    v81 = v2[3] <= 0xFu ? (const char *)v2 : (const char *)*v2;
    v82 = strtoll(v81, &EndPtr, 10);
    if ( !*(_DWORD *)_o__errno(v84, v83, v85) )
    {
      *(_QWORD *)(a1 + 120) = v82;
      return 6;
    }
  }
  if ( v2[3] > 0xFu )
    v2 = (_QWORD *)*v2;
  *(double *)(a1 + 136) = strtod((const char *)v2, &EndPtr);
  return 7;
}

```

## disassembly

```asm
0x180026060  mov     [rsp+arg_10], rbx
0x180026065  mov     [rsp+arg_18], rbp
0x18002606a  push    rsi
0x18002606b  push    rdi
0x18002606c  push    r14
0x18002606e  sub     rsp, 20h
0x180026072  mov     rdi, rcx
0x180026075  lea     rbx, [rcx+50h]
0x180026079  xor     ebp, ebp
0x18002607b  mov     [rbx+10h], rbp
0x18002607f  lea     r14d, [rbp+0Fh]
0x180026083  cmp     [rbx+18h], r14
0x180026087  jbe     short loc_18002608E
0x180026089  mov     rax, [rbx]
0x18002608c  jmp     short loc_180026091
0x18002608e  mov     rax, rbx
0x180026091  mov     [rax], bpl
0x180026094  add     rcx, 38h ; '8'
0x180026098  mov     rdx, [rcx]
0x18002609b  cmp     rdx, [rcx+8]
0x18002609f  jz      short loc_1800260A7
0x1800260a1  mov     [rcx+8], rdx
0x1800260a5  jmp     short loc_1800260AB
0x1800260a7  mov     rdx, [rcx+8]
0x1800260ab  mov     al, [rdi+14h]
0x1800260ae  mov     [rsp+38h+arg_0], al
0x1800260b2  cmp     rdx, [rcx+10h]
0x1800260b6  jz      short loc_1800260C0
0x1800260b8  mov     [rdx], al
0x1800260ba  inc     qword ptr [rcx+8]
0x1800260be  jmp     short loc_1800260CB
0x1800260c0  lea     r8, [rsp+38h+arg_0]
0x1800260c5  call    ??$_Emplace_reallocate@D@?$vector@DV?$allocator@D@std@@@std@@AEAAPEADQEAD$$QEAD@Z; std::vector<char>::_Emplace_reallocate<char>(char * const,char &&)
0x1800260ca  nop
0x1800260cb  mov     esi, 5
0x1800260d0  mov     r9d, [rdi+14h]
0x1800260d4  cmp     r9d, 34h ; '4'
0x1800260d8  jg      loc_18002617B
0x1800260de  jz      loc_18002622E
0x1800260e4  mov     ecx, r9d
0x1800260e7  sub     ecx, 2Dh ; '-'
0x1800260ea  jz      short loc_180026146
0x1800260ec  sub     ecx, 3
0x1800260ef  jnz     loc_180026190
0x1800260f5  mov     rcx, [rbx+10h]
0x1800260f9  cmp     rcx, [rbx+18h]
0x1800260fd  jnb     short loc_18002611D
0x1800260ff  lea     rax, [rcx+1]
0x180026103  mov     [rbx+10h], rax
0x180026107  cmp     [rbx+18h], r14
0x18002610b  jbe     short loc_180026112
0x18002610d  mov     rax, [rbx]
0x180026110  jmp     short loc_180026115
0x180026112  mov     rax, rbx
0x180026115  mov     word ptr [rcx+rax], 30h ; '0'
0x18002611b  jmp     short loc_180026128
0x18002611d  mov     r9b, 30h ; '0'
0x180026120  mov     rcx, rbx; Src
0x180026123  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026128  mov     rcx, rdi
0x18002612b  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180026130  cmp     eax, 2Eh ; '.'
0x180026133  jz      loc_180026317
0x180026139  add     eax, 0FFFFFFBBh
0x18002613c  test    eax, 0FFFFFFDFh
0x180026141  jmp     loc_1800262E5
0x180026146  mov     rcx, [rbx+10h]
0x18002614a  cmp     rcx, [rbx+18h]
0x18002614e  jnb     short loc_18002616E
0x180026150  lea     rax, [rcx+1]
0x180026154  mov     [rbx+10h], rax
0x180026158  cmp     [rbx+18h], r14
0x18002615c  jbe     short loc_180026163
0x18002615e  mov     rax, [rbx]
0x180026161  jmp     short loc_180026166
0x180026163  mov     rax, rbx
0x180026166  mov     word ptr [rcx+rax], 2Dh ; '-'
0x18002616c  jmp     short loc_1800261AB
0x18002616e  mov     r9b, 2Dh ; '-'
0x180026171  mov     rcx, rbx; Src
0x180026174  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026179  jmp     short loc_1800261AB
0x18002617b  mov     ecx, r9d
0x18002617e  sub     ecx, 35h ; '5'
0x180026181  jz      loc_18002622E
0x180026187  sub     ecx, 1
0x18002618a  jz      loc_18002622E
0x180026190  sub     ecx, 1
0x180026193  jz      loc_18002622E
0x180026199  sub     ecx, 1
0x18002619c  jz      loc_18002622E
0x1800261a2  cmp     ecx, 1
0x1800261a5  jz      loc_18002622E
0x1800261ab  mov     esi, 6
0x1800261b0  mov     rcx, rdi
0x1800261b3  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x1800261b8  mov     ecx, eax
0x1800261ba  cmp     eax, 35h ; '5'
0x1800261bd  jg      short loc_180026201
0x1800261bf  jz      short loc_18002622A
0x1800261c1  sub     ecx, 30h ; '0'
0x1800261c4  jz      short loc_1800261CB
0x1800261c6  sub     ecx, 1
0x1800261c9  jmp     short loc_180026204
0x1800261cb  mov     r9b, [rdi+14h]
0x1800261cf  mov     rcx, [rbx+10h]
0x1800261d3  cmp     rcx, [rbx+18h]
0x1800261d7  jnb     loc_180026120
0x1800261dd  lea     rax, [rcx+1]
0x1800261e1  mov     [rbx+10h], rax
0x1800261e5  cmp     [rbx+18h], r14
0x1800261e9  jbe     short loc_1800261F0
0x1800261eb  mov     rax, [rbx]
0x1800261ee  jmp     short loc_1800261F3
0x1800261f0  mov     rax, rbx
0x1800261f3  mov     [rcx+rax], r9b
0x1800261f7  mov     [rcx+rax+1], bpl
0x1800261fc  jmp     loc_180026128
0x180026201  sub     ecx, 36h ; '6'
0x180026204  jz      short loc_18002622A
0x180026206  sub     ecx, 1
0x180026209  jz      short loc_18002622A
0x18002620b  sub     ecx, 1
0x18002620e  jz      short loc_18002622A
0x180026210  cmp     ecx, 1
0x180026213  jz      short loc_18002622A
0x180026215  lea     rax, aInvalidNumberE_0; "invalid number; expected digit after '-"...
0x18002621c  mov     [rdi+70h], rax
0x180026220  mov     eax, 0Eh
0x180026225  jmp     loc_180026696
0x18002622a  mov     r9b, [rdi+14h]
0x18002622e  mov     rcx, [rbx+10h]
0x180026232  cmp     rcx, [rbx+18h]
0x180026236  jnb     loc_1800262C7
0x18002623c  lea     rax, [rcx+1]
0x180026240  mov     [rbx+10h], rax
0x180026244  cmp     [rbx+18h], r14
0x180026248  jbe     short loc_18002624F
0x18002624a  mov     rax, [rbx]
0x18002624d  jmp     short loc_180026252
0x18002624f  mov     rax, rbx
0x180026252  mov     [rcx+rax+1], bpl
0x180026257  mov     [rcx+rax], r9b
0x18002625b  jmp     short loc_1800262CF
0x18002625d  cmp     ecx, 45h ; 'E'
0x180026260  jz      loc_1800262EB
0x180026266  cmp     ecx, 34h ; '4'
0x180026269  jg      short loc_18002627B
0x18002626b  jz      short loc_180026298
0x18002626d  sub     ecx, 2Eh ; '.'
0x180026270  jz      loc_180026317
0x180026276  sub     ecx, 2
0x180026279  jmp     short loc_180026283
0x18002627b  sub     ecx, 35h ; '5'
0x18002627e  jz      short loc_180026298
0x180026280  sub     ecx, 1
0x180026283  jz      short loc_180026298
0x180026285  sub     ecx, 1
0x180026288  jz      short loc_180026298
0x18002628a  sub     ecx, 1
0x18002628d  jz      short loc_180026298
0x18002628f  cmp     ecx, 1
0x180026292  jnz     loc_18002642E
0x180026298  mov     r9b, [rdi+14h]
0x18002629c  mov     rcx, [rdi+60h]
0x1800262a0  cmp     rcx, [rdi+68h]
0x1800262a4  jnb     short loc_1800262C7
0x1800262a6  lea     rax, [rcx+1]
0x1800262aa  mov     [rbx+10h], rax
0x1800262ae  cmp     [rdi+68h], r14
0x1800262b2  jbe     short loc_1800262B9
0x1800262b4  mov     rax, [rbx]
0x1800262b7  jmp     short loc_1800262BC
0x1800262b9  mov     rax, rbx
0x1800262bc  mov     [rcx+rax], r9b
0x1800262c0  mov     [rcx+rax+1], bpl
0x1800262c5  jmp     short loc_1800262CF
0x1800262c7  mov     rcx, rbx; Src
0x1800262ca  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x1800262cf  mov     rcx, rdi
0x1800262d2  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x1800262d7  cmp     eax, 45h ; 'E'
0x1800262da  mov     ecx, eax
0x1800262dc  jle     loc_18002625D
0x1800262e2  cmp     eax, 65h ; 'e'
0x1800262e5  jnz     loc_18002642E
0x1800262eb  mov     r9b, [rdi+14h]
0x1800262ef  mov     rcx, [rbx+10h]
0x1800262f3  cmp     rcx, [rbx+18h]
0x1800262f7  jnb     loc_18002646A
0x1800262fd  lea     rax, [rcx+1]
0x180026301  mov     [rbx+10h], rax
0x180026305  cmp     [rbx+18h], r14
0x180026309  jbe     loc_18002645C
0x18002630f  mov     rax, [rbx]
0x180026312  jmp     loc_18002645F
0x180026317  mov     r9b, [rdi+90h]
0x18002631e  mov     rcx, [rbx+10h]
0x180026322  cmp     rcx, [rbx+18h]
0x180026326  jnb     short loc_180026349
0x180026328  lea     rax, [rcx+1]
0x18002632c  mov     [rbx+10h], rax
0x180026330  cmp     [rbx+18h], r14
0x180026334  jbe     short loc_18002633B
0x180026336  mov     rax, [rbx]
0x180026339  jmp     short loc_18002633E
0x18002633b  mov     rax, rbx
0x18002633e  mov     [rcx+rax+1], bpl
0x180026343  mov     [rcx+rax], r9b
0x180026347  jmp     short loc_180026351
0x180026349  mov     rcx, rbx; Src
0x18002634c  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026351  mov     rcx, rdi
0x180026354  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180026359  mov     ecx, eax
0x18002635b  cmp     eax, 35h ; '5'
0x18002635e  jg      short loc_18002636C
0x180026360  jz      short loc_18002638C
0x180026362  sub     ecx, 30h ; '0'
0x180026365  jz      short loc_18002638C
0x180026367  sub     ecx, 1
0x18002636a  jmp     short loc_18002636F
0x18002636c  sub     ecx, 36h ; '6'
0x18002636f  jz      short loc_18002638C
0x180026371  sub     ecx, 1
0x180026374  jz      short loc_18002638C
0x180026376  sub     ecx, 1
0x180026379  jz      short loc_18002638C
0x18002637b  cmp     ecx, 1
0x18002637e  jz      short loc_18002638C
0x180026380  lea     rax, aInvalidNumberE_1; "invalid number; expected digit after '."...
0x180026387  jmp     loc_18002621C
0x18002638c  mov     r9b, [rdi+14h]
0x180026390  mov     rcx, [rbx+10h]
0x180026394  cmp     rcx, [rbx+18h]
0x180026398  jnb     short loc_1800263A0
0x18002639a  cmp     [rbx+18h], r14
0x18002639e  jmp     short loc_1800263FA
0x1800263a0  mov     rcx, rbx; Src
0x1800263a3  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x1800263a8  mov     rcx, rdi
0x1800263ab  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x1800263b0  mov     ecx, eax
0x1800263b2  cmp     eax, 36h ; '6'
0x1800263b5  jg      short loc_1800263D9
0x1800263b7  jz      short loc_1800263E8
0x1800263b9  sub     ecx, 30h ; '0'
0x1800263bc  jz      short loc_1800263E8
0x1800263be  sub     ecx, 1
0x1800263c1  jz      short loc_1800263E8
0x1800263c3  sub     ecx, 1
0x1800263c6  jz      short loc_1800263E8
0x1800263c8  sub     ecx, 1
0x1800263cb  jz      short loc_1800263E8
0x1800263cd  sub     ecx, 1
0x1800263d0  jz      short loc_1800263E8
0x1800263d2  cmp     ecx, 1
0x1800263d5  jnz     short loc_180026429
0x1800263d7  jmp     short loc_1800263E8
0x1800263d9  sub     ecx, 37h ; '7'
0x1800263dc  jz      short loc_1800263E8
0x1800263de  sub     ecx, 1
0x1800263e1  jz      short loc_1800263E8
0x1800263e3  sub     ecx, 1
0x1800263e6  jnz     short loc_180026417
0x1800263e8  mov     r9b, [rdi+14h]
0x1800263ec  mov     rcx, [rdi+60h]
0x1800263f0  cmp     rcx, [rdi+68h]
0x1800263f4  jnb     short loc_1800263A0
0x1800263f6  cmp     [rdi+68h], r14
0x1800263fa  lea     rax, [rcx+1]
0x1800263fe  mov     [rbx+10h], rax
0x180026402  jbe     short loc_180026409
0x180026404  mov     rax, [rbx]
0x180026407  jmp     short loc_18002640C
0x180026409  mov     rax, rbx
0x18002640c  mov     [rcx+rax], r9b
0x180026410  mov     [rcx+rax+1], bpl
0x180026415  jmp     short loc_1800263A8
0x180026417  sub     ecx, 0Ch
0x18002641a  jz      loc_1800262EB
0x180026420  cmp     ecx, 20h ; ' '
0x180026423  jz      loc_1800262EB
0x180026429  mov     esi, 7
0x18002642e  mov     byte ptr [rdi+18h], 1
0x180026432  dec     qword ptr [rdi+20h]
0x180026436  mov     rax, [rdi+28h]
0x18002643a  test    rax, rax
0x18002643d  jnz     loc_1800265D9
0x180026443  mov     rax, [rdi+30h]
0x180026447  test    rax, rax
0x18002644a  jz      loc_1800265E0
0x180026450  dec     rax
0x180026453  mov     [rdi+30h], rax
0x180026457  jmp     loc_1800265E0
0x18002645c  mov     rax, rbx
0x18002645f  mov     [rcx+rax+1], bpl
0x180026464  mov     [rcx+rax], r9b
0x180026468  jmp     short loc_180026472
0x18002646a  mov     rcx, rbx; Src
  ... truncated ...
```
