# nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::token_type,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180024524`
- end: `0x1800247a7`
- name: `?exception_message@?$parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4token_type@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@23@AEBV45@@Z`
- size: `643`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180017b94`
- `0x180018df4`
- `0x180025448`

## callees

- `0x180002490`
- `0x180008a68`
- `0x18000fc54`
- `0x180012ddc`
- `0x180013070`
- `0x180013130`
- `0x180015b04`
- `0x180019fb8`
- `0x18001a0d0`
- `0x18001b7f4`
- `0x180024524`
- `0x180024a70`
- `0x180027a4c`

## string_xrefs

- `0x180024682`: `; last read: '`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
_QWORD *__fastcall nlohmann::detail::parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::exception_message(
        __int64 a1,
        _QWORD *a2,
        unsigned int a3,
        _QWORD *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  char *v13; // rdx
  __int64 token_string; // rbx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  _BYTE *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  _BYTE v27[32]; // [rsp+50h] [rbp-79h] BYREF
  _BYTE v28[32]; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v29[32]; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v30[32]; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v31[32]; // [rsp+D0h] [rbp+7h] BYREF

  std::string::string(a2, "syntax error ");
  v10 = a4[2];
  if ( v10 )
  {
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFFLL - v10) < 0xE )
      std::_Xlen_string();
    if ( a4[3] > 0xFu )
      a4 = (_QWORD *)*a4;
    std::string::string(v29, v8, v9, "while parsing ", 14, a4, v10);
    v11 = std::operator+<char>(v30, v29, " ");
    std::string::operator+=(a2, v11);
    std::string::~string(v30);
    std::string::~string(v29);
  }
  v12 = a2[2];
  if ( (unsigned __int64)(a2[3] - v12) < 2 )
  {
    std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(a2, 2u);
  }
  else
  {
    a2[2] = v12 + 2;
    if ( a2[3] <= 0xFu )
      v13 = (char *)a2;
    else
      v13 = (char *)*a2;
    strcpy(&v13[v12], "- ");
  }
  if ( *(_DWORD *)(a1 + 64) == 14 )
  {
    token_string = nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(
                     a1 + 72,
                     v28);
    v15 = std::string::string(v27, *(_QWORD *)(a1 + 184));
    v16 = std::operator+<char>(v31, v15, "; last read: '");
    v17 = std::operator+<char>(v29, v16, token_string);
    v18 = std::operator+<char>(v30, v17, "'");
    std::string::operator+=(a2, v18);
    std::string::~string(v30);
    std::string::~string(v29);
    std::string::~string(v31);
    std::string::~string(v27);
    v19 = v28;
  }
  else
  {
    v20 = ((__int64 (*)(void))nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::token_type_name)();
    v21 = std::string::string(v27, v20);
    v22 = std::operator+<char>(v28, "unexpected ", v21);
    std::string::operator+=(a2, v22);
    std::string::~string(v28);
    v19 = v27;
  }
  std::string::~string(v19);
  if ( a3 )
  {
    v23 = nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::token_type_name(a3);
    v24 = std::string::string(v27, v23);
    v25 = std::operator+<char>(v28, "; expected ", v24);
    std::string::operator+=(a2, v25);
    std::string::~string(v28);
    std::string::~string(v27);
  }
  return a2;
}

```

## disassembly

```asm
0x180024524  push    rbp
0x180024526  push    rbx
0x180024527  push    rsi
0x180024528  push    rdi
0x180024529  push    r14
0x18002452b  lea     rbp, [rsp-37h]
0x180024530  sub     rsp, 100h
0x180024537  mov     rax, cs:__security_cookie
0x18002453e  xor     rax, rsp
0x180024541  mov     [rbp+57h+var_30], rax
0x180024545  mov     rbx, r9
0x180024548  mov     esi, r8d
0x18002454b  mov     rdi, rdx
0x18002454e  mov     r14, rcx
0x180024551  mov     [rsp+120h+var_D8], rdx
0x180024556  mov     [rsp+120h+var_E0], 0
0x18002455e  lea     rdx, aSyntaxError; "syntax error "
0x180024565  mov     rcx, rdi
0x180024568  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18002456d  mov     [rsp+120h+var_E0], 1
0x180024575  mov     rcx, [rbx+10h]
0x180024579  test    rcx, rcx
0x18002457c  jz      loc_180024602
0x180024582  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002458c  sub     rax, rcx
0x18002458f  cmp     rax, 0Eh
0x180024593  jb      loc_1800247A1
0x180024599  cmp     qword ptr [rbx+18h], 0Fh
0x18002459e  jbe     short loc_1800245A3
0x1800245a0  mov     rbx, [rbx]
0x1800245a3  mov     [rsp+120h+var_F0], rcx
0x1800245a8  mov     [rsp+120h+var_F8], rbx
0x1800245ad  mov     [rsp+120h+Size], 0Eh
0x1800245b6  lea     r9, aWhileParsing; "while parsing "
0x1800245bd  lea     rcx, [rbp+57h+var_90]
0x1800245c1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBD_K23@Z; std::string::string(std::_String_constructor_concat_tag,std::string const &,char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1800245c6  mov     [rsp+120h+var_E0], 3
0x1800245ce  lea     r8, asc_1800348A8; " "
0x1800245d5  lea     rdx, [rbp+57h+var_90]
0x1800245d9  lea     rcx, [rbp+57h+var_70]
0x1800245dd  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800245e2  nop
0x1800245e3  mov     rdx, rax
0x1800245e6  mov     rcx, rdi
0x1800245e9  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x1800245ee  nop
0x1800245ef  lea     rcx, [rbp+57h+var_70]
0x1800245f3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800245f8  nop
0x1800245f9  lea     rcx, [rbp+57h+var_90]
0x1800245fd  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024602  mov     rcx, [rdi+10h]
0x180024606  mov     rax, [rdi+18h]
0x18002460a  sub     rax, rcx
0x18002460d  mov     edx, 2
0x180024612  cmp     rax, rdx
0x180024615  jb      short loc_180024640
0x180024617  lea     rax, [rcx+2]
0x18002461b  mov     [rdi+10h], rax
0x18002461f  cmp     qword ptr [rdi+18h], 0Fh
0x180024624  jbe     short loc_18002462B
0x180024626  mov     rdx, [rdi]
0x180024629  jmp     short loc_18002462E
0x18002462b  mov     rdx, rdi
0x18002462e  movzx   eax, word ptr cs:asc_180034890; "- "
0x180024635  mov     [rcx+rdx], ax
0x180024639  mov     byte ptr [rcx+rdx+2], 0
0x18002463e  jmp     short loc_180024654
0x180024640  mov     [rsp+120h+Size], rdx; Size
0x180024645  lea     r9, asc_180034890; "- "
0x18002464c  mov     rcx, rdi; Src
0x18002464f  call    ??$_Reallocate_grow_by@V_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_6e107f859707de1a71dcca60860853b1_@@PEBD_K@Z; std::string::_Reallocate_grow_by<_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64>(unsigned __int64,_lambda_6e107f859707de1a71dcca60860853b1_,char const *,unsigned __int64)
0x180024654  mov     ecx, [r14+40h]
0x180024658  cmp     ecx, 0Eh
0x18002465b  jnz     loc_1800246F4
0x180024661  lea     rcx, [r14+48h]
0x180024665  lea     rdx, [rbp+57h+var_B0]
0x180024669  call    ?get_token_string@?$lexer@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@V?$iterator_input_adapter@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@D@std@@@std@@@std@@@detail@2@@detail@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::detail::lexer<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,nlohmann::detail::iterator_input_adapter<std::_String_const_iterator<std::_String_val<std::_Simple_types<char>>>>>::get_token_string(void)
0x18002466e  mov     rbx, rax
0x180024671  mov     rdx, [r14+0B8h]
0x180024678  lea     rcx, [rbp+57h+var_D0]
0x18002467c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180024681  nop
0x180024682  lea     r8, aLastRead; "; last read: '"
0x180024689  mov     rdx, rax
0x18002468c  lea     rcx, [rbp+57h+var_50]
0x180024690  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x180024695  nop
0x180024696  mov     r8, rbx
0x180024699  mov     rdx, rax
0x18002469c  lea     rcx, [rbp+57h+var_90]
0x1800246a0  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@0@Z; std::operator+<char>(std::string &&,std::string &&)
0x1800246a5  nop
0x1800246a6  lea     r8, asc_180034B54; "'"
0x1800246ad  mov     rdx, rax
0x1800246b0  lea     rcx, [rbp+57h+var_70]
0x1800246b4  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1800246b9  nop
0x1800246ba  mov     rdx, rax
0x1800246bd  mov     rcx, rdi
0x1800246c0  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x1800246c5  nop
0x1800246c6  lea     rcx, [rbp+57h+var_70]
0x1800246ca  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800246cf  nop
0x1800246d0  lea     rcx, [rbp+57h+var_90]
0x1800246d4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800246d9  nop
0x1800246da  lea     rcx, [rbp+57h+var_50]
0x1800246de  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800246e3  nop
0x1800246e4  lea     rcx, [rbp+57h+var_D0]
0x1800246e8  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800246ed  nop
0x1800246ee  lea     rcx, [rbp+57h+var_B0]
0x1800246f2  jmp     short loc_180024734
0x1800246f4  call    ?token_type_name@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@SAPEBDW4token_type@123@@Z; nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type_name(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type)
0x1800246f9  mov     rdx, rax
0x1800246fc  lea     rcx, [rbp+57h+var_D0]
0x180024700  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180024705  nop
0x180024706  mov     r8, rax
0x180024709  lea     rdx, aUnexpected; "unexpected "
0x180024710  lea     rcx, [rbp+57h+var_B0]
0x180024714  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180024719  nop
0x18002471a  mov     rdx, rax
0x18002471d  mov     rcx, rdi
0x180024720  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x180024725  nop
0x180024726  lea     rcx, [rbp+57h+var_B0]
0x18002472a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002472f  nop
0x180024730  lea     rcx, [rbp+57h+var_D0]
0x180024734  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024739  test    esi, esi
0x18002473b  jz      short loc_180024784
0x18002473d  mov     ecx, esi
0x18002473f  call    ?token_type_name@?$lexer_base@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@SAPEBDW4token_type@123@@Z; nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type_name(nlohmann::detail::lexer_base<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::token_type)
0x180024744  mov     rdx, rax
0x180024747  lea     rcx, [rbp+57h+var_D0]
0x18002474b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180024750  nop
0x180024751  mov     r8, rax
0x180024754  lea     rdx, aExpected; "; expected "
0x18002475b  lea     rcx, [rbp+57h+var_B0]
0x18002475f  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180024764  nop
0x180024765  mov     rdx, rax
0x180024768  mov     rcx, rdi
0x18002476b  call    ??Y?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator+=(std::string const &)
0x180024770  nop
0x180024771  lea     rcx, [rbp+57h+var_B0]
0x180024775  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002477a  nop
0x18002477b  lea     rcx, [rbp+57h+var_D0]
0x18002477f  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180024784  mov     rax, rdi
0x180024787  mov     rcx, [rbp+57h+var_30]
0x18002478b  xor     rcx, rsp; StackCookie
0x18002478e  call    __security_check_cookie
0x180024793  add     rsp, 100h
0x18002479a  pop     r14
0x18002479c  pop     rdi
0x18002479d  pop     rsi
0x18002479e  pop     rbx
0x18002479f  pop     rbp
0x1800247a0  retn
0x1800247a1  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
