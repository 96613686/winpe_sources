# _EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor$1

- ea: `0x180015e3f`
- end: `0x180015e4b`
- name: `_EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a914`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::CheckECPComponentDevice_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(a2 + 80);
}

```

## disassembly

```asm
0x180015e3f  lea     rcx, [rdx+50h]
0x180015e46  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
```
