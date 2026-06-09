# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>,void *>>>(void)

- ea: `0x18000b1e4`
- end: `0x18000b20c`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a6d8`
- `0x180014215`

## callees

- `0x18000b04c`
- `0x18000b1e4`
- `0x18000b370`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::~pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(v2 + 16);
  std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(a1);
}

```

## disassembly

```asm
0x18000b1e4  push    rbx
0x18000b1e6  sub     rsp, 20h
0x18000b1ea  mov     rbx, rcx
0x18000b1ed  mov     rcx, [rcx+8]
0x18000b1f1  test    rcx, rcx
0x18000b1f4  jz      short loc_18000B1FF
0x18000b1f6  add     rcx, 10h
0x18000b1fa  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ; std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::~pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(void)
0x18000b1ff  mov     rcx, rbx
0x18000b202  add     rsp, 20h
0x18000b206  pop     rbx
0x18000b207  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>,void *>>>(void)
```
