# nlohmann::basic_json<std::map,std::vector,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar,std::allocator<uchar>>>::get<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::basic_string<char,std::char_traits<char>,std::allocator<char>>,0>(void)

- ea: `0x180016ed4`
- end: `0x180016fd9`
- name: `??$get@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@$0A@@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `261`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016e28`
- `0x180016fe0`
- `0x18001cb44`
- `0x180028cc4`

## callees

- `0x180002490`
- `0x180002f04`
- `0x180013130`
- `0x180015794`
- `0x180016ed4`
- `0x180019fb8`
- `0x180022be8`
- `0x180027b28`
- `0x18002e008`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::get<std::string,std::string,0>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  _QWORD *v4; // r9
  size_t v5; // rdi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-88h] BYREF
  _BYTE v11[32]; // [rsp+68h] [rbp-50h] BYREF
  _BYTE v12[32]; // [rsp+88h] [rbp-30h] BYREF

  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 15;
  *(_BYTE *)a2 = 0;
  if ( *(_BYTE *)a1 != 3 )
  {
    v7 = nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<unsigned char>>::type_name(a1);
    v8 = std::string::string(v11, v7);
    v9 = std::operator+<char>(v12, "type must be string, but is ", v8);
    nlohmann::detail::type_error::create(pExceptionObject, 302, v9);
    throw (nlohmann::detail::type_error *)pExceptionObject;
  }
  v4 = *(_QWORD **)(a1 + 8);
  if ( a2 != v4 )
  {
    v5 = v4[2];
    if ( v4[3] > 0xFu )
      v4 = (_QWORD *)*v4;
    if ( v5 > 0xF )
    {
      std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(a2, v5, a3, v4);
    }
    else
    {
      a2[2] = v5;
      memmove_0(a2, v4, v5);
      *((_BYTE *)a2 + v5) = 0;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180016ed4  mov     [rsp+arg_10], rbx
0x180016ed9  push    rdi
0x180016eda  sub     rsp, 0B0h
0x180016ee1  mov     rax, cs:__security_cookie
0x180016ee8  xor     rax, rsp
0x180016eeb  mov     [rsp+0B8h+var_10], rax
0x180016ef3  mov     rbx, rdx
0x180016ef6  mov     [rsp+0B8h+var_90], rdx
0x180016efb  mov     [rsp+0B8h+var_98], 0
0x180016f03  xorps   xmm0, xmm0
0x180016f06  movups  xmmword ptr [rdx], xmm0
0x180016f09  mov     qword ptr [rdx+10h], 0
0x180016f11  mov     qword ptr [rdx+18h], 0Fh
0x180016f19  mov     byte ptr [rdx], 0
0x180016f1c  mov     [rsp+0B8h+var_98], 1
0x180016f24  cmp     byte ptr [rcx], 3
0x180016f27  jnz     short loc_180016F8A
0x180016f29  mov     r9, [rcx+8]
0x180016f2d  cmp     rdx, r9
0x180016f30  jz      short loc_180016F66
0x180016f32  mov     rdi, [r9+10h]
0x180016f36  cmp     qword ptr [r9+18h], 0Fh
0x180016f3b  jbe     short loc_180016F40
0x180016f3d  mov     r9, [r9]
0x180016f40  mov     rcx, rbx; void *
0x180016f43  cmp     rdi, 0Fh
0x180016f47  ja      short loc_180016F5E
0x180016f49  mov     [rdx+10h], rdi
0x180016f4d  mov     r8, rdi; Size
0x180016f50  mov     rdx, r9; Src
0x180016f53  call    memmove_0
0x180016f58  mov     byte ptr [rdi+rbx], 0
0x180016f5c  jmp     short loc_180016F66
0x180016f5e  mov     rdx, rdi
0x180016f61  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x180016f66  mov     rax, rbx
0x180016f69  mov     rcx, [rsp+0B8h+var_10]
0x180016f71  xor     rcx, rsp; StackCookie
0x180016f74  call    __security_check_cookie
0x180016f79  mov     rbx, [rsp+0B8h+arg_10]
0x180016f81  add     rsp, 0B0h
0x180016f88  pop     rdi
0x180016f89  retn
0x180016f8a  call    ?type_name@?$basic_json@Vmap@std@@Vvector@2@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@_N_J_KNVallocator@2@Uadl_serializer@nlohmann@@V?$vector@EV?$allocator@E@std@@@2@@nlohmann@@QEBAPEBDXZ; nlohmann::basic_json<std::map,std::vector,std::string,bool,__int64,unsigned __int64,double,std::allocator,nlohmann::adl_serializer,std::vector<uchar>>::type_name(void)
0x180016f8f  mov     rdx, rax
0x180016f92  lea     rcx, [rsp+0B8h+var_50]
0x180016f97  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180016f9c  nop
0x180016f9d  mov     r8, rax
0x180016fa0  lea     rdx, aTypeMustBeStri; "type must be string, but is "
0x180016fa7  lea     rcx, [rsp+0B8h+var_30]
0x180016faf  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@QEBD$$QEAV10@@Z; std::operator+<char>(char const * const,std::string &&)
0x180016fb4  nop
0x180016fb5  mov     r8, rax
0x180016fb8  mov     edx, 12Eh
0x180016fbd  lea     rcx, [rsp+0B8h+pExceptionObject]
0x180016fc2  call    ?create@type_error@detail@nlohmann@@SA?AV123@HAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; nlohmann::detail::type_error::create(int,std::string const &)
0x180016fc7  lea     rdx, _TI3?AVtype_error@detail@nlohmann@@; pThrowInfo
0x180016fce  lea     rcx, [rsp+0B8h+pExceptionObject]; pExceptionObject
0x180016fd3  call    _CxxThrowException_0
```
