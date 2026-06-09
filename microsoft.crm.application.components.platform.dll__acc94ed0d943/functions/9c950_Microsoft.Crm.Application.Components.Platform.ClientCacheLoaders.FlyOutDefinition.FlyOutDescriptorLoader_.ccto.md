# Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::.cctor

- ea: `0x9c950`
- end: `0x9c9bf`
- name: `Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::.cctor`
- size: `111`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x9c95f`: `CaseResearchLinkControlId`
- `0x9c978`: `IncidentResolutionLinkControlId`
- `0x9c991`: `ProductSuggestionsLinkControlId`
- `0x9c9aa`: `DynamicPropertiesListLinkControlId`

## pseudocode

```c

```

## disassembly

```asm
0x9c950  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor()
0x9c955  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c95a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c95f  ldstr    aCaseresearchli// "CaseResearchLinkControlId"
0x9c964  ldstr    a0f337699D59548// "0F337699-D595-48D9-B733-6479E5F5EB07"
0x9c969  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c96e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x9c973  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c978  ldstr    aIncidentresolu// "IncidentResolutionLinkControlId"
0x9c97d  ldstr    a26cf241a886d48// "26cf241a-886d-4870-a22a-356cad9a75dd"
0x9c982  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c987  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x9c98c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c991  ldstr    aProductsuggest// "ProductSuggestionsLinkControlId"
0x9c996  ldstr    a05beff64E55e40// "05BEFF64-E55E-4000-A316-7CE46335755D"
0x9c99b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c9a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x9c9a5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.FlyOutDefinition.FlyOutDescriptorLoader::_linkControlGuid
0x9c9aa  ldstr    aDynamicpropert_0// "DynamicPropertiesListLinkControlId"
0x9c9af  ldstr    a9e5eebfc588343// "9E5EEBFC-5883-43C0-A36C-6FCA2615D5CA"
0x9c9b4  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x9c9b9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x9c9be  ret
```
