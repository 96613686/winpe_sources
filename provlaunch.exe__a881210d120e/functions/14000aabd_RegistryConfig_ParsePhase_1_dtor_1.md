# _RegistryConfig::ParsePhase_::_1_::dtor$1

- ea: `0x14000aabd`
- end: `0x14000aac9`
- name: `_RegistryConfig::ParsePhase_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140006ddc`

## pseudocode

```c
__int64 __fastcall RegistryConfig::ParsePhase_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::vector<unsigned short>::_Tidy(a2 + 128);
}

```

## disassembly

```asm
0x14000aabd  lea     rcx, [rdx+80h]
0x14000aac4  jmp     ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@IEAAXXZ; std::vector<ushort>::_Tidy(void)
```
