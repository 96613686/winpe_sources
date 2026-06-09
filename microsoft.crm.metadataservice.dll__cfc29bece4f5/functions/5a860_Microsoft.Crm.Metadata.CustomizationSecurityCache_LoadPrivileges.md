# Microsoft.Crm.Metadata.CustomizationSecurityCache::LoadPrivileges

- ea: `0x5a860`
- end: `0x5a952`
- name: `Microsoft.Crm.Metadata.CustomizationSecurityCache::LoadPrivileges`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5a810`

## callees

- `0x5a860`

## string_xrefs

- `0x5a87a`: `privilegeid`
- `0x5a8f8`: `privilegeid`
- `0x5a860`: `Privilege`
- `0x5a933`: `Customization privileges were loaded by organization {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5a860  ldstr    aPrivilege// "Privilege"
0x5a865  ldarg.0
0x5a866  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x5a86b  stloc.0
0x5a86c  ldloc.0
0x5a86d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x5a872  ldc.i4.2
0x5a873  newarr   [mscorlib]System.String
0x5a878  dup
0x5a879  ldc.i4.0
0x5a87a  ldstr    aPrivilegeid// "privilegeid"
0x5a87f  stelem.ref
0x5a880  dup
0x5a881  ldc.i4.1
0x5a882  ldstr    aName// "name"
0x5a887  stelem.ref
0x5a888  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x5a88d  ldloc.0
0x5a88e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5a893  ldstr    aName// "name"
0x5a898  ldc.i4.8
0x5a899  ldsfld   string[] Microsoft.Crm.Metadata.CustomizationSecurityCache::_customizationPrivilegeNames
0x5a89e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x5a8a3  pop
0x5a8a4  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PrivilegeService::.ctor()
0x5a8a9  stloc.1
0x5a8aa  ldnull
0x5a8ab  stloc.2
0x5a8ac  ldarg.0
0x5a8ad  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a8b2  stloc.3
0x5a8b3  ldloc.1
0x5a8b4  ldloc.0
0x5a8b5  ldarg.0
0x5a8b6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5a8bb  stloc.2
0x5a8bc  leave.s  loc_5A8C8
0x5a8be  ldloc.3
0x5a8bf  brfalse.s loc_5A8C7
0x5a8c1  ldloc.3
0x5a8c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a8c7  endfinally
0x5a8c8  ldloc.2
0x5a8c9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x5a8ce  stloc.s  4
0x5a8d0  br.s     loc_5A90C
0x5a8d2  ldloc.s  4
0x5a8d4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5a8d9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x5a8de  stloc.s  5
0x5a8e0  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.CustomizationSecurityCache::_customizationPrivileges
0x5a8e5  ldloc.s  5
0x5a8e7  ldstr    aName// "name"
0x5a8ec  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a8f1  castclass [mscorlib]System.String
0x5a8f6  ldloc.s  5
0x5a8f8  ldstr    aPrivilegeid// "privilegeid"
0x5a8fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5a902  unbox.any [mscorlib]System.Guid
0x5a907  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0x5a90c  ldloc.s  4
0x5a90e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5a913  brtrue.s loc_5A8D2
0x5a915  leave.s  loc_5A92C
0x5a917  ldloc.s  4
0x5a919  isinst   [mscorlib]System.IDisposable
0x5a91e  stloc.s  6
0x5a920  ldloc.s  6
0x5a922  brfalse.s loc_5A92B
0x5a924  ldloc.s  6
0x5a926  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a92b  endfinally
0x5a92c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5a931  ldc.i4.s 0x19
0x5a933  ldstr    aCustomizationP// "Customization privileges were loaded by"...
0x5a938  ldc.i4.1
0x5a939  newarr   [mscorlib]System.Object
0x5a93e  dup
0x5a93f  ldc.i4.0
0x5a940  ldarg.0
0x5a941  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5a946  box      [mscorlib]System.Guid
0x5a94b  stelem.ref
0x5a94c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5a951  ret
```
