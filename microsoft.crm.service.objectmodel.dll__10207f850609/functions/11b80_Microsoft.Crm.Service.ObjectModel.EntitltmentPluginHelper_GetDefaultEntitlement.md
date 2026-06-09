# Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetDefaultEntitlement

- ea: `0x11b80`
- end: `0x11c66`
- name: `Microsoft.Crm.Service.ObjectModel.EntitltmentPluginHelper::GetDefaultEntitlement`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x115d0`

## callees

- `0xb4f0`
- `0xb5f0`
- `0x11b80`

## pseudocode

```c

```

## disassembly

```asm
0x11b80  ldstr    aEntitlement// "Entitlement"
0x11b85  ldarg.3
0x11b86  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InitiatingUserId()
0x11b8b  ldarg.3
0x11b8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x11b91  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x11b96  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x11b9b  stloc.0
0x11b9c  newobj   instance void Microsoft.Crm.Service.ObjectModel.EntitlementService::.ctor()
0x11ba1  ldarg.0
0x11ba2  callvirt instance string [mscorlib]System.Object::ToString()
0x11ba7  ldarg.1
0x11ba8  callvirt instance string [mscorlib]System.Object::ToString()
0x11bad  ldarg.2
0x11bae  callvirt instance string [mscorlib]System.Object::ToString()
0x11bb3  ldloc.0
0x11bb4  ldarg.3
0x11bb5  castclass [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext
0x11bba  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.ObjectModel]Microsoft.Crm.Extensibility.PipelineExecutionContext::get_PlatformContext()
0x11bbf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.EntitlementService::RetrieveEntitlementsForCase(string customerId, string contactId, string productId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression query, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x11bc4  stloc.1
0x11bc5  ldloc.1
0x11bc6  brfalse  loc_11C61
0x11bcb  ldloc.1
0x11bcc  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x11bd1  ldc.i4.0
0x11bd2  ble      loc_11C61
0x11bd7  ldloc.1
0x11bd8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x11bdd  stloc.2
0x11bde  br.s     loc_11C43
0x11be0  ldloc.2
0x11be1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x11be6  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x11beb  stloc.3
0x11bec  ldloc.3
0x11bed  ldstr    aIsdefault// "isdefault"
0x11bf2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11bf7  unbox.any [mscorlib]System.Boolean
0x11bfc  brfalse.s loc_11C43
0x11bfe  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor()
0x11c03  dup
0x11c04  ldloc.3
0x11c05  ldstr    aEntitlementid// "entitlementid"
0x11c0a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11c0f  callvirt instance string [mscorlib]System.Object::ToString()
0x11c14  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11c19  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Id(valuetype [mscorlib]System.Guid)
0x11c1e  dup
0x11c1f  ldloc.3
0x11c20  ldstr    aName// "name"
0x11c25  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x11c2a  callvirt instance string [mscorlib]System.Object::ToString()
0x11c2f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_Name(string)
0x11c34  dup
0x11c35  ldstr    aEntitlement_0// "entitlement"
0x11c3a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::set_LogicalName(string)
0x11c3f  stloc.s  4
0x11c41  leave.s  loc_11C63
0x11c43  ldloc.2
0x11c44  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11c49  brtrue.s loc_11BE0
0x11c4b  leave.s  loc_11C61
0x11c4d  ldloc.2
0x11c4e  isinst   [mscorlib]System.IDisposable
0x11c53  stloc.s  5
0x11c55  ldloc.s  5
0x11c57  brfalse.s loc_11C60
0x11c59  ldloc.s  5
0x11c5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c60  endfinally
0x11c61  ldnull
0x11c62  ret
0x11c63  ldloc.s  4
0x11c65  ret
```
