# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const)

- ea: `0x18000c4d8`
- end: `0x18000c602`
- name: `?_Unchecked_erase@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `298`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000c648`

## callees

- `0x18000ac08`
- `0x18000bda4`
- `0x18000c4d8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  __int64 v7; // rsi
  _QWORD *v8; // r15
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  _QWORD *v15; // rax
  __int64 v17; // rax
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
      std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(&v20);
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
        std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(&v20);
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
0x18000c4d8  mov     r11, rsp
0x18000c4db  mov     [r11+18h], rbx
0x18000c4df  mov     [r11+8], rcx
0x18000c4e3  push    rbp
0x18000c4e4  push    rsi
0x18000c4e5  push    rdi
0x18000c4e6  push    r12
0x18000c4e8  push    r13
0x18000c4ea  push    r14
0x18000c4ec  push    r15
0x18000c4ee  sub     rsp, 40h
0x18000c4f2  mov     rdi, r8
0x18000c4f5  mov     rbp, rdx
0x18000c4f8  mov     rbx, rcx
0x18000c4fb  cmp     rdx, r8
0x18000c4fe  jz      short loc_18000C57E
0x18000c500  mov     r12, [rdx+8]
0x18000c504  lea     rax, [rcx+8]
0x18000c508  mov     rsi, [rcx+18h]
0x18000c50c  lea     rcx, [rdx+10h]
0x18000c510  mov     r15, [rax]
0x18000c513  mov     [r11-58h], rax
0x18000c517  mov     [r11-50h], r12
0x18000c51b  mov     r11, rdx
0x18000c51e  mov     [rsp+78h+var_48], rdx
0x18000c523  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000c528  mov     r14, rax
0x18000c52b  and     r14, [rbx+30h]
0x18000c52f  add     r14, r14
0x18000c532  mov     rax, [rsi+r14*8+8]
0x18000c537  mov     r13, [rsi+r14*8]
0x18000c53b  mov     [rsp+78h+arg_8], rax
0x18000c543  cmp     r11, rax
0x18000c546  lea     rcx, [rsp+78h+var_58]
0x18000c54b  setz    bl
0x18000c54e  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000c553  test    bl, bl
0x18000c555  jnz     short loc_18000C599
0x18000c557  mov     r11, [rsp+78h+var_48]
0x18000c55c  mov     rax, [rsp+78h+arg_8]
0x18000c564  cmp     r11, rdi
0x18000c567  jnz     short loc_18000C543
0x18000c569  cmp     r13, rbp
0x18000c56c  jnz     short loc_18000C572
0x18000c56e  mov     [rsi+r14*8], r11
0x18000c572  mov     rax, [rsp+78h+var_50]
0x18000c577  mov     [rax], r11
0x18000c57a  mov     [r11+8], rax
0x18000c57e  mov     rbx, [rsp+78h+arg_10]
0x18000c586  mov     rax, rdi
0x18000c589  add     rsp, 40h
0x18000c58d  pop     r15
0x18000c58f  pop     r14
0x18000c591  pop     r13
0x18000c593  pop     r12
0x18000c595  pop     rdi
0x18000c596  pop     rsi
0x18000c597  pop     rbp
0x18000c598  retn
0x18000c599  cmp     r13, rbp
0x18000c59c  jnz     short loc_18000C5A5
0x18000c59e  mov     [rsi+r14*8], r15
0x18000c5a2  mov     r12, r15
0x18000c5a5  mov     [rsi+r14*8+8], r12
0x18000c5aa  mov     rbp, [rsp+78h+arg_0]
0x18000c5b2  mov     r11, [rsp+78h+var_48]
0x18000c5b7  cmp     r11, rdi
0x18000c5ba  jz      short loc_18000C572
0x18000c5bc  lea     rcx, [r11+10h]
0x18000c5c0  call    ??R?$_Conditionally_enabled_hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$00@std@@SA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Conditionally_enabled_hash<std::wstring,1>::operator()(std::wstring const &)
0x18000c5c5  mov     r14, rax
0x18000c5c8  and     r14, [rbp+30h]
0x18000c5cc  add     r14, r14
0x18000c5cf  mov     r12, [rsi+r14*8+8]
0x18000c5d4  cmp     r11, r12
0x18000c5d7  lea     rcx, [rsp+78h+var_58]
0x18000c5dc  setz    bl
0x18000c5df  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(void)
0x18000c5e4  test    bl, bl
0x18000c5e6  jnz     short loc_18000C5F7
0x18000c5e8  mov     r11, [rsp+78h+var_48]
0x18000c5ed  cmp     r11, rdi
0x18000c5f0  jnz     short loc_18000C5D4
0x18000c5f2  jmp     loc_18000C56E
0x18000c5f7  mov     [rsi+r14*8], r15
0x18000c5fb  mov     [rsi+r14*8+8], r15
0x18000c600  jmp     short loc_18000C5B2
```
