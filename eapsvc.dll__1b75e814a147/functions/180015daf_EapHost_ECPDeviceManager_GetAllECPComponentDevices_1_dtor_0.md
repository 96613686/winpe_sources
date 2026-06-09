# _EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor$0

- ea: `0x180015daf`
- end: `0x180015dbb`
- name: `_EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a8f0`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>((__int64 *)(a2 + 56));
}

```

## disassembly

```asm
0x180015daf  lea     rcx, [rdx+38h]
0x180015db6  jmp     ??1?$CComPtr@UIFunctionDiscovery@@@ATL@@QEAA@XZ; ATL::CComPtr<IFunctionDiscovery>::~CComPtr<IFunctionDiscovery>(void)
```
