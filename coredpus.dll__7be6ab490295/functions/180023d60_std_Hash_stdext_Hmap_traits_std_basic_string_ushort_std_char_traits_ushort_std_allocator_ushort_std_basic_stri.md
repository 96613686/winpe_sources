# std::_Hash<stdext::_Hmap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,stdext::hash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Erase<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180023d60`
- end: `0x180023e01`
- name: `??$_Erase@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@AEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180024f40`

## callees

- `0x1800109b0`
- `0x180017aec`
- `0x180017bc4`
- `0x180023d60`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Erase<std::wstring>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v3; // rdi
  _QWORD *v4; // r11
  _QWORD *v5; // rdx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v3 = stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()((__int64)a1, a2);
  v5 = (_QWORD *)std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
                   a1,
                   v11,
                   v4,
                   v3)[1];
  if ( !v5 )
    return 0;
  v6 = a1[3];
  v7 = 2 * (v3 & a1[6]);
  if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6]) + 8) == v5 )
  {
    if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
    {
      v8 = a1[1];
      *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = v8;
    }
    else
    {
      v8 = v5[1];
    }
    *(_QWORD *)(v6 + 8 * v7 + 8) = v8;
  }
  else if ( *(_QWORD **)(v6 + 16 * (v3 & a1[6])) == v5 )
  {
    *(_QWORD *)(v6 + 16 * (v3 & a1[6])) = *v5;
  }
  v9 = *v5;
  --a1[2];
  *(_QWORD *)v5[1] = v9;
  *(_QWORD *)(v9 + 8) = v5[1];
  std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>();
  return 1;
}

```

## disassembly

```asm
0x180023d60  mov     [rsp+arg_0], rbx
0x180023d65  push    rdi
0x180023d66  sub     rsp, 30h
0x180023d6a  mov     r11, rdx
0x180023d6d  mov     rbx, rcx
0x180023d70  call    ??R?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; stdext::hash_compare<std::wstring,std::less<std::wstring>>::operator()(std::wstring const &)
0x180023d75  mov     r9, rax
0x180023d78  lea     rdx, [rsp+38h+var_18]
0x180023d7d  mov     r8, r11
0x180023d80  mov     rcx, rbx
0x180023d83  mov     rdi, rax
0x180023d86  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Hmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$hash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@stdext@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<stdext::_Hmap_traits<std::wstring,std::wstring,stdext::hash_compare<std::wstring,std::less<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180023d8b  mov     rdx, [rax+8]
0x180023d8f  test    rdx, rdx
0x180023d92  jz      short loc_180023DF3
0x180023d94  mov     rcx, [rbx+30h]
0x180023d98  mov     r8, [rbx+18h]
0x180023d9c  and     rcx, rdi
0x180023d9f  add     rcx, rcx
0x180023da2  cmp     [r8+rcx*8+8], rdx
0x180023da7  jnz     short loc_180023DC4
0x180023da9  cmp     [r8+rcx*8], rdx
0x180023dad  jnz     short loc_180023DB9
0x180023daf  mov     rax, [rbx+8]
0x180023db3  mov     [r8+rcx*8], rax
0x180023db7  jmp     short loc_180023DBD
0x180023db9  mov     rax, [rdx+8]
0x180023dbd  mov     [r8+rcx*8+8], rax
0x180023dc2  jmp     short loc_180023DD1
0x180023dc4  cmp     [r8+rcx*8], rdx
0x180023dc8  jnz     short loc_180023DD1
0x180023dca  mov     rax, [rdx]
0x180023dcd  mov     [r8+rcx*8], rax
0x180023dd1  mov     rcx, [rdx]
0x180023dd4  dec     qword ptr [rbx+10h]
0x180023dd8  mov     rax, [rdx+8]
0x180023ddc  mov     [rax], rcx
0x180023ddf  mov     rax, [rdx+8]
0x180023de3  mov     [rcx+8], rax
0x180023de7  call    ??$_Freenode@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::pair<std::wstring const,std::wstring>,void *>::_Freenode<std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_List_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_List_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x180023dec  mov     eax, 1
0x180023df1  jmp     short loc_180023DF5
0x180023df3  xor     eax, eax
0x180023df5  mov     rbx, [rsp+38h+arg_0]
0x180023dfa  add     rsp, 30h
0x180023dfe  pop     rdi
0x180023dff  retn
```
