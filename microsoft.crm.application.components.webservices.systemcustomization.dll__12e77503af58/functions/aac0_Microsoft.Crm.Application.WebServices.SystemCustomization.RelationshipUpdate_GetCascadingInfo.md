# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetCascadingInfo

- ea: `0xaac0`
- end: `0xabbf`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetCascadingInfo`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0xa7f0`

## callees

- `0x190`
- `0x1a0`
- `0x200`
- `0x340`
- `0x360`
- `0xaac0`

## string_xrefs

- `0xab5d`: `delete`
- `0xab6c`: `delete`

## pseudocode

```c

```

## disassembly

```asm
0xaac0  ldarg.0
0xaac1  ldstr    aCascading// "cascading"
0xaac6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xaacb  brfalse  loc_ABBE
0xaad0  ldarg.0
0xaad1  ldstr    aCascading// "cascading"
0xaad6  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0xaadb  stloc.0
0xaadc  ldarg.1
0xaadd  ldloc.0
0xaade  ldstr    aAssign// "assign"
0xaae3  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xaae8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaaed  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xaaf2  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xaaf7  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeAssign(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xaafc  ldarg.1
0xaafd  ldloc.0
0xaafe  ldstr    aShare// "share"
0xab03  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xab0d  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xab12  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab17  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeShare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xab1c  ldarg.1
0xab1d  ldloc.0
0xab1e  ldstr    aUnshare// "unshare"
0xab23  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab28  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xab2d  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xab32  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab37  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeUnshare(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xab3c  ldarg.1
0xab3d  ldloc.0
0xab3e  ldstr    aReparent// "reparent"
0xab43  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab48  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xab4d  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xab52  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab57  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeReparent(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xab5c  ldloc.0
0xab5d  ldstr    aDelete// "delete"
0xab62  ldnull
0xab63  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xab68  brfalse.s loc_AB90
0xab6a  ldarg.1
0xab6b  ldloc.0
0xab6c  ldstr    aDelete// "delete"
0xab71  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xab7b  ldc.i4.1
0xab7c  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab81  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType, class [mscorlib]System.Enum defaultValue)
0xab86  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xab8b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeDelete(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xab90  ldloc.0
0xab91  ldstr    aRollupview// "rollupview"
0xab96  ldnull
0xab97  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0xab9c  brfalse.s loc_ABBE
0xab9e  ldarg.1
0xab9f  ldloc.0
0xaba0  ldstr    aRollupview// "rollupview"
0xaba5  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xabaa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xabaf  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xabb4  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType
0xabb9  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.RelationshipUpdateInfo::set_CascadeRollupView(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CascadeLinkType)
0xabbe  ret
```
