# _DelegationConfig::s_GetAvailablePackages_::_1_::dtor$14

- ea: `0x1800195b7`
- end: `0x1800195c3`
- name: `_DelegationConfig::s_GetAvailablePackages_::_1_::dtor$14`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180015114`

## pseudocode

```c
__int64 __fastcall DelegationConfig::s_GetAvailablePackages_::_1_::dtor_14(__int64 a1, __int64 a2)
{
  return std::vector<DelegationConfig::DelegationBase>::~vector<DelegationConfig::DelegationBase>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x1800195b7  lea     rcx, [rdx+28h]
0x1800195be  jmp     ??1?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ; std::vector<DelegationConfig::DelegationBase>::~vector<DelegationConfig::DelegationBase>(void)
```
