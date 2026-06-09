# CNetDiagClient::CleanupDiagnosis(void)

- ea: `0x1800086cc`
- end: `0x1800087f0`
- name: `?CleanupDiagnosis@CNetDiagClient@@IEAAJXZ`
- size: `292`
- prototype: `__int64 __fastcall(CNetDiagClient *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, service_task`

## callers

- `0x180008304`
- `0x18000d390`

## callees

- `0x1800086cc`
- `0x180009dac`
- `0x180009fcc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000875b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800087b4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000875b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800087b4`
- `ole32!CoTaskMemFree` at `0x18000870b`
- `ole32!CoTaskMemFree` at `0x18000871d`
- `ole32!CoTaskMemFree` at `0x18000870b`
- `ole32!CoTaskMemFree` at `0x18000871d`
- `wdi!WdiCloseInstance` at `0x1800086e9`
- `wdi!WdiCloseInstance` at `0x1800086e9`

## pseudocode

```c
__int64 __fastcall CNetDiagClient::CleanupDiagnosis(CNetDiagClient *this)
{
  unsigned int v2; // r14d
  char *v3; // rsi
  _QWORD *v4; // rbp
  _QWORD *i; // rdi
  _QWORD *v6; // rsi
  _QWORD *j; // rdi

  v2 = 0;
  if ( *((_QWORD *)this + 16) )
  {
    v2 = WdiCloseInstance();
    *((_QWORD *)this + 16) = 0;
  }
  *((_DWORD *)this + 34) = 0;
  CoTaskMemFree(*((LPVOID *)this + 6));
  *((_QWORD *)this + 6) = 0;
  CoTaskMemFree(*((LPVOID *)this + 7));
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 760) = 0;
  v3 = (char *)this + 96;
  v4 = *(_QWORD **)(*((_QWORD *)this + 12) + 8LL);
  for ( i = v4; !*((_BYTE *)i + 25); v4 = i )
  {
    std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase((char *)this + 96, i[2]);
    i = (_QWORD *)*i;
    operator delete(v4);
  }
  *(_QWORD *)(*(_QWORD *)v3 + 8LL) = *(_QWORD *)v3;
  **(_QWORD **)v3 = *(_QWORD *)v3;
  *(_QWORD *)(*(_QWORD *)v3 + 16LL) = *(_QWORD *)v3;
  *((_QWORD *)this + 13) = 0;
  std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear((char *)this + 64);
  v6 = *(_QWORD **)(*((_QWORD *)this + 14) + 8LL);
  for ( j = v6; !*((_BYTE *)j + 25); v6 = j )
  {
    std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase((char *)this + 112, j[2]);
    j = (_QWORD *)*j;
    operator delete(v6);
  }
  *(_QWORD *)(*((_QWORD *)this + 14) + 8LL) = *((_QWORD *)this + 14);
  **((_QWORD **)this + 14) = *((_QWORD *)this + 14);
  *(_QWORD *)(*((_QWORD *)this + 14) + 16LL) = *((_QWORD *)this + 14);
  *((_QWORD *)this + 15) = 0;
  return v2;
}

```

## disassembly

```asm
0x1800086cc  push    rbx
0x1800086ce  push    rbp
0x1800086cf  push    rsi
0x1800086d0  push    rdi
0x1800086d1  push    r14
0x1800086d3  sub     rsp, 20h
0x1800086d7  mov     rbx, rcx
0x1800086da  xor     r14d, r14d
0x1800086dd  mov     rcx, [rcx+80h]
0x1800086e4  test    rcx, rcx
0x1800086e7  jz      short loc_1800086FD
0x1800086e9  call    cs:__imp_WdiCloseInstance
0x1800086ef  mov     r14d, eax
0x1800086f2  mov     qword ptr [rbx+80h], 0
0x1800086fd  mov     dword ptr [rbx+88h], 0
0x180008707  mov     rcx, [rbx+30h]; pv
0x18000870b  call    cs:__imp_CoTaskMemFree
0x180008711  mov     qword ptr [rbx+30h], 0
0x180008719  mov     rcx, [rbx+38h]; pv
0x18000871d  call    cs:__imp_CoTaskMemFree
0x180008723  mov     qword ptr [rbx+38h], 0
0x18000872b  mov     dword ptr [rbx+0BE0h], 0
0x180008735  lea     rsi, [rbx+60h]
0x180008739  mov     rax, [rsi]
0x18000873c  mov     rbp, [rax+8]
0x180008740  mov     rdi, rbp
0x180008743  cmp     byte ptr [rbp+19h], 0
0x180008747  jnz     short loc_18000876A
0x180008749  mov     rdx, [rdi+10h]
0x18000874d  mov     rcx, rsi
0x180008750  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase(std::_Tree_node<_GUID,void *> *)
0x180008755  mov     rdi, [rdi]
0x180008758  mov     rcx, rbp
0x18000875b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180008761  mov     rbp, rdi
0x180008764  cmp     byte ptr [rdi+19h], 0
0x180008768  jz      short loc_180008749
0x18000876a  mov     rax, [rsi]
0x18000876d  mov     [rax+8], rax
0x180008771  mov     rax, [rsi]
0x180008774  mov     [rax], rax
0x180008777  mov     rax, [rsi]
0x18000877a  mov     [rax+10h], rax
0x18000877e  mov     qword ptr [rsi+8], 0
0x180008786  lea     rcx, [rbx+40h]
0x18000878a  call    ?clear@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@UWstringLessThan@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,WstringLessThan,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::clear(void)
0x18000878f  nop
0x180008790  mov     rax, [rbx+70h]
0x180008794  mov     rsi, [rax+8]
0x180008798  mov     rdi, rsi
0x18000879b  cmp     byte ptr [rsi+19h], 0
0x18000879f  jnz     short loc_1800087C3
0x1800087a1  mov     rdx, [rdi+10h]
0x1800087a5  lea     rcx, [rbx+70h]
0x1800087a9  call    ?_Erase@?$_Tree@V?$_Tset_traits@U_GUID@@UGuidLessThan@@V?$allocator@U_GUID@@@std@@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U_GUID@@PEAX@2@@Z; std::_Tree<std::_Tset_traits<_GUID,GuidLessThan,std::allocator<_GUID>,0>>::_Erase(std::_Tree_node<_GUID,void *> *)
0x1800087ae  mov     rdi, [rdi]
0x1800087b1  mov     rcx, rsi
0x1800087b4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800087ba  mov     rsi, rdi
0x1800087bd  cmp     byte ptr [rdi+19h], 0
0x1800087c1  jz      short loc_1800087A1
0x1800087c3  mov     rax, [rbx+70h]
0x1800087c7  mov     [rax+8], rax
0x1800087cb  mov     rax, [rbx+70h]
0x1800087cf  mov     [rax], rax
0x1800087d2  mov     rax, [rbx+70h]
0x1800087d6  mov     [rax+10h], rax
0x1800087da  mov     qword ptr [rbx+78h], 0
0x1800087e2  mov     eax, r14d
0x1800087e5  add     rsp, 20h
0x1800087e9  pop     r14
0x1800087eb  pop     rdi
0x1800087ec  pop     rsi
0x1800087ed  pop     rbp
0x1800087ee  pop     rbx
0x1800087ef  retn
```
