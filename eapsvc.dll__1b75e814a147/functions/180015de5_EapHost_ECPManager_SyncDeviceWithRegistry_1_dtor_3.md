# _EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$3

- ea: `0x180015de5`
- end: `0x180015df1`
- name: `_EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$3`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000ed9c`

## pseudocode

```c
void __fastcall EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>((void **)(a2 + 80));
}

```

## disassembly

```asm
0x180015de5  lea     rcx, [rdx+50h]
0x180015dec  jmp     ??1?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@2@@std@@QEAA@XZ; std::map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~map<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>(void)
```
