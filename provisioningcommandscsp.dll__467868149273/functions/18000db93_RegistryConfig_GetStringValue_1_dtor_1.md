# _RegistryConfig::GetStringValue_::_1_::dtor$1

- ea: `0x18000db93`
- end: `0x18000db9f`
- name: `_RegistryConfig::GetStringValue_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000aa6c`

## pseudocode

```c
__int64 __fastcall RegistryConfig::GetStringValue_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(a2 + 72);
}

```

## disassembly

```asm
0x18000db93  lea     rcx, [rdx+48h]
0x18000db9a  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
