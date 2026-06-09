# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::GetFlyOutDescriptor

- ea: `0x9680`
- end: `0x96f0`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::GetFlyOutDescriptor`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x9630`
- `0x9650`

## string_xrefs

- `0x969a`: `Unexpected composite field type: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x9680  ldtoken  [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CompositeFieldType
0x9685  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x968a  ldarg.0
0x968b  call     instance int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_CompositeFieldType()
0x9690  box      [mscorlib]System.Int32
0x9695  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x969a  ldstr    aUnexpectedComp// "Unexpected composite field type: {0}"
0x969f  ldc.i4.1
0x96a0  newarr   [mscorlib]System.Object
0x96a5  dup
0x96a6  ldc.i4.0
0x96a7  ldarg.0
0x96a8  call     instance int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_CompositeFieldType()
0x96ad  box      [mscorlib]System.Int32
0x96b2  stelem.ref
0x96b3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string, object[])
0x96b8  ldarg.0
0x96b9  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_Metadata()
0x96be  ldarg.0
0x96bf  call     instance int32 Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.CompositionLinkControl::get_CompositeFieldType()
0x96c4  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICompositeFieldDefinition [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CompositeFieldDefinitionFactory::GetCompositeFieldDefinition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CompositeFieldType)
0x96c9  stloc.0
0x96ca  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ComplexControlCache [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ComplexControlCache::get_Instance()
0x96cf  ldloc.0
0x96d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICompositeFieldDefinition::get_LinkControlDefinitionId()
0x96d5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x96da  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ComplexControlData>::LookupEntry(void, var<u1>)
0x96df  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Caching.ComplexControlData::get_ComplexControlXml()
0x96e4  ldloc.0
0x96e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x96ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Components.Platform.FlyOutDefinition.FlyOutDescriptor::GetCompositionFlyOutDescriptor(string, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ICompositeFieldDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x96ef  ret
```
