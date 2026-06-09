# nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>>::key(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x1800250a0`
- end: `0x1800251c5`
- name: `?key@?$json_sax_dom_callback_parser@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@detail@nlohmann@@QEAA_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180017b94`

## callees

- `0x18000289c`
- `0x180019d08`
- `0x180019eac`
- `0x18001b694`
- `0x180022cf4`
- `0x1800250a0`
- `0x180025a34`
- `0x180030010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002510b`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002510b`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall nlohmann::detail::json_sax_dom_callback_parser<nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::key(
        _QWORD *a1,
        size_t *a2)
{
  __int64 v4; // rcx
  char v5; // bl
  __int64 v6; // rdi
  __int64 v7; // rbx
  char v8; // dl
  __int64 v9; // r8
  unsigned __int8 v11[8]; // [rsp+30h] [rbp-20h] BYREF
  void *v12; // [rsp+38h] [rbp-18h] BYREF
  _QWORD **v13; // [rsp+40h] [rbp-10h] BYREF
  void *v14; // [rsp+48h] [rbp-8h]
  _QWORD *v15; // [rsp+78h] [rbp+28h] BYREF
  int v16; // [rsp+80h] [rbp+30h] BYREF

  v11[0] = 3;
  v13 = &v15;
  v14 = operator new(0x20u);
  std::string::string(v14, a2);
  v12 = v14;
  LOBYTE(v15) = 4;
  v16 = (__int64)(a1[2] - a1[1]) >> 3;
  v4 = a1[21];
  if ( !v4 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  v5 = (*(__int64 (__fastcall **)(__int64, int *, _QWORD **, unsigned __int8 *))(*(_QWORD *)v4 + 16LL))(
         v4,
         &v16,
         &v15,
         v11);
  LOBYTE(v15) = v5;
  std::vector<bool>::push_back(a1 + 8, &v15);
  if ( v5 && *(_QWORD *)(a1[2] - 8LL) )
  {
    v15 = &v13;
    v6 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>(
           (__int64)&v13,
           (__int64)(a1 + 23));
    v7 = std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::operator[](
           *(__int64 **)(*(_QWORD *)(a1[2] - 8LL) + 8LL),
           a2);
    v8 = *(_BYTE *)v7;
    *(_BYTE *)v7 = *(_BYTE *)v6;
    *(_BYTE *)v6 = v8;
    v9 = *(_QWORD *)(v7 + 8);
    *(_QWORD *)(v7 + 8) = *(_QWORD *)(v6 + 8);
    *(_QWORD *)(v6 + 8) = v9;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
      (void **)(v6 + 8),
      *(_BYTE *)v6);
    a1[12] = v7;
  }
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::destroy(
    &v12,
    v11[0]);
  return 1;
}

```

## disassembly

```asm
0x1800250a0  mov     [rsp-18h+arg_0], rbx
0x1800250a5  mov     [rsp-18h+arg_18], rsi
0x1800250aa  push    rbp
0x1800250ab  push    rdi
0x1800250ac  push    r14
0x1800250ae  mov     rbp, rsp
0x1800250b1  sub     rsp, 50h
0x1800250b5  mov     r14, rdx
0x1800250b8  mov     rsi, rcx
0x1800250bb  xor     eax, eax
0x1800250bd  mov     [rbp+var_18], rax
0x1800250c1  mov     [rbp+var_20], 3
0x1800250c5  lea     ecx, [rax+20h]; Size
0x1800250c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800250cd  mov     rbx, rax
0x1800250d0  lea     rax, [rbp+arg_8]
0x1800250d4  mov     [rbp+var_10], rax
0x1800250d8  mov     [rbp+var_8], rbx
0x1800250dc  mov     rdx, r14
0x1800250df  mov     rcx, rbx
0x1800250e2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x1800250e7  nop
0x1800250e8  mov     [rbp+var_18], rbx
0x1800250ec  mov     byte ptr [rbp+arg_8], 4
0x1800250f0  mov     rax, [rsi+10h]
0x1800250f4  sub     rax, [rsi+8]
0x1800250f8  sar     rax, 3
0x1800250fc  mov     [rbp+arg_10], eax
0x1800250ff  mov     rcx, [rsi+0A8h]
0x180025106  test    rcx, rcx
0x180025109  jnz     short loc_180025112
0x18002510b  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x180025111  int     3; Trap to Debugger
0x180025112  mov     rax, [rcx]
0x180025115  lea     r9, [rbp+var_20]
0x180025119  lea     r8, [rbp+arg_8]
0x18002511d  lea     rdx, [rbp+arg_10]
0x180025121  mov     rax, [rax+10h]
0x180025125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002512a  mov     bl, al
0x18002512c  mov     byte ptr [rbp+arg_8], al
0x18002512f  lea     rcx, [rsi+40h]
0x180025133  lea     rdx, [rbp+arg_8]
0x180025137  call    ?push_back@?$vector@_NV?$allocator@_N@std@@@std@@QEAAXAEB_N@Z; std::vector<bool>::push_back(bool const &)
0x18002513c  test    bl, bl
0x18002513e  jz      short loc_1800251A2
0x180025140  mov     rax, [rsi+10h]
0x180025144  cmp     qword ptr [rax-8], 0
0x180025149  jz      short loc_1800251A2
0x18002514b  lea     rax, [rbp+var_10]
0x18002514f  mov     [rbp+arg_8], rax
0x180025153  lea     rdx, [rsi+0B8h]
0x18002515a  lea     rcx, [rbp+var_10]
0x18002515e  call    ??0?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@AEBV01@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>(nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>> const &)
0x180025163  mov     rdi, rax
0x180025166  mov     rcx, [rsi+10h]
0x18002516a  mov     rcx, [rcx-8]
0x18002516e  mov     rdx, r14
0x180025171  mov     rcx, [rcx+8]
0x180025175  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@QEAAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::operator[](std::string const &)
0x18002517a  mov     rbx, rax
0x18002517d  mov     dl, [rax]
0x18002517f  mov     cl, [rdi]
0x180025181  mov     [rax], cl
0x180025183  mov     [rdi], dl
0x180025185  lea     rcx, [rdi+8]
0x180025189  mov     r8, [rax+8]
0x18002518d  mov     rdx, [rcx]
0x180025190  mov     [rax+8], rdx
0x180025194  mov     [rcx], r8
0x180025197  mov     dl, [rdi]
0x180025199  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x18002519e  mov     [rsi+60h], rbx
0x1800251a2  mov     dl, [rbp+var_20]
0x1800251a5  lea     rcx, [rbp+var_18]
0x1800251a9  call    ?destroy@json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAXW4value_t@detail@3@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::destroy(nlohmann::detail::value_t)
0x1800251ae  mov     al, 1
0x1800251b0  lea     r11, [rsp+50h+var_s0]
0x1800251b5  mov     rbx, [r11+20h]
0x1800251b9  mov     rsi, [r11+38h]
0x1800251bd  mov     rsp, r11
0x1800251c0  pop     r14
0x1800251c2  pop     rdi
0x1800251c3  pop     rbp
0x1800251c4  retn
```
