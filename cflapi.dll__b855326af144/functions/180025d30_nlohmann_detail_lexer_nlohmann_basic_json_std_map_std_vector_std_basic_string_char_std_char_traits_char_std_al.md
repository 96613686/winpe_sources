# nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(void)

- ea: `0x180025d30`
- end: `0x180026057`
- name: `?scan@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ`
- size: `807`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800178d0`
- `0x180017b94`
- `0x180018df4`
- `0x180025448`

## callees

- `0x180024948`
- `0x180025d30`
- `0x180026060`
- `0x1800266b0`

## string_xrefs

- `0x180025df4`: `invalid comment; expecting '/' or '*' after '/'`
- `0x180025ef6`: `invalid comment; missing closing '*/'`

## pseudocode

```c
__int64 __fastcall nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan(
        __int64 a1)
{
  unsigned int v2; // edi
  const char *v3; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  int v6; // ecx
  int v7; // eax
  const char *v8; // rcx
  int v9; // ecx
  unsigned int v10; // eax
  bool v11; // zf
  __int64 v13; // rax
  __int64 v14; // rax
  int v15; // eax
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  int v23; // ecx
  __int64 v24; // rsi
  __int64 v25; // rsi
  __int64 v26; // rsi
  _DWORD v27[6]; // [rsp+20h] [rbp-18h] BYREF

  v2 = 1;
  if ( !*(_QWORD *)(a1 + 32) )
  {
    if ( (unsigned int)((__int64 (*)(void))nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get)() == 239 )
    {
      if ( (unsigned int)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) != 187
        || (unsigned int)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) != 191 )
      {
        v3 = "invalid BOM; must be 0xEF 0xBB 0xBF if given";
LABEL_39:
        *(_QWORD *)(a1 + 112) = v3;
        return 14;
      }
    }
    else
    {
      --*(_QWORD *)(a1 + 32);
      v4 = *(_QWORD *)(a1 + 40);
      *(_BYTE *)(a1 + 24) = 1;
      if ( v4 )
      {
        *(_QWORD *)(a1 + 40) = v4 - 1;
      }
      else
      {
        v5 = *(_QWORD *)(a1 + 48);
        if ( v5 )
          *(_QWORD *)(a1 + 48) = v5 - 1;
      }
      if ( *(_DWORD *)(a1 + 20) != -1 )
        --*(_QWORD *)(a1 + 64);
    }
  }
  do
  {
    do
    {
      nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
      v6 = *(_DWORD *)(a1 + 20);
    }
    while ( v6 == 32 );
  }
  while ( v6 == 9 || v6 == 10 || v6 == 13 );
  while ( 1 )
  {
    if ( !*(_BYTE *)(a1 + 16) || v6 != 47 )
    {
      if ( v6 <= 54 )
      {
        if ( v6 != 54 )
        {
          if ( v6 > 48 )
          {
            v16 = v6 - 49;
            if ( !v16 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
            v17 = v16 - 1;
            if ( !v17 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
            v18 = v17 - 1;
            if ( !v18 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
            v19 = v18 - 1;
            if ( !v19 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
            v11 = v19 == 1;
          }
          else
          {
            if ( v6 == 48 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
            if ( (unsigned int)(v6 + 1) <= 1 )
              return 15;
            if ( v6 == 34 )
              return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_string(a1);
            if ( v6 == 44 )
              return 13;
            v11 = v6 == 45;
          }
          if ( !v11 )
            goto LABEL_38;
        }
        return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
      }
      if ( v6 > 93 )
      {
        switch ( v6 )
        {
          case 'f':
            qmemcpy(v27, "false", 5);
            v26 = 1;
            while ( (unsigned __int8)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) == *((_BYTE *)v27 + v26) )
            {
              if ( (unsigned __int64)++v26 >= 5 )
                return 2;
            }
            break;
          case 'n':
            v27[0] = 1819047278;
            v25 = 1;
            while ( (unsigned __int8)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) == *((_BYTE *)v27 + v25) )
            {
              if ( (unsigned __int64)++v25 >= 4 )
                return 3;
            }
            break;
          case 't':
            v27[0] = 1702195828;
            v24 = 1;
            while ( (unsigned __int8)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) == *((_BYTE *)v27 + v24) )
            {
              if ( (unsigned __int64)++v24 >= 4 )
                return v2;
            }
            v2 = 14;
            *(_QWORD *)(a1 + 112) = "invalid literal";
            return v2;
          case '{':
            return 9;
          case '}':
            return 11;
        }
      }
      else
      {
        if ( v6 == 93 )
          return 10;
        v20 = v6 - 55;
        if ( !v20 )
          return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
        v21 = v20 - 1;
        if ( !v21 )
          return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
        v22 = v21 - 1;
        if ( !v22 )
          return nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(a1);
        v23 = v22 - 1;
        if ( !v23 )
          return 12;
        if ( v23 == 33 )
          return 8;
      }
LABEL_38:
      v3 = "invalid literal";
      goto LABEL_39;
    }
    v7 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
    if ( v7 == 42 )
      break;
    if ( v7 != 47 )
    {
      v8 = "invalid comment; expecting '/' or '*' after '/'";
      goto LABEL_52;
    }
    while ( 1 )
    {
      v10 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
      if ( v10 == -1 )
        break;
      if ( v10 <= 0xD )
      {
        v9 = 9217;
        if ( _bittest(&v9, v10) )
          break;
      }
    }
    do
    {
      do
      {
LABEL_24:
        nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
        v6 = *(_DWORD *)(a1 + 20);
      }
      while ( v6 == 32 );
    }
    while ( v6 == 9 || v6 == 10 || v6 == 13 );
  }
  while ( 1 )
  {
    v15 = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1);
    if ( v15 == -1 || !v15 )
      break;
    if ( v15 == 42 )
    {
      if ( (unsigned int)nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(a1) == 47 )
        goto LABEL_24;
      --*(_QWORD *)(a1 + 32);
      v13 = *(_QWORD *)(a1 + 40);
      *(_BYTE *)(a1 + 24) = 1;
      if ( v13 )
      {
        *(_QWORD *)(a1 + 40) = v13 - 1;
      }
      else
      {
        v14 = *(_QWORD *)(a1 + 48);
        if ( v14 )
          *(_QWORD *)(a1 + 48) = v14 - 1;
      }
      if ( *(_DWORD *)(a1 + 20) != -1 )
        --*(_QWORD *)(a1 + 64);
    }
  }
  v8 = "invalid comment; missing closing '*/'";
LABEL_52:
  *(_QWORD *)(a1 + 112) = v8;
  return 14;
}

```

## disassembly

```asm
0x180025d30  push    rbp
0x180025d32  push    rbx
0x180025d33  push    rsi
0x180025d34  push    rdi
0x180025d35  mov     rbp, rsp
0x180025d38  sub     rsp, 38h
0x180025d3c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025d40  mov     rbx, rcx
0x180025d43  cmp     qword ptr [rcx+20h], 0
0x180025d48  mov     edi, 1
0x180025d4d  jnz     short loc_180025DB8
0x180025d4f  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025d54  cmp     eax, 0EFh
0x180025d59  jnz     short loc_180025D85
0x180025d5b  mov     rcx, rbx
0x180025d5e  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025d63  cmp     eax, 0BBh
0x180025d68  jnz     short loc_180025D79
0x180025d6a  mov     rcx, rbx
0x180025d6d  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025d72  cmp     eax, 0BFh
0x180025d77  jz      short loc_180025DB8
0x180025d79  lea     rax, aInvalidBomMust; "invalid BOM; must be 0xEF 0xBB 0xBF if "...
0x180025d80  jmp     loc_180025E8B
0x180025d85  add     [rbx+20h], rsi
0x180025d89  mov     rax, [rbx+28h]
0x180025d8d  mov     [rbx+18h], dil
0x180025d91  test    rax, rax
0x180025d94  jnz     short loc_180025DA8
0x180025d96  mov     rax, [rbx+30h]
0x180025d9a  test    rax, rax
0x180025d9d  jz      short loc_180025DAF
0x180025d9f  dec     rax
0x180025da2  mov     [rbx+30h], rax
0x180025da6  jmp     short loc_180025DAF
0x180025da8  dec     rax
0x180025dab  mov     [rbx+28h], rax
0x180025daf  cmp     [rbx+14h], esi
0x180025db2  jz      short loc_180025DB8
0x180025db4  add     [rbx+40h], rsi
0x180025db8  mov     rcx, rbx
0x180025dbb  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025dc0  mov     ecx, [rbx+14h]
0x180025dc3  cmp     ecx, 20h ; ' '
0x180025dc6  jz      short loc_180025DB8
0x180025dc8  cmp     ecx, 9
0x180025dcb  jz      short loc_180025DB8
0x180025dcd  cmp     ecx, 0Ah
0x180025dd0  jz      short loc_180025DB8
0x180025dd2  cmp     ecx, 0Dh
0x180025dd5  jz      short loc_180025DB8
0x180025dd7  jmp     short loc_180025E3A
0x180025dd9  cmp     ecx, 2Fh ; '/'
0x180025ddc  jnz     short loc_180025E40
0x180025dde  mov     rcx, rbx
0x180025de1  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025de6  cmp     eax, 2Ah ; '*'
0x180025de9  jz      loc_180025EEA
0x180025def  cmp     eax, 2Fh ; '/'
0x180025df2  jz      short loc_180025E0F
0x180025df4  lea     rcx, aInvalidComment_0; "invalid comment; expecting '/' or '*' a"...
0x180025dfb  jmp     loc_180025EFD
0x180025e00  cmp     eax, 0Dh
0x180025e03  ja      short loc_180025E0F
0x180025e05  mov     ecx, 2401h
0x180025e0a  bt      ecx, eax
0x180025e0d  jb      short loc_180025E1B
0x180025e0f  mov     rcx, rbx
0x180025e12  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025e17  cmp     eax, esi
0x180025e19  jnz     short loc_180025E00
0x180025e1b  mov     rcx, rbx
0x180025e1e  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025e23  mov     ecx, [rbx+14h]
0x180025e26  cmp     ecx, 20h ; ' '
0x180025e29  jz      short loc_180025E1B
0x180025e2b  cmp     ecx, 9
0x180025e2e  jz      short loc_180025E1B
0x180025e30  cmp     ecx, 0Ah
0x180025e33  jz      short loc_180025E1B
0x180025e35  cmp     ecx, 0Dh
0x180025e38  jz      short loc_180025E1B
0x180025e3a  cmp     byte ptr [rbx+10h], 0
0x180025e3e  jnz     short loc_180025DD9
0x180025e40  cmp     ecx, 36h ; '6'
0x180025e43  jg      loc_180025F3E
0x180025e49  jz      loc_180025F71
0x180025e4f  cmp     ecx, 30h ; '0'
0x180025e52  jg      loc_180025F26
0x180025e58  jz      loc_180025F71
0x180025e5e  lea     eax, [rcx+1]
0x180025e61  cmp     eax, edi
0x180025e63  jbe     loc_180025F1C
0x180025e69  cmp     ecx, 22h ; '"'
0x180025e6c  jz      loc_180025F0F
0x180025e72  cmp     ecx, 2Ch ; ','
0x180025e75  jz      loc_180025F08
0x180025e7b  cmp     ecx, 2Dh ; '-'
0x180025e7e  jz      loc_180025F71
0x180025e84  lea     rax, aInvalidLiteral; "invalid literal"
0x180025e8b  mov     [rbx+70h], rax
0x180025e8f  mov     eax, 0Eh
0x180025e94  add     rsp, 38h
0x180025e98  pop     rdi
0x180025e99  pop     rsi
0x180025e9a  pop     rbx
0x180025e9b  pop     rbp
0x180025e9c  retn
0x180025e9d  test    eax, eax
0x180025e9f  jz      short loc_180025EF6
0x180025ea1  cmp     eax, 2Ah ; '*'
0x180025ea4  jnz     short loc_180025EEA
0x180025ea6  mov     rcx, rbx
0x180025ea9  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025eae  cmp     eax, 2Fh ; '/'
0x180025eb1  jz      loc_180025E1B
0x180025eb7  add     [rbx+20h], rsi
0x180025ebb  mov     rax, [rbx+28h]
0x180025ebf  mov     [rbx+18h], dil
0x180025ec3  test    rax, rax
0x180025ec6  jnz     short loc_180025EDA
0x180025ec8  mov     rax, [rbx+30h]
0x180025ecc  test    rax, rax
0x180025ecf  jz      short loc_180025EE1
0x180025ed1  dec     rax
0x180025ed4  mov     [rbx+30h], rax
0x180025ed8  jmp     short loc_180025EE1
0x180025eda  dec     rax
0x180025edd  mov     [rbx+28h], rax
0x180025ee1  cmp     [rbx+14h], esi
0x180025ee4  jz      short loc_180025EEA
0x180025ee6  add     [rbx+40h], rsi
0x180025eea  mov     rcx, rbx
0x180025eed  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025ef2  cmp     eax, esi
0x180025ef4  jnz     short loc_180025E9D
0x180025ef6  lea     rcx, aInvalidComment; "invalid comment; missing closing '*/'"
0x180025efd  mov     eax, 70h ; 'p'
0x180025f02  mov     [rax+rbx], rcx
0x180025f06  jmp     short loc_180025E8F
0x180025f08  mov     eax, 0Dh
0x180025f0d  jmp     short loc_180025E94
0x180025f0f  mov     rcx, rbx
0x180025f12  call    ?scan_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_string(void)
0x180025f17  jmp     loc_180025E94
0x180025f1c  mov     eax, 0Fh
0x180025f21  jmp     loc_180025E94
0x180025f26  sub     ecx, 31h ; '1'
0x180025f29  jz      short loc_180025F71
0x180025f2b  sub     ecx, edi
0x180025f2d  jz      short loc_180025F71
0x180025f2f  sub     ecx, edi
0x180025f31  jz      short loc_180025F71
0x180025f33  sub     ecx, edi
0x180025f35  jz      short loc_180025F71
0x180025f37  cmp     ecx, edi
0x180025f39  jmp     loc_180025E7E
0x180025f3e  cmp     ecx, 5Dh ; ']'
0x180025f41  jg      short loc_180025F88
0x180025f43  jz      short loc_180025F7E
0x180025f45  sub     ecx, 37h ; '7'
0x180025f48  jz      short loc_180025F71
0x180025f4a  sub     ecx, edi
0x180025f4c  jz      short loc_180025F71
0x180025f4e  sub     ecx, edi
0x180025f50  jz      short loc_180025F71
0x180025f52  sub     ecx, edi
0x180025f54  jz      short loc_180025F67
0x180025f56  cmp     ecx, 21h ; '!'
0x180025f59  jnz     loc_180025E84
0x180025f5f  lea     eax, [rcx-19h]
0x180025f62  jmp     loc_180025E94
0x180025f67  mov     eax, 0Ch
0x180025f6c  jmp     loc_180025E94
0x180025f71  mov     rcx, rbx
0x180025f74  call    ?scan_number@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AW4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::scan_number(void)
0x180025f79  jmp     loc_180025E94
0x180025f7e  mov     eax, 0Ah
0x180025f83  jmp     loc_180025E94
0x180025f88  cmp     ecx, 66h ; 'f'
0x180025f8b  jz      loc_180026024
0x180025f91  cmp     ecx, 6Eh ; 'n'
0x180025f94  jz      short loc_180025FF5
0x180025f96  cmp     ecx, 74h ; 't'
0x180025f99  jz      short loc_180025FBB
0x180025f9b  cmp     ecx, 7Bh ; '{'
0x180025f9e  jz      short loc_180025FB1
0x180025fa0  cmp     ecx, 7Dh ; '}'
0x180025fa3  jnz     loc_180025E84
0x180025fa9  lea     eax, [rcx-72h]
0x180025fac  jmp     loc_180025E94
0x180025fb1  mov     eax, 9
0x180025fb6  jmp     loc_180025E94
0x180025fbb  mov     [rbp+var_18], 65757274h
0x180025fc2  mov     rsi, rdi
0x180025fc5  mov     rcx, rbx
0x180025fc8  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180025fcd  cmp     al, byte ptr [rbp+rsi+var_18]
0x180025fd1  jnz     short loc_180025FDE
0x180025fd3  add     rsi, rdi
0x180025fd6  cmp     rsi, 4
0x180025fda  jb      short loc_180025FC5
0x180025fdc  jmp     short loc_180025FEE
0x180025fde  lea     rax, aInvalidLiteral; "invalid literal"
0x180025fe5  mov     edi, 0Eh
0x180025fea  mov     [rbx+70h], rax
0x180025fee  mov     eax, edi
0x180025ff0  jmp     loc_180025E94
0x180025ff5  mov     [rbp+var_18], 6C6C756Eh
0x180025ffc  mov     rsi, rdi
0x180025fff  mov     rcx, rbx
0x180026002  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x180026007  cmp     al, byte ptr [rbp+rsi+var_18]
0x18002600b  jnz     loc_180025E84
0x180026011  add     rsi, rdi
0x180026014  cmp     rsi, 4
0x180026018  jb      short loc_180025FFF
0x18002601a  mov     eax, 3
0x18002601f  jmp     loc_180025E94
0x180026024  mov     [rbp+var_18], 736C6166h
0x18002602b  mov     rsi, rdi
0x18002602e  mov     [rbp+var_14], 65h ; 'e'
0x180026032  mov     rcx, rbx
0x180026035  call    ?get@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAAHXZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get(void)
0x18002603a  cmp     al, byte ptr [rbp+rsi+var_18]
0x18002603e  jnz     loc_180025E84
0x180026044  add     rsi, rdi
0x180026047  cmp     rsi, 5
0x18002604b  jb      short loc_180026032
0x18002604d  mov     eax, 2
0x180026052  jmp     loc_180025E94
```
