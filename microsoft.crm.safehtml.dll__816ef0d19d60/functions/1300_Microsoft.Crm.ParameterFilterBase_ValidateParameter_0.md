# Microsoft.Crm.ParameterFilterBase::ValidateParameter_0

- ea: `0x1300`
- end: `0x131b`
- name: `Microsoft.Crm.ParameterFilterBase::ValidateParameter_0`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1370`

## callees

- `0x1070`
- `0x1200`
- `0x1300`

## pseudocode

```c

```

## disassembly

```asm
0x1300  ldarg.0
0x1301  ldarg.2
0x1302  ldarg.3
0x1303  ldarg.s  4
0x1305  ldarg.s  5
0x1307  call     instance bool Microsoft.Crm.ParameterFilterBase::TryValidateParameter(class [mscorlib]System.Collections.ArrayList parameterCollection, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x130c  brtrue.s loc_131A
0x130e  ldarg.1
0x130f  ldarg.3
0x1310  ldarg.s  4
0x1312  ldarg.s  5
0x1314  call     class [mscorlib]System.Exception Microsoft.Crm.ParameterFilterBase::CreateValidationException(class [System.Web]System.Web.HttpRequest request, string key, string value, valuetype Microsoft.Crm.ParameterSources source)
0x1319  throw
0x131a  ret
```
