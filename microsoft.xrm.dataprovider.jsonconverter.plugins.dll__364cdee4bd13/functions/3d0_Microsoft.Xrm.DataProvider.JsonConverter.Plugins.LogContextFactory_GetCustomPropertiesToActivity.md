# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::GetCustomPropertiesToActivity

- ea: `0x3d0`
- end: `0x477`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::GetCustomPropertiesToActivity`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x290`

## callees

- `0x3d0`

## string_xrefs

- `0x41c`: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins`
- `0x428`: `pluginName`

## pseudocode

```c

```

## disassembly

```asm
0x3d0  nop
0x3d1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x3d6  dup
0x3d7  ldstr    aDatasource// "datasource"
0x3dc  ldarg.0
0x3dd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_DataSourceId()
0x3e2  stloc.0
0x3e3  ldloca.s 0
0x3e5  constrained. [mscorlib]System.Guid
0x3eb  callvirt instance string [mscorlib]System.Object::ToString()
0x3f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x3f5  nop
0x3f6  dup
0x3f7  ldstr    aDataprovider// "dataprovider"
0x3fc  ldarg.0
0x3fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_DataProviderId()
0x402  stloc.0
0x403  ldloca.s 0
0x405  constrained. [mscorlib]System.Guid
0x40b  callvirt instance string [mscorlib]System.Object::ToString()
0x410  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x415  nop
0x416  dup
0x417  ldstr    aAssemblyname// "assemblyName"
0x41c  ldstr    aMicrosoftXrmDa// "Microsoft.Xrm.DataProvider.JsonConverte"...
0x421  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x426  nop
0x427  dup
0x428  ldstr    aPluginname// "pluginName"
0x42d  ldarg.2
0x42e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x433  nop
0x434  dup
0x435  ldstr    aSdkmessage// "sdkMessage"
0x43a  ldarg.1
0x43b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x440  nop
0x441  dup
0x442  ldstr    aPrimaryentitym// "primaryEntityMetadataId"
0x447  ldarg.0
0x448  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.IDataProviderContext::get_PrimaryEntityMetadataId()
0x44d  stloc.0
0x44e  ldloca.s 0
0x450  constrained. [mscorlib]System.Guid
0x456  callvirt instance string [mscorlib]System.Object::ToString()
0x45b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x460  nop
0x461  dup
0x462  ldstr    aVersion// "version"
0x467  ldsfld   string Microsoft.Xrm.DataProvider.JsonConverter.Plugins.LogContextFactory::DataProviderVersion
0x46c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x471  nop
0x472  stloc.1
0x473  br.s     loc_475
0x475  ldloc.1
0x476  ret
```
