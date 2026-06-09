# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)

- ea: `0x180020998`
- end: `0x1800209e2`
- name: `?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020750`
- `0x180020b48`

## callees

- `0x180020998`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v2; // r8
  _QWORD *result; // rax

  v2 = *(_QWORD **)(a2 + 16);
  *(_QWORD *)(a2 + 16) = *v2;
  if ( !*(_BYTE *)(*v2 + 49LL) )
    *(_QWORD *)(*v2 + 8LL) = a2;
  v2[1] = *(_QWORD *)(a2 + 8);
  result = *(_QWORD **)(a1 + 8);
  if ( a2 == result[1] )
  {
    result[1] = v2;
  }
  else
  {
    result = *(_QWORD **)(a2 + 8);
    if ( a2 == *result )
      *result = v2;
    else
      result[2] = v2;
  }
  *v2 = a2;
  *(_QWORD *)(a2 + 8) = v2;
  return result;
}

```

## disassembly

```asm
0x180020998  mov     r8, [rdx+10h]
0x18002099c  mov     rax, [r8]
0x18002099f  mov     [rdx+10h], rax
0x1800209a3  mov     rax, [r8]
0x1800209a6  cmp     byte ptr [rax+31h], 0
0x1800209aa  jnz     short loc_1800209B0
0x1800209ac  mov     [rax+8], rdx
0x1800209b0  mov     rax, [rdx+8]
0x1800209b4  mov     [r8+8], rax
0x1800209b8  mov     rax, [rcx+8]
0x1800209bc  cmp     rdx, [rax+8]
0x1800209c0  jnz     short loc_1800209C8
0x1800209c2  mov     [rax+8], r8
0x1800209c6  jmp     short loc_1800209DA
0x1800209c8  mov     rax, [rdx+8]
0x1800209cc  cmp     rdx, [rax]
0x1800209cf  jnz     short loc_1800209D6
0x1800209d1  mov     [rax], r8
0x1800209d4  jmp     short loc_1800209DA
0x1800209d6  mov     [rax+10h], r8
0x1800209da  mov     [r8], rdx
0x1800209dd  mov     [rdx+8], r8
0x1800209e1  retn
```
