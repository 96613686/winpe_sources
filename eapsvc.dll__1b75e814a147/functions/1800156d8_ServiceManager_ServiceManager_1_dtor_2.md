# _ServiceManager::ServiceManager_::_1_::dtor$2

- ea: `0x1800156d8`
- end: `0x1800156e4`
- name: `_ServiceManager::ServiceManager_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a914`

## pseudocode

```c
__int64 __fastcall ServiceManager::ServiceManager_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(a2 + 96);
}

```

## disassembly

```asm
0x1800156d8  lea     rcx, [rdx+60h]
0x1800156df  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
```
