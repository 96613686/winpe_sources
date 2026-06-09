# Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::IsV4Plugin

- ea: `0x1420`
- end: `0x1440`
- name: `Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::IsV4Plugin`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1500`

## callees

- `0x1420`

## string_xrefs

- `0x142a`: `Microsoft.Crm.Sdk.IPlugin`

## pseudocode

```c

```

## disassembly

```asm
0x1420  ldc.i4.0
0x1421  stloc.0
0x1422  ldarg.1
0x1423  ldarg.2
0x1424  ldc.i4.1
0x1425  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string, bool)
0x142a  ldstr    aMicrosoftCrmSd// "Microsoft.Crm.Sdk.IPlugin"
0x142f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Type::GetInterface(string)
0x1434  ldnull
0x1435  call     bool [mscorlib]System.Type::op_Inequality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x143a  brfalse.s loc_143E
0x143c  ldc.i4.1
0x143d  stloc.0
0x143e  ldloc.0
0x143f  ret
```
