# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(void)

- ea: `0x18002067c`
- end: `0x1800206ac`
- name: `?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@XZ`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020130`

## callees

- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(
        __int64 a1,
        const char *a2,
        int a3)
{
  _QWORD *result; // rax

  result = MmAllocate(0x38u, a2, a3);
  *result = 0;
  result[1] = 0;
  result[2] = 0;
  *((_WORD *)result + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x18002067c  mov     [rsp+arg_0], rcx
0x180020681  sub     rsp, 28h
0x180020685  mov     ecx, 38h ; '8'; unsigned __int64
0x18002068a  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18002068f  mov     [rsp+28h+arg_0], rax
0x180020694  xor     ecx, ecx
0x180020696  mov     [rax], rcx
0x180020699  mov     [rax+8], rcx
0x18002069d  mov     [rax+10h], rcx
0x1800206a1  mov     word ptr [rax+30h], 1
0x1800206a7  add     rsp, 28h
0x1800206ab  retn
```
