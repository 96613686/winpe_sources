# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateOwnermappings

- ea: `0x4df0`
- end: `0x4e92`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::CreateOwnermappings`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4ac0`

## callees

- `0x4df0`

## pseudocode

```c

```

## disassembly

```asm
0x4df0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4df5  ldarg.1
0x4df6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4dfb  brfalse.s loc_4DFE
0x4dfd  ret
0x4dfe  ldstr    aOwnermapping// "ownermapping"
0x4e03  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x4e08  dup
0x4e09  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.AllColumns::.ctor()
0x4e0e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x4e13  dup
0x4e14  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x4e19  ldstr    aImportmapid// "importmapid"
0x4e1e  ldc.i4.0
0x4e1f  ldarg.1
0x4e20  box      [mscorlib]System.Guid
0x4e25  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x4e2a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4e2f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e34  stloc.0
0x4e35  ldloc.0
0x4e36  brfalse.s loc_4E91
0x4e38  ldloc.0
0x4e39  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x4e3e  ldc.i4.0
0x4e3f  ble.s    loc_4E91
0x4e41  ldloc.0
0x4e42  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x4e47  stloc.1
0x4e48  br.s     loc_4E7D
0x4e4a  ldloc.1
0x4e4b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x4e50  dup
0x4e51  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Properties()
0x4e56  ldstr    aOwnermappingid// "ownermappingid"
0x4e5b  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Remove(var<u1>)
0x4e60  pop
0x4e61  dup
0x4e62  ldstr    aImportmapid// "importmapid"
0x4e67  ldarg.2
0x4e68  box      [mscorlib]System.Guid
0x4e6d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x4e72  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4e77  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Create(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e7c  pop
0x4e7d  ldloc.1
0x4e7e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4e83  brtrue.s loc_4E4A
0x4e85  leave.s  loc_4E91
0x4e87  ldloc.1
0x4e88  brfalse.s loc_4E90
0x4e8a  ldloc.1
0x4e8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4e90  endfinally
0x4e91  ret
```
