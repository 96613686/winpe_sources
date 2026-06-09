# std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>(void)

- ea: `0x18000ecfc`
- end: `0x18000ed95`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `153`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ed9c`
- `0x18000f77c`

## callees

- `0x180002330`
- `0x18000ab70`
- `0x18000eafc`
- `0x18000ecfc`
- `0x180017010`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>::~_Tree<std::_Tmap_traits<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>,std::less<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>,std::allocator<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>,0>>(
        void **a1)
{
  __int64 *v2; // rdi
  __int64 *v3; // rbx
  __int64 v4; // rcx

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      (__int64 *)v2[2]);
    v3 = v2;
    v2 = (__int64 *)*v2;
    v4 = v3[8];
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    if ( (unsigned __int64)v3[7] > 7 )
      operator delete((LPCVOID)v3[4]);
    v3[6] = 0;
    v3[7] = 7;
    *((_WORD *)v3 + 16) = 0;
    operator delete(v3, 0x48u);
  }
  operator delete(*a1, 0x48u);
}

```

## disassembly

```asm
0x18000ecfc  mov     [rsp+arg_0], rbx
0x18000ed01  mov     [rsp+arg_8], rsi
0x18000ed06  push    rdi
0x18000ed07  sub     rsp, 20h
0x18000ed0b  mov     rsi, rcx
0x18000ed0e  mov     rax, [rcx]
0x18000ed11  mov     rdi, [rax+8]
0x18000ed15  jmp     short loc_18000ED73
0x18000ed17  mov     r8, [rdi+10h]
0x18000ed1b  mov     rdx, rsi
0x18000ed1e  mov     rcx, rsi
0x18000ed21  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> *)
0x18000ed26  mov     rbx, rdi
0x18000ed29  mov     rdi, [rdi]
0x18000ed2c  mov     rcx, [rbx+40h]
0x18000ed30  test    rcx, rcx
0x18000ed33  jz      short loc_18000ED42
0x18000ed35  mov     rax, [rcx]
0x18000ed38  mov     rax, [rax+10h]
0x18000ed3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed41  nop
0x18000ed42  cmp     qword ptr [rbx+38h], 7
0x18000ed47  jbe     short loc_18000ED52
0x18000ed49  mov     rcx, [rbx+20h]; lpMem
0x18000ed4d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000ed52  mov     qword ptr [rbx+30h], 0
0x18000ed5a  mov     qword ptr [rbx+38h], 7
0x18000ed62  xor     eax, eax
0x18000ed64  mov     [rbx+20h], ax
0x18000ed68  lea     edx, [rax+48h]; unsigned __int64
0x18000ed6b  mov     rcx, rbx; void *
0x18000ed6e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ed73  cmp     byte ptr [rdi+19h], 0
0x18000ed77  jz      short loc_18000ED17
0x18000ed79  mov     edx, 48h ; 'H'; unsigned __int64
0x18000ed7e  mov     rcx, [rsi]; void *
0x18000ed81  mov     rbx, [rsp+28h+arg_0]
0x18000ed86  mov     rsi, [rsp+28h+arg_8]
0x18000ed8b  add     rsp, 20h
0x18000ed8f  pop     rdi
0x18000ed90  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
