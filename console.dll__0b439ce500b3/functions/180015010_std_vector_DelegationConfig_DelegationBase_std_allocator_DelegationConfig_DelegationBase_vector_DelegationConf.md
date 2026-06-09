# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>(void)

- ea: `0x180015010`
- end: `0x180015021`
- name: `??0?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@QEAA@XZ`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180016c14`

## pseudocode

```c
_QWORD *__fastcall std::vector<DelegationConfig::DelegationBase>::vector<DelegationConfig::DelegationBase>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  return a1;
}

```

## disassembly

```asm
0x180015010  xor     eax, eax
0x180015012  mov     [rcx], rax
0x180015015  mov     [rcx+8], rax
0x180015019  mov     [rcx+10h], rax
0x18001501d  mov     rax, rcx
0x180015020  retn
```
