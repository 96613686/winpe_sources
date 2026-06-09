# std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>(void)

- ea: `0x18001cb94`
- end: `0x18001cbbc`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@U?$pair@$$CB_KV?$com_ptr_t@VCFrameProcessorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c52c`
- `0x18001f55c`
- `0x18001f704`
- `0x180029a76`

## callees

- `0x180007b28`
- `0x18001cab8`
- `0x18001cb94`

## pseudocode

```c
__int64 __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<std::pair<unsigned __int64 const,wil::com_ptr_t<Rdp::Stack::Shim::CFrameProcessorShim,wil::err_exception_policy>>,void *>>>(
        __int64 a1)
{
  __int64 v2; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  if ( v2 )
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>((__int64 *)(v2 + 24));
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>,void *>>>(a1);
}

```

## disassembly

```asm
0x18001cb94  push    rbx
0x18001cb96  sub     rsp, 20h
0x18001cb9a  mov     rbx, rcx
0x18001cb9d  mov     rcx, [rcx+8]
0x18001cba1  test    rcx, rcx
0x18001cba4  jz      short loc_18001CBAF
0x18001cba6  add     rcx, 18h
0x18001cbaa  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x18001cbaf  mov     rcx, rbx
0x18001cbb2  add     rsp, 20h
0x18001cbb6  pop     rbx
0x18001cbb7  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@U?$pair@QEAXV?$com_ptr_t@UID3D11Fence@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::pair<void * const,wil::com_ptr_t<ID3D11Fence,wil::err_exception_policy>>,void *>>>(void)
```
