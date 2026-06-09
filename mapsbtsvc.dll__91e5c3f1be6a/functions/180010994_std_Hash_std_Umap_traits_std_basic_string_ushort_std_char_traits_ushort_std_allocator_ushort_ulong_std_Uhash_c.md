# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>,void *> * const)

- ea: `0x180010994`
- end: `0x180010abe`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010d6c`

## callees

- `0x18000b880`
- `0x18000fbac`
- `0x180010994`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rsi
  _QWORD *v8; // r15
  unsigned __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  _QWORD *v15; // rax
  unsigned __int64 v17; // rax
  __int64 v18; // r12
  bool v19; // bl
  _QWORD *v20; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-50h]
  __int64 v22; // [rsp+30h] [rbp-48h]
  __int64 v24; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = a1[3];
    v8 = (_QWORD *)a1[1];
    v20 = a1 + 1;
    v21 = v6;
    v22 = a2;
    v9 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(a2 + 16);
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v7 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v7 + 8 * v11);
    v24 = *(_QWORD *)(v7 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Range_eraser::_Bump_erased(&v20);
      if ( v14 )
        break;
      v10 = v22;
      v12 = v24;
      if ( v22 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v7 + 8 * v11) = v10;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v7 + 8 * v11) = v8;
      v6 = v8;
    }
    for ( *(_QWORD *)(v7 + 8 * v11 + 8) = v6; ; *(_QWORD *)(v7 + 8 * v11 + 8) = v8 )
    {
      v10 = v22;
      if ( v22 == a3 )
        break;
      v17 = std::_Conditionally_enabled_hash<std::wstring,1>::operator()(v22 + 16);
      v11 = 2 * (a1[6] & v17);
      v18 = *(_QWORD *)(v7 + 16 * (a1[6] & v17) + 8);
      while ( 1 )
      {
        v19 = v10 == v18;
        std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Range_eraser::_Bump_erased(&v20);
        if ( v19 )
          break;
        v10 = v22;
        if ( v22 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v7 + 8 * v11) = v8;
    }
LABEL_7:
    v15 = v21;
    *v21 = v10;
    *(_QWORD *)(v10 + 8) = v15;
  }
  return a3;
}

```

## disassembly

```asm
0x180010994  mov     r11, rsp
0x180010997  mov     [r11+18h], rbx
0x18001099b  mov     [r11+8], rcx
0x18001099f  push    rbp
0x1800109a0  push    rsi
0x1800109a1  push    rdi
0x1800109a2  push    r12
0x1800109a4  push    r13
0x1800109a6  push    r14
0x1800109a8  push    r15
0x1800109aa  sub     rsp, 40h
0x1800109ae  mov     rdi, r8
0x1800109b1  mov     rbp, rdx
0x1800109b4  mov     rbx, rcx
0x1800109b7  cmp     rdx, r8
0x1800109ba  jz      short loc_180010A3A
0x1800109bc  mov     r12, [rdx+8]
0x1800109c0  lea     rax, [rcx+8]
0x1800109c4  mov     rsi, [rcx+18h]
0x1800109c8  lea     rcx, [rdx+10h]
0x1800109cc  mov     r15, [rax]
0x1800109cf  mov     [r11-58h], rax
0x1800109d3  mov     [r11-50h], r12
0x1800109d7  mov     r11, rdx
0x1800109da  mov     [rsp+78h+var_48], rdx
0x1800109df  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x1800109e4  mov     r14, rax
0x1800109e7  and     r14, [rbx+30h]
0x1800109eb  add     r14, r14
0x1800109ee  mov     rax, [rsi+r14*8+8]
0x1800109f3  mov     r13, [rsi+r14*8]
0x1800109f7  mov     [rsp+78h+arg_8], rax
0x1800109ff  cmp     r11, rax
0x180010a02  lea     rcx, [rsp+78h+var_58]
0x180010a07  setz    bl
0x180010a0a  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Range_eraser::_Bump_erased(void)
0x180010a0f  test    bl, bl
0x180010a11  jnz     short loc_180010A55
0x180010a13  mov     r11, [rsp+78h+var_48]
0x180010a18  mov     rax, [rsp+78h+arg_8]
0x180010a20  cmp     r11, rdi
0x180010a23  jnz     short loc_1800109FF
0x180010a25  cmp     r13, rbp
0x180010a28  jnz     short loc_180010A2E
0x180010a2a  mov     [rsi+r14*8], r11
0x180010a2e  mov     rax, [rsp+78h+var_50]
0x180010a33  mov     [rax], r11
0x180010a36  mov     [r11+8], rax
0x180010a3a  mov     rbx, [rsp+78h+arg_10]
0x180010a42  mov     rax, rdi
0x180010a45  add     rsp, 40h
0x180010a49  pop     r15
0x180010a4b  pop     r14
0x180010a4d  pop     r13
0x180010a4f  pop     r12
0x180010a51  pop     rdi
0x180010a52  pop     rsi
0x180010a53  pop     rbp
0x180010a54  retn
0x180010a55  cmp     r13, rbp
0x180010a58  jnz     short loc_180010A61
0x180010a5a  mov     [rsi+r14*8], r15
0x180010a5e  mov     r12, r15
0x180010a61  mov     [rsi+r14*8+8], r12
0x180010a66  mov     rbp, [rsp+78h+arg_0]
0x180010a6e  mov     r11, [rsp+78h+var_48]
0x180010a73  cmp     r11, rdi
0x180010a76  jz      short loc_180010A2E
0x180010a78  lea     rcx, [r11+10h]
0x180010a7c  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x180010a81  mov     r14, rax
0x180010a84  and     r14, [rbp+30h]
0x180010a88  add     r14, r14
0x180010a8b  mov     r12, [rsi+r14*8+8]
0x180010a90  cmp     r11, r12
0x180010a93  lea     rcx, [rsp+78h+var_58]
0x180010a98  setz    bl
0x180010a9b  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Range_eraser::_Bump_erased(void)
0x180010aa0  test    bl, bl
0x180010aa2  jnz     short loc_180010AB3
0x180010aa4  mov     r11, [rsp+78h+var_48]
0x180010aa9  cmp     r11, rdi
0x180010aac  jnz     short loc_180010A90
0x180010aae  jmp     loc_180010A2A
0x180010ab3  mov     [rsi+r14*8], r15
0x180010ab7  mov     [rsi+r14*8+8], r15
0x180010abc  jmp     short loc_180010A6E
```
