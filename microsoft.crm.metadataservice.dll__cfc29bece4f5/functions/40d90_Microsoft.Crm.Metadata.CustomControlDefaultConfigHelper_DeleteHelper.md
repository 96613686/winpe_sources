# Microsoft.Crm.Metadata.CustomControlDefaultConfigHelper::DeleteHelper

- ea: `0x40d90`
- end: `0x40e3f`
- name: `Microsoft.Crm.Metadata.CustomControlDefaultConfigHelper::DeleteHelper`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x769a0`

## callees

- `0x40d90`

## string_xrefs

- `0x40d9d`: `CustomControlDefaultConfig`
- `0x40dbc`: `CustomControlDefaultConfig`
- `0x40dc8`: `CustomControlDefaultConfig`
- `0x40e0a`: `CustomControlDefaultConfig`
- `0x40dfb`: `customcontroldefaultconfigid`

## pseudocode

```c

```

## disassembly

```asm
0x40d90  ldarg.2
0x40d91  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlDefaultConfig::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x40d96  pop
0x40d97  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::.ctor()
0x40d9c  stloc.0
0x40d9d  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x40da2  ldarg.2
0x40da3  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40da8  stloc.1
0x40da9  ldloc.1
0x40daa  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x40daf  ldc.i4.0
0x40db0  ldarg.1
0x40db1  box      [mscorlib]System.Int32
0x40db6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x40dbb  pop
0x40dbc  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x40dc1  ldarg.2
0x40dc2  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40dc7  stloc.2
0x40dc8  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x40dcd  ldarg.2
0x40dce  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x40dd3  dup
0x40dd4  ldloc.1
0x40dd5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x40dda  ldloc.2
0x40ddb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x40de0  ldloc.0
0x40de1  ldloc.1
0x40de2  ldarg.2
0x40de3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40de8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x40ded  stloc.3
0x40dee  br.s     loc_40E20
0x40df0  ldloc.3
0x40df1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x40df6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x40dfb  ldstr    aCustomcontrold_0// "customcontroldefaultconfigid"
0x40e00  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x40e05  unbox.any [mscorlib]System.Guid
0x40e0a  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x40e0f  ldarg.2
0x40e10  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x40e15  stloc.s  4
0x40e17  ldloc.0
0x40e18  ldloc.s  4
0x40e1a  ldarg.2
0x40e1b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x40e20  ldloc.3
0x40e21  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x40e26  brtrue.s loc_40DF0
0x40e28  leave.s  loc_40E3E
0x40e2a  ldloc.3
0x40e2b  isinst   [mscorlib]System.IDisposable
0x40e30  stloc.s  5
0x40e32  ldloc.s  5
0x40e34  brfalse.s loc_40E3D
0x40e36  ldloc.s  5
0x40e38  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x40e3d  endfinally
0x40e3e  ret
```
