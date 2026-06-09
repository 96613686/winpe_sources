# std::_Hash<std::_Umap_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const,std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,void *> * const)

- ea: `0x18000c130`
- end: `0x18000c17f`
- name: `?_Insert_new_node_before@?$_Hash@V?$_Umap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAPEAU?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@_KQEAU32@1@Z`
- size: `79`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000983c`
- `0x18000da04`

## callees

- `0x18000c130`

## pseudocode

```c
_QWORD *__fastcall std::_Hash<std::_Umap_traits<std::wstring,std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Insert_new_node_before(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v4; // r10
  __int64 v5; // rax
  __int64 v6; // rdx
  __int64 v7; // rax
  __int64 v8; // r11

  v4 = *(_QWORD **)(a3 + 8);
  ++a1[2];
  *a4 = a3;
  a4[1] = v4;
  *v4 = a4;
  *(_QWORD *)(a3 + 8) = a4;
  v5 = a2 & a1[6];
  v6 = a1[3];
  v7 = 2 * v5;
  v8 = *(_QWORD *)(v6 + 8 * v7);
  if ( v8 == a1[1] )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
LABEL_6:
    *(_QWORD *)(v6 + 8 * v7 + 8) = a4;
    return a4;
  }
  if ( v8 == a3 )
  {
    *(_QWORD *)(v6 + 8 * v7) = a4;
  }
  else if ( *(_QWORD **)(v6 + 8 * v7 + 8) == v4 )
  {
    goto LABEL_6;
  }
  return a4;
}

```

## disassembly

```asm
0x18000c130  mov     r10, [r8+8]
0x18000c134  inc     qword ptr [rcx+10h]
0x18000c138  mov     [r9], r8
0x18000c13b  mov     [r9+8], r10
0x18000c13f  mov     [r10], r9
0x18000c142  mov     [r8+8], r9
0x18000c146  mov     rax, [rcx+30h]
0x18000c14a  and     rax, rdx
0x18000c14d  mov     rdx, [rcx+18h]
0x18000c151  add     rax, rax
0x18000c154  mov     r11, [rdx+rax*8]
0x18000c158  cmp     r11, [rcx+8]
0x18000c15c  jnz     short loc_18000C164
0x18000c15e  mov     [rdx+rax*8], r9
0x18000c162  jmp     short loc_18000C176
0x18000c164  cmp     r11, r8
0x18000c167  jnz     short loc_18000C16F
0x18000c169  mov     [rdx+rax*8], r9
0x18000c16d  jmp     short loc_18000C17B
0x18000c16f  cmp     [rdx+rax*8+8], r10
0x18000c174  jnz     short loc_18000C17B
0x18000c176  mov     [rdx+rax*8+8], r9
0x18000c17b  mov     rax, r9
0x18000c17e  retn
```
