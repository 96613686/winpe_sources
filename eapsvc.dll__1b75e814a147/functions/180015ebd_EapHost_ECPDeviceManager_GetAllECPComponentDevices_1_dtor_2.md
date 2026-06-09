# _EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor$2

- ea: `0x180015ebd`
- end: `0x180015ec9`
- name: `_EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001159c`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::GetAllECPComponentDevices_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>(a2 + 96);
}

```

## disassembly

```asm
0x180015ebd  lea     rcx, [rdx+60h]
0x180015ec4  jmp     ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$CComPtr@UIUMBusPDO@@@ATL@@@std@@QEAA@XZ; std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>::~pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>,ATL::CComPtr<IUMBusPDO>>(void)
```
