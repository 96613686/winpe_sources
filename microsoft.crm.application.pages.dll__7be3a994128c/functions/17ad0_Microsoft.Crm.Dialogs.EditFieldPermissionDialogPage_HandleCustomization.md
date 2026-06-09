# Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleCustomization

- ea: `0x17ad0`
- end: `0x17c0b`
- name: `Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::HandleCustomization`
- size: `315`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17430`

## callees

- `0x17860`
- `0x17ad0`

## string_xrefs

- `0x17b20`: `fieldsecurityprofileid`
- `0x17b4d`: `canread`
- `0x17bb9`: `canread`
- `0x17b5b`: `canupdate`
- `0x17bc7`: `canupdate`
- `0x17b69`: `cancreate`
- `0x17bd5`: `cancreate`

## pseudocode

```c

```

## disassembly

```asm
0x17ad0  ldarg.2
0x17ad1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x17ad6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x17adb  brfalse  loc_17B80
0x17ae0  ldarg.s  5
0x17ae2  ldc.i4.1
0x17ae3  beq.s    loc_17AF2
0x17ae5  ldarg.s  6
0x17ae7  ldc.i4.1
0x17ae8  beq.s    loc_17AF2
0x17aea  ldarg.s  7
0x17aec  ldc.i4.1
0x17aed  bne.un   loc_17C0A
0x17af2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x17af7  starg.s  2
0x17af9  ldstr    aFieldpermissio// "fieldpermission"
0x17afe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17b03  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b08  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x17b0d  stloc.0
0x17b0e  ldloc.0
0x17b0f  ldstr    aFieldpermissio_0// "fieldpermissionid"
0x17b14  ldarg.2
0x17b15  box      [mscorlib]System.Guid
0x17b1a  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17b1f  ldloc.0
0x17b20  ldstr    aFieldsecurityp// "fieldsecurityprofileid"
0x17b25  ldarg.1
0x17b26  box      [mscorlib]System.Guid
0x17b2b  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17b30  ldloc.0
0x17b31  ldstr    aEntityname// "entityname"
0x17b36  ldarg.3
0x17b37  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17b3c  ldloc.0
0x17b3d  ldstr    aAttributelogic// "attributelogicalname"
0x17b42  ldarg.s  4
0x17b44  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17b49  ldarg.0
0x17b4a  ldarg.s  5
0x17b4c  ldloc.0
0x17b4d  ldstr    aCanread// "canread"
0x17b52  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17b57  ldarg.0
0x17b58  ldarg.s  6
0x17b5a  ldloc.0
0x17b5b  ldstr    aCanupdate// "canupdate"
0x17b60  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17b65  ldarg.0
0x17b66  ldarg.s  7
0x17b68  ldloc.0
0x17b69  ldstr    aCancreate// "cancreate"
0x17b6e  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17b73  ldloc.0
0x17b74  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17b79  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b7e  pop
0x17b7f  ret
0x17b80  ldarg.s  5
0x17b82  ldc.i4.1
0x17b83  beq.s    loc_17B8F
0x17b85  ldarg.s  6
0x17b87  ldc.i4.1
0x17b88  beq.s    loc_17B8F
0x17b8a  ldarg.s  7
0x17b8c  ldc.i4.1
0x17b8d  bne.un.s loc_17BEB
0x17b8f  ldstr    aFieldpermissio// "fieldpermission"
0x17b94  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17b99  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17b9e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x17ba3  stloc.1
0x17ba4  ldloc.1
0x17ba5  ldstr    aFieldpermissio_0// "fieldpermissionid"
0x17baa  ldarg.2
0x17bab  box      [mscorlib]System.Guid
0x17bb0  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x17bb5  ldarg.0
0x17bb6  ldarg.s  5
0x17bb8  ldloc.1
0x17bb9  ldstr    aCanread// "canread"
0x17bbe  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17bc3  ldarg.0
0x17bc4  ldarg.s  6
0x17bc6  ldloc.1
0x17bc7  ldstr    aCanupdate// "canupdate"
0x17bcc  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17bd1  ldarg.0
0x17bd2  ldarg.s  7
0x17bd4  ldloc.1
0x17bd5  ldstr    aCancreate// "cancreate"
0x17bda  call     instance void Microsoft.Crm.Dialogs.EditFieldPermissionDialogPage::SetState(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FieldLevelSecurityAccess state, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity entity, string columnName)
0x17bdf  ldloc.1
0x17be0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17be5  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Update(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17bea  ret
0x17beb  ldstr    aFieldpermissio// "fieldpermission"
0x17bf0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17bf5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17bfa  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x17bff  ldarg.2
0x17c00  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x17c05  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x17c0a  ret
```
