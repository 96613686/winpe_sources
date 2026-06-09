# std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>>::_Unchecked_begin(void)

- ea: `0x18000eb2c`
- end: `0x18000eb34`
- name: `?_Unchecked_begin@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ`
- size: `8`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000e94c`
- `0x180016c14`

## pseudocode

```c
__int64 std::vector<DelegationConfig::DelegationPackage>::_Unchecked_begin()
{
  return g_availablePackages;
}

```

## disassembly

```asm
0x18000eb2c  mov     rax, cs:?g_availablePackages@@3V?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@A; std::vector<DelegationConfig::DelegationPackage> g_availablePackages
0x18000eb33  retn
```
