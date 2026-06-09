# nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_string(void)

- ea: `0x1800266b0`
- end: `0x18002798e`
- name: `?scan_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ`
- size: `4830`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config`

## callers

- `0x180025d30`

## callees

- `0x180002490`
- `0x180002860`
- `0x18000289c`
- `0x18000fc2c`
- `0x18000fc54`
- `0x180014b74`
- `0x1800159b0`
- `0x180024948`
- `0x1800249cc`
- `0x18002537c`
- `0x1800266b0`
- `0x18002dffc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_string(
        __int64 a1)
{
  __int64 v1; // rbx
  char *v2; // r14
  _BYTE *v3; // rax
  __int64 v4; // rcx
  _BYTE *v5; // rdx
  char v6; // al
  __m128i si128; // xmm6
  __m128i v8; // xmm7
  __m128i v9; // xmm8
  __m128i v10; // xmm9
  __m128i v11; // xmm10
  int v12; // eax
  int v13; // ecx
  int v14; // eax
  int codepoint; // eax
  int v16; // r15d
  int v17; // eax
  size_t v18; // rsi
  unsigned __int64 v19; // r13
  _BYTE *v20; // rax
  unsigned __int64 v21; // rbx
  size_t v22; // rcx
  __int64 v23; // rcx
  _QWORD *v24; // rdi
  void *v25; // rax
  _BYTE *v26; // rbx
  unsigned __int64 v27; // rdx
  _BYTE *v28; // rcx
  unsigned __int64 v29; // rcx
  char v30; // r9
  char v31; // r9
  _BYTE *v32; // rax
  _BYTE *v33; // rax
  _BYTE *v34; // rax
  char v35; // r15
  unsigned __int64 v36; // rcx
  _BYTE *v37; // rax
  size_t v38; // rsi
  unsigned __int64 v39; // r15
  char *v40; // rax
  unsigned __int64 v41; // rdi
  size_t v42; // rcx
  __int64 v43; // rcx
  char *v44; // rbx
  void *v45; // rax
  _BYTE *v46; // rdi
  size_t v47; // rsi
  char *v48; // rax
  unsigned __int64 v49; // rdi
  size_t v50; // rcx
  __int64 v51; // rcx
  void *v52; // rax
  size_t v53; // rsi
  char *v54; // rax
  unsigned __int64 v55; // rdi
  size_t v56; // rcx
  __int64 v57; // rcx
  void *v58; // rax
  size_t v59; // rsi
  char *v60; // rax
  unsigned __int64 v61; // rdi
  size_t v62; // rcx
  __int64 v63; // rcx
  void *v64; // rax
  size_t v65; // rsi
  char *v66; // rax
  unsigned __int64 v67; // rdi
  size_t v68; // rcx
  __int64 v69; // rcx
  void *v70; // rax
  size_t v71; // rsi
  char *v72; // rax
  unsigned __int64 v73; // rdi
  size_t v74; // rcx
  __int64 v75; // rcx
  void *v76; // rax
  size_t v77; // rsi
  char *v78; // rax
  unsigned __int64 v79; // rdi
  size_t v80; // rcx
  __int64 v81; // rcx
  void *v82; // rax
  unsigned __int64 v83; // rdx
  _BYTE *v84; // rcx
  size_t v85; // rsi
  char *v86; // rax
  unsigned __int64 v87; // rdi
  size_t v88; // rcx
  __int64 v89; // rcx
  void *v90; // rax
  bool v91; // zf
  int v92; // ecx
  bool v93; // zf
  int v94; // ecx
  bool v95; // zf
  int v96; // ecx
  int v97; // ecx
  char v98; // r9
  unsigned __int64 v99; // rcx
  _BYTE *v100; // rax
  bool v101; // zf
  int v102; // ecx
  bool v103; // zf
  int v104; // ecx
  int v105; // ecx
  _QWORD *v106; // rdx
  bool v107; // zf
  int v108; // ecx
  int v109; // ecx
  const char *v110; // rax
  int v113; // [rsp+30h] [rbp-D8h] BYREF
  _DWORD v114[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v115; // [rsp+40h] [rbp-C8h] BYREF
  _QWORD v116[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v117[2]; // [rsp+58h] [rbp-B0h] BYREF
  _QWORD v118[2]; // [rsp+68h] [rbp-A0h] BYREF
  _QWORD v119[2]; // [rsp+78h] [rbp-90h] BYREF
  _QWORD v120[2]; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v121[2]; // [rsp+98h] [rbp-70h] BYREF
  _QWORD v122[2]; // [rsp+A8h] [rbp-60h] BYREF
  __m128i v123; // [rsp+B8h] [rbp-50h] BYREF
  int v124; // [rsp+C8h] [rbp-40h] BYREF
  int v125; // [rsp+CCh] [rbp-3Ch]
  _QWORD v126[12]; // [rsp+D0h] [rbp-38h] BYREF

  v1 = a1;
  v2 = (char *)(a1 + 80);
  *(_QWORD *)(a1 + 96) = 0;
  if ( *(_QWORD *)(a1 + 104) <= 0xFu )
    v3 = (_BYTE *)(a1 + 80);
  else
    v3 = *(_BYTE **)v2;
  *v3 = 0;
  v4 = a1 + 56;
  v5 = *(_BYTE **)v4;
  if ( *(_QWORD *)v4 == *(_QWORD *)(v4 + 8) )
    v5 = *(_BYTE **)(v4 + 8);
  else
    *(_QWORD *)(v4 + 8) = v5;
  v6 = *(_BYTE *)(v1 + 20);
  LOBYTE(v113) = v6;
  if ( v5 == *(_BYTE **)(v4 + 16) )
  {
    std::vector<char>::_Emplace_reallocate<char>(v4, v5, &v113);
  }
  else
  {
    *v5 = v6;
    ++*(_QWORD *)(v4 + 8);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v8 = _mm_load_si128((const __m128i *)&_xmm);
  v9 = _mm_load_si128((const __m128i *)&_xmm);
  v10 = _mm_load_si128((const __m128i *)&_xmm);
  v11 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    while ( 1 )
    {
      v12 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(v1);
      if ( v12 <= 89 )
      {
        if ( v12 != 89 )
        {
          switch ( v12 )
          {
            case -1:
              v110 = "invalid string: missing closing quote";
              goto LABEL_383;
            case 0:
              v110 = "invalid string: control character U+0000 (NUL) must be escaped to \\u0000";
              goto LABEL_383;
            case 1:
              v110 = "invalid string: control character U+0001 (SOH) must be escaped to \\u0001";
              goto LABEL_383;
            case 2:
              v110 = "invalid string: control character U+0002 (STX) must be escaped to \\u0002";
              goto LABEL_383;
            case 3:
              v110 = "invalid string: control character U+0003 (ETX) must be escaped to \\u0003";
              goto LABEL_383;
            case 4:
              v110 = "invalid string: control character U+0004 (EOT) must be escaped to \\u0004";
              goto LABEL_383;
            case 5:
              v110 = "invalid string: control character U+0005 (ENQ) must be escaped to \\u0005";
              goto LABEL_383;
            case 6:
              v110 = "invalid string: control character U+0006 (ACK) must be escaped to \\u0006";
              goto LABEL_383;
            case 7:
              v110 = "invalid string: control character U+0007 (BEL) must be escaped to \\u0007";
              goto LABEL_383;
            case 8:
              v110 = "invalid string: control character U+0008 (BS) must be escaped to \\u0008 or \\b";
              goto LABEL_383;
            case 9:
              v110 = "invalid string: control character U+0009 (HT) must be escaped to \\u0009 or \\t";
              goto LABEL_383;
            case 10:
              v110 = "invalid string: control character U+000A (LF) must be escaped to \\u000A or \\n";
              goto LABEL_383;
            case 11:
              v110 = "invalid string: control character U+000B (VT) must be escaped to \\u000B";
              goto LABEL_383;
            case 12:
              v110 = "invalid string: control character U+000C (FF) must be escaped to \\u000C or \\f";
              goto LABEL_383;
            case 13:
              v110 = "invalid string: control character U+000D (CR) must be escaped to \\u000D or \\r";
              goto LABEL_383;
            case 14:
              v110 = "invalid string: control character U+000E (SO) must be escaped to \\u000E";
              goto LABEL_383;
            case 15:
              v110 = "invalid string: control character U+000F (SI) must be escaped to \\u000F";
              goto LABEL_383;
            case 16:
              v110 = "invalid string: control character U+0010 (DLE) must be escaped to \\u0010";
              goto LABEL_383;
            case 17:
              v110 = "invalid string: control character U+0011 (DC1) must be escaped to \\u0011";
              goto LABEL_383;
            case 18:
              v110 = "invalid string: control character U+0012 (DC2) must be escaped to \\u0012";
              goto LABEL_383;
            case 19:
              v110 = "invalid string: control character U+0013 (DC3) must be escaped to \\u0013";
              goto LABEL_383;
            case 20:
              v110 = "invalid string: control character U+0014 (DC4) must be escaped to \\u0014";
              goto LABEL_383;
            case 21:
              v110 = "invalid string: control character U+0015 (NAK) must be escaped to \\u0015";
              goto LABEL_383;
            case 22:
              v110 = "invalid string: control character U+0016 (SYN) must be escaped to \\u0016";
              goto LABEL_383;
            case 23:
              v110 = "invalid string: control character U+0017 (ETB) must be escaped to \\u0017";
              goto LABEL_383;
            case 24:
              v110 = "invalid string: control character U+0018 (CAN) must be escaped to \\u0018";
              goto LABEL_383;
            case 25:
              v110 = "invalid string: control character U+0019 (EM) must be escaped to \\u0019";
              goto LABEL_383;
            case 26:
              v110 = "invalid string: control character U+001A (SUB) must be escaped to \\u001A";
              goto LABEL_383;
            case 27:
              v110 = "invalid string: control character U+001B (ESC) must be escaped to \\u001B";
              goto LABEL_383;
            case 28:
              v110 = "invalid string: control character U+001C (FS) must be escaped to \\u001C";
              goto LABEL_383;
            case 29:
              v110 = "invalid string: control character U+001D (GS) must be escaped to \\u001D";
              goto LABEL_383;
            case 30:
              v110 = "invalid string: control character U+001E (RS) must be escaped to \\u001E";
              goto LABEL_383;
            case 31:
              v110 = "invalid string: control character U+001F (US) must be escaped to \\u001F";
              goto LABEL_383;
            case 32:
            case 33:
            case 35:
            case 36:
            case 37:
            case 38:
            case 39:
            case 40:
            case 41:
            case 42:
            case 43:
            case 44:
            case 45:
            case 46:
            case 47:
            case 48:
            case 49:
            case 50:
            case 51:
            case 52:
            case 53:
            case 54:
            case 55:
            case 56:
            case 57:
            case 58:
            case 59:
            case 60:
            case 61:
            case 62:
            case 63:
            case 64:
            case 65:
            case 66:
            case 67:
            case 68:
            case 69:
            case 70:
            case 71:
            case 72:
            case 73:
            case 74:
            case 75:
            case 76:
            case 77:
            case 78:
            case 79:
            case 80:
            case 81:
            case 82:
            case 83:
            case 84:
            case 85:
            case 86:
            case 87:
            case 88:
              goto LABEL_292;
            case 34:
              return 4;
            default:
              goto LABEL_382;
          }
        }
        goto LABEL_292;
      }
      if ( v12 > 200 )
        break;
      if ( v12 == 200 )
        goto LABEL_315;
      if ( v12 > 112 )
      {
        if ( v12 > 194 )
        {
          v102 = v12 - 195;
          v101 = v12 == 195;
          goto LABEL_298;
        }
        if ( v12 == 194 )
          goto LABEL_315;
        if ( v12 > 120 )
        {
          v96 = v12 - 121;
          v95 = v12 == 121;
        }
        else
        {
          if ( v12 == 120 )
            goto LABEL_292;
          v96 = v12 - 113;
          v95 = v12 == 113;
        }
        if ( !v95 )
        {
          v97 = v96 - 1;
          if ( v97 )
          {
            v92 = v97 - 1;
            v91 = v92 == 0;
            goto LABEL_287;
          }
        }
LABEL_292:
        v98 = *(_BYTE *)(v1 + 20);
        v99 = *((_QWORD *)v2 + 2);
        if ( v99 >= *((_QWORD *)v2 + 3) )
          goto LABEL_70;
        *((_QWORD *)v2 + 2) = v99 + 1;
        if ( *((_QWORD *)v2 + 3) <= 0xFu )
          v100 = v2;
        else
          v100 = *(_BYTE **)v2;
        v100[v99] = v98;
        v100[v99 + 1] = 0;
      }
      else
      {
        if ( v12 == 112 )
          goto LABEL_292;
        if ( v12 > 101 )
        {
          if ( v12 > 107 )
          {
            v94 = v12 - 108;
            v93 = v12 == 108;
          }
          else
          {
            if ( v12 == 107 )
              goto LABEL_292;
            v92 = v12 - 102;
            v91 = v12 == 102;
LABEL_287:
            if ( v91 )
              goto LABEL_292;
            v94 = v92 - 1;
            v93 = v94 == 0;
          }
          if ( v93 )
            goto LABEL_292;
          v13 = v94 - 1;
          if ( !v13 )
            goto LABEL_292;
LABEL_291:
          if ( (unsigned int)(v13 - 1) > 1 )
            goto LABEL_382;
          goto LABEL_292;
        }
        if ( v12 == 101 )
          goto LABEL_292;
        if ( v12 > 95 )
        {
          v92 = v12 - 96;
          v91 = v12 == 96;
          goto LABEL_287;
        }
        if ( v12 == 95 || v12 == 90 || v12 == 91 )
          goto LABEL_292;
        v13 = v12 - 92;
        if ( v12 != 92 )
          goto LABEL_291;
        v14 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(v1);
        switch ( v14 )
        {
          case '"':
            v85 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v85 >= v39 )
            {
              if ( v85 == 0x7FFFFFFFFFFFFFFFLL )
LABEL_386:
                std::_Xlen_string();
              v87 = (v85 + 1) | 0xF;
              if ( v87 > 0x7FFFFFFFFFFFFFFFLL || (v89 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v87 = 0x7FFFFFFFFFFFFFFFLL;
                v88 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v87 < v89 + v39 )
                  v87 = v89 + v39;
                if ( v87 == -1 )
                {
                  v44 = 0;
LABEL_268:
                  *((_QWORD *)v2 + 2) = v85 + 1;
                  *((_QWORD *)v2 + 3) = v87;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v85);
                    *(_WORD *)&v44[v85] = 34;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v85);
                  *(_WORD *)&v44[v85] = 34;
                  goto LABEL_271;
                }
                if ( v87 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v87 + 1);
                  goto LABEL_268;
                }
                v88 = v87 + 40;
                if ( v87 + 40 < v87 + 1 )
LABEL_387:
                  __scrt_throw_std_bad_array_new_length();
              }
              v90 = operator new(v88);
              if ( !v90 )
LABEL_381:
                __fastfail(5u);
              v44 = (char *)(((unsigned __int64)v90 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v90;
              goto LABEL_268;
            }
            *((_QWORD *)v2 + 2) = v85 + 1;
            if ( v39 <= 0xF )
              v86 = v2;
            else
              v86 = *(char **)v2;
            *(_WORD *)&v86[v85] = 34;
            break;
          case '/':
            v77 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v77 >= v39 )
            {
              if ( v77 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v79 = (v77 + 1) | 0xF;
              if ( v79 > 0x7FFFFFFFFFFFFFFFLL || (v81 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v79 = 0x7FFFFFFFFFFFFFFFLL;
                v80 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v79 < v81 + v39 )
                  v79 = v81 + v39;
                if ( v79 == -1 )
                {
                  v44 = 0;
LABEL_242:
                  *((_QWORD *)v2 + 2) = v77 + 1;
                  *((_QWORD *)v2 + 3) = v79;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v77);
                    *(_WORD *)&v44[v77] = 47;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v77);
                  *(_WORD *)&v44[v77] = 47;
                  goto LABEL_271;
                }
                if ( v79 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v79 + 1);
                  goto LABEL_242;
                }
                v80 = v79 + 40;
                if ( v79 + 40 < v79 + 1 )
                  goto LABEL_387;
              }
              v82 = operator new(v80);
              if ( !v82 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v82 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v82;
              goto LABEL_242;
            }
            *((_QWORD *)v2 + 2) = v77 + 1;
            if ( v39 <= 0xF )
              v78 = v2;
            else
              v78 = *(char **)v2;
            *(_WORD *)&v78[v77] = 47;
            break;
          case '\\':
            v71 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v71 >= v39 )
            {
              if ( v71 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v73 = (v71 + 1) | 0xF;
              if ( v73 > 0x7FFFFFFFFFFFFFFFLL || (v75 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v73 = 0x7FFFFFFFFFFFFFFFLL;
                v74 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v73 < v75 + v39 )
                  v73 = v75 + v39;
                if ( v73 == -1 )
                {
                  v44 = 0;
LABEL_221:
                  *((_QWORD *)v2 + 2) = v71 + 1;
                  *((_QWORD *)v2 + 3) = v73;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v71);
                    *(_WORD *)&v44[v71] = 92;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v71);
                  *(_WORD *)&v44[v71] = 92;
                  goto LABEL_271;
                }
                if ( v73 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v73 + 1);
                  goto LABEL_221;
                }
                v74 = v73 + 40;
                if ( v73 + 40 < v73 + 1 )
                  goto LABEL_387;
              }
              v76 = operator new(v74);
              if ( !v76 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v76 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v76;
              goto LABEL_221;
            }
            *((_QWORD *)v2 + 2) = v71 + 1;
            if ( v39 <= 0xF )
              v72 = v2;
            else
              v72 = *(char **)v2;
            *(_WORD *)&v72[v71] = 92;
            break;
          case 'b':
            v65 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v65 >= v39 )
            {
              if ( v65 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v67 = (v65 + 1) | 0xF;
              if ( v67 > 0x7FFFFFFFFFFFFFFFLL || (v69 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v67 = 0x7FFFFFFFFFFFFFFFLL;
                v68 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v67 < v69 + v39 )
                  v67 = v69 + v39;
                if ( v67 == -1 )
                {
                  v44 = 0;
LABEL_200:
                  *((_QWORD *)v2 + 2) = v65 + 1;
                  *((_QWORD *)v2 + 3) = v67;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v65);
                    *(_WORD *)&v44[v65] = 8;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v65);
                  *(_WORD *)&v44[v65] = 8;
                  goto LABEL_271;
                }
                if ( v67 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v67 + 1);
                  goto LABEL_200;
                }
                v68 = v67 + 40;
                if ( v67 + 40 < v67 + 1 )
                  goto LABEL_387;
              }
              v70 = operator new(v68);
              if ( !v70 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v70 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v70;
              goto LABEL_200;
            }
            *((_QWORD *)v2 + 2) = v65 + 1;
            if ( v39 <= 0xF )
              v66 = v2;
            else
              v66 = *(char **)v2;
            *(_WORD *)&v66[v65] = 8;
            break;
          case 'f':
            v59 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v59 >= v39 )
            {
              if ( v59 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v61 = (v59 + 1) | 0xF;
              if ( v61 > 0x7FFFFFFFFFFFFFFFLL || (v63 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v61 = 0x7FFFFFFFFFFFFFFFLL;
                v62 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v61 < v63 + v39 )
                  v61 = v63 + v39;
                if ( v61 == -1 )
                {
                  v44 = 0;
LABEL_179:
                  *((_QWORD *)v2 + 2) = v59 + 1;
                  *((_QWORD *)v2 + 3) = v61;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v59);
                    *(_WORD *)&v44[v59] = 12;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v59);
                  *(_WORD *)&v44[v59] = 12;
                  goto LABEL_271;
                }
                if ( v61 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v61 + 1);
                  goto LABEL_179;
                }
                v62 = v61 + 40;
                if ( v61 + 40 < v61 + 1 )
                  goto LABEL_387;
              }
              v64 = operator new(v62);
              if ( !v64 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v64 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v64;
              goto LABEL_179;
            }
            *((_QWORD *)v2 + 2) = v59 + 1;
            if ( v39 <= 0xF )
              v60 = v2;
            else
              v60 = *(char **)v2;
            *(_WORD *)&v60[v59] = 12;
            break;
          case 'n':
            v53 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v53 >= v39 )
            {
              if ( v53 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v55 = (v53 + 1) | 0xF;
              if ( v55 > 0x7FFFFFFFFFFFFFFFLL || (v57 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v55 = 0x7FFFFFFFFFFFFFFFLL;
                v56 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v55 < v57 + v39 )
                  v55 = v57 + v39;
                if ( v55 == -1 )
                {
                  v44 = 0;
LABEL_158:
                  *((_QWORD *)v2 + 2) = v53 + 1;
                  *((_QWORD *)v2 + 3) = v55;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v53);
                    *(_WORD *)&v44[v53] = 10;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v53);
                  *(_WORD *)&v44[v53] = 10;
                  goto LABEL_271;
                }
                if ( v55 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v55 + 1);
                  goto LABEL_158;
                }
                v56 = v55 + 40;
                if ( v55 + 40 < v55 + 1 )
                  goto LABEL_387;
              }
              v58 = operator new(v56);
              if ( !v58 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v58 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v58;
              goto LABEL_158;
            }
            *((_QWORD *)v2 + 2) = v53 + 1;
            if ( v39 <= 0xF )
              v54 = v2;
            else
              v54 = *(char **)v2;
            *(_WORD *)&v54[v53] = 10;
            break;
          case 'r':
            v47 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v47 >= v39 )
            {
              if ( v47 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v49 = (v47 + 1) | 0xF;
              if ( v49 > 0x7FFFFFFFFFFFFFFFLL || (v51 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v49 = 0x7FFFFFFFFFFFFFFFLL;
                v50 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v49 < v51 + v39 )
                  v49 = v51 + v39;
                if ( v49 == -1 )
                {
                  v44 = 0;
LABEL_137:
                  *((_QWORD *)v2 + 2) = v47 + 1;
                  *((_QWORD *)v2 + 3) = v49;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v47);
                    *(_WORD *)&v44[v47] = 13;
                    goto LABEL_244;
                  }
                  memcpy_0(v44, v2, v47);
                  *(_WORD *)&v44[v47] = 13;
LABEL_271:
                  *(_QWORD *)v2 = v44;
                  goto LABEL_272;
                }
                if ( v49 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v49 + 1);
                  goto LABEL_137;
                }
                v50 = v49 + 40;
                if ( v49 + 40 < v49 + 1 )
                  goto LABEL_387;
              }
              v52 = operator new(v50);
              if ( !v52 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v52 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v52;
              goto LABEL_137;
            }
            *((_QWORD *)v2 + 2) = v47 + 1;
            if ( v39 <= 0xF )
              v48 = v2;
            else
              v48 = *(char **)v2;
            *(_WORD *)&v48[v47] = 13;
            break;
          case 't':
            v38 = *((_QWORD *)v2 + 2);
            v39 = *((_QWORD *)v2 + 3);
            if ( v38 >= v39 )
            {
              if ( v38 == 0x7FFFFFFFFFFFFFFFLL )
                goto LABEL_386;
              v41 = (v38 + 1) | 0xF;
              if ( v41 > 0x7FFFFFFFFFFFFFFFLL || (v43 = v39 >> 1, v39 > 0x7FFFFFFFFFFFFFFFLL - (v39 >> 1)) )
              {
                v41 = 0x7FFFFFFFFFFFFFFFLL;
                v42 = 0x8000000000000027uLL;
              }
              else
              {
                if ( v41 < v43 + v39 )
                  v41 = v43 + v39;
                if ( v41 == -1 )
                {
                  v44 = 0;
LABEL_116:
                  *((_QWORD *)v2 + 2) = v38 + 1;
                  *((_QWORD *)v2 + 3) = v41;
                  if ( v39 > 0xF )
                  {
                    v46 = *(_BYTE **)v2;
                    memcpy_0(v44, *(const void **)v2, v38);
                    *(_WORD *)&v44[v38] = 9;
LABEL_244:
                    v83 = v39 + 1;
                    if ( v39 + 1 < 0x1000 )
                    {
                      v84 = v46;
                    }
                    else
                    {
                      v84 = (_BYTE *)*((_QWORD *)v46 - 1);
                      if ( (unsigned __int64)(v46 - v84 - 8) > 0x1F )
                        goto LABEL_381;
                      v83 = v39 + 40;
                    }
                    operator delete(v84, v83);
                    goto LABEL_271;
                  }
                  memcpy_0(v44, v2, v38);
                  *(_WORD *)&v44[v38] = 9;
                  goto LABEL_271;
                }
                if ( v41 + 1 < 0x1000 )
                {
                  v44 = (char *)operator new(v41 + 1);
                  goto LABEL_116;
                }
                v42 = v41 + 40;
                if ( v41 + 40 < v41 + 1 )
                  goto LABEL_387;
              }
              v45 = operator new(v42);
              if ( !v45 )
                goto LABEL_381;
              v44 = (char *)(((unsigned __int64)v45 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
              *((_QWORD *)v44 - 1) = v45;
              goto LABEL_116;
            }
            *((_QWORD *)v2 + 2) = v38 + 1;
            if ( v39 <= 0xF )
              v40 = v2;
            else
              v40 = *(char **)v2;
            *(_WORD *)&v40[v38] = 9;
            break;
          case 'u':
            codepoint = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_codepoint(v1);
            v16 = codepoint;
            if ( codepoint == -1 )
              goto LABEL_379;
            if ( (unsigned int)(codepoint - 55296) > 0x3FF )
            {
              if ( (unsigned int)(codepoint - 56320) <= 0x3FF )
              {
                v110 = "invalid string: surrogate U+DC00..U+DFFF must follow U+D800..U+DBFF";
                goto LABEL_383;
              }
            }
            else
            {
              if ( (unsigned int)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(v1) != 92
                || (unsigned int)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(v1) != 117 )
              {
LABEL_377:
                v110 = "invalid string: surrogate U+D800..U+DBFF must be followed by U+DC00..U+DFFF";
                goto LABEL_383;
              }
              v17 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_codepoint(v1);
              if ( v17 == -1 )
              {
LABEL_379:
                v110 = "invalid string: '\\u' must be followed by 4 hex digits";
                goto LABEL_383;
              }
              if ( (unsigned int)(v17 - 56320) > 0x3FF )
                goto LABEL_377;
              v16 = v17 + (v16 << 10) - 56613888;
            }
            if ( v16 >= 128 )
            {
              v29 = *((_QWORD *)v2 + 2);
              if ( v16 > 2047 )
              {
                if ( v16 > 0xFFFF )
                {
                  if ( v29 >= *((_QWORD *)v2 + 3) )
                  {
                    std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                  }
                  else
                  {
                    *((_QWORD *)v2 + 2) = v29 + 1;
                    if ( *((_QWORD *)v2 + 3) <= 0xFu )
                      v32 = v2;
                    else
                      v32 = *(_BYTE **)v2;
                    v32[v29] = ((unsigned int)v16 >> 18) | 0xF0;
                    v32[v29 + 1] = 0;
                  }
                  v31 = ((unsigned int)v16 >> 12) & 0x3F | 0x80;
                  v29 = *((_QWORD *)v2 + 2);
                }
                else
                {
                  v31 = ((unsigned int)v16 >> 12) | 0xE0;
                }
                if ( v29 >= *((_QWORD *)v2 + 3) )
                {
                  std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
                }
                else
                {
                  *((_QWORD *)v2 + 2) = v29 + 1;
                  if ( *((_QWORD *)v2 + 3) <= 0xFu )
                    v33 = v2;
                  else
                    v33 = *(_BYTE **)v2;
                  v33[v29] = v31;
                  v33[v29 + 1] = 0;
                }
                v30 = ((unsigned int)v16 >> 6) & 0x3F | 0x80;
                v29 = *((_QWORD *)v2 + 2);
              }
              else
              {
                v30 = ((unsigned int)v16 >> 6) | 0xC0;
              }
              if ( v29 >= *((_QWORD *)v2 + 3) )
              {
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
              }
              else
              {
                *((_QWORD *)v2 + 2) = v29 + 1;
                if ( *((_QWORD *)v2 + 3) <= 0xFu )
                  v34 = v2;
                else
                  v34 = *(_BYTE **)v2;
                v34[v29] = v30;
                v34[v29 + 1] = 0;
              }
              v35 = v16 & 0x3F | 0x80;
              v36 = *((_QWORD *)v2 + 2);
              if ( v36 >= *((_QWORD *)v2 + 3) )
              {
LABEL_70:
                std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(v2);
              }
              else
              {
                *((_QWORD *)v2 + 2) = v36 + 1;
                if ( *((_QWORD *)v2 + 3) <= 0xFu )
                  v37 = v2;
                else
                  v37 = *(_BYTE **)v2;
                v37[v36] = v35;
                v37[v36 + 1] = 0;
              }
            }
            else
            {
              v18 = *((_QWORD *)v2 + 2);
              v19 = *((_QWORD *)v2 + 3);
              if ( v18 >= v19 )
              {
                if ( v18 == 0x7FFFFFFFFFFFFFFFLL )
                  goto LABEL_386;
                v21 = (v18 + 1) | 0xF;
                if ( v21 > 0x7FFFFFFFFFFFFFFFLL || (v23 = v19 >> 1, v19 > 0x7FFFFFFFFFFFFFFFLL - (v19 >> 1)) )
                {
                  v21 = 0x7FFFFFFFFFFFFFFFLL;
                  v22 = 0x8000000000000027uLL;
                }
                else
                {
                  if ( v21 < v23 + v19 )
                    v21 = v23 + v19;
                  if ( v21 == -1 )
                  {
                    v24 = 0;
                    goto LABEL_61;
                  }
                  if ( v21 + 1 < 0x1000 )
                  {
                    v24 = operator new(v21 + 1);
                    goto LABEL_61;
                  }
                  v22 = v21 + 40;
                  if ( v21 + 40 < v21 + 1 )
                    goto LABEL_387;
                }
                v25 = operator new(v22);
                if ( !v25 )
                  goto LABEL_381;
                v24 = (_QWORD *)(((unsigned __int64)v25 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
                *(v24 - 1) = v25;
LABEL_61:
                *((_QWORD *)v2 + 2) = v18 + 1;
                *((_QWORD *)v2 + 3) = v21;
                if ( v19 <= 0xF )
                {
                  memcpy_0(v24, v2, v18);
                  *((_BYTE *)v24 + v18) = v16;
                  *((_BYTE *)v24 + v18 + 1) = 0;
                  *(_QWORD *)v2 = v24;
                }
                else
                {
                  v26 = *(_BYTE **)v2;
                  memcpy_0(v24, *(const void **)v2, v18);
                  *((_BYTE *)v24 + v18) = v16;
                  *((_BYTE *)v24 + v18 + 1) = 0;
                  v27 = v19 + 1;
                  if ( v19 + 1 < 0x1000 )
                  {
                    v28 = v26;
                  }
                  else
                  {
                    v28 = (_BYTE *)*((_QWORD *)v26 - 1);
                    if ( (unsigned __int64)(v26 - v28 - 8) > 0x1F )
                      goto LABEL_381;
                    v27 = v19 + 40;
                  }
                  operator delete(v28, v27);
                  *(_QWORD *)v2 = v24;
                }
LABEL_272:
                v1 = a1;
              }
              else
              {
                *((_QWORD *)v2 + 2) = v18 + 1;
                if ( v19 <= 0xF )
                  v20 = v2;
                else
                  v20 = *(_BYTE **)v2;
                v20[v18] = v16;
                v20[v18 + 1] = 0;
              }
            }
            break;
          default:
            v110 = "invalid string: forbidden character after backslash";
            goto LABEL_383;
        }
      }
    }
    if ( v12 <= 223 )
      break;
    if ( v12 <= 234 )
    {
      if ( v12 != 234 )
      {
        if ( v12 > 229 )
        {
          v108 = v12 - 230;
          v107 = v12 == 230;
        }
        else
        {
          if ( v12 == 229 )
            goto LABEL_327;
          if ( v12 == 224 )
          {
            v123 = v11;
            v117[0] = &v123;
            v117[1] = &v124;
            v106 = v117;
            goto LABEL_316;
          }
          v108 = v12 - 225;
          v107 = v12 == 225;
        }
        if ( !v107 )
        {
          v109 = v108 - 1;
          if ( v109 )
            goto LABEL_326;
        }
      }
LABEL_327:
      v123 = si128;
      v119[0] = &v123;
      v119[1] = &v124;
      v106 = v119;
      goto LABEL_316;
    }
    if ( v12 <= 240 )
    {
      if ( v12 == 240 )
      {
        v123 = v9;
        v124 = 128;
        v125 = 191;
        v120[0] = &v123;
        v120[1] = v126;
        v106 = v120;
        goto LABEL_316;
      }
      if ( v12 != 235 && v12 != 236 )
      {
        v109 = v12 - 237;
        if ( v12 == 237 )
        {
          v123 = v10;
          v118[0] = &v123;
          v118[1] = &v124;
          v106 = v118;
          goto LABEL_316;
        }
LABEL_326:
        if ( (unsigned int)(v109 - 1) > 1 )
          goto LABEL_382;
      }
      goto LABEL_327;
    }
    if ( v12 == 241 || v12 == 242 || v12 == 243 )
    {
      v123 = si128;
      v124 = 128;
      v125 = 191;
      v122[0] = &v123;
      v122[1] = v126;
      v106 = v122;
    }
    else
    {
      if ( v12 != 244 )
        goto LABEL_382;
      v123 = v8;
      v124 = 128;
      v125 = 191;
      v121[0] = &v123;
      v121[1] = v126;
      v106 = v121;
    }
LABEL_316:
    if ( !(unsigned __int8)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::next_byte_in_range(
                             v1,
                             v106) )
      return 14;
  }
  if ( v12 == 223 )
    goto LABEL_315;
  if ( v12 > 212 )
  {
    if ( v12 > 218 )
    {
      v104 = v12 - 219;
      v103 = v12 == 219;
      goto LABEL_312;
    }
    if ( v12 != 218 )
    {
      v102 = v12 - 213;
      v101 = v12 == 213;
      goto LABEL_298;
    }
LABEL_315:
    v114[0] = 128;
    v114[1] = 191;
    v116[0] = v114;
    v116[1] = &v115;
    v106 = v116;
    goto LABEL_316;
  }
  if ( v12 == 212 )
    goto LABEL_315;
  if ( v12 > 206 )
  {
    v102 = v12 - 207;
    v101 = v12 == 207;
  }
  else
  {
    if ( v12 == 206 )
      goto LABEL_315;
    v102 = v12 - 201;
    v101 = v12 == 201;
  }
LABEL_298:
  if ( v101 )
    goto LABEL_315;
  v104 = v102 - 1;
  v103 = v104 == 0;
LABEL_312:
  if ( v103 )
    goto LABEL_315;
  v105 = v104 - 1;
  if ( !v105 || (unsigned int)(v105 - 1) <= 1 )
    goto LABEL_315;
LABEL_382:
  v110 = "invalid string: ill-formed UTF-8 byte";
LABEL_383:
  *(_QWORD *)(v1 + 112) = v110;
  return 14;
}

```

## disassembly

```asm
0x1800266b0  mov     rax, rsp
0x1800266b3  push    rbp
0x1800266b4  push    rbx
0x1800266b5  push    rsi
0x1800266b6  push    rdi
0x1800266b7  push    r12
0x1800266b9  push    r13
0x1800266bb  push    r14
0x1800266bd  push    r15
0x1800266bf  lea     rbp, [rax-68h]
0x1800266c3  sub     rsp, 128h
0x1800266ca  movaps  xmmword ptr [rax-58h], xmm6
0x1800266ce  movaps  xmmword ptr [rax-68h], xmm7
0x1800266d2  movaps  xmmword ptr [rax-78h], xmm8
0x1800266d7  movaps  xmmword ptr [rax-88h], xmm9
0x1800266df  movaps  xmmword ptr [rax-98h], xmm10
0x1800266e7  mov     rax, cs:__security_cookie
0x1800266ee  xor     rax, rsp
0x1800266f1  mov     [rbp+60h+var_98], rax
0x1800266f5  mov     rbx, rcx
0x1800266f8  mov     qword ptr [rsp+160h+var_140], rcx
0x1800266fd  lea     r14, [rcx+50h]
0x180026701  xor     r13d, r13d
0x180026704  mov     [r14+10h], r13
0x180026708  cmp     qword ptr [r14+18h], 0Fh
0x18002670d  jbe     short loc_180026714
0x18002670f  mov     rax, [r14]
0x180026712  jmp     short loc_180026717
0x180026714  mov     rax, r14
0x180026717  mov     [rax], r13b
0x18002671a  add     rcx, 38h ; '8'
0x18002671e  mov     rdx, [rcx]
0x180026721  cmp     rdx, [rcx+8]
0x180026725  jz      short loc_18002672D
0x180026727  mov     [rcx+8], rdx
0x18002672b  jmp     short loc_180026731
0x18002672d  mov     rdx, [rcx+8]
0x180026731  mov     al, [rbx+14h]
0x180026734  mov     byte ptr [rsp+160h+var_138], al
0x180026738  cmp     rdx, [rcx+10h]
0x18002673c  jz      short loc_180026746
0x18002673e  mov     [rdx], al
0x180026740  inc     qword ptr [rcx+8]
0x180026744  jmp     short loc_180026751
0x180026746  lea     r8, [rsp+160h+var_138]
0x18002674b  call    ??$_Emplace_reallocate@D@?$vector@DV?$allocator@D@std@@@std@@AEAAPEADQEAD$$QEAD@Z; std::vector<char>::_Emplace_reallocate<char>(char * const,char &&)
0x180026750  nop
0x180026751  movdqa  xmm6, cs:__xmm@000000bf00000080000000bf00000080
0x180026759  movdqa  xmm7, cs:__xmm@000000bf000000800000008f00000080
0x180026761  movdqa  xmm8, cs:__xmm@000000bf00000080000000bf00000090
0x18002676a  movdqa  xmm9, cs:__xmm@000000bf000000800000009f00000080
0x180026773  movdqa  xmm10, cs:__xmm@000000bf00000080000000bf000000a0
0x18002677c  mov     rdi, 7FFFFFFFFFFFFFFFh
0x180026786  mov     rcx, rbx
0x180026789  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x18002678e  mov     ecx, eax
0x180026790  cmp     eax, 59h ; 'Y'
0x180026793  jg      short loc_1800267C4
0x180026795  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x18002679b  inc     ecx; switch 90 cases
0x18002679d  cmp     ecx, 59h
0x1800267a0  ja      def_1800267C2; jumptable 00000001800267C2 default case
0x1800267a6  movsxd  rax, ecx
0x1800267a9  lea     rdx, __ImageBase
0x1800267b0  movzx   eax, ds:(byte_180027934 - 180000000h)[rdx+rax]
0x1800267b8  mov     ecx, ds:(jpt_1800267C2 - 180000000h)[rdx+rax*4]
0x1800267bf  add     rcx, rdx
0x1800267c2  jmp     rcx; switch jump
0x1800267c4  cmp     ecx, 0C8h
0x1800267ca  jg      loc_1800274B0
0x1800267d0  jz      loc_18002750F
0x1800267d6  cmp     ecx, 70h ; 'p'
0x1800267d9  jg      loc_18002742B
0x1800267df  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x1800267e5  cmp     ecx, 65h ; 'e'
0x1800267e8  jg      loc_18002741A
0x1800267ee  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x1800267f4  cmp     ecx, 5Fh ; '_'
0x1800267f7  jg      loc_180027415
0x1800267fd  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x180026803  sub     ecx, 5Ah ; 'Z'
0x180026806  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x18002680c  sub     ecx, 1
0x18002680f  jz      loc_18002746C; jumptable 00000001800267C2 cases 32,33,35-88
0x180026815  sub     ecx, 1
0x180026818  jnz     loc_18002745E
0x18002681e  mov     rcx, rbx
0x180026821  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180026826  mov     ecx, eax
0x180026828  sub     ecx, 22h ; '"'
0x18002682b  jz      loc_180027303
0x180026831  sub     ecx, 0Dh
0x180026834  jz      loc_1800271C9
0x18002683a  sub     ecx, 2Dh ; '-'
0x18002683d  jz      loc_1800270BF
0x180026843  sub     ecx, 6
0x180026846  jz      loc_180026FB5
0x18002684c  sub     ecx, 4
0x18002684f  jz      loc_180026EAB
0x180026855  sub     ecx, 8
0x180026858  jz      loc_180026DA1
0x18002685e  sub     ecx, 4
0x180026861  jz      loc_180026C97
0x180026867  sub     ecx, 2
0x18002686a  jz      loc_180026B8D
0x180026870  cmp     ecx, 1
0x180026873  jnz     loc_18002783D
0x180026879  mov     rcx, rbx
0x18002687c  call    ?get_codepoint@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_codepoint(void)
0x180026881  mov     r15d, eax
0x180026884  cmp     eax, 0FFFFFFFFh
0x180026887  jz      loc_180027834
0x18002688d  add     eax, 0FFFF2800h
0x180026892  cmp     eax, 3FFh
0x180026897  ja      short loc_1800268EE
0x180026899  mov     rcx, rbx
0x18002689c  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x1800268a1  cmp     eax, 5Ch ; '\'
0x1800268a4  jnz     loc_180027822
0x1800268aa  mov     rcx, rbx
0x1800268ad  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x1800268b2  cmp     eax, 75h ; 'u'
0x1800268b5  jnz     loc_180027822
0x1800268bb  mov     rcx, rbx
0x1800268be  call    ?get_codepoint@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_codepoint(void)
0x1800268c3  mov     ecx, eax
0x1800268c5  cmp     eax, 0FFFFFFFFh
0x1800268c8  jz      loc_180027834
0x1800268ce  add     eax, 0FFFF2400h
0x1800268d3  cmp     eax, 3FFh
0x1800268d8  ja      loc_180027822
0x1800268de  shl     r15d, 0Ah
0x1800268e2  add     r15d, 0FCA02400h
0x1800268e9  add     r15d, ecx
0x1800268ec  jmp     short loc_180026900
0x1800268ee  lea     eax, [r15-0DC00h]
0x1800268f5  cmp     eax, 3FFh
0x1800268fa  jbe     loc_18002782B
0x180026900  cmp     r15d, 80h
0x180026907  jge     loc_180026A54
0x18002690d  mov     rsi, [r14+10h]
0x180026911  mov     r13, [r14+18h]
0x180026915  cmp     rsi, r13
0x180026918  jnb     short loc_180026941
0x18002691a  lea     rax, [rsi+1]
0x18002691e  mov     [r14+10h], rax
0x180026922  cmp     r13, 0Fh
0x180026926  jbe     short loc_18002692D
0x180026928  mov     rax, [r14]
0x18002692b  jmp     short loc_180026930
0x18002692d  mov     rax, r14
0x180026930  mov     [rax+rsi], r15b
0x180026934  xor     r13d, r13d
0x180026937  mov     [rax+rsi+1], r13b
0x18002693c  jmp     loc_180026786
0x180026941  mov     rax, rdi
0x180026944  sub     rax, rsi
0x180026947  cmp     rax, 1
0x18002694b  jb      loc_18002789A
0x180026951  lea     r12, [rsi+1]
0x180026955  mov     rbx, r12
0x180026958  or      rbx, 0Fh
0x18002695c  cmp     rbx, rdi
0x18002695f  jbe     short loc_180026970
0x180026961  mov     rbx, rdi
0x180026964  mov     rcx, 8000000000000027h
0x18002696e  jmp     short loc_1800269AE
0x180026970  mov     rcx, r13
0x180026973  shr     rcx, 1
0x180026976  mov     rax, rdi
0x180026979  sub     rax, rcx
0x18002697c  cmp     r13, rax
0x18002697f  ja      short loc_180026961
0x180026981  lea     rax, [rcx+r13]
0x180026985  cmp     rbx, rax
0x180026988  cmovb   rbx, rax
0x18002698c  lea     rax, [rbx+1]
0x180026990  test    rax, rax
0x180026993  jnz     short loc_180026999
0x180026995  xor     edi, edi
0x180026997  jmp     short loc_1800269D5
0x180026999  cmp     rax, 1000h
0x18002699f  jb      short loc_1800269CA
0x1800269a1  lea     rcx, [rax+27h]; Size
0x1800269a5  cmp     rcx, rax
0x1800269a8  jbe     loc_1800278A0
0x1800269ae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800269b3  test    rax, rax
0x1800269b6  jz      loc_180027846
0x1800269bc  lea     rdi, [rax+27h]
0x1800269c0  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800269c4  mov     [rdi-8], rax
0x1800269c8  jmp     short loc_1800269D5
0x1800269ca  mov     rcx, rax; Size
0x1800269cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800269d2  mov     rdi, rax
0x1800269d5  mov     [r14+10h], r12
0x1800269d9  mov     [r14+18h], rbx
0x1800269dd  mov     r8, rsi; Size
0x1800269e0  mov     rcx, rdi; void *
0x1800269e3  cmp     r13, 0Fh
0x1800269e7  jbe     short loc_180026A38
0x1800269e9  mov     rbx, [r14]
0x1800269ec  mov     rdx, rbx; Src
0x1800269ef  call    memcpy_0
0x1800269f4  mov     [rdi+rsi], r15b
0x1800269f8  mov     byte ptr [rdi+rsi+1], 0
0x1800269fd  lea     rdx, [r13+1]; unsigned __int64
0x180026a01  cmp     rdx, 1000h
0x180026a08  jb      short loc_180026A25
0x180026a0a  mov     rcx, [rbx-8]
0x180026a0e  sub     rbx, rcx
0x180026a11  sub     rbx, 8
0x180026a15  cmp     rbx, 1Fh
0x180026a19  ja      loc_180027846
0x180026a1f  add     rdx, 27h ; '''
0x180026a23  jmp     short loc_180026A28
0x180026a25  mov     rcx, rbx; void *
0x180026a28  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026a2d  mov     [r14], rdi
0x180026a30  xor     r13d, r13d
0x180026a33  jmp     loc_18002740B
0x180026a38  mov     rdx, r14; Src
0x180026a3b  call    memcpy_0
0x180026a40  mov     [rdi+rsi], r15b
0x180026a44  xor     r13d, r13d
0x180026a47  mov     [rdi+rsi+1], r13b
0x180026a4c  mov     [r14], rdi
0x180026a4f  jmp     loc_18002740B
0x180026a54  mov     r9d, r15d
0x180026a57  mov     rcx, [r14+10h]
0x180026a5b  cmp     r15d, 7FFh
0x180026a62  jg      short loc_180026A81
0x180026a64  shr     r9d, 6
0x180026a68  or      r9b, 0C0h
0x180026a6c  jmp     loc_180026B22
0x180026a71  mov     r9b, r15b
0x180026a74  mov     rcx, r14; Src
0x180026a77  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026a7c  jmp     loc_180026786
0x180026a81  cmp     r15d, 0FFFFh
0x180026a88  jg      short loc_180026A94
0x180026a8a  shr     r9d, 0Ch
0x180026a8e  or      r9b, 0E0h
0x180026a92  jmp     short loc_180026ADF
0x180026a94  shr     r9d, 12h
0x180026a98  or      r9b, 0F0h
0x180026a9c  cmp     rcx, [r14+18h]
0x180026aa0  jnb     short loc_180026AC4
0x180026aa2  lea     rax, [rcx+1]
0x180026aa6  mov     [r14+10h], rax
0x180026aaa  cmp     qword ptr [r14+18h], 0Fh
0x180026aaf  jbe     short loc_180026AB6
0x180026ab1  mov     rax, [r14]
0x180026ab4  jmp     short loc_180026AB9
0x180026ab6  mov     rax, r14
0x180026ab9  mov     [rax+rcx], r9b
0x180026abd  mov     [rax+rcx+1], r13b
0x180026ac2  jmp     short loc_180026ACC
0x180026ac4  mov     rcx, r14; Src
0x180026ac7  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026acc  mov     r9d, r15d
0x180026acf  shr     r9d, 0Ch
0x180026ad3  and     r9b, 3Fh
0x180026ad7  or      r9b, 80h
0x180026adb  mov     rcx, [r14+10h]
0x180026adf  cmp     rcx, [r14+18h]
0x180026ae3  jnb     short loc_180026B07
0x180026ae5  lea     rax, [rcx+1]
0x180026ae9  mov     [r14+10h], rax
0x180026aed  cmp     qword ptr [r14+18h], 0Fh
0x180026af2  jbe     short loc_180026AF9
0x180026af4  mov     rax, [r14]
0x180026af7  jmp     short loc_180026AFC
0x180026af9  mov     rax, r14
0x180026afc  mov     [rax+rcx], r9b
0x180026b00  mov     [rax+rcx+1], r13b
0x180026b05  jmp     short loc_180026B0F
0x180026b07  mov     rcx, r14; Src
0x180026b0a  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026b0f  mov     r9d, r15d
0x180026b12  shr     r9d, 6
0x180026b16  and     r9b, 3Fh
0x180026b1a  or      r9b, 80h
0x180026b1e  mov     rcx, [r14+10h]
0x180026b22  cmp     rcx, [r14+18h]
0x180026b26  jnb     short loc_180026B4A
0x180026b28  lea     rax, [rcx+1]
0x180026b2c  mov     [r14+10h], rax
0x180026b30  cmp     qword ptr [r14+18h], 0Fh
0x180026b35  jbe     short loc_180026B3C
0x180026b37  mov     rax, [r14]
0x180026b3a  jmp     short loc_180026B3F
0x180026b3c  mov     rax, r14
0x180026b3f  mov     [rax+rcx], r9b
0x180026b43  mov     [rax+rcx+1], r13b
0x180026b48  jmp     short loc_180026B52
0x180026b4a  mov     rcx, r14; Src
0x180026b4d  call    ??$_Reallocate_grow_by@V_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_319d5e083f45f90dcdce5dce53cbb275_@@D@Z; std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(unsigned __int64,_lambda_319d5e083f45f90dcdce5dce53cbb275_,char)
0x180026b52  and     r15b, 3Fh
  ... truncated ...
```
