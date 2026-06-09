# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::GetRequiredColumns

- ea: `0x21a30`
- end: `0x21a87`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::GetRequiredColumns`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x21750`
- `0x21760`
- `0x21a30`

## string_xrefs

- `0x21a57`: `address1_composite`
- `0x21a64`: `address1_composite`

## pseudocode

```c

```

## disassembly

```asm
0x21a30  ldarg.0
0x21a31  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::get_AddressField()
0x21a36  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21a3b  brfalse.s loc_21A77
0x21a3d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x21a42  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x21a47  ldarg.1
0x21a48  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x21a4d  stloc.0
0x21a4e  ldloc.0
0x21a4f  brfalse.s loc_21A70
0x21a51  ldloc.0
0x21a52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x21a57  ldstr    aAddress1Compos// "address1_composite"
0x21a5c  callvirt instance bool class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::ContainsKey(object)
0x21a61  brfalse.s loc_21A70
0x21a63  ldarg.0
0x21a64  ldstr    aAddress1Compos// "address1_composite"
0x21a69  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::set_AddressField(string value)
0x21a6e  br.s     loc_21A77
0x21a70  ldc.i4.0
0x21a71  newarr   [mscorlib]System.String
0x21a76  ret
0x21a77  ldc.i4.1
0x21a78  newarr   [mscorlib]System.String
0x21a7d  dup
0x21a7e  ldc.i4.0
0x21a7f  ldarg.0
0x21a80  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::get_AddressField()
0x21a85  stelem.ref
0x21a86  ret
```
