# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$16

- ea: `0x1400135af`
- end: `0x1400135bb`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$16`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000e7ec`

## pseudocode

```c
__int64 __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_16(__int64 a1, __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>(a2 + 112);
}

```

## disassembly

```asm
0x1400135af  lea     rcx, [rdx+70h]
0x1400135b6  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>(void)
```
