# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Unchecked_erase(std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> *,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const)

- ea: `0x18001d6ac`
- end: `0x18001d7d7`
- name: `?_Unchecked_erase@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@AEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@PEAU32@QEAU32@@Z`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010a68`

## callees

- `0x1800109b0`
- `0x18001d2b8`
- `0x18001d6ac`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Unchecked_erase(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v6; // r12
  _QWORD *v7; // r15
  __int64 v8; // rsi
  __int64 v9; // rax
  __int64 v10; // r11
  __int64 v11; // r14
  __int64 v12; // rax
  __int64 v13; // r13
  bool v14; // bl
  __int64 v15; // rcx
  _QWORD *v16; // rax
  __int64 v18; // rax
  __int64 v19; // r12
  bool v20; // bl
  _QWORD *v21; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v22; // [rsp+28h] [rbp-50h]
  __int64 v23; // [rsp+30h] [rbp-48h]
  __int64 v25; // [rsp+88h] [rbp+10h]

  if ( a2 != a3 )
  {
    v6 = *(_QWORD **)(a2 + 8);
    v7 = (_QWORD *)a1[1];
    v8 = a1[3];
    v21 = a1 + 1;
    v22 = v6;
    v23 = a2;
    v9 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()((__int64)a1, (_QWORD *)(a2 + 16));
    v11 = 2 * (a1[6] & v9);
    v12 = *(_QWORD *)(v8 + 16 * (a1[6] & v9) + 8);
    v13 = *(_QWORD *)(v8 + 8 * v11);
    v25 = *(_QWORD *)(v8 + 8 * v11 + 8);
    while ( 1 )
    {
      v14 = v10 == v12;
      std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(&v21);
      if ( v14 )
        break;
      v10 = v23;
      v12 = v25;
      if ( v23 == a3 )
      {
        if ( v13 == a2 )
LABEL_6:
          *(_QWORD *)(v8 + 8 * v11) = v10;
        goto LABEL_7;
      }
    }
    if ( v13 == a2 )
    {
      *(_QWORD *)(v8 + 8 * v11) = v7;
      v6 = v7;
    }
    for ( *(_QWORD *)(v8 + 8 * v11 + 8) = v6; ; *(_QWORD *)(v8 + 8 * v11 + 8) = v7 )
    {
      v10 = v23;
      if ( v23 == a3 )
        break;
      v18 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(v15, (_QWORD *)(v23 + 16));
      v11 = 2 * (a1[6] & v18);
      v19 = *(_QWORD *)(v8 + 16 * (a1[6] & v18) + 8);
      while ( 1 )
      {
        v20 = v10 == v19;
        std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(&v21);
        if ( v20 )
          break;
        v10 = v23;
        if ( v23 == a3 )
          goto LABEL_6;
      }
      *(_QWORD *)(v8 + 8 * v11) = v7;
    }
LABEL_7:
    v16 = v22;
    *v22 = v10;
    *(_QWORD *)(v10 + 8) = v16;
  }
  return a3;
}

```

## disassembly

```asm
0x18001d6ac  mov     r11, rsp
0x18001d6af  mov     [r11+18h], rbx
0x18001d6b3  mov     [r11+8], rcx
0x18001d6b7  push    rbp
0x18001d6b8  push    rsi
0x18001d6b9  push    rdi
0x18001d6ba  push    r12
0x18001d6bc  push    r13
0x18001d6be  push    r14
0x18001d6c0  push    r15
0x18001d6c2  sub     rsp, 40h
0x18001d6c6  mov     rdi, r8
0x18001d6c9  mov     rbp, rdx
0x18001d6cc  mov     rbx, rcx
0x18001d6cf  cmp     rdx, r8
0x18001d6d2  jz      short loc_18001D752
0x18001d6d4  mov     r12, [rdx+8]
0x18001d6d8  lea     rax, [rcx+8]
0x18001d6dc  mov     r15, [rax]
0x18001d6df  mov     rsi, [rcx+18h]
0x18001d6e3  mov     [r11-58h], rax
0x18001d6e7  mov     [r11-50h], r12
0x18001d6eb  mov     r11, rdx
0x18001d6ee  mov     [rsp+78h+var_48], rdx
0x18001d6f3  add     rdx, 10h
0x18001d6f7  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x18001d6fc  mov     r14, rax
0x18001d6ff  and     r14, [rbx+30h]
0x18001d703  add     r14, r14
0x18001d706  mov     rax, [rsi+r14*8+8]
0x18001d70b  mov     r13, [rsi+r14*8]
0x18001d70f  mov     [rsp+78h+arg_8], rax
0x18001d717  cmp     r11, rax
0x18001d71a  lea     rcx, [rsp+78h+var_58]
0x18001d71f  setz    bl
0x18001d722  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001d727  test    bl, bl
0x18001d729  jnz     short loc_18001D76E
0x18001d72b  mov     r11, [rsp+78h+var_48]
0x18001d730  mov     rax, [rsp+78h+arg_8]
0x18001d738  cmp     r11, rdi
0x18001d73b  jnz     short loc_18001D717
0x18001d73d  cmp     r13, rbp
0x18001d740  jnz     short loc_18001D746
0x18001d742  mov     [rsi+r14*8], r11
0x18001d746  mov     rax, [rsp+78h+var_50]
0x18001d74b  mov     [rax], r11
0x18001d74e  mov     [r11+8], rax
0x18001d752  mov     rbx, [rsp+78h+arg_10]
0x18001d75a  mov     rax, rdi
0x18001d75d  add     rsp, 40h
0x18001d761  pop     r15
0x18001d763  pop     r14
0x18001d765  pop     r13
0x18001d767  pop     r12
0x18001d769  pop     rdi
0x18001d76a  pop     rsi
0x18001d76b  pop     rbp
0x18001d76c  retn
0x18001d76e  cmp     r13, rbp
0x18001d771  jnz     short loc_18001D77A
0x18001d773  mov     [rsi+r14*8], r15
0x18001d777  mov     r12, r15
0x18001d77a  mov     [rsi+r14*8+8], r12
0x18001d77f  mov     rbp, [rsp+78h+arg_0]
0x18001d787  mov     r11, [rsp+78h+var_48]
0x18001d78c  cmp     r11, rdi
0x18001d78f  jz      short loc_18001D746
0x18001d791  lea     rdx, [r11+10h]
0x18001d795  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x18001d79a  mov     r14, rax
0x18001d79d  and     r14, [rbp+30h]
0x18001d7a1  add     r14, r14
0x18001d7a4  mov     r12, [rsi+r14*8+8]
0x18001d7a9  cmp     r11, r12
0x18001d7ac  lea     rcx, [rsp+78h+var_58]
0x18001d7b1  setz    bl
0x18001d7b4  call    ?_Bump_erased@_Range_eraser@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@QEAAXXZ; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Range_eraser::_Bump_erased(void)
0x18001d7b9  test    bl, bl
0x18001d7bb  jnz     short loc_18001D7CC
0x18001d7bd  mov     r11, [rsp+78h+var_48]
0x18001d7c2  cmp     r11, rdi
0x18001d7c5  jnz     short loc_18001D7A9
0x18001d7c7  jmp     loc_18001D742
0x18001d7cc  mov     [rsi+r14*8], r15
0x18001d7d0  mov     [rsi+r14*8+8], r15
0x18001d7d5  jmp     short loc_18001D787
```
