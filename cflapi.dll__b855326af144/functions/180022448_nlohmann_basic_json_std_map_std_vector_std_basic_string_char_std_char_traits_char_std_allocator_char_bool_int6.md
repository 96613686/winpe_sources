# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::at(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x180022448`
- end: `0x180022564`
- name: `?at@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV12@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18001cb44`
- `0x180028cc4`

## callees

- `0x180002490`
- `0x180002f04`
- `0x180013130`
- `0x180015408`
- `0x180019fb8`
- `0x180022448`
- `0x180022be8`
- `0x180027b28`
- `0x18002dff0`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800224e7`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x1800224e7`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::at(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdx
  size_t v4; // r14
  size_t v5; // rsi
  size_t v6; // r8
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _BYTE v14[56]; // [rsp+28h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+60h] [rbp-98h] BYREF
  _BYTE v16[16]; // [rsp+98h] [rbp-60h] BYREF
  __int64 v17; // [rsp+A8h] [rbp-50h]
  _BYTE v18[32]; // [rsp+B8h] [rbp-40h] BYREF

  v2 = a2;
  if ( *(_BYTE *)a1 != 1 )
  {
    v8 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::type_name(a1);
    v9 = std::string::string(v18, v8);
    v10 = std::operator+<char>(v16, "cannot use at() with ", v9);
    nlohmann::detail::type_error::create((__int64)pExceptionObject, 0x130u, v10);
    throw (nlohmann::detail::type_error *)pExceptionObject;
  }
  std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>>,0>>::_Find_lower_bound<std::string>(
    *(_QWORD *)(a1 + 8),
    v16,
    a2);
  if ( !*(_BYTE *)(v17 + 25) )
  {
    v3 = (_QWORD *)(v17 + 32);
    v4 = *(_QWORD *)(v17 + 48);
    if ( *(_QWORD *)(v17 + 56) > 0xFu )
      v3 = (_QWORD *)*v3;
    v5 = v2[2];
    if ( v2[3] > 0xFu )
      v2 = (_QWORD *)*v2;
    v6 = *(_QWORD *)(v17 + 48);
    if ( v4 >= v5 )
      v6 = v5;
    v7 = memcmp_0(v2, v3, v6);
    if ( v7 )
    {
      if ( v7 >= 0 )
        return;
    }
    else if ( v5 >= v4 )
    {
      return;
    }
  }
  try
  {
    std::_Xout_of_range("invalid map<K, T> key");
  }
  catch ( std::out_of_range )
  {
    v11 = std::operator+<char>(v16, "key '", a2);
    v12 = std::operator+<char>(v18, v11, "' not found");
    nlohmann::detail::out_of_range::create(v14, 403, v12);
    throw (nlohmann::detail::out_of_range *)v14;
  }
}

```

## disassembly

```asm
0x180022448  mov     r11, rsp
0x18002244b  mov     [r11+18h], rbx
0x18002244f  push    rsi
0x180022450  push    rdi
0x180022451  push    r14
0x180022453  sub     rsp, 0E0h
0x18002245a  mov     rax, cs:__security_cookie
0x180022461  xor     rax, rsp
0x180022464  mov     [rsp+0F8h+var_20], rax
0x18002246c  mov     rbx, rdx
0x18002246f  mov     [rsp+0F8h+var_D8], rdx
0x180022474  cmp     byte ptr [rcx], 1
0x180022477  jnz     loc_180022512
0x18002247d  mov     r8, rdx
0x180022480  lea     rdx, [r11-60h]
0x180022484  mov     rcx, [rcx+8]
0x180022488  call    ??$_Find_lower_bound@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@PEAX@std@@@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>,std::less<void>,std::allocator<std::pair<std::string const,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>>,0>>::_Find_lower_bound<std::string>(std::string const &)
0x18002248d  mov     rdi, [rsp+0F8h+var_50]
0x180022495  cmp     byte ptr [rdi+19h], 0
0x180022499  jnz     short loc_1800224E0
0x18002249b  lea     rdx, [rdi+20h]
0x18002249f  mov     r14, [rdx+10h]
0x1800224a3  cmp     qword ptr [rdx+18h], 0Fh
0x1800224a8  jbe     short loc_1800224AD
0x1800224aa  mov     rdx, [rdx]; Buf2
0x1800224ad  mov     rsi, [rbx+10h]
0x1800224b1  cmp     qword ptr [rbx+18h], 0Fh
0x1800224b6  jbe     short loc_1800224BB
0x1800224b8  mov     rbx, [rbx]
0x1800224bb  mov     r8, r14
0x1800224be  cmp     r14, rsi
0x1800224c1  cmovnb  r8, rsi; Size
0x1800224c5  mov     rcx, rbx; Buf1
0x1800224c8  call    memcmp_0
0x1800224cd  test    eax, eax
0x1800224cf  jnz     short loc_1800224D8
0x1800224d1  cmp     rsi, r14
0x1800224d4  jnb     short loc_1800224DA
0x1800224d6  jmp     short loc_1800224E0
0x1800224d8  js      short loc_1800224E0
0x1800224da  lea     rax, [rdi+40h]
0x1800224de  jmp     short loc_1800224EE
0x1800224e0  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x1800224e7  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x1800224ed  nop
0x1800224ee  mov     rcx, [rsp+0F8h+var_20]
0x1800224f6  xor     rcx, rsp; StackCookie
0x1800224f9  call    __security_check_cookie
0x1800224fe  mov     rbx, [rsp+0F8h+arg_10]
0x180022506  add     rsp, 0E0h
0x18002250d  pop     r14
0x18002250f  pop     rdi
0x180022510  pop     rsi
0x180022511  retn
0x180022512  call    ?type_name@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBAPEBDXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::type_name(void)
0x180022517  mov     rdx, rax
0x18002251a  lea     rcx, [rsp+0F8h+var_40]
0x180022522  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180022527  nop
0x180022528  mov     r8, rax
0x18002252b  lea     rdx, aCannotUseAtWit; "cannot use at() with "
0x180022532  lea     rcx, [rsp+0F8h+var_60]
0x18002253a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x18002253f  nop
0x180022540  mov     r8, rax
0x180022543  mov     edx, 130h
0x180022548  lea     rcx, [rsp+0F8h+pExceptionObject]
0x18002254d  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180022552  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180022559  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x18002255e  call    _CxxThrowException_0
```
