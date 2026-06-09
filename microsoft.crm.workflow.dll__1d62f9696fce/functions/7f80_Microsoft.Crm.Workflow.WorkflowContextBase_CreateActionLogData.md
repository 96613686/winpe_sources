# Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLogData

- ea: `0x7f80`
- end: `0x808a`
- name: `Microsoft.Crm.Workflow.WorkflowContextBase::CreateActionLogData`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7ee0`

## callees

- `0x7f80`

## string_xrefs

- `0x8005`: `completedon`

## pseudocode

```c

```

## disassembly

```asm
0x7f80  ldstr    aWorkflowlog_0// "WorkflowLog"
0x7f85  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::.ctor(string)
0x7f8a  ldarg.s  8
0x7f8c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x7f91  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowLog::.ctor(valuetype [mscorlib]System.Guid)
0x7f96  stloc.0
0x7f97  ldloc.0
0x7f98  ldstr    aObjecttypecode// "objecttypecode"
0x7f9d  ldarg.3
0x7f9e  box      [mscorlib]System.Int32
0x7fa3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7fa8  ldloc.0
0x7fa9  ldstr    aAsyncoperation_0// "asyncoperationid"
0x7fae  ldarg.1
0x7faf  box      [mscorlib]System.Guid
0x7fb4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7fb9  ldloc.0
0x7fba  ldstr    aActivityname// "activityname"
0x7fbf  ldarg.0
0x7fc0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7fc5  ldloc.0
0x7fc6  ldstr    aStepname// "stepname"
0x7fcb  ldarga.s 2
0x7fcd  constrained. [mscorlib]System.Guid
0x7fd3  callvirt instance string [mscorlib]System.Object::ToString()
0x7fd8  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7fdd  ldloc.0
0x7fde  ldstr    aStatus// "status"
0x7fe3  ldarg.s  5
0x7fe5  box      [mscorlib]System.Int32
0x7fea  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x7fef  ldloc.0
0x7ff0  ldstr    aWorkflowlogid// "workflowlogid"
0x7ff5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x7ffa  box      [mscorlib]System.Guid
0x7fff  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8004  ldloc.0
0x8005  ldstr    aCompletedon// "completedon"
0x800a  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalNow()
0x800f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8014  ldloc.0
0x8015  ldstr    aOwnerid// "ownerid"
0x801a  ldarg.s  8
0x801c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x8021  box      [mscorlib]System.Guid
0x8026  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x802b  ldarga.s 4
0x802d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8032  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x8037  brtrue.s loc_804D
0x8039  ldloc.0
0x803a  ldstr    aRegardingobjec_0// "regardingobjectid"
0x803f  ldarg.s  4
0x8041  box      [mscorlib]System.Guid
0x8046  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x804b  br.s     loc_8059
0x804d  ldloc.0
0x804e  ldstr    aRegardingobjec_0// "regardingobjectid"
0x8053  ldnull
0x8054  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8059  ldarg.s  7
0x805b  brfalse.s loc_806A
0x805d  ldloc.0
0x805e  ldstr    aMessage// "message"
0x8063  ldarg.s  7
0x8065  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x806a  ldarg.s  6
0x806c  brfalse.s loc_8080
0x806e  ldloc.0
0x806f  ldstr    aErrorcode// "errorcode"
0x8074  ldarg.s  6
0x8076  box      [mscorlib]System.Int32
0x807b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8080  ldloc.0
0x8081  ldarg.s  8
0x8083  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8088  pop
0x8089  ret
```
