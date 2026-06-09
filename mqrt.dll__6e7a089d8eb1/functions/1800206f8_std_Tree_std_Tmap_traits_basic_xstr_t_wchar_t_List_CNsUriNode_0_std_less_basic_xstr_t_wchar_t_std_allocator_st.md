# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)

- ea: `0x1800206f8`
- end: `0x180020748`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800206f8`
- `0x180020a60`

## callees

- `0x1800206f8`

## import_xrefs

- `msvcrt!free` at `0x180020728`
- `msvcrt!free` at `0x180020728`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(
        __int64 a1,
        void *a2)
{
  void *v2; // rdi
  _QWORD *v4; // rbx

  v2 = a2;
  v4 = a2;
  if ( !*((_BYTE *)a2 + 49) )
  {
    do
    {
      std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(
        a1,
        v4[2]);
      v4 = (_QWORD *)*v4;
      free(v2);
      v2 = v4;
    }
    while ( !*((_BYTE *)v4 + 49) );
  }
}

```

## disassembly

```asm
0x1800206f8  mov     [rsp+arg_0], rbx
0x1800206fd  mov     [rsp+arg_8], rsi
0x180020702  push    rdi
0x180020703  sub     rsp, 20h
0x180020707  mov     rdi, rdx
0x18002070a  mov     rsi, rcx
0x18002070d  mov     rbx, rdx
0x180020710  cmp     byte ptr [rdx+31h], 0
0x180020714  jnz     short loc_180020738
0x180020716  mov     rdx, [rbx+10h]
0x18002071a  mov     rcx, rsi
0x18002071d  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020722  mov     rbx, [rbx]
0x180020725  mov     rcx, rdi; Block
0x180020728  call    cs:__imp_free
0x18002072e  nop
0x18002072f  mov     rdi, rbx
0x180020732  cmp     byte ptr [rbx+31h], 0
0x180020736  jz      short loc_180020716
0x180020738  mov     rbx, [rsp+28h+arg_0]
0x18002073d  mov     rsi, [rsp+28h+arg_8]
0x180020742  add     rsp, 20h
0x180020746  pop     rdi
0x180020747  retn
```
