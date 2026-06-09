# std::vector<DelegationConfig::DelegationBase,std::allocator<DelegationConfig::DelegationBase>>::_Xlength(void)

- ea: `0x180015860`
- end: `0x180015878`
- name: `?_Xlength@?$vector@UDelegationBase@DelegationConfig@@V?$allocator@UDelegationBase@DelegationConfig@@@std@@@std@@CAXXZ`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180014ac0`
- `0x180014c20`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001586b`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18001586b`

## pseudocode

```c
void __noreturn std::vector<DelegationConfig::DelegationBase>::_Xlength()
{
  std::_Xlength_error("vector too long");
}

```

## disassembly

```asm
0x180015860  sub     rsp, 28h
0x180015864  lea     rcx, aVectorTooLong; "vector too long"
0x18001586b  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
