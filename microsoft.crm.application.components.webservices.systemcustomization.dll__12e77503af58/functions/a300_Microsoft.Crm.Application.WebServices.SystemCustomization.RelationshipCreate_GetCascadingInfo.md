# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetCascadingInfo

- ea: `0xa300`
- end: `0xa3cf`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetCascadingInfo`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xa0c0`

## callees

- `0x200`
- `0x360`
- `0xa300`

## string_xrefs

- `0xa382`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0xa300  ldarg.1
0xa301  ldarg.0
0xa302  ldstr    aAssign// "assign"
0xa307  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa30c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa311  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa316  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa31b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa320  ldarg.1
0xa321  ldarg.0
0xa322  ldstr    aShare// "share"
0xa327  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa32c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa331  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa336  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa33b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa340  ldarg.1
0xa341  ldarg.0
0xa342  ldstr    aUnshare// "unshare"
0xa347  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa34c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa351  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa356  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa35b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa360  ldarg.1
0xa361  ldarg.0
0xa362  ldstr    aReparent// "reparent"
0xa367  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa36c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa371  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa376  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa37b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa380  ldarg.1
0xa381  ldarg.0
0xa382  ldstr    aDelete// "delete"
0xa387  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa38c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa391  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa396  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa39b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa3a0  ldarg.0
0xa3a1  ldstr    aRollupview// "rollupview"
0xa3a6  ldnull
0xa3a7  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xa3ac  brfalse.s loc_A3CE
0xa3ae  ldarg.1
0xa3af  ldarg.0
0xa3b0  ldstr    aRollupview// "rollupview"
0xa3b5  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa3ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3bf  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa3c4  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xa3c9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipCreateInfo::set_CascadeRollupView(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xa3ce  ret
```
