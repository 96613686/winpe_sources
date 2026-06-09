# Microsoft.Crm.Asynchronous.ReadCommittedSnapshotIsolationUpdate::InternalExecute

- ea: `0xd220`
- end: `0xd39c`
- name: `Microsoft.Crm.Asynchronous.ReadCommittedSnapshotIsolationUpdate::InternalExecute`
- size: `380`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xd220`

## string_xrefs

- `0xd22a`: `Operation type must be 'ReadCommittedSnapshotIsolationUpdate'`
- `0xd23c`: `Attempting to change read committed snapshot isolation state for org {0}`
- `0xd291`: `Invalid Read Committed Snapshot Isolation State specified in the JobParameters. Allowed values are ON or OFF`
- `0xd2dd`: `Changing read committed snapshot isolation state for org {0} was successful`
- `0xd313`: `Error while updating read committed snapshot isolation for organization: {0}, Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0xd220  ldarg.1
0xd221  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xd226  ldc.i4.s 0x40
0xd228  ceq
0xd22a  ldstr    aOperationTypeM_20// "Operation type must be 'ReadCommittedSn"...
0xd22f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xd234  ldarg.1
0xd235  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd23a  ldc.i4.s 0x15
0xd23c  ldstr    aAttemptingToCh// "Attempting to change read committed sna"...
0xd241  ldc.i4.1
0xd242  newarr   [mscorlib]System.Object
0xd247  dup
0xd248  ldc.i4.0
0xd249  ldarg.0
0xd24a  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd24f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd254  box      [mscorlib]System.Guid
0xd259  stelem.ref
0xd25a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd25f  ldarg.1
0xd260  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd265  stloc.0
0xd266  ldarg.1
0xd267  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd26c  ldstr    aOn_0// "ON"
0xd271  ldc.i4.5
0xd272  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd277  brfalse.s loc_D2A2
0xd279  ldarg.1
0xd27a  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd27f  ldstr    aOff// "OFF"
0xd284  ldc.i4.5
0xd285  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd28a  brfalse.s loc_D2A2
0xd28c  ldc.i4   0x80040216
0xd291  ldstr    aInvalidReadCom// "Invalid Read Committed Snapshot Isolati"...
0xd296  ldc.i4.0
0xd297  newarr   [mscorlib]System.Object
0xd29c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xd2a1  ret
0xd2a2  nop
0xd2a3  ldarg.1
0xd2a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd2a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0xd2ae  ldloc.0
0xd2af  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::SetReadCommittedSnapshotIsolation(string)
0xd2b4  ldloc.0
0xd2b5  ldstr    aOn_0// "ON"
0xd2ba  ldc.i4.5
0xd2bb  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd2c0  ldc.i4.0
0xd2c1  ceq
0xd2c3  stloc.1
0xd2c4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xd2c9  ldarg.1
0xd2ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd2cf  ldloc.1
0xd2d0  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::SetOrganizationReadCommittedSnapshotIsolation(valuetype [mscorlib]System.Guid, bool)
0xd2d5  ldarg.1
0xd2d6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd2db  ldc.i4.s 0x15
0xd2dd  ldstr    aChangingReadCo// "Changing read committed snapshot isolat"...
0xd2e2  ldc.i4.1
0xd2e3  newarr   [mscorlib]System.Object
0xd2e8  dup
0xd2e9  ldc.i4.0
0xd2ea  ldarg.0
0xd2eb  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd2f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd2f5  box      [mscorlib]System.Guid
0xd2fa  stelem.ref
0xd2fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd300  ldc.i4.s 0x1E
0xd302  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0xd307  stloc.2
0xd308  leave    loc_D39A
0xd30d  stloc.3
0xd30e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd313  ldstr    aErrorWhileUpda// "Error while updating read committed sna"...
0xd318  ldc.i4.2
0xd319  newarr   [mscorlib]System.Object
0xd31e  dup
0xd31f  ldc.i4.0
0xd320  ldarg.1
0xd321  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd326  box      [mscorlib]System.Guid
0xd32b  stelem.ref
0xd32c  dup
0xd32d  ldc.i4.1
0xd32e  ldloc.3
0xd32f  stelem.ref
0xd330  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd335  stloc.s  4
0xd337  ldloc.3
0xd338  ldarg.1
0xd339  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd33e  ldc.i4.s 0x15
0xd340  ldstr    a0// "{0}"
0xd345  ldc.i4.1
0xd346  newarr   [mscorlib]System.Object
0xd34b  dup
0xd34c  ldc.i4.0
0xd34d  ldloc.s  4
0xd34f  stelem.ref
0xd350  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd355  ldarg.0
0xd356  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0xd35b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_CrmEventLog()
0xd360  ldarg.0
0xd361  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0xd366  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_ServiceName()
0xd36b  ldc.i4.2
0xd36c  ldc.i4   0x8000441F
0xd371  conv.u8
0xd372  ldc.i4.3
0xd373  newarr   [mscorlib]System.Object
0xd378  dup
0xd379  ldc.i4.0
0xd37a  call     string [mscorlib]System.Environment::get_MachineName()
0xd37f  stelem.ref
0xd380  dup
0xd381  ldc.i4.1
0xd382  ldarg.1
0xd383  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd388  box      [mscorlib]System.Guid
0xd38d  stelem.ref
0xd38e  dup
0xd38f  ldc.i4.2
0xd390  ldloc.s  4
0xd392  stelem.ref
0xd393  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xd398  rethrow
0xd39a  ldloc.2
0xd39b  ret
```
