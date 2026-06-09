# _ServiceManager::ServiceManager_::_1_::dtor$4

- ea: `0x1800156fc`
- end: `0x180015708`
- name: `_ServiceManager::ServiceManager_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000a914`

## pseudocode

```c
__int64 __fastcall ServiceManager::ServiceManager_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(a2 + 128);
}

```

## disassembly

```asm
0x1800156fc  lea     rcx, [rdx+80h]
0x180015703  jmp     ??1?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@QEAA@XZ; std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>::~basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>(void)
```
