# Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::LoadCacheData

- ea: `0x9c9c0`
- end: `0x9ca09`
- name: `Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::LoadCacheData`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x59710`
- `0x5be20`
- `0x98e80`
- `0x9c9c0`

## string_xrefs

- `0x9c9cf`: `complexcontrol`
- `0x9c9dd`: `complexcontrolid`
- `0x9c9e5`: `complexcontrolxml`
- `0x9c9f1`: `complexcontrolxml`

## pseudocode

```c

```

## disassembly

```asm
0x9c9c0  ldnull
0x9c9c1  stloc.0
0x9c9c2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c9c7  ldarg.1
0x9c9c8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsValue(var<u1>)
0x9c9cd  brfalse.s loc_9CA01
0x9c9cf  ldstr    aComplexcontrol_0// "complexcontrol"
0x9c9d4  ldarg.1
0x9c9d5  ldc.i4.2
0x9c9d6  newarr   [mscorlib]System.String
0x9c9db  dup
0x9c9dc  ldc.i4.0
0x9c9dd  ldstr    aComplexcontrol_1// "complexcontrolid"
0x9c9e2  stelem.ref
0x9c9e3  dup
0x9c9e4  ldc.i4.1
0x9c9e5  ldstr    aComplexcontrol_2// "complexcontrolxml"
0x9c9ea  stelem.ref
0x9c9eb  ldarg.2
0x9c9ec  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9c9f1  ldstr    aComplexcontrol_2// "complexcontrolxml"
0x9c9f6  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x9c9fb  castclass [mscorlib]System.String
0x9ca00  stloc.0
0x9ca01  ldloc.0
0x9ca02  ldarg.2
0x9ca03  call     class Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor::GetFlyOutDescriptor(string flyOutDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x9ca08  ret
```
