# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)

- ea: `0x180020a0c`
- end: `0x180020a58`
- name: `?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020750`
- `0x180020b48`

## callees

- `0x180020a0c`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v2; // r8
  __int64 v3; // rax
  _QWORD *result; // rax

  v2 = *a2;
  *a2 = *(_QWORD *)(*a2 + 16LL);
  v3 = *(_QWORD *)(v2 + 16);
  if ( !*(_BYTE *)(v3 + 49) )
    *(_QWORD *)(v3 + 8) = a2;
  *(_QWORD *)(v2 + 8) = a2[1];
  result = *(_QWORD **)(a1 + 8);
  if ( a2 == (_QWORD *)result[1] )
  {
    result[1] = v2;
  }
  else
  {
    result = (_QWORD *)a2[1];
    if ( a2 == (_QWORD *)result[2] )
      result[2] = v2;
    else
      *result = v2;
  }
  *(_QWORD *)(v2 + 16) = a2;
  a2[1] = v2;
  return result;
}

```

## disassembly

```asm
0x180020a0c  mov     r8, [rdx]
0x180020a0f  mov     rax, [r8+10h]
0x180020a13  mov     [rdx], rax
0x180020a16  mov     rax, [r8+10h]
0x180020a1a  cmp     byte ptr [rax+31h], 0
0x180020a1e  jnz     short loc_180020A24
0x180020a20  mov     [rax+8], rdx
0x180020a24  mov     rax, [rdx+8]
0x180020a28  mov     [r8+8], rax
0x180020a2c  mov     rax, [rcx+8]
0x180020a30  cmp     rdx, [rax+8]
0x180020a34  jnz     short loc_180020A3C
0x180020a36  mov     [rax+8], r8
0x180020a3a  jmp     short loc_180020A4F
0x180020a3c  mov     rax, [rdx+8]
0x180020a40  cmp     rdx, [rax+10h]
0x180020a44  jnz     short loc_180020A4C
0x180020a46  mov     [rax+10h], r8
0x180020a4a  jmp     short loc_180020A4F
0x180020a4c  mov     [rax], r8
0x180020a4f  mov     [r8+10h], rdx
0x180020a53  mov     [rdx+8], r8
0x180020a57  retn
```
