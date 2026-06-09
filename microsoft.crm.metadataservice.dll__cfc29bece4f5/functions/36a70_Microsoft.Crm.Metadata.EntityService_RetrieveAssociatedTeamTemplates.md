# Microsoft.Crm.Metadata.EntityService::RetrieveAssociatedTeamTemplates

- ea: `0x36a70`
- end: `0x36ab9`
- name: `Microsoft.Crm.Metadata.EntityService::RetrieveAssociatedTeamTemplates`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x36ac0`
- `0x37ad0`

## callees

- `0x36a70`

## string_xrefs

- `0x36a70`: `TeamTemplate`
- `0x36a7c`: `TeamTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x36a70  ldstr    aTeamtemplate// "TeamTemplate"
0x36a75  ldarg.2
0x36a76  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x36a7b  stloc.0
0x36a7c  ldstr    aTeamtemplate// "TeamTemplate"
0x36a81  ldarg.2
0x36a82  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x36a87  stloc.1
0x36a88  ldloc.1
0x36a89  ldstr    aObjecttypecode_0// "objecttypecode"
0x36a8e  ldc.i4.0
0x36a8f  ldarg.1
0x36a90  box      [mscorlib]System.Int32
0x36a95  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x36a9a  pop
0x36a9b  ldarg.2
0x36a9c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x36aa1  stloc.2
0x36aa2  ldloc.0
0x36aa3  ldloc.1
0x36aa4  ldarg.2
0x36aa5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x36aaa  stloc.3
0x36aab  leave.s  loc_36AB7
0x36aad  ldloc.2
0x36aae  brfalse.s loc_36AB6
0x36ab0  ldloc.2
0x36ab1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x36ab6  endfinally
0x36ab7  ldloc.3
0x36ab8  ret
```
