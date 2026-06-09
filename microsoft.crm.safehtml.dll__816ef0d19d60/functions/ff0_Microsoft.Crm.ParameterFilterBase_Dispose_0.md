# Microsoft.Crm.ParameterFilterBase::Dispose_0

- ea: `0xff0`
- end: `0x100e`
- name: `Microsoft.Crm.ParameterFilterBase::Dispose_0`
- size: `30`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xe70`
- `0xfe0`

## callees

- `0x450`
- `0xff0`

## pseudocode

```c

```

## disassembly

```asm
0xff0  ldarg.1
0xff1  brfalse.s loc_100D
0xff3  ldarg.0
0xff4  ldfld    class Microsoft.Crm.PageParametersCache Microsoft.Crm.ParameterFilterBase::_cache
0xff9  brfalse.s loc_100D
0xffb  ldarg.0
0xffc  ldfld    class Microsoft.Crm.PageParametersCache Microsoft.Crm.ParameterFilterBase::_cache
0x1001  callvirt instance void Microsoft.Crm.PageParametersCache::Dispose()
0x1006  ldarg.0
0x1007  ldnull
0x1008  stfld    class Microsoft.Crm.PageParametersCache Microsoft.Crm.ParameterFilterBase::_cache
0x100d  ret
```
