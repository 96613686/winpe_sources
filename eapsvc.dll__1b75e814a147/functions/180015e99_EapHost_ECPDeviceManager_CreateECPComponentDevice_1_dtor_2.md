# _EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$2

- ea: `0x180015e99`
- end: `0x180015ea5`
- name: `_EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a914`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(a2 + 192);
}

```

## disassembly

```asm
0x180015e99  lea     rcx, [rdx+0C0h]
0x180015ea0  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
```
