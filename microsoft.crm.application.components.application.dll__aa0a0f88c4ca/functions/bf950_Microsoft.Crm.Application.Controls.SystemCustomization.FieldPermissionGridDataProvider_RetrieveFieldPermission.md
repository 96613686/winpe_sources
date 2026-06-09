# Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissions

- ea: `0xbf950`
- end: `0xbf9fe`
- name: `Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissions`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xbf6b0`

## callees

- `0xbf950`
- `0xbfa00`
- `0xbfbc0`

## string_xrefs

- `0xbf97a`: `fieldsecurityprofileid`
- `0xbf9c0`: `fieldsecurityprofileid`
- `0xbf992`: `canread`
- `0xbf99a`: `canupdate`
- `0xbf9a2`: `cancreate`

## pseudocode

```c

```

## disassembly

```asm
0xbf950  ldc.i4.2
0xbf951  newarr   [mscorlib]System.Guid
0xbf956  stloc.0
0xbf957  ldloc.0
0xbf958  ldc.i4.0
0xbf959  ldarg.1
0xbf95a  stelem   [mscorlib]System.Guid
0xbf95f  ldloc.0
0xbf960  ldc.i4.1
0xbf961  ldarg.2
0xbf962  stelem   [mscorlib]System.Guid
0xbf967  ldstr    aFieldpermissio// "fieldpermission"
0xbf96c  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0xbf971  stloc.1
0xbf972  ldc.i4.6
0xbf973  newarr   [mscorlib]System.String
0xbf978  dup
0xbf979  ldc.i4.0
0xbf97a  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xbf97f  stelem.ref
0xbf980  dup
0xbf981  ldc.i4.1
0xbf982  ldstr    aEntityname// "entityname"
0xbf987  stelem.ref
0xbf988  dup
0xbf989  ldc.i4.2
0xbf98a  ldstr    aAttributelogic// "attributelogicalname"
0xbf98f  stelem.ref
0xbf990  dup
0xbf991  ldc.i4.3
0xbf992  ldstr    aCanread// "canread"
0xbf997  stelem.ref
0xbf998  dup
0xbf999  ldc.i4.4
0xbf99a  ldstr    aCanupdate// "canupdate"
0xbf99f  stelem.ref
0xbf9a0  dup
0xbf9a1  ldc.i4.5
0xbf9a2  ldstr    aCancreate// "cancreate"
0xbf9a7  stelem.ref
0xbf9a8  stloc.2
0xbf9a9  ldloc.1
0xbf9aa  ldloc.2
0xbf9ab  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor(string[])
0xbf9b0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0xbf9b5  ldloc.1
0xbf9b6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0xbf9bb  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0xbf9c0  ldstr    aFieldsecurityp_1// "fieldsecurityprofileid"
0xbf9c5  ldc.i4.8
0xbf9c6  ldloc.0
0xbf9c7  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0xbf9cc  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xbf9d1  pop
0xbf9d2  ldloc.1
0xbf9d3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xbf9d8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbf9dd  stloc.3
0xbf9de  ldarg.0
0xbf9df  ldloc.3
0xbf9e0  ldarg.1
0xbf9e1  ldarg.3
0xbf9e2  ldarg.s  4
0xbf9e4  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissionsFromCurrentProfile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid profileId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION> fps, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xbf9e9  ldarg.1
0xbf9ea  ldarg.2
0xbf9eb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xbf9f0  brfalse.s loc_BF9FD
0xbf9f2  ldarg.0
0xbf9f3  ldloc.3
0xbf9f4  ldarg.2
0xbf9f5  ldarg.3
0xbf9f6  ldarg.s  4
0xbf9f8  call     instance void Microsoft.Crm.Application.Controls.SystemCustomization.FieldPermissionGridDataProvider::RetrieveFieldPermissionsFromSystemProfile(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities, valuetype [mscorlib]System.Guid sysProfileId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.Crm.Application.Controls.SystemCustomization.FIELD_PERMISSION> fps, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache mdCache)
0xbf9fd  ret
```
