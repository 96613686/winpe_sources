# Microsoft.Crm.Sandbox.SandboxSdkListener::IsReportsOperation

- ea: `0x5420`
- end: `0x5440`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::IsReportsOperation`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x53e0`
- `0x5480`

## callees

- `0x5420`

## string_xrefs

- `0x5421`: `RetrieveEntityFromCache`

## pseudocode

```c

```

## disassembly

```asm
0x5420  ldarg.0
0x5421  ldstr    aRetrieveentity_0// "RetrieveEntityFromCache"
0x5426  ldc.i4.5
0x5427  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x542c  brfalse.s loc_543C
0x542e  ldarg.0
0x542f  ldstr    aRetrieveentiti// "RetrieveEntitiesForAggregateQuery"
0x5434  ldc.i4.5
0x5435  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x543a  brtrue.s loc_543E
0x543c  ldc.i4.1
0x543d  ret
0x543e  ldc.i4.0
0x543f  ret
```
