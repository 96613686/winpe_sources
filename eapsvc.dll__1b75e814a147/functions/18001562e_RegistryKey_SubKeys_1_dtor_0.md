# _RegistryKey::SubKeys_::_1_::dtor$0

- ea: `0x18001562e`
- end: `0x18001563a`
- name: `_RegistryKey::SubKeys_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000cc1c`

## pseudocode

```c
void __fastcall RegistryKey::SubKeys_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>((void **)(a2 + 112));
}

```

## disassembly

```asm
0x18001562e  lea     rcx, [rdx+70h]
0x180015635  jmp     ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::~vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
```
