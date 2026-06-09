# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> *)

- ea: `0x18000eafc`
- end: `0x18000eb80`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@1@@Z`
- size: `132`
- prototype: `void __fastcall(__int64, __int64, __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000eafc`
- `0x18000ecfc`

## callees

- `0x180002330`
- `0x18000ab70`
- `0x18000eafc`
- `0x180017010`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 *v3; // rdi
  __int64 *v6; // rbx
  __int64 v7; // rcx

  v3 = a3;
  while ( !*((_BYTE *)v3 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(
      a1,
      a2,
      v3[2]);
    v6 = v3;
    v3 = (__int64 *)*v3;
    v7 = v6[8];
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    if ( (unsigned __int64)v6[7] > 7 )
      operator delete((LPCVOID)v6[4]);
    v6[6] = 0;
    v6[7] = 7;
    *((_WORD *)v6 + 16) = 0;
    operator delete(v6, 0x48u);
  }
}

```

## disassembly

```asm
0x18000eafc  push    rbx
0x18000eafe  push    rbp
0x18000eaff  push    rsi
0x18000eb00  push    rdi
0x18000eb01  sub     rsp, 28h
0x18000eb05  mov     rdi, r8
0x18000eb08  mov     rsi, rdx
0x18000eb0b  mov     rbp, rcx
0x18000eb0e  cmp     byte ptr [r8+19h], 0
0x18000eb13  jnz     short loc_18000EB77
0x18000eb15  mov     r8, [rdi+10h]
0x18000eb19  mov     rdx, rsi
0x18000eb1c  mov     rcx, rbp
0x18000eb1f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>> &,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *> *)
0x18000eb24  mov     rbx, rdi
0x18000eb27  mov     rdi, [rdi]
0x18000eb2a  mov     rcx, [rbx+40h]
0x18000eb2e  test    rcx, rcx
0x18000eb31  jz      short loc_18000EB40
0x18000eb33  mov     rax, [rcx]
0x18000eb36  mov     rax, [rax+10h]
0x18000eb3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb3f  nop
0x18000eb40  cmp     qword ptr [rbx+38h], 7
0x18000eb45  jbe     short loc_18000EB50
0x18000eb47  mov     rcx, [rbx+20h]; lpMem
0x18000eb4b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000eb50  mov     qword ptr [rbx+30h], 0
0x18000eb58  mov     qword ptr [rbx+38h], 7
0x18000eb60  xor     eax, eax
0x18000eb62  mov     [rbx+20h], ax
0x18000eb66  lea     edx, [rax+48h]; unsigned __int64
0x18000eb69  mov     rcx, rbx; void *
0x18000eb6c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000eb71  cmp     byte ptr [rdi+19h], 0
0x18000eb75  jz      short loc_18000EB15
0x18000eb77  add     rsp, 28h
0x18000eb7b  pop     rdi
0x18000eb7c  pop     rsi
0x18000eb7d  pop     rbp
0x18000eb7e  pop     rbx
0x18000eb7f  retn
```
