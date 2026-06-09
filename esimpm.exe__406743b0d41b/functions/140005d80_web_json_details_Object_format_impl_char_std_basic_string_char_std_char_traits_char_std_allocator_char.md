# web::json::details::_Object::format_impl<char>(std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x140005d80`
- end: `0x140005f35`
- name: `??$format_impl@D@_Object@details@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `437`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007c50`

## callees

- `0x140005d80`
- `0x14000c180`
- `0x14000c280`
- `0x140037140`

## pseudocode

```c
__int64 __fastcall web::json::details::_Object::format_impl<char>(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // r8
  _QWORD *v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 i; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rax
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  _QWORD *v15; // rax
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  _QWORD *v18; // rax
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  __int64 result; // rax

  v2 = a2;
  v4 = a2[2];
  v5 = v2[3];
  if ( v4 >= v5 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  }
  else
  {
    v2[2] = v4 + 1;
    v6 = v2;
    if ( v5 > 0xF )
      v6 = (_QWORD *)*v2;
    *(_WORD *)((char *)v6 + v4) = 123;
  }
  v7 = *(_QWORD *)(a1 + 16);
  v8 = *(_QWORD *)(a1 + 8);
  if ( v8 != v7 )
  {
    for ( i = v7 - 40; v8 != i; v8 += 40 )
    {
      web::json::details::format_string(v8, v2);
      v10 = v2[2];
      v11 = v2[3];
      if ( v10 >= v11 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
      }
      else
      {
        v2[2] = v10 + 1;
        v12 = v2;
        if ( v11 > 0xF )
          v12 = (_QWORD *)*v2;
        *(_WORD *)((char *)v12 + v10) = 58;
      }
      web::json::value::format(v8 + 32, v2);
      v13 = v2[2];
      v14 = v2[3];
      if ( v13 >= v14 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
      }
      else
      {
        v2[2] = v13 + 1;
        v15 = v2;
        if ( v14 > 0xF )
          v15 = (_QWORD *)*v2;
        *(_WORD *)((char *)v15 + v13) = 44;
      }
    }
    web::json::details::format_string(i, v2);
    v16 = v2[2];
    v17 = v2[3];
    if ( v16 >= v17 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
    }
    else
    {
      v2[2] = v16 + 1;
      v18 = v2;
      if ( v17 > 0xF )
        v18 = (_QWORD *)*v2;
      *(_WORD *)((char *)v18 + v16) = 58;
    }
    web::json::value::format(i + 32, v2);
  }
  v19 = v2[2];
  v20 = v2[3];
  if ( v19 >= v20 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__QEAAXD_Z_D___basic_string_DU__char_traits_D_std__V__allocator_D_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXD_Z_D_Z(v2);
  result = v19 + 1;
  v2[2] = v19 + 1;
  if ( v20 > 0xF )
    v2 = (_QWORD *)*v2;
  *(_WORD *)((char *)v2 + v19) = 125;
  return result;
}

```

## disassembly

```asm
0x140005d80  mov     [rsp+arg_0], rbx
0x140005d85  mov     [rsp+arg_8], rsi
0x140005d8a  push    rdi
0x140005d8b  sub     rsp, 20h
0x140005d8f  mov     rsi, rdx
0x140005d92  mov     rbx, rcx
0x140005d95  mov     rdx, [rdx+10h]
0x140005d99  mov     r8, [rsi+18h]
0x140005d9d  cmp     rdx, r8
0x140005da0  jnb     short loc_140005DBE
0x140005da2  lea     rax, [rdx+1]
0x140005da6  mov     [rsi+10h], rax
0x140005daa  mov     rax, rsi
0x140005dad  cmp     r8, 0Fh
0x140005db1  jbe     short loc_140005DB6
0x140005db3  mov     rax, [rsi]
0x140005db6  mov     word ptr [rdx+rax], 7Bh ; '{'
0x140005dbc  jmp     short loc_140005DD1
0x140005dbe  mov     r9b, 7Bh ; '{'
0x140005dc1  xor     r8d, r8d
0x140005dc4  mov     edx, 1
0x140005dc9  mov     rcx, rsi; Src
0x140005dcc  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x140005dd1  mov     rdi, [rbx+10h]
0x140005dd5  mov     rbx, [rbx+8]
0x140005dd9  cmp     rbx, rdi
0x140005ddc  jz      loc_140005EDF
0x140005de2  add     rdi, 0FFFFFFFFFFFFFFD8h
0x140005de6  cmp     rbx, rdi
0x140005de9  jz      loc_140005E8C
0x140005def  nop
0x140005df0  mov     rdx, rsi
0x140005df3  mov     rcx, rbx
0x140005df6  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x140005dfb  mov     rcx, [rsi+10h]
0x140005dff  mov     rdx, [rsi+18h]
0x140005e03  cmp     rcx, rdx
0x140005e06  jnb     short loc_140005E24
0x140005e08  lea     rax, [rcx+1]
0x140005e0c  mov     [rsi+10h], rax
0x140005e10  mov     rax, rsi
0x140005e13  cmp     rdx, 0Fh
0x140005e17  jbe     short loc_140005E1C
0x140005e19  mov     rax, [rsi]
0x140005e1c  mov     word ptr [rcx+rax], 3Ah ; ':'
0x140005e22  jmp     short loc_140005E37
0x140005e24  mov     r9b, 3Ah ; ':'
0x140005e27  xor     r8d, r8d
0x140005e2a  mov     edx, 1
0x140005e2f  mov     rcx, rsi; Src
0x140005e32  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x140005e37  lea     rcx, [rbx+20h]
0x140005e3b  mov     rdx, rsi
0x140005e3e  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x140005e43  mov     rcx, [rsi+10h]
0x140005e47  mov     rdx, [rsi+18h]
0x140005e4b  cmp     rcx, rdx
0x140005e4e  jnb     short loc_140005E6C
0x140005e50  lea     rax, [rcx+1]
0x140005e54  mov     [rsi+10h], rax
0x140005e58  mov     rax, rsi
0x140005e5b  cmp     rdx, 0Fh
0x140005e5f  jbe     short loc_140005E64
0x140005e61  mov     rax, [rsi]
0x140005e64  mov     word ptr [rcx+rax], 2Ch ; ','
0x140005e6a  jmp     short loc_140005E7F
0x140005e6c  mov     r9b, 2Ch ; ','
0x140005e6f  xor     r8d, r8d
0x140005e72  mov     edx, 1
0x140005e77  mov     rcx, rsi; Src
0x140005e7a  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x140005e7f  add     rbx, 28h ; '('
0x140005e83  cmp     rbx, rdi
0x140005e86  jnz     loc_140005DF0
0x140005e8c  mov     rdx, rsi
0x140005e8f  mov     rcx, rdi
0x140005e92  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; web::json::details::format_string(std::wstring const &,std::string &)
0x140005e97  mov     rcx, [rsi+10h]
0x140005e9b  mov     rdx, [rsi+18h]
0x140005e9f  cmp     rcx, rdx
0x140005ea2  jnb     short loc_140005EC0
0x140005ea4  lea     rax, [rcx+1]
0x140005ea8  mov     [rsi+10h], rax
0x140005eac  mov     rax, rsi
0x140005eaf  cmp     rdx, 0Fh
0x140005eb3  jbe     short loc_140005EB8
0x140005eb5  mov     rax, [rsi]
0x140005eb8  mov     word ptr [rcx+rax], 3Ah ; ':'
0x140005ebe  jmp     short loc_140005ED3
0x140005ec0  mov     r9b, 3Ah ; ':'
0x140005ec3  xor     r8d, r8d
0x140005ec6  mov     edx, 1
0x140005ecb  mov     rcx, rsi; Src
0x140005ece  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
0x140005ed3  lea     rcx, [rdi+20h]
0x140005ed7  mov     rdx, rsi
0x140005eda  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; web::json::value::format(std::string &)
0x140005edf  mov     rcx, [rsi+10h]
0x140005ee3  mov     rdx, [rsi+18h]
0x140005ee7  cmp     rcx, rdx
0x140005eea  jnb     short loc_140005F13
0x140005eec  lea     rax, [rcx+1]
0x140005ef0  mov     [rsi+10h], rax
0x140005ef4  cmp     rdx, 0Fh
0x140005ef8  jbe     short loc_140005EFD
0x140005efa  mov     rsi, [rsi]
0x140005efd  mov     word ptr [rcx+rsi], 7Dh ; '}'
0x140005f03  mov     rbx, [rsp+28h+arg_0]
0x140005f08  mov     rsi, [rsp+28h+arg_8]
0x140005f0d  add     rsp, 20h
0x140005f11  pop     rdi
0x140005f12  retn
0x140005f13  mov     r9b, 7Dh ; '}'
0x140005f16  xor     r8d, r8d
0x140005f19  mov     edx, 1
0x140005f1e  mov     rcx, rsi; Src
0x140005f21  mov     rbx, [rsp+28h+arg_0]
0x140005f26  mov     rsi, [rsp+28h+arg_8]
0x140005f2b  add     rsp, 20h
0x140005f2f  pop     rdi
0x140005f30  jmp     ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXD@Z@D@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXD@Z@D@Z; std::string::_Reallocate_grow_by<`std::string::push_back(char)'::`2'::_lambda_1_,char>(unsigned __int64,`std::string::push_back(char)'::`2'::_lambda_1_,char)
```
