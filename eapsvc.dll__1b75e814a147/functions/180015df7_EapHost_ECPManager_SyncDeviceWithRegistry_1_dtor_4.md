# _EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$4

- ea: `0x180015df7`
- end: `0x180015e03`
- name: `_EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$4`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000eda8`

## pseudocode

```c
void __fastcall EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  std::vector<ATL::CComPtr<IUMBusPDO>>::~vector<ATL::CComPtr<IUMBusPDO>>(a2 + 96);
}

```

## disassembly

```asm
0x180015df7  lea     rcx, [rdx+60h]
0x180015dfe  jmp     ??1?$vector@V?$CComPtr@UIUMBusPDO@@@ATL@@V?$allocator@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CComPtr<IUMBusPDO>>::~vector<ATL::CComPtr<IUMBusPDO>>(void)
```
