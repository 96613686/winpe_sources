# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::.ctor

- ea: `0x7d50`
- end: `0x7e52`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::.ctor`
- size: `258`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x7d50`

## pseudocode

```c

```

## disassembly

```asm
0x7d50  ldarg.0
0x7d51  call     instance void [mscorlib]System.Object::.ctor()
0x7d56  ldarg.0
0x7d57  ldarg.3
0x7d58  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.AttributeMapView Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_view
0x7d5d  ldarg.0
0x7d5e  ldarg.2
0x7d5f  stfld    string Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_inputFileId
0x7d64  ldarg.0
0x7d65  ldarg.1
0x7d66  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7d6b  ldarg.0
0x7d6c  ldarg.0
0x7d6d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7d72  callvirt instance class [System.Xml]System.Xml.XPath.IXPathNavigable [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_EntityMapNode()
0x7d77  isinst   [System.Xml]System.Xml.XmlNode
0x7d7c  stfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetMap
0x7d81  ldarg.0
0x7d82  ldarg.0
0x7d83  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7d88  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_ProcessCode()
0x7d8d  ldc.i4.3
0x7d8e  beq.s    loc_7DC1
0x7d90  ldarg.0
0x7d91  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7d96  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_Metadata()
0x7d9b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x7da0  brfalse.s loc_7DBE
0x7da2  ldarg.0
0x7da3  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x7da8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_Metadata()
0x7dad  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x7db2  ldstr    aSystemuser// "systemuser"
0x7db7  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7dbc  br.s     loc_7DC2
0x7dbe  ldc.i4.0
0x7dbf  br.s     loc_7DC2
0x7dc1  ldc.i4.1
0x7dc2  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7dc7  ldarg.0
0x7dc8  ldarg.0
0x7dc9  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7dce  brfalse.s loc_7DE1
0x7dd0  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateAttribute()
0x7dd5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7dda  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7ddf  br.s     loc_7DE2
0x7de1  ldc.i4.0
0x7de2  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7de7  ldarg.0
0x7de8  ldarg.0
0x7de9  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7dee  brfalse.s loc_7E08
0x7df0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7df5  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7dfa  brfalse.s loc_7E08
0x7dfc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7e01  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x7e06  br.s     loc_7E09
0x7e08  ldc.i4.0
0x7e09  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7e0e  ldarg.0
0x7e0f  ldarg.0
0x7e10  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7e15  brfalse.s loc_7E40
0x7e17  ldarg.1
0x7e18  callvirt instance valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.ImportWizard.ImportEntityProcessCode [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_ProcessCode()
0x7e1d  ldc.i4.3
0x7e1e  beq.s    loc_7E3D
0x7e20  ldarg.1
0x7e21  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_Metadata()
0x7e26  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomizable()
0x7e2b  brfalse.s loc_7E3A
0x7e2d  ldarg.1
0x7e2e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_Metadata()
0x7e33  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanCreateAttributes()
0x7e38  br.s     loc_7E41
0x7e3a  ldc.i4.0
0x7e3b  br.s     loc_7E41
0x7e3d  ldc.i4.1
0x7e3e  br.s     loc_7E41
0x7e40  ldc.i4.0
0x7e41  stfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x7e46  ldarg.0
0x7e47  newobj   instance void [System.Web]System.Web.UI.HtmlControls.HtmlTable::.ctor()
0x7e4c  stfld    class [System.Web]System.Web.UI.HtmlControls.HtmlTable Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_attributeMapTable
0x7e51  ret
```
