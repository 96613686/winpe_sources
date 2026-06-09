# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(basic_xstr_t<wchar_t> const &)

- ea: `0x180020930`
- end: `0x180020990`
- name: `?_Lbound@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEBAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@AEBV?$basic_xstr_t@_W@@@Z`
- size: `96`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800203e4`
- `0x180020488`

## callees

- `0x180020930`
- `0x180023c42`

## pseudocode

```c
__int64 *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lbound(
        __int64 a1,
        int *a2)
{
  __int64 *v2; // rdi
  __int64 *v3; // rbx
  const void *v4; // rbp
  int v5; // esi
  int v6; // eax
  int v7; // eax

  v2 = *(__int64 **)(a1 + 8);
  v3 = (__int64 *)v2[1];
  if ( !*((_BYTE *)v3 + 49) )
  {
    v4 = (const void *)*((_QWORD *)a2 + 1);
    v5 = *a2;
    do
    {
      v6 = *((_DWORD *)v3 + 6);
      if ( v6 >= v5 )
        v6 = v5;
      v7 = memcmp_0((const void *)v3[4], v4, 2LL * v6);
      if ( v7 )
      {
        if ( v7 < 0 )
          goto LABEL_11;
      }
      else if ( *((_DWORD *)v3 + 6) < v5 )
      {
LABEL_11:
        v3 = (__int64 *)v3[2];
        continue;
      }
      v2 = v3;
      v3 = (__int64 *)*v3;
    }
    while ( !*((_BYTE *)v3 + 49) );
  }
  return v2;
}

```

## disassembly

```asm
0x180020930  push    rbx
0x180020932  push    rbp
0x180020933  push    rsi
0x180020934  push    rdi
0x180020935  sub     rsp, 28h
0x180020939  mov     rdi, [rcx+8]
0x18002093d  mov     rbx, [rdi+8]
0x180020941  cmp     byte ptr [rbx+31h], 0
0x180020945  jnz     short loc_180020979
0x180020947  mov     rbp, [rdx+8]
0x18002094b  mov     esi, [rdx]
0x18002094d  mov     eax, [rbx+18h]
0x180020950  mov     rdx, rbp; Buf2
0x180020953  mov     rcx, [rbx+20h]; Buf1
0x180020957  cmp     eax, esi
0x180020959  cmovge  eax, esi
0x18002095c  movsxd  r8, eax
0x18002095f  add     r8, r8; Size
0x180020962  call    memcmp_0
0x180020967  test    eax, eax
0x180020969  jz      short loc_180020985
0x18002096b  js      short loc_18002098A
0x18002096d  mov     rdi, rbx
0x180020970  mov     rbx, [rbx]
0x180020973  cmp     byte ptr [rbx+31h], 0
0x180020977  jz      short loc_18002094D
0x180020979  mov     rax, rdi
0x18002097c  add     rsp, 28h
0x180020980  pop     rdi
0x180020981  pop     rsi
0x180020982  pop     rbp
0x180020983  pop     rbx
0x180020984  retn
0x180020985  cmp     [rbx+18h], esi
0x180020988  jge     short loc_18002096D
0x18002098a  mov     rbx, [rbx+10h]
0x18002098e  jmp     short loc_180020973
```
