# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &,char)

- ea: `0x180020610`
- end: `0x180020673`
- name: `?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@00AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@D@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020750`

## callees

- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(
        __int64 a1,
        const char *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  char *result; // rax

  result = (char *)MmAllocate(0x38u, a2, a3);
  *(_QWORD *)result = a2;
  *((_QWORD *)result + 1) = a3;
  *((_QWORD *)result + 2) = a4;
  *(_OWORD *)(result + 24) = *(_OWORD *)a5;
  *((_QWORD *)result + 5) = *(_QWORD *)(a5 + 16);
  *((_WORD *)result + 24) = 0;
  return result;
}

```

## disassembly

```asm
0x180020610  mov     [rsp+arg_8], rbx
0x180020615  mov     [rsp+arg_10], rsi
0x18002061a  mov     [rsp+arg_0], rcx
0x18002061f  push    rdi
0x180020620  sub     rsp, 20h
0x180020624  mov     rbx, r9
0x180020627  mov     rdi, r8
0x18002062a  mov     rsi, rdx
0x18002062d  mov     ecx, 38h ; '8'; unsigned __int64
0x180020632  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180020637  mov     [rsp+28h+arg_0], rax
0x18002063c  mov     [rax], rsi
0x18002063f  mov     [rax+8], rdi
0x180020643  mov     [rax+10h], rbx
0x180020647  mov     rcx, [rsp+28h+arg_20]
0x18002064c  movups  xmm0, xmmword ptr [rcx]
0x18002064f  movups  xmmword ptr [rax+18h], xmm0
0x180020653  movsd   xmm1, qword ptr [rcx+10h]
0x180020658  movsd   qword ptr [rax+28h], xmm1
0x18002065d  mov     word ptr [rax+30h], 0
0x180020663  mov     rbx, [rsp+28h+arg_8]
0x180020668  mov     rsi, [rsp+28h+arg_10]
0x18002066d  add     rsp, 20h
0x180020671  pop     rdi
0x180020672  retn
```
