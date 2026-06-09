# Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetSelectEventSQL

- ea: `0x33e0`
- end: `0x348a`
- name: `Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::GetSelectEventSQL`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x3230`

## callees

- `0x33d0`
- `0x33e0`
- `0xd5a0`
- `0xd8c0`

## string_xrefs

- `0x33fe`: `update AsyncOperationBase\nset\n	HostId = @hostId,\n	StateCode = @lockedState,\n	StatusCode = @inProgressStatus,\n	StartedOn = @modifiedOn,\n	ModifiedOn = @modifiedOn,\n	ModifiedBy = CreatedBy,\n	RetryCount = case coalesce(ErrorCode, 0)\n					when 0 then coalesce(RetryCount, 0)\n					else coalesce(RetryCount, 0)+1\n					end\noutput\n	INSERTED.AsyncOperationId,\n	INSERTED.OperationType,\n	INSERTED.Data,\n	INSERTED.DependencyToken,\n	INSERTED.RegardingObjectId,\n	INSERTED.Regardi`
- `0x3421`: `, INSERTED.ParentPluginExecutionId `
- `0x344c`: `where\nAsyncOperationId in\n	(select top(@recordsToSelect) AsyncOperationId from AsyncOperationBase WITH (READPAST, READCOMMITTEDLOCK, UPDLOCK)  \nwhere StateCode = @readyState `

## pseudocode

```c

```

## disassembly

```asm
0x33e0  ldstr    a8020// "8.0.2.0"
0x33e5  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x33ea  stloc.0
0x33eb  ldstr    a9010// "9.0.1.0"
0x33f0  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x33f5  stloc.1
0x33f6  ldc.i4.6
0x33f7  newarr   [mscorlib]System.String
0x33fc  dup
0x33fd  ldc.i4.0
0x33fe  ldstr    aUpdateAsyncope// "update AsyncOperationBase\r\nset\r\n\tH"...
0x3403  stelem.ref
0x3404  dup
0x3405  ldc.i4.1
0x3406  ldarg.0
0x3407  ldarg.0
0x3408  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x340d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3412  ldloc.0
0x3413  call     instance bool Microsoft.Crm.Asynchronous.DataAccessBase::CheckHasNewColumnsAdded(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Version baselineVersion)
0x3418  brtrue.s loc_3421
0x341a  ldsfld   string [mscorlib]System.String::Empty
0x341f  br.s     loc_3426
0x3421  ldstr    aInsertedParent// ", INSERTED.ParentPluginExecutionId "
0x3426  stelem.ref
0x3427  dup
0x3428  ldc.i4.2
0x3429  ldarg.0
0x342a  ldarg.0
0x342b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x3430  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x3435  ldloc.1
0x3436  call     instance bool Microsoft.Crm.Asynchronous.DataAccessBase::CheckHasNewColumnsAdded(valuetype [mscorlib]System.Guid organizationId, class [mscorlib]System.Version baselineVersion)
0x343b  brtrue.s loc_3444
0x343d  ldsfld   string [mscorlib]System.String::Empty
0x3442  br.s     loc_3449
0x3444  ldstr    aInsertedRootex// ", INSERTED.RootExecutionContext "
0x3449  stelem.ref
0x344a  dup
0x344b  ldc.i4.3
0x344c  ldstr    aWhereAsyncoper// "where\r\nAsyncOperationId in\r\n\t(sele"...
0x3451  stelem.ref
0x3452  dup
0x3453  ldc.i4.4
0x3454  ldarg.0
0x3455  call     instance bool Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::get_IsSelectingPriorityJobs()
0x345a  brtrue.s loc_3463
0x345c  ldsfld   string [mscorlib]System.String::Empty
0x3461  br.s     loc_347B
0x3463  ldstr    aAndSubtype// " and Subtype >  "
0x3468  ldc.i4.1
0x3469  stloc.2
0x346a  ldloca.s 2
0x346c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3471  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x3476  call     string [mscorlib]System.String::Concat(string, string)
0x347b  stelem.ref
0x347c  dup
0x347d  ldc.i4.5
0x347e  ldstr    aOrderBySequenc// " order by Sequence asc)"
0x3483  stelem.ref
0x3484  call     string [mscorlib]System.String::Concat(string[])
0x3489  ret
```
