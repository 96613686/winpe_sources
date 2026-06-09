# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::iterator,std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::iterator)

- ea: `0x180020a60`
- end: `0x180020b42`
- name: `?erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@0@Z`
- size: `226`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800202c0`

## callees

- `0x1800026fc`
- `0x1800206f8`
- `0x1800209e8`
- `0x180020a60`
- `0x180020b48`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        _QWORD *a4)
{
  _QWORD *v6; // rdx
  __int64 v7; // rbx
  _QWORD *v9; // rax
  _QWORD *v10; // rsi
  __int64 v11; // rcx
  __int64 i; // rax
  __int64 v14; // [rsp+50h] [rbp+8h] BYREF

  v6 = *(_QWORD **)(a1 + 8);
  v7 = a3;
  if ( a3 == *v6 && a4 == v6 )
  {
    std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(
      a1,
      v6[1]);
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) = *(_QWORD *)(a1 + 8);
    v9 = *(_QWORD **)(a1 + 8);
    *(_QWORD *)(a1 + 16) = 0;
    *v9 = v9;
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 16LL) = *(_QWORD *)(a1 + 8);
    *a2 = **(_QWORD **)(a1 + 8);
  }
  else
  {
    while ( (_QWORD *)v7 != a4 )
    {
      v10 = (_QWORD *)v7;
      if ( *(_BYTE *)(v7 + 49) )
        invalid_parameter(0, 0, 0, 0, 0);
      v11 = *(_QWORD *)(v7 + 16);
      if ( *(_BYTE *)(v11 + 49) )
      {
        for ( i = *(_QWORD *)(v7 + 8); !*(_BYTE *)(i + 49) && v7 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v7 = i;
      }
      else
      {
        i = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(v11);
      }
      v7 = i;
      std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(
        a1,
        &v14,
        v10);
    }
    *a2 = v7;
  }
  return a2;
}

```

## disassembly

```asm
0x180020a60  mov     [rsp+arg_8], rbx
0x180020a65  mov     [rsp+arg_10], rsi
0x180020a6a  push    rdi
0x180020a6b  push    r14
0x180020a6d  push    r15
0x180020a6f  sub     rsp, 30h
0x180020a73  mov     r15, rdx
0x180020a76  mov     rdi, r9
0x180020a79  mov     rdx, [rcx+8]
0x180020a7d  mov     rbx, r8
0x180020a80  mov     r14, rcx
0x180020a83  cmp     r8, [rdx]
0x180020a86  jnz     short loc_180020AC1
0x180020a88  cmp     r9, rdx
0x180020a8b  jnz     short loc_180020AC1
0x180020a8d  mov     rdx, [rdx+8]
0x180020a91  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Erase(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020a96  mov     rax, [r14+8]
0x180020a9a  mov     [rax+8], rax
0x180020a9e  mov     rax, [r14+8]
0x180020aa2  mov     qword ptr [r14+10h], 0
0x180020aaa  mov     [rax], rax
0x180020aad  mov     rax, [r14+8]
0x180020ab1  mov     [rax+10h], rax
0x180020ab5  mov     rax, [r14+8]
0x180020ab9  mov     rcx, [rax]
0x180020abc  mov     [r15], rcx
0x180020abf  jmp     short loc_180020B2B
0x180020ac1  cmp     rbx, rdi
0x180020ac4  jz      short loc_180020B28
0x180020ac6  cmp     byte ptr [rbx+31h], 0
0x180020aca  mov     rsi, rbx
0x180020acd  jz      short loc_180020AE9
0x180020acf  xor     r9d, r9d; LineNo
0x180020ad2  mov     [rsp+48h+Reserved], 0; Reserved
0x180020adb  xor     r8d, r8d; FileName
0x180020ade  xor     edx, edx; FunctionName
0x180020ae0  xor     ecx, ecx; Expression
0x180020ae2  call    _invalid_parameter
0x180020ae7  jmp     short loc_180020B16
0x180020ae9  mov     rcx, [rbx+10h]
0x180020aed  cmp     byte ptr [rcx+31h], 0
0x180020af1  jnz     short loc_180020AFA
0x180020af3  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020af8  jmp     short loc_180020B13
0x180020afa  mov     rax, [rbx+8]
0x180020afe  jmp     short loc_180020B0D
0x180020b00  cmp     rbx, [rax+10h]
0x180020b04  jnz     short loc_180020B13
0x180020b06  mov     rbx, rax
0x180020b09  mov     rax, [rax+8]
0x180020b0d  cmp     byte ptr [rax+31h], 0
0x180020b11  jz      short loc_180020B00
0x180020b13  mov     rbx, rax
0x180020b16  mov     r8, rsi
0x180020b19  lea     rdx, [rsp+48h+arg_0]
0x180020b1e  mov     rcx, r14
0x180020b21  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::iterator)
0x180020b26  jmp     short loc_180020AC1
0x180020b28  mov     [r15], rbx
0x180020b2b  mov     rbx, [rsp+48h+arg_8]
0x180020b30  mov     rax, r15
0x180020b33  mov     rsi, [rsp+48h+arg_10]
0x180020b38  add     rsp, 30h
0x180020b3c  pop     r15
0x180020b3e  pop     r14
0x180020b40  pop     rdi
0x180020b41  retn
```
