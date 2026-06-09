# std::vector<DelegationConfig::DelegationPackage,std::allocator<DelegationConfig::DelegationPackage>>::_Unchecked_end(void)

- ea: `0x18000eb3c`
- end: `0x18000eb44`
- name: `?_Unchecked_end@?$vector@UDelegationPackage@DelegationConfig@@V?$allocator@UDelegationPackage@DelegationConfig@@@std@@@std@@QEBAPEBUDelegationPackage@DelegationConfig@@XZ`
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
__int64 std::vector<DelegationConfig::DelegationPackage>::_Unchecked_end()
{
  return xmmword_180023990;
}

```

## disassembly

```asm
0x18000eb3c  mov     rax, qword ptr cs:xmmword_180023990
0x18000eb43  retn
```
