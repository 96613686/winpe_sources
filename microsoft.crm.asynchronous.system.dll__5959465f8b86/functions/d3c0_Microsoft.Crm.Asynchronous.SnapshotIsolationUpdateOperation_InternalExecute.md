# Microsoft.Crm.Asynchronous.SnapshotIsolationUpdateOperation::InternalExecute

- ea: `0xd3c0`
- end: `0xd53e`
- name: `Microsoft.Crm.Asynchronous.SnapshotIsolationUpdateOperation::InternalExecute`
- size: `382`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xd3c0`

## string_xrefs

- `0xd3ca`: `Operation type must be 'SnapshotIsolationUpdate'`
- `0xd3dc`: `Attempting to change snapshot isolation state for org {0}`

## pseudocode

```c

```

## disassembly

```asm
0xd3c0  ldarg.1
0xd3c1  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OperationType()
0xd3c6  ldc.i4.s 0x37
0xd3c8  ceq
0xd3ca  ldstr    aOperationTypeM_21// "Operation type must be 'SnapshotIsolati"...
0xd3cf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xd3d4  ldarg.1
0xd3d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd3da  ldc.i4.s 0x15
0xd3dc  ldstr    aAttemptingToCh_0// "Attempting to change snapshot isolation"...
0xd3e1  ldc.i4.1
0xd3e2  newarr   [mscorlib]System.Object
0xd3e7  dup
0xd3e8  ldc.i4.0
0xd3e9  ldarg.0
0xd3ea  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd3ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd3f4  box      [mscorlib]System.Guid
0xd3f9  stelem.ref
0xd3fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd3ff  ldarg.1
0xd400  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd405  stloc.0
0xd406  ldarg.1
0xd407  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd40c  ldstr    aOn_0// "ON"
0xd411  ldc.i4.5
0xd412  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd417  brfalse.s loc_D442
0xd419  ldarg.1
0xd41a  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEvent::get_JobParameters()
0xd41f  ldstr    aOff// "OFF"
0xd424  ldc.i4.5
0xd425  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd42a  brfalse.s loc_D442
0xd42c  ldc.i4   0x80040216
0xd431  ldstr    aInvalidSnapsho// "Invalid Snapshot Isolation State specif"...
0xd436  ldc.i4.0
0xd437  newarr   [mscorlib]System.Object
0xd43c  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncFailedResult::.ctor(int32, string, object[])
0xd441  ret
0xd442  nop
0xd443  ldarg.1
0xd444  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd449  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::.ctor(valuetype [mscorlib]System.Guid)
0xd44e  ldloc.0
0xd44f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationDatabaseUtility::SetSnapshotIsolation(string)
0xd454  ldc.i4.0
0xd455  stloc.1
0xd456  ldloc.0
0xd457  ldstr    aOn_0// "ON"
0xd45c  ldc.i4.5
0xd45d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0xd462  brtrue.s loc_D466
0xd464  ldc.i4.1
0xd465  stloc.1
0xd466  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0xd46b  ldarg.1
0xd46c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd471  ldloc.1
0xd472  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::SetOrganizationSnapshotIsolation(valuetype [mscorlib]System.Guid, bool)
0xd477  ldarg.1
0xd478  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd47d  ldc.i4.s 0x15
0xd47f  ldstr    aChangingSnapsh// "Changing snapshot isolation state for o"...
0xd484  ldc.i4.1
0xd485  newarr   [mscorlib]System.Object
0xd48a  dup
0xd48b  ldc.i4.0
0xd48c  ldarg.0
0xd48d  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_Configuration()
0xd492  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0xd497  box      [mscorlib]System.Guid
0xd49c  stelem.ref
0xd49d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd4a2  ldc.i4.s 0x1E
0xd4a4  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncRemoveEventResult::.ctor(int32)
0xd4a9  stloc.2
0xd4aa  leave    loc_D53C
0xd4af  stloc.3
0xd4b0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xd4b5  ldstr    aErrorWhileUpda_0// "Error while updating snapshot isolation"...
0xd4ba  ldc.i4.2
0xd4bb  newarr   [mscorlib]System.Object
0xd4c0  dup
0xd4c1  ldc.i4.0
0xd4c2  ldarg.1
0xd4c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd4c8  box      [mscorlib]System.Guid
0xd4cd  stelem.ref
0xd4ce  dup
0xd4cf  ldc.i4.1
0xd4d0  ldloc.3
0xd4d1  stelem.ref
0xd4d2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xd4d7  stloc.s  4
0xd4d9  ldloc.3
0xd4da  ldarg.1
0xd4db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd4e0  ldc.i4.s 0x15
0xd4e2  ldstr    a0// "{0}"
0xd4e7  ldc.i4.1
0xd4e8  newarr   [mscorlib]System.Object
0xd4ed  dup
0xd4ee  ldc.i4.0
0xd4ef  ldloc.s  4
0xd4f1  stelem.ref
0xd4f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xd4f7  ldarg.0
0xd4f8  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0xd4fd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_CrmEventLog()
0xd502  ldarg.0
0xd503  call     instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventHandlerCommand::get_AsyncService()
0xd508  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncService::get_ServiceName()
0xd50d  ldc.i4.2
0xd50e  ldc.i4   0x8000441F
0xd513  conv.u8
0xd514  ldc.i4.3
0xd515  newarr   [mscorlib]System.Object
0xd51a  dup
0xd51b  ldc.i4.0
0xd51c  call     string [mscorlib]System.Environment::get_MachineName()
0xd521  stelem.ref
0xd522  dup
0xd523  ldc.i4.1
0xd524  ldarg.1
0xd525  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0xd52a  box      [mscorlib]System.Guid
0xd52f  stelem.ref
0xd530  dup
0xd531  ldc.i4.2
0xd532  ldloc.s  4
0xd534  stelem.ref
0xd535  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0xd53a  rethrow
0xd53c  ldloc.2
0xd53d  ret
```
