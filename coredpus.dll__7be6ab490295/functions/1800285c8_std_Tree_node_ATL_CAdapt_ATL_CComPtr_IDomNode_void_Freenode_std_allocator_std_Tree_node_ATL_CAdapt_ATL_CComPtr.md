# std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>::_Freenode<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>> &,std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *> *)

- ea: `0x1800285c8`
- end: `0x1800285ec`
- name: `??$_Freenode@V?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@std@@@?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@1@PEAU01@@Z`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002851c`
- `0x18002ad1c`

## callees

- `0x1800110bc`
- `0x180011ec4`

## pseudocode

```c
__int64 __fastcall std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>::_Freenode<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(
        __int64 a1,
        __int64 a2)
{
  wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>((__int64 *)(a2 + 32));
  return std::_Deallocate<16>(a2, 40);
}

```

## disassembly

```asm
0x1800285c8  push    rbx
0x1800285ca  sub     rsp, 20h
0x1800285ce  lea     rcx, [rdx+20h]
0x1800285d2  mov     rbx, rdx
0x1800285d5  call    ??1?$com_ptr_t@UIConfigManager2URI@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IConfigManager2URI,wil::err_exception_policy>::~com_ptr_t<IConfigManager2URI,wil::err_exception_policy>(void)
0x1800285da  mov     edx, 28h ; '('
0x1800285df  mov     rcx, rbx
0x1800285e2  add     rsp, 20h
0x1800285e6  pop     rbx
0x1800285e7  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
