# Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::CurrentDomain_ReflectionOnlyAssemblyResolve

- ea: `0x1440`
- end: `0x145a`
- name: `Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::CurrentDomain_ReflectionOnlyAssemblyResolve`
- size: `26`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1440`

## string_xrefs

- `0x1446`: `Microsoft.Crm.Sdk, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x1440  ldarg.2
0x1441  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x1446  ldstr    aMicrosoftCrmSd_0// "Microsoft.Crm.Sdk, Version=4.0.0.0, Cul"...
0x144b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1450  brfalse.s loc_1458
0x1452  ldsfld   class [mscorlib]System.Reflection.Assembly Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::v4MicrosoftCrmSdkAssembly
0x1457  ret
0x1458  ldnull
0x1459  ret
```
