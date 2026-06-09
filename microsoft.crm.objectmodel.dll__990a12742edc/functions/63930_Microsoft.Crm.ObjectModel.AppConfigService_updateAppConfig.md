# Microsoft.Crm.ObjectModel.AppConfigService::updateAppConfig

- ea: `0x63930`
- end: `0x63a25`
- name: `Microsoft.Crm.ObjectModel.AppConfigService::updateAppConfig`
- size: `245`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x63d00`
- `0x63f60`
- `0x644b0`
- `0x98c30`
- `0x98d90`
- `0x98ed0`

## callees

- `0x628e0`
- `0x63930`

## string_xrefs

- `0x63944`: `AppConfig`
- `0x63975`: `AppConfig`
- `0x639ae`: `AppConfig`
- `0x63937`: `appconfigid`
- `0x63961`: `appconfigid`
- `0x6398e`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x63930  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x63935  stloc.0
0x63936  ldarg.1
0x63937  ldstr    aAppconfigid// "appconfigid"
0x6393c  ldloca.s 0
0x6393e  callvirt T0x2B0000EF
0x63943  pop
0x63944  ldstr    aAppconfig// "AppConfig"
0x63949  ldarg.2
0x6394a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6394f  stloc.1
0x63950  ldloc.1
0x63951  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x63956  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x6395b  ldloc.1
0x6395c  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x63961  ldstr    aAppconfigid// "appconfigid"
0x63966  ldc.i4.0
0x63967  ldloc.0
0x63968  box      [mscorlib]System.Guid
0x6396d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x63972  pop
0x63973  ldarg.0
0x63974  ldloc.0
0x63975  ldstr    aAppconfig// "AppConfig"
0x6397a  ldarg.2
0x6397b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63980  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x63985  ldloc.1
0x63986  ldarg.2
0x63987  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6398c  stloc.2
0x6398d  ldloc.2
0x6398e  ldstr    aComponentstate_0// "componentstate"
0x63993  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x63998  callvirt instance string [mscorlib]System.Object::ToString()
0x6399d  call     int32 [mscorlib]System.Convert::ToInt32(string)
0x639a2  brtrue.s loc_639C8
0x639a4  ldarg.0
0x639a5  ldloc.2
0x639a6  ldarg.2
0x639a7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x639ac  ldarg.0
0x639ad  ldloc.0
0x639ae  ldstr    aAppconfig// "AppConfig"
0x639b3  ldarg.2
0x639b4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x639b9  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x639be  ldloc.1
0x639bf  ldarg.2
0x639c0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x639c5  stloc.2
0x639c6  br.s     loc_639FC
0x639c8  ldarg.1
0x639c9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PlatformName()
0x639ce  ldstr    aNavigationsett_0// "NavigationSetting"
0x639d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x639d8  brfalse.s loc_639FC
0x639da  ldarg.1
0x639db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x639e0  ldarg.0
0x639e1  ldfld    string Microsoft.Crm.ObjectModel.AppConfigService::NavigationSettingProgressStateAttrName
0x639e6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::Contains(string)
0x639eb  brfalse.s loc_639FC
0x639ed  ldarg.0
0x639ee  ldarg.2
0x639ef  call     instance void Microsoft.Crm.ObjectModel.AppConfigService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x639f4  ldarg.0
0x639f5  ldloc.2
0x639f6  ldarg.2
0x639f7  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x639fc  leave.s  loc_63A23
0x639fe  stloc.3
0x639ff  ldloc.3
0x63a00  ldarg.2
0x63a01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x63a06  ldc.i4.s 0x14
0x63a08  ldstr    a0_0// "{0}"
0x63a0d  ldc.i4.1
0x63a0e  newarr   [mscorlib]System.Object
0x63a13  dup
0x63a14  ldc.i4.0
0x63a15  ldloc.3
0x63a16  callvirt instance string [mscorlib]System.Exception::get_Message()
0x63a1b  stelem.ref
0x63a1c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x63a21  rethrow
0x63a23  ldloc.2
0x63a24  ret
```
