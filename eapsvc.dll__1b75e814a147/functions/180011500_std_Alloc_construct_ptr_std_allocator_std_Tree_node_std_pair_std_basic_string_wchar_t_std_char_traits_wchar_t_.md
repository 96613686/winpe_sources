# std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(void)

- ea: `0x180011500`
- end: `0x18001151c`
- name: `??1?$_Alloc_construct_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `28`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015e1b`

## callees

- `0x180002330`
- `0x180011500`

## pseudocode

```c
void __fastcall std::_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> const,ATL::CComPtr<IUMBusPDO>>,void *>>>(
        __int64 a1)
{
  void *v1; // rcx

  v1 = *(void **)(a1 + 8);
  if ( v1 )
    operator delete(v1, 0x48u);
}

```

## disassembly

```asm
0x180011500  sub     rsp, 28h
0x180011504  mov     rcx, [rcx+8]; void *
0x180011508  test    rcx, rcx
0x18001150b  jz      short loc_180011517
0x18001150d  mov     edx, 48h ; 'H'; unsigned __int64
0x180011512  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011517  add     rsp, 28h
0x18001151b  retn
```
