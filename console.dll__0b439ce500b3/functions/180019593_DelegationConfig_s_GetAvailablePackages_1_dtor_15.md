# _DelegationConfig::s_GetAvailablePackages_::_1_::dtor$15

- ea: `0x180019593`
- end: `0x18001959f`
- name: `_DelegationConfig::s_GetAvailablePackages_::_1_::dtor$15`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180008cb0`

## pseudocode

```c
void __fastcall DelegationConfig::s_GetAvailablePackages_::_1_::dtor_15(__int64 a1, __int64 a2)
{
  DelegationConfig::DelegationPackage::~DelegationPackage((DelegationConfig::DelegationPackage *)(a2 + 176));
}

```

## disassembly

```asm
0x180019593  lea     rcx, [rdx+0B0h]; this
0x18001959a  jmp     ??1DelegationPackage@DelegationConfig@@QEAA@XZ; DelegationConfig::DelegationPackage::~DelegationPackage(void)
```
