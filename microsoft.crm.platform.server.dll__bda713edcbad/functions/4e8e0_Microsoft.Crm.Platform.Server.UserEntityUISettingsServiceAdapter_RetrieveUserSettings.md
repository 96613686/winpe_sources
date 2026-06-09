# Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::RetrieveUserSettings

- ea: `0x4e8e0`
- end: `0x4ea31`
- name: `Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::RetrieveUserSettings`
- size: `337`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4ebf0`

## callees

- `0x13b10`
- `0x18520`
- `0x18540`
- `0x18800`
- `0x1ae30`
- `0x1aee0`
- `0x1af00`
- `0x4df40`
- `0x4e8e0`
- `0x55bb0`

## string_xrefs

- `0x4e8f7`: `recentlyviewedxml`
- `0x4e93a`: `recentlyviewedxml`
- `0x4e94d`: `recentlyviewedxml`

## pseudocode

```c

```

## disassembly

```asm
0x4e8e0  ldstr    aUserentityuise// "UserEntityUISettings"
0x4e8e5  ldarg.0
0x4e8e6  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4e8eb  newobj   instance void Microsoft.Crm.Query.EntityExpression::.ctor(string entityPlatformName, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext userAndOrganizationContext)
0x4e8f0  stloc.0
0x4e8f1  ldloc.0
0x4e8f2  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4e8f7  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x4e8fc  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x4e901  ldloc.0
0x4e902  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x4e907  ldstr    aObjecttypecode_81// "objecttypecode"
0x4e90c  callvirt instance void Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string attributePlatformName)
0x4e911  ldloc.0
0x4e912  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4e917  ldstr    aOwnerid// "ownerid"
0x4e91c  ldc.i4.0
0x4e91d  ldarg.2
0x4e91e  box      [mscorlib]System.Guid
0x4e923  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x4e928  pop
0x4e929  ldarg.1
0x4e92a  brfalse.s loc_4E934
0x4e92c  ldarg.1
0x4e92d  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<int32>::get_Count()
0x4e932  brtrue.s loc_4E960
0x4e934  ldloc.0
0x4e935  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4e93a  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x4e93f  ldc.i4.s 0xD
0x4e941  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator)
0x4e946  pop
0x4e947  ldloc.0
0x4e948  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4e94d  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x4e952  ldc.i4.1
0x4e953  ldsfld   string [mscorlib]System.String::Empty
0x4e958  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, object value)
0x4e95d  pop
0x4e95e  br.s     loc_4E9B9
0x4e960  ldarg.1
0x4e961  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<int32>::get_Count()
0x4e966  newarr   [mscorlib]System.Object
0x4e96b  stloc.2
0x4e96c  ldc.i4.0
0x4e96d  stloc.3
0x4e96e  ldarg.1
0x4e96f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<int32>::GetEnumerator()
0x4e974  stloc.s  4
0x4e976  br.s     loc_4E98F
0x4e978  ldloc.s  4
0x4e97a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0x4e97f  stloc.s  5
0x4e981  ldloc.2
0x4e982  ldloc.3
0x4e983  ldloc.s  5
0x4e985  box      [mscorlib]System.Int32
0x4e98a  stelem.ref
0x4e98b  ldloc.3
0x4e98c  ldc.i4.1
0x4e98d  add
0x4e98e  stloc.3
0x4e98f  ldloc.s  4
0x4e991  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e996  brtrue.s loc_4E978
0x4e998  leave.s  loc_4E9A6
0x4e99a  ldloc.s  4
0x4e99c  brfalse.s loc_4E9A5
0x4e99e  ldloc.s  4
0x4e9a0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e9a5  endfinally
0x4e9a6  ldloc.0
0x4e9a7  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x4e9ac  ldstr    aObjecttypecode_81// "objecttypecode"
0x4e9b1  ldc.i4.8
0x4e9b2  ldloc.2
0x4e9b3  callvirt instance class Microsoft.Crm.Query.ConditionExpression Microsoft.Crm.Query.FilterExpression::AddCondition(string attributeName, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator conditionOperator, class [mscorlib]System.Array values)
0x4e9b8  pop
0x4e9b9  ldarg.0
0x4e9ba  ldfld    class Microsoft.Crm.BusinessEntities.IBusinessProcessObject Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::service
0x4e9bf  ldloc.0
0x4e9c0  ldarg.0
0x4e9c1  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4e9c6  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4e9cb  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.IBusinessProcessObject::RetrieveMultiple(class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4e9d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::.ctor()
0x4e9d5  stloc.1
0x4e9d6  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x4e9db  stloc.s  6
0x4e9dd  br.s     loc_4EA0F
0x4e9df  ldloc.s  6
0x4e9e1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4e9e6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4e9eb  stloc.s  7
0x4e9ed  ldloc.s  7
0x4e9ef  ldstr    aObjecttypecode_81// "objecttypecode"
0x4e9f4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4e9f9  unbox.any [mscorlib]System.Int32
0x4e9fe  stloc.s  8
0x4ea00  ldloc.s  8
0x4ea02  ldc.i4.0
0x4ea03  ble.s    loc_4EA0F
0x4ea05  ldloc.1
0x4ea06  ldloc.s  8
0x4ea08  ldloc.s  7
0x4ea0a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::set_Item(var<u1>, !!T0)
0x4ea0f  ldloc.s  6
0x4ea11  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4ea16  brtrue.s loc_4E9DF
0x4ea18  leave.s  loc_4EA2F
0x4ea1a  ldloc.s  6
0x4ea1c  isinst   [mscorlib]System.IDisposable
0x4ea21  stloc.s  9
0x4ea23  ldloc.s  9
0x4ea25  brfalse.s loc_4EA2E
0x4ea27  ldloc.s  9
0x4ea29  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4ea2e  endfinally
0x4ea2f  ldloc.1
0x4ea30  ret
```
