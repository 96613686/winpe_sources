# Microsoft.Crm.Metadata.AttributeInfo::SetValidForApiProperties

- ea: `0x17ee0`
- end: `0x17f81`
- name: `Microsoft.Crm.Metadata.AttributeInfo::SetValidForApiProperties`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17980`

## callees

- `0x17ee0`
- `0x18760`
- `0x187b0`

## string_xrefs

- `0x17f06`: `validforcreateapi`
- `0x17f46`: `validforupdateapi`
- `0x17f23`: `ValidForCreateApi`
- `0x17f63`: `ValidForUpdateApi`

## pseudocode

```c

```

## disassembly

```asm
0x17ee0  ldarg.0
0x17ee1  call     instance bool Microsoft.Crm.Metadata.AttributeInfo::get_IsRollupField()
0x17ee6  brfalse.s loc_17F00
0x17ee8  ldarg.1
0x17ee9  ldarg.2
0x17eea  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForCreateApi()
0x17eef  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool)
0x17ef4  ldarg.1
0x17ef5  ldarg.2
0x17ef6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForUpdateApi()
0x17efb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool)
0x17f00  ldarg.0
0x17f01  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f06  ldstr    aValidforcreate// "validforcreateapi"
0x17f0b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17f10  brfalse.s loc_17F40
0x17f12  ldarg.1
0x17f13  ldarg.0
0x17f14  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f19  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForCreateApi()
0x17f1e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForCreateApi(bool)
0x17f23  ldstr    aValidforcreate_0// "ValidForCreateApi"
0x17f28  ldarg.0
0x17f29  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f2e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForCreateApi()
0x17f33  stloc.0
0x17f34  ldloca.s 0
0x17f36  call     instance string [mscorlib]System.Boolean::ToString()
0x17f3b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17f40  ldarg.0
0x17f41  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f46  ldstr    aValidforupdate// "validforupdateapi"
0x17f4b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ManagedMetadataDescriptionBase::get_Item(string)
0x17f50  brfalse.s loc_17F80
0x17f52  ldarg.1
0x17f53  ldarg.0
0x17f54  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f59  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForUpdateApi()
0x17f5e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_ValidForUpdateApi(bool)
0x17f63  ldstr    aValidforupdate_0// "ValidForUpdateApi"
0x17f68  ldarg.0
0x17f69  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::get_AttributeDescription()
0x17f6e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::get_ValidForUpdateApi()
0x17f73  stloc.0
0x17f74  ldloca.s 0
0x17f76  call     instance string [mscorlib]System.Boolean::ToString()
0x17f7b  call     void [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::AddCustomProperty(string, string)
0x17f80  ret
```
