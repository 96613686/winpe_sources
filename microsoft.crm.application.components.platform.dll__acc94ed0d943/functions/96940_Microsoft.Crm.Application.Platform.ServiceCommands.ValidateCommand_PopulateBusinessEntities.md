# Microsoft.Crm.Application.Platform.ServiceCommands.ValidateCommand::PopulateBusinessEntities

- ea: `0x96940`
- end: `0x96a1b`
- name: `Microsoft.Crm.Application.Platform.ServiceCommands.ValidateCommand::PopulateBusinessEntities`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x96900`

## callees

- `0x577f0`
- `0x59800`
- `0x90d80`
- `0x96940`

## string_xrefs

- `0x9697d`: `scheduledend`
- `0x96988`: `serviceappointment`
- `0x9696d`: `scheduledstart`
- `0x9695d`: `serviceid`

## pseudocode

```c

```

## disassembly

```asm
0x96940  ldarg.2
0x96941  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x96946  stloc.0
0x96947  ldloc.0
0x96948  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x9694d  ldstr    aActivityid// "activityid"
0x96952  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x96957  ldloc.0
0x96958  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x9695d  ldstr    aServiceid// "serviceid"
0x96962  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x96967  ldloc.0
0x96968  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x9696d  ldstr    aScheduledstart// "scheduledstart"
0x96972  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x96977  ldloc.0
0x96978  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x9697d  ldstr    aScheduledend// "scheduledend"
0x96982  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x96987  ldarg.2
0x96988  ldstr    aServiceappoint// "serviceappointment"
0x9698d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x96992  brfalse.s loc_969A6
0x96994  ldloc.0
0x96995  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x9699a  ldstr    aResources// "resources"
0x9699f  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x969a4  br.s     loc_969D3
0x969a6  ldarg.2
0x969a7  ldstr    aAppointment// "appointment"
0x969ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x969b1  brfalse.s loc_969D3
0x969b3  ldloc.0
0x969b4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x969b9  ldstr    aRequiredattend// "requiredattendees"
0x969be  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x969c3  ldloc.0
0x969c4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x969c9  ldstr    aOptionalattend_0// "optionalattendees"
0x969ce  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x969d3  ldarg.3
0x969d4  ldlen
0x969d5  conv.i4
0x969d6  newarr   [mscorlib]System.Object
0x969db  stloc.1
0x969dc  ldarg.3
0x969dd  ldloc.1
0x969de  ldc.i4.0
0x969df  callvirt instance void [mscorlib]System.Array::CopyTo(class [mscorlib]System.Array, int32)
0x969e4  ldloc.0
0x969e5  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x969ea  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x969ef  ldstr    aActivityid// "activityid"
0x969f4  ldc.i4.8
0x969f5  ldloc.1
0x969f6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x969fb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x96a00  pop
0x96a01  ldloc.0
0x96a02  ldarg.0
0x96a03  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.ServiceCommands.PlatformCommand::get_OrganizationContext()
0x96a08  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x96a0d  stloc.2
0x96a0e  ldarg.1
0x96a0f  ldloc.2
0x96a10  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection Microsoft.Crm.Application.Platform.ApplicationEntityCollection::get_Entities()
0x96a15  callvirt instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.ValidateRequest::set_Activities(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection)
0x96a1a  ret
```
