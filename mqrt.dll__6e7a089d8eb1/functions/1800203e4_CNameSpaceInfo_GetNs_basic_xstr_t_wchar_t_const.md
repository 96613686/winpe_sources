# CNameSpaceInfo::GetNs(basic_xstr_t<wchar_t> const &)

- ea: `0x1800203e4`
- end: `0x180020482`
- name: `?GetNs@CNameSpaceInfo@@QEBA?BUCNsUri@@AEBV?$basic_xstr_t@_W@@@Z`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001f068`

## callees

- `0x1800203e4`
- `0x180020930`
- `0x180023c42`

## pseudocode

```c
__int64 __fastcall CNameSpaceInfo::GetNs(__int64 *a1, __int64 a2, const void **a3)
{
  __int64 v3; // rbx
  __int64 v6; // rax
  __int64 v7; // rsi
  int v8; // ebx
  int v9; // ecx
  int v10; // eax
  _QWORD *v12; // rax
  _QWORD *v13; // rcx
  __int64 v14; // xmm1_8
  int v15; // [rsp+24h] [rbp-34h]

  v3 = *a1;
  v6 = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(*a1 + 16);
  v7 = v6;
  if ( v6 == *(_QWORD *)(v3 + 24) )
    goto LABEL_6;
  v8 = *(_DWORD *)(v6 + 24);
  v9 = *(_DWORD *)a3;
  if ( *(_DWORD *)a3 >= v8 )
    v9 = *(_DWORD *)(v6 + 24);
  v10 = memcmp_0(a3[1], *(const void **)(v6 + 32), 2LL * v9);
  if ( v10 )
  {
    if ( v10 < 0 )
      goto LABEL_6;
  }
  else if ( *(_DWORD *)a3 < v8 )
  {
    goto LABEL_6;
  }
  v12 = *(_QWORD **)(v7 + 40);
  v13 = (_QWORD *)*v12;
  if ( (_QWORD *)*v12 != v12 && v13 )
  {
    v14 = v13[6];
    *(_OWORD *)a2 = *((_OWORD *)v13 + 2);
    *(_QWORD *)(a2 + 16) = v14;
    return a2;
  }
LABEL_6:
  *(_DWORD *)(a2 + 4) = v15;
  *(_DWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = 0;
  return a2;
}

```

## disassembly

```asm
0x1800203e4  push    rbx
0x1800203e6  push    rsi
0x1800203e7  push    rdi
0x1800203e8  push    r14
0x1800203ea  sub     rsp, 38h
0x1800203ee  mov     rbx, [rcx]
0x1800203f1  mov     rdi, rdx
0x1800203f4  mov     rdx, r8
0x1800203f7  mov     r14, r8
0x1800203fa  lea     rcx, [rbx+10h]
0x1800203fe  call    ?_Lbound@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEBAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@AEBV?$basic_xstr_t@_W@@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(basic_xstr_t<wchar_t> const &)
0x180020403  mov     rsi, rax
0x180020406  cmp     rax, [rbx+18h]
0x18002040a  jz      short loc_180020430
0x18002040c  mov     ebx, [rax+18h]
0x18002040f  mov     ecx, [r14]
0x180020412  cmp     ecx, ebx
0x180020414  mov     rdx, [rax+20h]; Buf2
0x180020418  cmovge  ecx, ebx
0x18002041b  movsxd  r8, ecx
0x18002041e  mov     rcx, [r14+8]; Buf1
0x180020422  add     r8, r8; Size
0x180020425  call    memcmp_0
0x18002042a  test    eax, eax
0x18002042c  jz      short loc_180020459
0x18002042e  jns     short loc_18002045E
0x180020430  mov     eax, [rsp+58h+var_34]
0x180020434  mov     [rdi+4], eax
0x180020437  mov     dword ptr [rdi], 0
0x18002043d  mov     qword ptr [rdi+8], 0
0x180020445  mov     dword ptr [rdi+10h], 0
0x18002044c  mov     rax, rdi
0x18002044f  add     rsp, 38h
0x180020453  pop     r14
0x180020455  pop     rdi
0x180020456  pop     rsi
0x180020457  pop     rbx
0x180020458  retn
0x180020459  cmp     [r14], ebx
0x18002045c  jl      short loc_180020430
0x18002045e  mov     rax, [rsi+28h]
0x180020462  mov     rcx, [rax]
0x180020465  cmp     rcx, rax
0x180020468  jz      short loc_180020430
0x18002046a  test    rcx, rcx
0x18002046d  jz      short loc_180020430
0x18002046f  movups  xmm0, xmmword ptr [rcx+20h]
0x180020473  movsd   xmm1, qword ptr [rcx+30h]
0x180020478  movups  xmmword ptr [rdi], xmm0
0x18002047b  movsd   qword ptr [rdi+10h], xmm1
0x180020480  jmp     short loc_18002044C
```
