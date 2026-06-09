# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Find_last<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64)

- ea: `0x180009388`
- end: `0x1800093fa`
- name: `??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z`
- size: `114`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, __int64, __int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000983c`
- `0x18000c784`
- `0x18000da04`

## callees

- `0x1800087c8`
- `0x180009388`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
        _QWORD *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rsi
  _QWORD *v6; // rdx
  _QWORD *v8; // rdi
  _QWORD *v9; // rsi

  v5 = a1[3];
  v6 = (_QWORD *)a1[1];
  v8 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]) + 8);
  if ( v8 == v6 )
  {
    *a2 = v6;
LABEL_3:
    a2[1] = 0;
  }
  else
  {
    v9 = *(_QWORD **)(v5 + 16 * (a4 & a1[6]));
    while ( std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(
              (__int64)a1,
              a3,
              (__int64)(v8 + 2)) )
    {
      if ( v8 == v9 )
      {
        *a2 = v8;
        goto LABEL_3;
      }
      v8 = (_QWORD *)v8[1];
    }
    *a2 = *v8;
    a2[1] = v8;
  }
  return a2;
}

```

## disassembly

```asm
0x180009388  push    rbx
0x18000938a  push    rbp
0x18000938b  push    rsi
0x18000938c  push    rdi
0x18000938d  sub     rsp, 28h
0x180009391  mov     rax, [rcx+30h]
0x180009395  mov     rbx, rdx
0x180009398  mov     rsi, [rcx+18h]
0x18000939c  and     rax, r9
0x18000939f  mov     rdx, [rcx+8]
0x1800093a3  add     rax, rax
0x1800093a6  mov     rbp, r8
0x1800093a9  mov     rdi, [rsi+rax*8+8]
0x1800093ae  cmp     rdi, rdx
0x1800093b1  jnz     short loc_1800093C0
0x1800093b3  mov     [rbx], rdx
0x1800093b6  mov     qword ptr [rbx+8], 0
0x1800093be  jmp     short loc_1800093EE
0x1800093c0  mov     rsi, [rsi+rax*8]
0x1800093c4  lea     r8, [rdi+10h]
0x1800093c8  mov     rdx, rbp
0x1800093cb  call    ??$?RV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V01@@?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@0@Z; std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>::operator()<std::wstring,std::wstring>(std::wstring const &,std::wstring const &)
0x1800093d0  test    al, al
0x1800093d2  jz      short loc_1800093E4
0x1800093d4  cmp     rdi, rsi
0x1800093d7  jz      short loc_1800093DF
0x1800093d9  mov     rdi, [rdi+8]
0x1800093dd  jmp     short loc_1800093C4
0x1800093df  mov     [rbx], rdi
0x1800093e2  jmp     short loc_1800093B6
0x1800093e4  mov     rax, [rdi]
0x1800093e7  mov     [rbx], rax
0x1800093ea  mov     [rbx+8], rdi
0x1800093ee  mov     rax, rbx
0x1800093f1  add     rsp, 28h
0x1800093f5  pop     rdi
0x1800093f6  pop     rsi
0x1800093f7  pop     rbp
0x1800093f8  pop     rbx
0x1800093f9  retn
```
