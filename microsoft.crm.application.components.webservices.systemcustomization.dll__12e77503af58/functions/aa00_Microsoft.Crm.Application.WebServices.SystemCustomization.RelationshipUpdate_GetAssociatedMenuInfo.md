# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo

- ea: `0xaa00`
- end: `0xaab2`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipUpdate::GetAssociatedMenuInfo`
- size: `178`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0xa6b0`
- `0xa7f0`

## callees

- `0x190`
- `0x220`
- `0x270`
- `0x360`
- `0xaa00`

## pseudocode

```c

```

## disassembly

```asm
0xaa00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xaa05  stloc.0
0xaa06  ldarg.0
0xaa07  ldstr    aDisplayoption// "displayoption"
0xaa0c  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xaa11  brfalse.s loc_AA33
0xaa13  ldarg.1
0xaa14  ldarg.0
0xaa15  ldstr    aDisplayoption// "displayoption"
0xaa1a  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption
0xaa1f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaa24  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xaa29  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption
0xaa2e  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption)
0xaa33  ldarg.0
0xaa34  ldstr    aDisplayarea// "displayarea"
0xaa39  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xaa3e  brfalse.s loc_AA60
0xaa40  ldarg.1
0xaa41  ldarg.0
0xaa42  ldstr    aDisplayarea// "displayarea"
0xaa47  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea
0xaa4c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xaa51  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xaa56  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea
0xaa5b  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayArea(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea)
0xaa60  ldarg.0
0xaa61  ldstr    aNavpaneorder// "navpaneorder"
0xaa66  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xaa6b  brfalse.s loc_AA7E
0xaa6d  ldarg.1
0xaa6e  ldarg.0
0xaa6f  ldstr    aNavpaneorder// "navpaneorder"
0xaa74  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xaa79  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_NavPaneOrder(int32)
0xaa7e  ldarg.0
0xaa7f  ldstr    aCustomlabel// "customlabel"
0xaa84  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xaa89  brfalse.s loc_AAB1
0xaa8b  ldarg.1
0xaa8c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0xaa91  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xaa96  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xaa9b  ldarg.0
0xaa9c  ldstr    aCustomlabel// "customlabel"
0xaaa1  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xaaa6  ldloc.0
0xaaa7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xaaac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xaab1  ret
```
