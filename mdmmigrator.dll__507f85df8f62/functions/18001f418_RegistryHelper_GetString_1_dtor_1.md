# _RegistryHelper::GetString_::_1_::dtor$1

- ea: `0x18001f418`
- end: `0x18001f424`
- name: `_RegistryHelper::GetString_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180009ed0`

## pseudocode

```c
__int64 __fastcall RegistryHelper::GetString_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::~vector<unsigned short>(a2 + 96);
}

```

## disassembly

```asm
0x18001f418  lea     rcx, [rdx+60h]
0x18001f41f  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
