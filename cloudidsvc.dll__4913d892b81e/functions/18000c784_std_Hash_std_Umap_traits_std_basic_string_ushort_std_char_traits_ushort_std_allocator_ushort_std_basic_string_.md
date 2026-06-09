# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::count(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18000c784`
- end: `0x18000c7ee`
- name: `?count@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEBA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `106`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000b67c`

## callees

- `0x180009388`
- `0x18000c338`
- `0x18000c784`

## pseudocode

```c
_BOOL8 std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::count()
{
  __int64 v0; // rax
  __int64 v1; // rdx
  _QWORD *v2; // r11
  __int64 v3; // r9
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // r10
  __int64 v6; // rcx
  _QWORD v8[3]; // [rsp+20h] [rbp-18h] BYREF

  v0 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  v3 = 0xCBF29CE484222325uLL;
  v4 = 0;
  v5 = 2LL * *(_QWORD *)(v1 + 16);
  if ( v5 )
  {
    do
    {
      v6 = *(unsigned __int8 *)(v0 + v4++);
      v3 = 0x100000001B3LL * (v6 ^ v3);
    }
    while ( v4 < v5 );
  }
  return std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(
           v2,
           v8,
           v1,
           v3)[1] != 0;
}

```

## disassembly

```asm
0x18000c784  push    rbx
0x18000c786  sub     rsp, 30h
0x18000c78a  mov     r11, rcx
0x18000c78d  mov     rcx, rdx
0x18000c790  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000c795  mov     r10, [rdx+10h]
0x18000c799  mov     r9, 0CBF29CE484222325h
0x18000c7a3  mov     r8d, 0
0x18000c7a9  add     r10, r10
0x18000c7ac  jz      short loc_18000C7CC
0x18000c7ae  movzx   ecx, byte ptr [rax+r8]
0x18000c7b3  mov     rbx, 100000001B3h
0x18000c7bd  xor     r9, rcx
0x18000c7c0  inc     r8
0x18000c7c3  imul    r9, rbx
0x18000c7c7  cmp     r8, r10
0x18000c7ca  jb      short loc_18000C7AE
0x18000c7cc  mov     r8, rdx
0x18000c7cf  mov     rcx, r11
0x18000c7d2  lea     rdx, [rsp+38h+var_18]
0x18000c7d7  call    ??$_Find_last@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_K@Z; std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_last<std::wstring>(std::wstring const &,unsigned __int64)
0x18000c7dc  xor     ecx, ecx
0x18000c7de  cmp     [rax+8], rcx
0x18000c7e2  setnz   cl
0x18000c7e5  mov     rax, rcx
0x18000c7e8  add     rsp, 30h
0x18000c7ec  pop     rbx
0x18000c7ed  retn
```
