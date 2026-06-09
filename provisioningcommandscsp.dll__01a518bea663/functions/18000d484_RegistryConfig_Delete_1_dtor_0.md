# _RegistryConfig::Delete_::_1_::dtor$0

- ea: `0x18000d484`
- end: `0x18000d490`
- name: `_RegistryConfig::Delete_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1800069c0`

## pseudocode

```c
__int64 __fastcall RegistryConfig::Delete_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::wstring::~wstring(a2 + 176);
}

```

## disassembly

```asm
0x18000d484  lea     rcx, [rdx+0B0h]
0x18000d48b  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
