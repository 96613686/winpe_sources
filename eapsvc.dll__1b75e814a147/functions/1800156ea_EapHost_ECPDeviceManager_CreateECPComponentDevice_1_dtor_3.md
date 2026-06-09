# _EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$3

- ea: `0x1800156ea`
- end: `0x1800156f6`
- name: `_EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor$3`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000a914`

## pseudocode

```c
__int64 __fastcall EapHost::ECPDeviceManager::CreateECPComponentDevice_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(a2 + 160);
}

```

## disassembly

```asm
0x1800156ea  lea     rcx, [rdx+0A0h]
0x1800156f1  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
```
