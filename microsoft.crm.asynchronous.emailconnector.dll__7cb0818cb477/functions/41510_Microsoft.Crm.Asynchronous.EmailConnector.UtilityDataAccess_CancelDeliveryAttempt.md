# Microsoft.Crm.Asynchronous.EmailConnector.UtilityDataAccess::CancelDeliveryAttempt

- ea: `0x41510`
- end: `0x41595`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.UtilityDataAccess::CancelDeliveryAttempt`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x471f0`

## callees

- `0x413a0`
- `0x413d0`
- `0x413e0`
- `0x41510`

## string_xrefs

- `0x41533`: `deliveryattempts`
- `0x41517`: ` \n				UPDATE ActivityPointerBase\n				SET DeliveryAttempts = @deliveryAttempts, PostponeActivityProcessingUntil = @dateTimeNow\n				WHERE ActivityId = @activityId`
- `0x4152d`: `@deliveryAttempts`

## pseudocode

```c

```

## disassembly

```asm
0x41510  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x41515  stloc.0
0x41516  ldloc.0
0x41517  ldstr    aUpdateActivity// " \r\n\t\t\t\tUPDATE ActivityPointerBase"...
0x4151c  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x41521  ldloc.0
0x41522  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x41527  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x4152c  dup
0x4152d  ldstr    aDeliveryattemp_0// "@deliveryAttempts"
0x41532  ldarg.0
0x41533  ldstr    aDeliveryattemp// "deliveryattempts"
0x41538  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4153d  unbox.any [mscorlib]System.Int32
0x41542  ldc.i4.1
0x41543  sub
0x41544  box      [mscorlib]System.Int32
0x41549  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4154e  pop
0x4154f  dup
0x41550  ldstr    aDatetimenow// "@dateTimeNow"
0x41555  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetUTCDateWithoutMilliseconds()
0x4155a  box      [mscorlib]System.DateTime
0x4155f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x41564  pop
0x41565  ldstr    aActivityid_0// "@activityId"
0x4156a  ldarg.0
0x4156b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x41570  box      [mscorlib]System.Guid
0x41575  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4157a  pop
0x4157b  ldnull
0x4157c  ldarg.1
0x4157d  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.UtilityDataAccess::.ctor(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration organizationConfiguration, valuetype [mscorlib]System.Guid organizationId)
0x41582  ldloc.0
0x41583  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.UtilityDataAccess::ExecuteSql(class [System.Data]System.Data.IDbCommand command)
0x41588  leave.s  loc_41594
0x4158a  ldloc.0
0x4158b  brfalse.s loc_41593
0x4158d  ldloc.0
0x4158e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x41593  endfinally
0x41594  ret
```
