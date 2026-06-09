# _RegistryConfig::Delete_::_1_::dtor$0

- ea: `0x18000db51`
- end: `0x18000db5d`
- name: `_RegistryConfig::Delete_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180006ce0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::Delete_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 176);
}

```

## disassembly

```asm
0x18000db51  lea     rcx, [rdx+0B0h]
0x18000db58  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
