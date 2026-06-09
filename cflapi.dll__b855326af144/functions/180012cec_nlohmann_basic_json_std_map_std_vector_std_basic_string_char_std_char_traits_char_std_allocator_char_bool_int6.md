# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::operator[]<char const>(char const *)

- ea: `0x180012cec`
- end: `0x180012dd5`
- name: `??$?A$$CBD@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAAAEAV01@PEBD@Z`
- size: `233`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18001fb28`
- `0x18002b264`

## callees

- `0x180002490`
- `0x180002f04`
- `0x180008a68`
- `0x180012cec`
- `0x180013130`
- `0x180019fb8`
- `0x18001a674`
- `0x18001b560`
- `0x180022be8`
- `0x180027b28`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::operator[]<char const>(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 v5; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // [rsp+20h] [rbp-98h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+28h] [rbp-90h] BYREF
  _BYTE v12[32]; // [rsp+60h] [rbp-58h] BYREF
  _BYTE v13[32]; // [rsp+80h] [rbp-38h] BYREF

  if ( !*(_BYTE *)a1 )
  {
    *(_BYTE *)a1 = 1;
    nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::json_value::json_value(
      &v10,
      1);
    *(_QWORD *)(a1 + 8) = v10;
  }
  if ( *(_BYTE *)a1 != 1 )
  {
    v7 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::type_name(a1);
    v8 = std::string::string(v12, v7);
    v9 = std::operator+<char>(v13, "cannot use operator[] with a string argument with ", v8);
    nlohmann::detail::type_error::create((__int64)pExceptionObject, 0x131u, v9);
    throw (nlohmann::detail::type_error *)pExceptionObject;
  }
  v4 = *(_QWORD *)(a1 + 8);
  std::string::string(v12, a2);
  v5 = std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>>::operator[](
         v4,
         v12);
  std::string::~string(v12);
  return v5;
}

```

## disassembly

```asm
0x180012cec  mov     [rsp+arg_10], rbx
0x180012cf1  push    rdi
0x180012cf2  sub     rsp, 0B0h
0x180012cf9  mov     rax, cs:__security_cookie
0x180012d00  xor     rax, rsp
0x180012d03  mov     [rsp+0B8h+var_18], rax
0x180012d0b  mov     rdi, rdx
0x180012d0e  mov     rbx, rcx
0x180012d11  cmp     byte ptr [rcx], 0
0x180012d14  jnz     short loc_180012D2E
0x180012d16  mov     byte ptr [rcx], 1
0x180012d19  mov     dl, 1
0x180012d1b  lea     rcx, [rsp+0B8h+var_98]
0x180012d20  call    ??0json_value@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEAA@W4value_t@detail@2@@Z; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::json_value::json_value(nlohmann::detail::value_t)
0x180012d25  mov     rax, [rsp+0B8h+var_98]
0x180012d2a  mov     [rbx+8], rax
0x180012d2e  cmp     byte ptr [rbx], 1
0x180012d31  jnz     short loc_180012D83
0x180012d33  mov     rbx, [rbx+8]
0x180012d37  mov     rdx, rdi
0x180012d3a  lea     rcx, [rsp+0B8h+var_58]
0x180012d3f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180012d44  nop
0x180012d45  lea     rdx, [rsp+0B8h+var_58]
0x180012d4a  mov     rcx, rbx
0x180012d4d  call    ??A?$map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@@std@@@2@@std@@QEAAAEAV?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@$$QEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::map<std::string,nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>>::operator[](std::string &&)
0x180012d52  mov     rbx, rax
0x180012d55  lea     rcx, [rsp+0B8h+var_58]
0x180012d5a  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180012d5f  mov     rax, rbx
0x180012d62  mov     rcx, [rsp+0B8h+var_18]
0x180012d6a  xor     rcx, rsp; StackCookie
0x180012d6d  call    __security_check_cookie
0x180012d72  mov     rbx, [rsp+0B8h+arg_10]
0x180012d7a  add     rsp, 0B0h
0x180012d81  pop     rdi
0x180012d82  retn
0x180012d83  mov     rcx, rbx
0x180012d86  call    ?type_name@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBAPEBDXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::type_name(void)
0x180012d8b  mov     rdx, rax
0x180012d8e  lea     rcx, [rsp+0B8h+var_58]
0x180012d93  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180012d98  nop
0x180012d99  mov     r8, rax
0x180012d9c  lea     rdx, aCannotUseOpera; "cannot use operator[] with a string arg"...
0x180012da3  lea     rcx, [rsp+0B8h+var_38]
0x180012dab  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180012db0  nop
0x180012db1  mov     r8, rax
0x180012db4  mov     edx, 131h
0x180012db9  lea     rcx, [rsp+0B8h+pExceptionObject]
0x180012dbe  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180012dc3  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180012dca  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180012dcf  call    _CxxThrowException_0
```
