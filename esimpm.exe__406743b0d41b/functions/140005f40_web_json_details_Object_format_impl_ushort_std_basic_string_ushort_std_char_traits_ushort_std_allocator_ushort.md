# web::json::details::_Object::format_impl<ushort>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x140005f40`
- end: `0x140006111`
- name: `??$format_impl@G@_Object@details@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `465`
- prototype: `void **__fastcall(__int64, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007c60`

## callees

- `0x140005450`
- `0x140005f40`
- `0x14000c1a0`
- `0x14000c1c0`

## pseudocode

```c
void **__fastcall web::json::details::_Object::format_impl<unsigned short>(__int64 a1, unsigned __int64 *a2)
{
  unsigned __int64 *v2; // rsi
  unsigned __int64 v3; // rdx
  unsigned __int64 *v5; // rcx
  unsigned __int64 v6; // r8
  __int64 v7; // rdi
  __int64 v8; // rbx
  __int64 i; // rdi
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // r8
  char *v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // r8
  char *v15; // rdx
  unsigned __int64 v16; // rcx
  unsigned __int64 v17; // r8
  char *v18; // rdx
  unsigned __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  void **result; // rax

  v2 = a2;
  v3 = a2[2];
  v5 = v2;
  v6 = v2[3];
  if ( v3 >= v6 )
  {
    ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
      (void **)v2,
      1u,
      0,
      123);
  }
  else
  {
    v2[2] = v3 + 1;
    if ( v6 > 7 )
      v5 = (unsigned __int64 *)*v2;
    *(_DWORD *)((char *)v5 + 2 * v3) = 123;
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
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
          (void **)v2,
          1u,
          0,
          58);
      }
      else
      {
        v12 = (char *)v2;
        v2[2] = v10 + 1;
        if ( v11 > 7 )
          v12 = (char *)*v2;
        *(_DWORD *)&v12[2 * v10] = 58;
      }
      web::json::value::format(v8 + 32, v2);
      v13 = v2[2];
      v14 = v2[3];
      if ( v13 >= v14 )
      {
        ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
          (void **)v2,
          1u,
          0,
          44);
      }
      else
      {
        v15 = (char *)v2;
        v2[2] = v13 + 1;
        if ( v14 > 7 )
          v15 = (char *)*v2;
        *(_DWORD *)&v15[2 * v13] = 44;
      }
    }
    web::json::details::format_string(i, v2);
    v16 = v2[2];
    v17 = v2[3];
    if ( v16 >= v17 )
    {
      ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
        (void **)v2,
        1u,
        0,
        58);
    }
    else
    {
      v18 = (char *)v2;
      v2[2] = v16 + 1;
      if ( v17 > 7 )
        v18 = (char *)*v2;
      *(_DWORD *)&v18[2 * v16] = 58;
    }
    web::json::value::format(i + 32, v2);
  }
  v19 = v2[2];
  v20 = v2[3];
  if ( v19 >= v20 )
    return ____Reallocate_grow_by_V_lambda_1___1__push_back___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__QEAAXG_Z_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1__push_back_01_QEAAXG_Z_G_Z(
             (void **)v2,
             1u,
             0,
             125);
  result = (void **)(v19 + 1);
  v2[2] = v19 + 1;
  if ( v20 > 7 )
    v2 = (unsigned __int64 *)*v2;
  *(_DWORD *)((char *)v2 + 2 * v19) = 125;
  return result;
}

```

## disassembly

```asm
0x140005f40  push    rsi
0x140005f42  sub     rsp, 20h
0x140005f46  mov     rsi, rdx
0x140005f49  mov     [rsp+28h+arg_0], rbx
0x140005f4e  mov     rdx, [rdx+10h]
0x140005f52  mov     rbx, rcx
0x140005f55  mov     [rsp+28h+arg_10], rdi
0x140005f5a  mov     rcx, rsi; Src
0x140005f5d  mov     r8, [rsi+18h]
0x140005f61  cmp     rdx, r8
0x140005f64  jnb     short loc_140005F80
0x140005f66  lea     rax, [rdx+1]
0x140005f6a  mov     [rsi+10h], rax
0x140005f6e  cmp     r8, 7
0x140005f72  jbe     short loc_140005F77
0x140005f74  mov     rcx, [rsi]
0x140005f77  mov     dword ptr [rcx+rdx*2], 7Bh ; '{'
0x140005f7e  jmp     short loc_140005F93
0x140005f80  mov     r9d, 7Bh ; '{'
0x140005f86  xor     r8d, r8d
0x140005f89  mov     edx, 1
0x140005f8e  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x140005f93  mov     rdi, [rbx+10h]
0x140005f97  mov     rbx, [rbx+8]
0x140005f9b  cmp     rbx, rdi
0x140005f9e  jz      loc_1400060C1
0x140005fa4  add     rdi, 0FFFFFFFFFFFFFFD8h
0x140005fa8  mov     [rsp+28h+arg_8], rbp
0x140005fad  mov     ebp, 3Ah ; ':'
0x140005fb2  cmp     rbx, rdi
0x140005fb5  jz      loc_14000606C
0x140005fbb  mov     [rsp+28h+arg_18], r14
0x140005fc0  mov     r14d, 2Ch ; ','
0x140005fc6  nop     word ptr [rax+rax+00000000h]
0x140005fd0  mov     rdx, rsi
0x140005fd3  mov     rcx, rbx
0x140005fd6  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x140005fdb  mov     rcx, [rsi+10h]
0x140005fdf  mov     r8, [rsi+18h]
0x140005fe3  cmp     rcx, r8
0x140005fe6  jnb     short loc_140006001
0x140005fe8  lea     rax, [rcx+1]
0x140005fec  mov     rdx, rsi
0x140005fef  mov     [rsi+10h], rax
0x140005ff3  cmp     r8, 7
0x140005ff7  jbe     short loc_140005FFC
0x140005ff9  mov     rdx, [rsi]
0x140005ffc  mov     [rdx+rcx*2], ebp
0x140005fff  jmp     short loc_140006014
0x140006001  mov     r9d, ebp
0x140006004  xor     r8d, r8d
0x140006007  mov     edx, 1
0x14000600c  mov     rcx, rsi; Src
0x14000600f  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x140006014  lea     rcx, [rbx+20h]
0x140006018  mov     rdx, rsi
0x14000601b  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x140006020  mov     rcx, [rsi+10h]
0x140006024  mov     r8, [rsi+18h]
0x140006028  cmp     rcx, r8
0x14000602b  jnb     short loc_140006047
0x14000602d  lea     rax, [rcx+1]
0x140006031  mov     rdx, rsi
0x140006034  mov     [rsi+10h], rax
0x140006038  cmp     r8, 7
0x14000603c  jbe     short loc_140006041
0x14000603e  mov     rdx, [rsi]
0x140006041  mov     [rdx+rcx*2], r14d
0x140006045  jmp     short loc_14000605A
0x140006047  mov     r9d, r14d
0x14000604a  xor     r8d, r8d
0x14000604d  mov     edx, 1
0x140006052  mov     rcx, rsi; Src
0x140006055  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x14000605a  add     rbx, 28h ; '('
0x14000605e  cmp     rbx, rdi
0x140006061  jnz     loc_140005FD0
0x140006067  mov     r14, [rsp+28h+arg_18]
0x14000606c  mov     rdx, rsi
0x14000606f  mov     rcx, rdi
0x140006072  call    ?format_string@details@json@web@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV45@@Z; web::json::details::format_string(std::wstring const &,std::wstring &)
0x140006077  mov     rcx, [rsi+10h]
0x14000607b  mov     r8, [rsi+18h]
0x14000607f  cmp     rcx, r8
0x140006082  jnb     short loc_14000609D
0x140006084  lea     rax, [rcx+1]
0x140006088  mov     rdx, rsi
0x14000608b  mov     [rsi+10h], rax
0x14000608f  cmp     r8, 7
0x140006093  jbe     short loc_140006098
0x140006095  mov     rdx, [rsi]
0x140006098  mov     [rdx+rcx*2], ebp
0x14000609b  jmp     short loc_1400060B0
0x14000609d  mov     r9d, ebp
0x1400060a0  xor     r8d, r8d
0x1400060a3  mov     edx, 1
0x1400060a8  mov     rcx, rsi; Src
0x1400060ab  call    ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
0x1400060b0  lea     rcx, [rdi+20h]
0x1400060b4  mov     rdx, rsi
0x1400060b7  call    ?format@value@json@web@@AEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; web::json::value::format(std::wstring &)
0x1400060bc  mov     rbp, [rsp+28h+arg_8]
0x1400060c1  mov     rcx, [rsi+10h]
0x1400060c5  mov     rdx, [rsi+18h]
0x1400060c9  mov     rdi, [rsp+28h+arg_10]
0x1400060ce  mov     rbx, [rsp+28h+arg_0]
0x1400060d3  cmp     rcx, rdx
0x1400060d6  jnb     short loc_1400060F6
0x1400060d8  lea     rax, [rcx+1]
0x1400060dc  mov     [rsi+10h], rax
0x1400060e0  cmp     rdx, 7
0x1400060e4  jbe     short loc_1400060E9
0x1400060e6  mov     rsi, [rsi]
0x1400060e9  mov     dword ptr [rsi+rcx*2], 7Dh ; '}'
0x1400060f0  add     rsp, 20h
0x1400060f4  pop     rsi
0x1400060f5  retn
0x1400060f6  mov     r9d, 7Dh ; '}'
0x1400060fc  xor     r8d, r8d
0x1400060ff  mov     edx, 1
0x140006104  mov     rcx, rsi; Src
0x140006107  add     rsp, 20h
0x14000610b  pop     rsi
0x14000610c  jmp     ??$_Reallocate_grow_by@V_lambda_1_@?1??push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXG@Z@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_1_@?1??push_back@01@QEAAXG@Z@G@Z; std::wstring::_Reallocate_grow_by<`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort>(unsigned __int64,`std::wstring::push_back(ushort)'::`2'::_lambda_1_,ushort)
```
