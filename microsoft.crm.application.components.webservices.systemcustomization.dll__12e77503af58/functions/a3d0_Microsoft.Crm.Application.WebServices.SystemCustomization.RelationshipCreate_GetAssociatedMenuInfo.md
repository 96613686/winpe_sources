# Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetAssociatedMenuInfo

- ea: `0xa3d0`
- end: `0xa4ac`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.RelationshipCreate::GetAssociatedMenuInfo`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x9fe0`
- `0xa0c0`

## callees

- `0x190`
- `0x220`
- `0x270`
- `0x360`
- `0xa3d0`

## pseudocode

```c

```

## disassembly

```asm
0xa3d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa3d5  stloc.0
0xa3d6  ldarg.0
0xa3d7  ldstr    aDisplayoption// "displayoption"
0xa3dc  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa3e1  brfalse.s loc_A405
0xa3e3  ldarg.1
0xa3e4  ldarg.0
0xa3e5  ldstr    aDisplayoption// "displayoption"
0xa3ea  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption
0xa3ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa3f4  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa3f9  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption
0xa3fe  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption)
0xa403  br.s     loc_A40C
0xa405  ldarg.1
0xa406  ldc.i4.2
0xa407  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayOption(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneDisplayOption)
0xa40c  ldarg.0
0xa40d  ldstr    aDisplayarea// "displayarea"
0xa412  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa417  brfalse.s loc_A439
0xa419  ldarg.1
0xa41a  ldarg.0
0xa41b  ldstr    aDisplayarea// "displayarea"
0xa420  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea
0xa425  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa42a  callvirt instance object Microsoft.Crm.Application.WebServices.ParameterBag::GetEnum(string name, class [mscorlib]System.Type enumType)
0xa42f  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea
0xa434  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_DisplayArea(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NavPaneArea)
0xa439  ldarg.0
0xa43a  ldstr    aNavpaneorder// "navpaneorder"
0xa43f  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa444  brfalse.s loc_A457
0xa446  ldarg.1
0xa447  ldarg.0
0xa448  ldstr    aNavpaneorder// "navpaneorder"
0xa44d  callvirt instance int32 Microsoft.Crm.Application.WebServices.ParameterBag::GetInt(string name)
0xa452  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::set_NavPaneOrder(int32)
0xa457  ldarg.0
0xa458  ldstr    aCustomlabel// "customlabel"
0xa45d  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0xa462  brfalse.s loc_A48B
0xa464  ldarg.1
0xa465  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0xa46a  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa46f  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa474  ldarg.0
0xa475  ldstr    aCustomlabel// "customlabel"
0xa47a  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0xa47f  ldloc.0
0xa480  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa485  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa48a  ret
0xa48b  ldarg.1
0xa48c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityRelationshipRoleInfo::get_CustomLabels()
0xa491  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa496  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa49b  ldsfld   string [mscorlib]System.String::Empty
0xa4a0  ldloc.0
0xa4a1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::.ctor(int32, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa4a6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LabelCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label)
0xa4ab  ret
```
