# _EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$2

- ea: `0x180015dd3`
- end: `0x180015ddf`
- name: `_EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cc1c`

## pseudocode

```c
void __fastcall EapHost::ECPManager::SyncDeviceWithRegistry_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>((void **)(a2 + 120));
}

```

## disassembly

```asm
0x180015dd3  lea     rcx, [rdx+78h]
0x180015dda  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
```
