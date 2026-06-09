# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ulong,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,ulong>>,0>>::find(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010ed4`
- end: `0x180010f2f`
- name: `?find@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `91`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000c4dc`
- `0x18000dd10`
- `0x18000f308`

## callees

- `0x180005e50`
- `0x180009f40`
- `0x18001074c`
- `0x180010ed4`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::find(
        _QWORD *a1,
        _QWORD *a2)
{
  const unsigned __int8 *v4; // rax
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // r8
  __int64 appended; // rax
  __int64 v8; // r11
  __int64 v9; // rcx
  _QWORD v11[3]; // [rsp+20h] [rbp-18h] BYREF

  v4 = (const unsigned __int8 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  appended = std::_Fnv1a_append_bytes(v5, v4, v6);
  v9 = std::_Hash<std::_Umap_traits<std::wstring,unsigned long,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,unsigned long>>,0>>::_Find_last<std::wstring>(
         a1,
         v11,
         v8,
         appended)[1];
  if ( !v9 )
    v9 = a1[1];
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x180010ed4  mov     [rsp+arg_0], rbx
0x180010ed9  push    rdi
0x180010eda  sub     rsp, 30h
0x180010ede  mov     r11, r8
0x180010ee1  mov     rdi, rcx
0x180010ee4  mov     r8, [r8+10h]
0x180010ee8  mov     rcx, r11
0x180010eeb  add     r8, r8
0x180010eee  mov     rbx, rdx
0x180010ef1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180010ef6  mov     rdx, rax; unsigned __int8 *
0x180010ef9  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180010efe  mov     r9, rax
0x180010f01  lea     rdx, [rsp+38h+var_18]
0x180010f06  mov     rcx, rdi
0x180010f09  mov     r8, r11
0x180010f0c  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KV?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,ulong,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,ulong>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x180010f11  mov     rcx, [rax+8]
0x180010f15  test    rcx, rcx
0x180010f18  jnz     short loc_180010F1E
0x180010f1a  mov     rcx, [rdi+8]
0x180010f1e  mov     [rbx], rcx
0x180010f21  mov     rax, rbx
0x180010f24  mov     rbx, [rsp+38h+arg_0]
0x180010f29  add     rsp, 30h
0x180010f2d  pop     rdi
0x180010f2e  retn
```
