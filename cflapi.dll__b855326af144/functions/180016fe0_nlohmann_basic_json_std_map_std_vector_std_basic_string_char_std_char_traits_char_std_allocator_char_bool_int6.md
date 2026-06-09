# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::get<std::vector<uchar,std::allocator<uchar>>,std::vector<uchar,std::allocator<uchar>>,0>(void)

- ea: `0x180016fe0`
- end: `0x18001706e`
- name: `??$get@V?$vector@EV?$allocator@E@std@@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$vector@EV?$allocator@E@std@@@std@@XZ`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18001cb44`
- `0x180028cc4`

## callees

- `0x180002490`
- `0x180008a68`
- `0x180016c70`
- `0x180016ed4`
- `0x18001b0bc`
- `0x18001b49c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::vector<unsigned char>,std::vector<unsigned char>,0>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  __int64 v4; // rax
  _BYTE v6[24]; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v7[4]; // [rsp+48h] [rbp-30h] BYREF

  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
    a1,
    v7,
    a3);
  v4 = anonymous_namespace_::from_base64_std::vector_unsigned_char_std::allocator_unsigned_char____std::basic_string_char_std::char_traits_char__std::allocator_char_____(
         v6,
         v7);
  std::vector<unsigned char>::operator=(a2, v4);
  std::vector<char>::~vector<char>(v6);
  std::string::~string(v7);
  return a2;
}

```

## disassembly

```asm
0x180016fe0  push    rbx
0x180016fe2  sub     rsp, 70h
0x180016fe6  mov     rax, cs:__security_cookie
0x180016fed  xor     rax, rsp
0x180016ff0  mov     [rsp+78h+var_10], rax
0x180016ff5  mov     rbx, rdx
0x180016ff8  mov     [rsp+78h+var_50], rdx
0x180016ffd  xor     eax, eax
0x180016fff  mov     [rsp+78h+var_58], eax
0x180017003  mov     [rdx], rax
0x180017006  mov     [rdx+8], rax
0x18001700a  mov     [rdx+10h], rax
0x18001700e  mov     [rsp+78h+var_58], 1
0x180017016  lea     rdx, [rsp+78h+var_30]
0x18001701b  call    ??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::get<std::string,std::string,0>(void)
0x180017020  mov     [rsp+78h+var_58], 3
0x180017028  lea     rdx, [rsp+78h+var_30]
0x18001702d  lea     rcx, [rsp+78h+var_48]
0x180017032  call    _anonymous_namespace___from_base64_std__vector_unsigned_char_std__allocator_unsigned_char____std__basic_string_char_std__char_traits_char__std__allocator_char_____
0x180017037  mov     rdx, rax
0x18001703a  mov     rcx, rbx
0x18001703d  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x180017042  lea     rcx, [rsp+78h+var_48]
0x180017047  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001704c  nop
0x18001704d  lea     rcx, [rsp+78h+var_30]
0x180017052  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180017057  mov     rax, rbx
0x18001705a  mov     rcx, [rsp+78h+var_10]
0x18001705f  xor     rcx, rsp; StackCookie
0x180017062  call    __security_check_cookie
0x180017067  add     rsp, 70h
0x18001706b  pop     rbx
0x18001706c  retn
```
