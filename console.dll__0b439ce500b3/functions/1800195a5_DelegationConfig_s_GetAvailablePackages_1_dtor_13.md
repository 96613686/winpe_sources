# _DelegationConfig::s_GetAvailablePackages_::_1_::dtor$13

- ea: `0x1800195a5`
- end: `0x1800195b1`
- name: `_DelegationConfig::s_GetAvailablePackages_::_1_::dtor$13`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180015114`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_GetAvailablePackages_::_1_::dtor_13(__int64 a1, __int64 a2)
{
  return std::vector<DelegationConfig::DelegationBase>::~vector<DelegationConfig::DelegationBase>((__int64 *)(a2 + 64));
}

```

## disassembly

```asm
0x1800195a5  lea     rcx, [rdx+40h]
0x1800195ac  jmp     ??1?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationBase>::~vector<DelegationConfig::DelegationBase>(void)
```
