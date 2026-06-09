# Microsoft.Crm.ParameterFilterBase::get_PageParameterCache

- ea: `0xe90`
- end: `0xe97`
- name: `Microsoft.Crm.ParameterFilterBase::get_PageParameterCache`
- size: `7`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xea0`
- `0xee0`
- `0xf20`
- `0xf70`
- `0xfa0`

## pseudocode

```c

```

## disassembly

```asm
0xe90  ldarg.0
0xe91  ldfld    class Microsoft.Crm.PageParametersCache Microsoft.Crm.ParameterFilterBase::_cache
0xe96  ret
```
