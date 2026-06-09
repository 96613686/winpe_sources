# Microsoft.Crm.Asynchronous.JobDataAccess::.cctor

- ea: `0x3d10`
- end: `0x3d59`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::.cctor`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## string_xrefs

- `0x3d10`: `\nDeclare @tableResult table \n(\n	OrganizationId uniqueidentifier not null,\n	OperationType int not null,\n	OperationStartTime datetime not null,\n	OperationEndTime datetime not null\n)\n\nUpdate ScaleGroupOrganizationMaintenanceJobs\nSet \n	HostId = null, \n	State = @newState, \n	LastResultCode = @errorCode, \n	LastRunTime = @modifiedOn,	\n	ModifiedOn = @modifiedOn,	\n	NextRunTime = @nextRunTime\n	{0} {1}\noutput\n	INSERTED.OrganizationId,\n	INSERTED.OperationType,\n	DELET`
- `0x3d1a`: `\nDeclare @tableResult table \n(\n	OrganizationId uniqueidentifier not null,\n	OperationType int not null,\n	OperationStartTime datetime not null,\n	OperationEndTime datetime not null\n)\n\nUpdate ScaleGroupOrganizationMaintenanceJobs\nSet \n	HostId = null, \n	State = @newState, \n	LastResultCode = @errorCode, \n	LastResultData = @resultData,\n	LastRunTime = @modifiedOn,	\n	ModifiedOn = @modifiedOn,	\n	ExecutionTime = @executionTime,\n\n	NextRunTime = @nextRunTime\n	{0} {1}\`

## pseudocode

```c

```

## disassembly

```asm
0x3d10  ldstr    aDeclareTablere// "\r\nDeclare @tableResult table \r\n(\r"...
0x3d15  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::_updateStateAndStatusCommand
0x3d1a  ldstr    aDeclareTablere_0// "\r\nDeclare @tableResult table \r\n(\r"...
0x3d1f  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::_updateStateAndStatusWithLastResultDataCommand
0x3d24  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_updatelastResultData
0x3d29  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x3d2f  ldsflda  valuetype [mscorlib]System.Nullable`1<bool> Microsoft.Crm.Asynchronous.JobDataAccess::_readJobParameters
0x3d34  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x3d3a  ldsfld   string [mscorlib]System.String::Empty
0x3d3f  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::operationTypePriorityMapping
0x3d44  ldsfld   string [mscorlib]System.String::Empty
0x3d49  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::prioritySettingCache
0x3d4e  ldsfld   string [mscorlib]System.String::Empty
0x3d53  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::capacitySettingCache
0x3d58  ret
```
