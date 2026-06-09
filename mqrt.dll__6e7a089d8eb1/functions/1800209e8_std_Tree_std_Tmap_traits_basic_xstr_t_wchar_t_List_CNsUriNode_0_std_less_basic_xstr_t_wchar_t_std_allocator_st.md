# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)

- ea: `0x1800209e8`
- end: `0x180020a04`
- name: `?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@@Z`
- size: `28`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020a60`
- `0x180020b48`

## callees

- `0x1800209e8`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(
        _QWORD *a1)
{
  __int64 *v1; // rdx

  v1 = (__int64 *)*a1;
  if ( !*(_BYTE *)(*a1 + 49LL) )
  {
    do
    {
      a1 = v1;
      v1 = (__int64 *)*v1;
    }
    while ( !*((_BYTE *)v1 + 49) );
  }
  return a1;
}

```

## disassembly

```asm
0x1800209e8  mov     rdx, [rcx]
0x1800209eb  cmp     byte ptr [rdx+31h], 0
0x1800209ef  jnz     short loc_180020A00
0x1800209f1  mov     rax, [rdx]
0x1800209f4  mov     rcx, rdx
0x1800209f7  mov     rdx, rax
0x1800209fa  cmp     byte ptr [rax+31h], 0
0x1800209fe  jz      short loc_1800209F1
0x180020a00  mov     rax, rcx
0x180020a03  retn
```
