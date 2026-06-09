# _RegistryStore::LoadInstalledPrinters_::_1_::dtor$13

- ea: `0x14001359d`
- end: `0x1400135a9`
- name: `_RegistryStore::LoadInstalledPrinters_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x14000e7ec`

## pseudocode

```c
__int64 __fastcall RegistryStore::LoadInstalledPrinters_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>(a2 + 96);
}

```

## disassembly

```asm
0x14001359d  lea     rcx, [rdx+60h]
0x1400135a4  jmp     ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<std::wstring,void *>>>(void)
```
