# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::insert(std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &)

- ea: `0x180020e7c`
- end: `0x180020fcb`
- name: `?insert@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@_N@2@AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@@Z`
- size: `335`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180020488`

## callees

- `0x180020750`
- `0x180020e7c`
- `0x180023c42`

## pseudocode

```c
__int64 __fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::insert(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 **v3; // r14
  __int64 *v7; // rdi
  int v8; // r12d
  int v9; // eax
  __int64 v10; // rbx
  int v11; // eax
  char v12; // bp
  __int64 *v13; // rdi
  char v14; // r8
  __int64 *v15; // rax
  __int64 j; // rax
  __int64 i; // rax
  int v18; // eax
  int v19; // r14d
  int v20; // eax
  __int64 v22; // [rsp+80h] [rbp+8h] BYREF

  v3 = *(__int64 ***)(a1 + 8);
  v7 = v3[1];
  if ( *((_BYTE *)v7 + 49) )
  {
    v12 = 1;
    v13 = *(__int64 **)(a1 + 8);
    v10 = (__int64)v13;
    goto LABEL_14;
  }
  v8 = *(_DWORD *)a3;
  do
  {
    v9 = v8;
    v10 = (__int64)v7;
    if ( v8 >= *((_DWORD *)v7 + 6) )
      v9 = *((_DWORD *)v7 + 6);
    v11 = memcmp_0(*(const void **)(a3 + 8), (const void *)v7[4], 2LL * v9);
    if ( v11 )
    {
      if ( v11 >= 0 )
        goto LABEL_7;
    }
    else if ( v8 >= *((_DWORD *)v7 + 6) )
    {
LABEL_7:
      v7 = (__int64 *)v7[2];
      v12 = 0;
      continue;
    }
    v7 = (__int64 *)*v7;
    v12 = 1;
  }
  while ( !*((_BYTE *)v7 + 49) );
  v13 = (__int64 *)v10;
  if ( v12 )
  {
LABEL_14:
    if ( v13 == *v3 )
    {
      v14 = 1;
      goto LABEL_16;
    }
    if ( *((_BYTE *)v13 + 49) )
    {
      v10 = v13[2];
    }
    else if ( *(_BYTE *)(*v13 + 49) )
    {
      for ( i = v13[1]; !*(_BYTE *)(i + 49) && v10 == *(_QWORD *)i; i = *(_QWORD *)(i + 8) )
        v10 = i;
      if ( !*(_BYTE *)(v10 + 49) )
        v10 = i;
    }
    else
    {
      v10 = *v13;
      for ( j = *(_QWORD *)(*v13 + 16); !*(_BYTE *)(j + 49); j = *(_QWORD *)(v10 + 16) )
        v10 = *(_QWORD *)(v10 + 16);
    }
  }
  v18 = *(_DWORD *)(v10 + 24);
  v19 = *(_DWORD *)a3;
  if ( v18 >= *(_DWORD *)a3 )
    v18 = *(_DWORD *)a3;
  v20 = memcmp_0(*(const void **)(v10 + 32), *(const void **)(a3 + 8), 2LL * v18);
  if ( v20 )
  {
    if ( v20 >= 0 )
      goto LABEL_34;
LABEL_37:
    v14 = v12;
LABEL_16:
    v15 = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Insert(
            a1,
            &v22,
            v14,
            v13,
            a3);
    *(_BYTE *)(a2 + 8) = 1;
    *(_QWORD *)a2 = *v15;
  }
  else
  {
    if ( *(_DWORD *)(v10 + 24) < v19 )
      goto LABEL_37;
LABEL_34:
    *(_QWORD *)a2 = v10;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x180020e7c  push    rbx
0x180020e7e  push    rbp
0x180020e7f  push    rsi
0x180020e80  push    rdi
0x180020e81  push    r12
0x180020e83  push    r13
0x180020e85  push    r14
0x180020e87  push    r15
0x180020e89  sub     rsp, 38h
0x180020e8d  mov     r14, [rcx+8]
0x180020e91  mov     r13, rcx
0x180020e94  xor     ecx, ecx
0x180020e96  mov     r15, r8
0x180020e99  mov     rsi, rdx
0x180020e9c  mov     rdi, [r14+8]
0x180020ea0  cmp     [rdi+31h], cl
0x180020ea3  jnz     short loc_180020EF9
0x180020ea5  mov     r12d, [r8]
0x180020ea8  cmp     r12d, [rdi+18h]
0x180020eac  mov     eax, r12d
0x180020eaf  mov     rdx, [rdi+20h]; Buf2
0x180020eb3  mov     rbx, rdi
0x180020eb6  cmovge  eax, [rdi+18h]
0x180020eba  mov     rcx, [r15+8]; Buf1
0x180020ebe  movsxd  r8, eax
0x180020ec1  add     r8, r8; Size
0x180020ec4  call    memcmp_0
0x180020ec9  xor     ecx, ecx
0x180020ecb  test    eax, eax
0x180020ecd  jz      short loc_180020EEB
0x180020ecf  js      short loc_180020EF1
0x180020ed1  mov     rdi, [rdi+10h]
0x180020ed5  mov     bpl, cl
0x180020ed8  cmp     [rdi+31h], cl
0x180020edb  jz      short loc_180020EA8
0x180020edd  mov     rdi, rbx
0x180020ee0  test    bpl, bpl
0x180020ee3  jz      loc_180020F77
0x180020ee9  jmp     short loc_180020F02
0x180020eeb  cmp     r12d, [rdi+18h]
0x180020eef  jge     short loc_180020ED1
0x180020ef1  mov     rdi, [rdi]
0x180020ef4  mov     bpl, 1
0x180020ef7  jmp     short loc_180020ED8
0x180020ef9  mov     bpl, 1
0x180020efc  mov     rdi, r14
0x180020eff  mov     rbx, r14
0x180020f02  cmp     rdi, [r14]
0x180020f05  jnz     short loc_180020F2E
0x180020f07  mov     r8b, 1
0x180020f0a  mov     r9, rdi
0x180020f0d  mov     [rsp+78h+var_58], r15
0x180020f12  lea     rdx, [rsp+78h+arg_0]
0x180020f1a  mov     rcx, r13
0x180020f1d  call    ?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &)
0x180020f22  mov     byte ptr [rsi+8], 1
0x180020f26  mov     rcx, [rax]
0x180020f29  mov     [rsi], rcx
0x180020f2c  jmp     short loc_180020FA9
0x180020f2e  cmp     [rdi+31h], cl
0x180020f31  jz      short loc_180020F39
0x180020f33  mov     rbx, [rdi+10h]
0x180020f37  jmp     short loc_180020F77
0x180020f39  mov     rax, [rdi]
0x180020f3c  cmp     [rax+31h], cl
0x180020f3f  jnz     short loc_180020F59
0x180020f41  mov     rbx, rax
0x180020f44  mov     rax, [rax+10h]
0x180020f48  jmp     short loc_180020F52
0x180020f4a  mov     rbx, [rbx+10h]
0x180020f4e  mov     rax, [rbx+10h]
0x180020f52  cmp     [rax+31h], cl
0x180020f55  jz      short loc_180020F4A
0x180020f57  jmp     short loc_180020F77
0x180020f59  mov     rax, [rdi+8]
0x180020f5d  jmp     short loc_180020F6B
0x180020f5f  cmp     rbx, [rax]
0x180020f62  jnz     short loc_180020F70
0x180020f64  mov     rbx, rax
0x180020f67  mov     rax, [rax+8]
0x180020f6b  cmp     [rax+31h], cl
0x180020f6e  jz      short loc_180020F5F
0x180020f70  cmp     [rbx+31h], cl
0x180020f73  cmovz   rbx, rax
0x180020f77  mov     eax, [rbx+18h]
0x180020f7a  mov     r14d, [r15]
0x180020f7d  cmp     eax, r14d
0x180020f80  mov     rdx, [r15+8]; Buf2
0x180020f84  mov     rcx, [rbx+20h]; Buf1
0x180020f88  cmovge  eax, r14d
0x180020f8c  movsxd  r8, eax
0x180020f8f  add     r8, r8; Size
0x180020f92  call    memcmp_0
0x180020f97  test    eax, eax
0x180020f99  jz      short loc_180020FBD
0x180020f9b  sets    al
0x180020f9e  test    al, al
0x180020fa0  jnz     short loc_180020FC3
0x180020fa2  mov     [rsi], rbx
0x180020fa5  mov     byte ptr [rsi+8], 0
0x180020fa9  mov     rax, rsi
0x180020fac  add     rsp, 38h
0x180020fb0  pop     r15
0x180020fb2  pop     r14
0x180020fb4  pop     r13
0x180020fb6  pop     r12
0x180020fb8  pop     rdi
0x180020fb9  pop     rsi
0x180020fba  pop     rbp
0x180020fbb  pop     rbx
0x180020fbc  retn
0x180020fbd  cmp     [rbx+18h], r14d
0x180020fc1  jge     short loc_180020FA2
0x180020fc3  mov     r8b, bpl
0x180020fc6  jmp     loc_180020F0A
```
