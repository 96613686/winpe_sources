# _RegistryConfig::GetStringValue_::_1_::dtor$1

- ea: `0x18000d4c5`
- end: `0x18000d4d1`
- name: `_RegistryConfig::GetStringValue_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a514`

## pseudocode

```c
void __fastcall RegistryConfig::GetStringValue_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::vector<unsigned short>::~vector<unsigned short>(a2 + 72);
}

```

## disassembly

```asm
0x18000d4c5  lea     rcx, [rdx+48h]
0x18000d4cc  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
