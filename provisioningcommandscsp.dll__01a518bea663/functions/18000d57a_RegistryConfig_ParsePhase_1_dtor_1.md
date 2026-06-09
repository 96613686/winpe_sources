# _RegistryConfig::ParsePhase_::_1_::dtor$1

- ea: `0x18000d57a`
- end: `0x18000d586`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a514`

## pseudocode

```c
void __fastcall RegistryConfig::ParsePhase_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  std::vector<unsigned short>::~vector<unsigned short>(a2 + 128);
}

```

## disassembly

```asm
0x18000d57a  lea     rcx, [rdx+80h]
0x18000d581  jmp     ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
```
