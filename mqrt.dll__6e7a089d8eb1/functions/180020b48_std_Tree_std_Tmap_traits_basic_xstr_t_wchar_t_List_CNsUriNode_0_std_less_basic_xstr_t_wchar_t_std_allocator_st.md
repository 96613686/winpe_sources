# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::iterator)

- ea: `0x180020b48`
- end: `0x180020e76`
- name: `?erase@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@QEAA?AViterator@12@V312@@Z`
- size: `814`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800202c0`
- `0x180020a60`

## callees

- `0x1800022d6`
- `0x180012fe8`
- `0x1800201f8`
- `0x180020998`
- `0x1800209e8`
- `0x180020a0c`
- `0x180020b48`
- `0x180023ca0`

## import_xrefs

- `msvcrt!free` at `0x180020e2d`
- `msvcrt!free` at `0x180020e2d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::erase(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _BYTE *v5; // r14
  _QWORD *v6; // rbp
  _QWORD *v7; // rsi
  _QWORD *v8; // r10
  char v9; // r9
  _QWORD **v10; // r11
  _QWORD *i; // rbx
  _QWORD *v12; // r9
  __int64 v13; // rax
  __int64 *v14; // r8
  __int64 v15; // rax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 j; // rax
  _BYTE *v19; // rdx
  __int64 v20; // rax
  _QWORD *v21; // rax
  char v22; // cl
  char v23; // r11
  _BYTE *v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // rcx
  _BYTE v28[48]; // [rsp+20h] [rbp-A8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-78h] BYREF

  if ( *((_BYTE *)a3 + 49) )
  {
    std::string::string(v28, "invalid map/set<T> iterator");
    std::out_of_range::out_of_range(pExceptionObject, v28, 0);
    throw (std::out_of_range *)pExceptionObject;
  }
  v5 = a3;
  v6 = a3;
  v7 = a3 + 2;
  v8 = (_QWORD *)a3[2];
  v9 = *((_BYTE *)v8 + 49);
  v10 = (_QWORD **)(a3 + 1);
  if ( v9 )
  {
    for ( i = *v10; !*((_BYTE *)i + 49) && a3 == (_QWORD *)i[2]; i = (_QWORD *)i[1] )
      a3 = i;
  }
  else
  {
    i = (_QWORD *)std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(a3[2]);
  }
  if ( *(_BYTE *)(*(_QWORD *)v5 + 49LL) )
    goto LABEL_13;
  if ( v9 )
  {
    v8 = *(_QWORD **)v5;
LABEL_13:
    v12 = *v10;
    if ( !*((_BYTE *)v8 + 49) )
      v8[1] = v12;
    v13 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE **)(v13 + 8) == v5 )
    {
      *(_QWORD *)(v13 + 8) = v8;
    }
    else if ( (_BYTE *)*v12 == v5 )
    {
      *v12 = v8;
    }
    else
    {
      v12[2] = v8;
    }
    v14 = *(__int64 **)(a1 + 8);
    if ( (_BYTE *)*v14 == v5 )
    {
      if ( *((_BYTE *)v8 + 49) )
        v15 = (__int64)v12;
      else
        v15 = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(v8);
      *v14 = v15;
    }
    v16 = *(_QWORD *)(a1 + 8);
    if ( *(_BYTE **)(v16 + 16) == v5 )
    {
      if ( *((_BYTE *)v8 + 49) )
      {
        v17 = v12;
      }
      else
      {
        v17 = v8;
        for ( j = v8[2]; !*(_BYTE *)(j + 49); j = v17[2] )
          v17 = (_QWORD *)v17[2];
      }
      *(_QWORD *)(v16 + 16) = v17;
    }
    v19 = v6 + 6;
    goto LABEL_44;
  }
  v8 = (_QWORD *)i[2];
  if ( i == (_QWORD *)v5 )
    goto LABEL_13;
  *(_QWORD *)(*(_QWORD *)v5 + 8LL) = i;
  *i = *(_QWORD *)v5;
  if ( i == (_QWORD *)*v7 )
  {
    v12 = i;
  }
  else
  {
    v12 = (_QWORD *)i[1];
    if ( !*((_BYTE *)v8 + 49) )
      v8[1] = v12;
    *v12 = v8;
    i[2] = *v7;
    *(_QWORD *)(*v7 + 8LL) = i;
  }
  v20 = *(_QWORD *)(a1 + 8);
  if ( *(_BYTE **)(v20 + 8) == v5 )
  {
    *(_QWORD *)(v20 + 8) = i;
  }
  else
  {
    v21 = *v10;
    if ( (_BYTE *)**v10 == v5 )
      *v21 = i;
    else
      v21[2] = i;
  }
  i[1] = *v10;
  v19 = v5 + 48;
  v22 = *((_BYTE *)i + 48);
  *((_BYTE *)i + 48) = v5[48];
  v5[48] = v22;
LABEL_44:
  v23 = 1;
  if ( *v19 != 1 )
    goto LABEL_67;
  while ( v8 != *(_QWORD **)(*(_QWORD *)(a1 + 8) + 8LL) && *((_BYTE *)v8 + 48) == v23 )
  {
    v24 = (_BYTE *)*v12;
    if ( v8 == (_QWORD *)*v12 )
    {
      v24 = (_BYTE *)v12[2];
      if ( !v24[48] )
      {
        v24[48] = v23;
        *((_BYTE *)v12 + 48) = 0;
        std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(a1);
        v24 = (_BYTE *)v12[2];
      }
      if ( !v24[49] )
      {
        if ( *(_BYTE *)(*(_QWORD *)v24 + 48LL) != v23 || *(_BYTE *)(*((_QWORD *)v24 + 2) + 48LL) != v23 )
        {
          if ( *(_BYTE *)(*((_QWORD *)v24 + 2) + 48LL) == v23 )
          {
            *(_BYTE *)(*(_QWORD *)v24 + 48LL) = v23;
            v24[48] = 0;
            std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
              a1,
              v24);
            v24 = (_BYTE *)v12[2];
          }
          v24[48] = *((_BYTE *)v12 + 48);
          *((_BYTE *)v12 + 48) = v23;
          *(_BYTE *)(*((_QWORD *)v24 + 2) + 48LL) = v23;
          std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(a1);
          break;
        }
LABEL_61:
        v24[48] = 0;
      }
    }
    else
    {
      if ( !v24[48] )
      {
        v24[48] = v23;
        *((_BYTE *)v12 + 48) = 0;
        std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
          a1,
          v12);
        v24 = (_BYTE *)*v12;
      }
      if ( !v24[49] )
      {
        v25 = *((_QWORD *)v24 + 2);
        if ( *(_BYTE *)(v25 + 48) != v23 || *(_BYTE *)(*(_QWORD *)v24 + 48LL) != v23 )
        {
          if ( *(_BYTE *)(*(_QWORD *)v24 + 48LL) == v23 )
          {
            *(_BYTE *)(v25 + 48) = v23;
            v24[48] = 0;
            std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(a1);
            v24 = (_BYTE *)*v12;
          }
          v24[48] = *((_BYTE *)v12 + 48);
          *((_BYTE *)v12 + 48) = v23;
          *(_BYTE *)(*(_QWORD *)v24 + 48LL) = v23;
          std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
            a1,
            v12);
          break;
        }
        goto LABEL_61;
      }
    }
    v8 = v12;
    v12 = (_QWORD *)v12[1];
  }
  *((_BYTE *)v8 + 48) = v23;
LABEL_67:
  free(v5);
  v26 = *(_QWORD *)(a1 + 16);
  if ( v26 )
    *(_QWORD *)(a1 + 16) = v26 - 1;
  *a2 = i;
  return a2;
}

```

## disassembly

```asm
0x180020b48  mov     [rsp+arg_10], rbx
0x180020b4d  mov     [rsp+arg_18], rbp
0x180020b52  push    rsi
0x180020b53  push    rdi
0x180020b54  push    r12
0x180020b56  push    r14
0x180020b58  push    r15
0x180020b5a  sub     rsp, 0A0h
0x180020b61  mov     rax, cs:__security_cookie
0x180020b68  xor     rax, rsp
0x180020b6b  mov     [rsp+0C8h+var_38], rax
0x180020b73  mov     r15, rdx
0x180020b76  mov     rdi, rcx
0x180020b79  xor     r12d, r12d
0x180020b7c  cmp     [r8+31h], r12b
0x180020b80  jz      short loc_180020BB8
0x180020b82  lea     rdx, aInvalidMapSetT; "invalid map/set<T> iterator"
0x180020b89  lea     rcx, [rsp+0C8h+var_A8]
0x180020b8e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x180020b93  nop
0x180020b94  xor     r8d, r8d
0x180020b97  lea     rdx, [rsp+0C8h+var_A8]
0x180020b9c  lea     rcx, [rsp+0C8h+pExceptionObject]
0x180020ba1  call    ??0out_of_range@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@PEAV_STL70@@@Z; std::out_of_range::out_of_range(std::string const &,_STL70 *)
0x180020ba6  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180020bad  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180020bb2  call    _CxxThrowException_0
0x180020bb8  mov     r14, r8
0x180020bbb  mov     rbp, r8
0x180020bbe  lea     rsi, [r8+10h]
0x180020bc2  mov     r10, [rsi]
0x180020bc5  mov     r9b, [r10+31h]
0x180020bc9  lea     r11, [r8+8]
0x180020bcd  test    r9b, r9b
0x180020bd0  jnz     short loc_180020BDF
0x180020bd2  mov     rcx, r10
0x180020bd5  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020bda  mov     rbx, rax
0x180020bdd  jmp     short loc_180020BF7
0x180020bdf  mov     rbx, [r11]
0x180020be2  jmp     short loc_180020BF1
0x180020be4  cmp     r8, [rbx+10h]
0x180020be8  jnz     short loc_180020BF7
0x180020bea  mov     r8, rbx
0x180020bed  mov     rbx, [rbx+8]
0x180020bf1  cmp     [rbx+31h], r12b
0x180020bf5  jz      short loc_180020BE4
0x180020bf7  mov     rax, [r14]
0x180020bfa  cmp     [rax+31h], r12b
0x180020bfe  jnz     short loc_180020C17
0x180020c00  test    r9b, r9b
0x180020c03  jz      short loc_180020C0A
0x180020c05  mov     r10, rax
0x180020c08  jmp     short loc_180020C17
0x180020c0a  mov     r10, [rbx+10h]
0x180020c0e  cmp     rbx, r14
0x180020c11  jnz     loc_180020C97
0x180020c17  mov     r9, [r11]
0x180020c1a  cmp     [r10+31h], r12b
0x180020c1e  jnz     short loc_180020C24
0x180020c20  mov     [r10+8], r9
0x180020c24  mov     rax, [rdi+8]
0x180020c28  cmp     [rax+8], r14
0x180020c2c  jnz     short loc_180020C34
0x180020c2e  mov     [rax+8], r10
0x180020c32  jmp     short loc_180020C42
0x180020c34  cmp     [r9], r14
0x180020c37  jnz     short loc_180020C3E
0x180020c39  mov     [r9], r10
0x180020c3c  jmp     short loc_180020C42
0x180020c3e  mov     [r9+10h], r10
0x180020c42  mov     r8, [rdi+8]
0x180020c46  cmp     [r8], r14
0x180020c49  jnz     short loc_180020C61
0x180020c4b  cmp     [r10+31h], r12b
0x180020c4f  jz      short loc_180020C56
0x180020c51  mov     rax, r9
0x180020c54  jmp     short loc_180020C5E
0x180020c56  mov     rcx, r10
0x180020c59  call    ?_Min@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@KAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Min(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020c5e  mov     [r8], rax
0x180020c61  mov     rdx, [rdi+8]
0x180020c65  cmp     [rdx+10h], r14
0x180020c69  jnz     short loc_180020C91
0x180020c6b  cmp     [r10+31h], r12b
0x180020c6f  jz      short loc_180020C76
0x180020c71  mov     rcx, r9
0x180020c74  jmp     short loc_180020C8D
0x180020c76  mov     rcx, r10
0x180020c79  mov     rax, [r10+10h]
0x180020c7d  jmp     short loc_180020C87
0x180020c7f  mov     rcx, [rcx+10h]
0x180020c83  mov     rax, [rcx+10h]
0x180020c87  cmp     [rax+31h], r12b
0x180020c8b  jz      short loc_180020C7F
0x180020c8d  mov     [rdx+10h], rcx
0x180020c91  lea     rdx, [rbp+30h]
0x180020c95  jmp     short loc_180020D00
0x180020c97  mov     [rax+8], rbx
0x180020c9b  mov     rax, [r14]
0x180020c9e  mov     [rbx], rax
0x180020ca1  cmp     rbx, [rsi]
0x180020ca4  jnz     short loc_180020CAB
0x180020ca6  mov     r9, rbx
0x180020ca9  jmp     short loc_180020CCA
0x180020cab  mov     r9, [rbx+8]
0x180020caf  cmp     [r10+31h], r12b
0x180020cb3  jnz     short loc_180020CB9
0x180020cb5  mov     [r10+8], r9
0x180020cb9  mov     [r9], r10
0x180020cbc  mov     rax, [rsi]
0x180020cbf  mov     [rbx+10h], rax
0x180020cc3  mov     rax, [rsi]
0x180020cc6  mov     [rax+8], rbx
0x180020cca  mov     rax, [rdi+8]
0x180020cce  cmp     [rax+8], r14
0x180020cd2  jnz     short loc_180020CDA
0x180020cd4  mov     [rax+8], rbx
0x180020cd8  jmp     short loc_180020CEB
0x180020cda  mov     rax, [r11]
0x180020cdd  cmp     [rax], r14
0x180020ce0  jnz     short loc_180020CE7
0x180020ce2  mov     [rax], rbx
0x180020ce5  jmp     short loc_180020CEB
0x180020ce7  mov     [rax+10h], rbx
0x180020ceb  mov     rax, [r11]
0x180020cee  mov     [rbx+8], rax
0x180020cf2  lea     rdx, [r14+30h]
0x180020cf6  mov     cl, [rbx+30h]
0x180020cf9  mov     al, [rdx]
0x180020cfb  mov     [rbx+30h], al
0x180020cfe  mov     [rdx], cl
0x180020d00  mov     r11b, 1
0x180020d03  cmp     [rdx], r11b
0x180020d06  jnz     loc_180020E2A
0x180020d0c  mov     rax, [rdi+8]
0x180020d10  cmp     r10, [rax+8]
0x180020d14  jz      loc_180020E26
0x180020d1a  cmp     [r10+30h], r11b
0x180020d1e  jnz     loc_180020E26
0x180020d24  mov     rdx, [r9]
0x180020d27  cmp     r10, rdx
0x180020d2a  jnz     short loc_180020DA8
0x180020d2c  mov     rdx, [r9+10h]
0x180020d30  cmp     [rdx+30h], r12b
0x180020d34  jnz     short loc_180020D4D
0x180020d36  mov     [rdx+30h], r11b
0x180020d3a  mov     [r9+30h], r12b
0x180020d3e  mov     rdx, r9
0x180020d41  mov     rcx, rdi
0x180020d44  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020d49  mov     rdx, [r9+10h]
0x180020d4d  cmp     [rdx+31h], r12b
0x180020d51  jnz     loc_180020DE1
0x180020d57  mov     r8, [rdx]
0x180020d5a  cmp     [r8+30h], r11b
0x180020d5e  jnz     short loc_180020D6A
0x180020d60  mov     rax, [rdx+10h]
0x180020d64  cmp     [rax+30h], r11b
0x180020d68  jz      short loc_180020DDD
0x180020d6a  mov     rax, [rdx+10h]
0x180020d6e  cmp     [rax+30h], r11b
0x180020d72  jnz     short loc_180020D88
0x180020d74  mov     [r8+30h], r11b
0x180020d78  mov     [rdx+30h], r12b
0x180020d7c  mov     rcx, rdi
0x180020d7f  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020d84  mov     rdx, [r9+10h]
0x180020d88  mov     al, [r9+30h]
0x180020d8c  mov     [rdx+30h], al
0x180020d8f  mov     [r9+30h], r11b
0x180020d93  mov     rax, [rdx+10h]
0x180020d97  mov     [rax+30h], r11b
0x180020d9b  mov     rdx, r9
0x180020d9e  mov     rcx, rdi
0x180020da1  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020da6  jmp     short loc_180020E26
0x180020da8  cmp     [rdx+30h], r12b
0x180020dac  jnz     short loc_180020DC4
0x180020dae  mov     [rdx+30h], r11b
0x180020db2  mov     [r9+30h], r12b
0x180020db6  mov     rdx, r9
0x180020db9  mov     rcx, rdi
0x180020dbc  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020dc1  mov     rdx, [r9]
0x180020dc4  cmp     [rdx+31h], r12b
0x180020dc8  jnz     short loc_180020DE1
0x180020dca  mov     rcx, [rdx+10h]
0x180020dce  cmp     [rcx+30h], r11b
0x180020dd2  jnz     short loc_180020DED
0x180020dd4  mov     rax, [rdx]
0x180020dd7  cmp     [rax+30h], r11b
0x180020ddb  jnz     short loc_180020DED
0x180020ddd  mov     [rdx+30h], r12b
0x180020de1  mov     r10, r9
0x180020de4  mov     r9, [r9+8]
0x180020de8  jmp     loc_180020D0C
0x180020ded  mov     rax, [rdx]
0x180020df0  cmp     [rax+30h], r11b
0x180020df4  jnz     short loc_180020E09
0x180020df6  mov     [rcx+30h], r11b
0x180020dfa  mov     [rdx+30h], r12b
0x180020dfe  mov     rcx, rdi
0x180020e01  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020e06  mov     rdx, [r9]
0x180020e09  mov     al, [r9+30h]
0x180020e0d  mov     [rdx+30h], al
0x180020e10  mov     [r9+30h], r11b
0x180020e14  mov     rax, [rdx]
0x180020e17  mov     [rax+30h], r11b
0x180020e1b  mov     rdx, r9
0x180020e1e  mov     rcx, rdi
0x180020e21  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020e26  mov     [r10+30h], r11b
0x180020e2a  mov     rcx, r14; Block
0x180020e2d  call    cs:__imp_free
0x180020e33  nop
0x180020e34  mov     rcx, [rdi+10h]
0x180020e38  test    rcx, rcx
0x180020e3b  jz      short loc_180020E44
0x180020e3d  dec     rcx
0x180020e40  mov     [rdi+10h], rcx
0x180020e44  mov     [r15], rbx
0x180020e47  mov     rax, r15
0x180020e4a  mov     rcx, [rsp+0C8h+var_38]
0x180020e52  xor     rcx, rsp; StackCookie
0x180020e55  call    __security_check_cookie
0x180020e5a  lea     r11, [rsp+0C8h+var_28]
0x180020e62  mov     rbx, [r11+40h]
0x180020e66  mov     rbp, [r11+48h]
0x180020e6a  mov     rsp, r11
0x180020e6d  pop     r15
0x180020e6f  pop     r14
0x180020e71  pop     r12
0x180020e73  pop     rdi
0x180020e74  pop     rsi
0x180020e75  retn
```
