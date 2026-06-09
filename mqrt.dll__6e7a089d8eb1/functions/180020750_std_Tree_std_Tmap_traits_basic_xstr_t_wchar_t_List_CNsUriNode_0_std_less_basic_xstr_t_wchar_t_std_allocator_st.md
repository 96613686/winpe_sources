# std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Insert(bool,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &)

- ea: `0x180020750`
- end: `0x180020927`
- name: `?_Insert@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAA?AViterator@12@_NPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@@Z`
- size: `471`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180020e7c`

## callees

- `0x1800022d6`
- `0x180012fe8`
- `0x180013124`
- `0x180020610`
- `0x180020750`
- `0x180020998`
- `0x180020a0c`
- `0x180023ca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 *__fastcall std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Insert(
        __int64 a1,
        __int64 *a2,
        char a3,
        __int64 *a4,
        __int64 a5)
{
  __int64 v9; // r10
  __int64 *v10; // rax
  char v11; // r11
  __int64 v12; // rax
  __int64 *v13; // rax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rcx
  __int64 v17; // rax
  _BYTE v19[48]; // [rsp+30h] [rbp-98h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+60h] [rbp-68h] BYREF

  if ( *(_QWORD *)(a1 + 16) >= 0xAAAAAAAAAAAAAA9uLL )
  {
    std::string::string(v19, "map/set<T> too long");
    std::length_error::length_error(pExceptionObject, v19);
    throw (std::length_error *)pExceptionObject;
  }
  v9 = std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(
         -1431655767,
         *(_QWORD *)(a1 + 8),
         (_DWORD)a4,
         *(_QWORD *)(a1 + 8),
         a5);
  ++*(_QWORD *)(a1 + 16);
  v10 = *(__int64 **)(a1 + 8);
  v11 = 0;
  if ( a4 == v10 )
  {
    v10[1] = v9;
    **(_QWORD **)(a1 + 8) = v9;
    v12 = *(_QWORD *)(a1 + 8);
LABEL_9:
    *(_QWORD *)(v12 + 16) = v9;
    goto LABEL_10;
  }
  if ( !a3 )
  {
    a4[2] = v9;
    v12 = *(_QWORD *)(a1 + 8);
    if ( a4 != *(__int64 **)(v12 + 16) )
      goto LABEL_10;
    goto LABEL_9;
  }
  *a4 = v9;
  v13 = *(__int64 **)(a1 + 8);
  if ( a4 == (__int64 *)*v13 )
    *v13 = v9;
LABEL_10:
  v14 = v9;
  if ( !*(_BYTE *)(*(_QWORD *)(v9 + 8) + 48LL) )
  {
    do
    {
      v15 = *(_QWORD *)(v14 + 8);
      v16 = *(__int64 **)(v15 + 8);
      v17 = *v16;
      if ( v15 == *v16 )
      {
        v17 = v16[2];
        if ( *(_BYTE *)(v17 + 48) != v11 )
        {
          if ( v14 == *(_QWORD *)(v15 + 16) )
            std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(a1);
          *(_BYTE *)(*(_QWORD *)(v14 + 8) + 48LL) = 1;
          *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 48LL) = v11;
          std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
            a1,
            *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL));
          continue;
        }
      }
      else if ( *(_BYTE *)(v17 + 48) != v11 )
      {
        if ( v14 == *(_QWORD *)v15 )
          std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(
            a1,
            v15);
        *(_BYTE *)(*(_QWORD *)(v14 + 8) + 48LL) = 1;
        *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 48LL) = v11;
        std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(a1);
        continue;
      }
      *(_BYTE *)(v15 + 48) = 1;
      *(_BYTE *)(v17 + 48) = 1;
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL) + 48LL) = v11;
      v14 = *(_QWORD *)(*(_QWORD *)(v14 + 8) + 8LL);
    }
    while ( *(_BYTE *)(*(_QWORD *)(v14 + 8) + 48LL) == v11 );
  }
  *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL) + 48LL) = 1;
  *a2 = v9;
  return a2;
}

```

## disassembly

```asm
0x180020750  mov     [rsp+arg_10], rbx
0x180020755  push    rsi
0x180020756  push    rdi
0x180020757  push    r14
0x180020759  sub     rsp, 0B0h
0x180020760  mov     rax, cs:__security_cookie
0x180020767  xor     rax, rsp
0x18002076a  mov     [rsp+0C8h+var_28], rax
0x180020772  mov     rdi, r9
0x180020775  mov     sil, r8b
0x180020778  mov     r14, rdx
0x18002077b  mov     rbx, rcx
0x18002077e  mov     rax, [rsp+0C8h+arg_20]
0x180020786  mov     rcx, 0AAAAAAAAAAAAAA9h
0x180020790  cmp     [rbx+10h], rcx
0x180020794  jb      short loc_1800207C9
0x180020796  lea     rdx, aMapSetTTooLong; "map/set<T> too long"
0x18002079d  lea     rcx, [rsp+0C8h+var_98]
0x1800207a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAA@PEBD@Z; std::string::string(char const *)
0x1800207a7  nop
0x1800207a8  lea     rdx, [rsp+0C8h+var_98]
0x1800207ad  lea     rcx, [rsp+0C8h+pExceptionObject]
0x1800207b2  call    ??0length_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@1@@Z; std::length_error::length_error(std::string const &)
0x1800207b7  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800207be  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x1800207c3  call    _CxxThrowException_0
0x1800207c9  mov     rdx, [rbx+8]
0x1800207cd  mov     [rsp+0C8h+var_A8], rax
0x1800207d2  mov     r9, rdx
0x1800207d5  mov     r8, rdi
0x1800207d8  call    ?_Buynode@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@PEAU342@00AEBU?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@2@D@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Buynode(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *,std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *> const &,char)
0x1800207dd  mov     r10, rax
0x1800207e0  inc     qword ptr [rbx+10h]
0x1800207e4  mov     rax, [rbx+8]
0x1800207e8  xor     r11d, r11d
0x1800207eb  cmp     rdi, rax
0x1800207ee  jnz     short loc_180020801
0x1800207f0  mov     [rax+8], r10
0x1800207f4  mov     rax, [rbx+8]
0x1800207f8  mov     [rax], r10
0x1800207fb  mov     rax, [rbx+8]
0x1800207ff  jmp     short loc_180020825
0x180020801  test    sil, sil
0x180020804  jz      short loc_180020817
0x180020806  mov     [rdi], r10
0x180020809  mov     rax, [rbx+8]
0x18002080d  cmp     rdi, [rax]
0x180020810  jnz     short loc_180020829
0x180020812  mov     [rax], r10
0x180020815  jmp     short loc_180020829
0x180020817  mov     [rdi+10h], r10
0x18002081b  mov     rax, [rbx+8]
0x18002081f  cmp     rdi, [rax+10h]
0x180020823  jnz     short loc_180020829
0x180020825  mov     [rax+10h], r10
0x180020829  mov     r9, r10
0x18002082c  mov     rax, [r10+8]
0x180020830  cmp     [rax+30h], r11b
0x180020834  jnz     loc_1800208F1
0x18002083a  mov     rdx, [r9+8]
0x18002083e  mov     rcx, [rdx+8]
0x180020842  mov     rax, [rcx]
0x180020845  cmp     rdx, rax
0x180020848  jnz     short loc_18002088B
0x18002084a  mov     rax, [rcx+10h]
0x18002084e  cmp     [rax+30h], r11b
0x180020852  jz      short loc_180020891
0x180020854  cmp     r9, [rdx+10h]
0x180020858  jnz     short loc_180020865
0x18002085a  mov     r9, rdx
0x18002085d  mov     rcx, rbx
0x180020860  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020865  mov     rax, [r9+8]
0x180020869  mov     byte ptr [rax+30h], 1
0x18002086d  mov     rax, [r9+8]
0x180020871  mov     rcx, [rax+8]
0x180020875  mov     [rcx+30h], r11b
0x180020879  mov     rdx, [r9+8]
0x18002087d  mov     rdx, [rdx+8]
0x180020881  mov     rcx, rbx
0x180020884  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x180020889  jmp     short loc_1800208E3
0x18002088b  cmp     [rax+30h], r11b
0x18002088f  jnz     short loc_1800208AF
0x180020891  mov     byte ptr [rdx+30h], 1
0x180020895  mov     byte ptr [rax+30h], 1
0x180020899  mov     rax, [r9+8]
0x18002089d  mov     rcx, [rax+8]
0x1800208a1  mov     [rcx+30h], r11b
0x1800208a5  mov     rax, [r9+8]
0x1800208a9  mov     r9, [rax+8]
0x1800208ad  jmp     short loc_1800208E3
0x1800208af  cmp     r9, [rdx]
0x1800208b2  jnz     short loc_1800208BF
0x1800208b4  mov     r9, rdx
0x1800208b7  mov     rcx, rbx
0x1800208ba  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Rrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x1800208bf  mov     rax, [r9+8]
0x1800208c3  mov     byte ptr [rax+30h], 1
0x1800208c7  mov     rax, [r9+8]
0x1800208cb  mov     rcx, [rax+8]
0x1800208cf  mov     [rcx+30h], r11b
0x1800208d3  mov     rdx, [r9+8]
0x1800208d7  mov     rdx, [rdx+8]
0x1800208db  mov     rcx, rbx
0x1800208de  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@std@@IEAAXPEAU_Node@?$_Tree_nod@V?$_Tmap_traits@V?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@U?$less@V?$basic_xstr_t@_W@@@std@@V?$allocator@U?$pair@$$CBV?$basic_xstr_t@_W@@PEAV?$List@VCNsUriNode@@$0A@@@@std@@@4@$0A@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Lrotate(std::_Tree_nod<std::_Tmap_traits<basic_xstr_t<wchar_t>,List<CNsUriNode,0> *,std::less<basic_xstr_t<wchar_t>>,std::allocator<std::pair<basic_xstr_t<wchar_t> const,List<CNsUriNode,0> *>>,0>>::_Node *)
0x1800208e3  mov     rcx, [r9+8]
0x1800208e7  cmp     [rcx+30h], r11b
0x1800208eb  jz      loc_18002083A
0x1800208f1  mov     rcx, [rbx+8]
0x1800208f5  mov     rdx, [rcx+8]
0x1800208f9  mov     byte ptr [rdx+30h], 1
0x1800208fd  mov     [r14], r10
0x180020900  mov     rax, r14
0x180020903  mov     rcx, [rsp+0C8h+var_28]
0x18002090b  xor     rcx, rsp; StackCookie
0x18002090e  call    __security_check_cookie
0x180020913  mov     rbx, [rsp+0C8h+arg_10]
0x18002091b  add     rsp, 0B0h
0x180020922  pop     r14
0x180020924  pop     rdi
0x180020925  pop     rsi
0x180020926  retn
```
