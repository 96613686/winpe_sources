# Microsoft.Crm.Asynchronous.JobDataAccess::SelectTimedOutJobInternal

- ea: `0x2860`
- end: `0x2940`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::SelectTimedOutJobInternal`
- size: `224`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2810`
- `0x2820`
- `0x2840`

## callees

- `0x2860`
- `0x2980`

## pseudocode

```c

```

## disassembly

```asm
0x2860  ldnull
0x2861  stloc.0
0x2862  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x2867  stloc.1
0x2868  ldloc.1
0x2869  ldstr    aSelectTop1IdOr// "\r\n\t\t\t\t\tSELECT TOP(1)\r\n\t\t\t\t"...
0x286e  ldarg.0
0x286f  ldfld    class [mscorlib]System.Lazy`1<string> Microsoft.Crm.Asynchronous.JobDataAccess::validOrgIdsInClause
0x2874  callvirt instance var<u1> class [mscorlib]System.Lazy`1<string>::get_Value()
0x2879  call     string [mscorlib]System.String::Concat(string, string)
0x287e  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x2883  ldarg.2
0x2884  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x2889  brtrue.s loc_289D
0x288b  ldloc.1
0x288c  dup
0x288d  callvirt instance string [System.Data]System.Data.IDbCommand::get_CommandText()
0x2892  ldarg.2
0x2893  call     string [mscorlib]System.String::Concat(string, string)
0x2898  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x289d  ldloc.1
0x289e  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x28a3  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x28a8  dup
0x28a9  ldstr    aModifiedon// "@modifiedOn"
0x28ae  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x28b3  ldarg.1
0x28b4  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x28b9  box      [mscorlib]System.DateTime
0x28be  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28c3  pop
0x28c4  ldstr    aLockedstate// "@lockedState"
0x28c9  ldc.i4.1
0x28ca  box      [mscorlib]System.Int32
0x28cf  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x28d4  pop
0x28d5  ldarg.0
0x28d6  ldloc.1
0x28d7  ldstr    a0Selected1Time// "{0}: Selected {1} timeouted jobs."
0x28dc  call     instance class Microsoft.Crm.Asynchronous.AsyncJob Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSelect(class [System.Data]System.Data.IDbCommand selectCommand, string traceFormat)
0x28e1  stloc.0
0x28e2  leave.s  loc_28EE
0x28e4  ldloc.1
0x28e5  brfalse.s loc_28ED
0x28e7  ldloc.1
0x28e8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x28ed  endfinally
0x28ee  leave.s  loc_293E
0x28f0  stloc.2
0x28f1  ldloc.2
0x28f2  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmException
0x28f7  brtrue.s loc_2909
0x28f9  ldloc.2
0x28fa  isinst   [System.Data]System.Data.SqlClient.SqlException
0x28ff  brtrue.s loc_2909
0x2901  ldloc.2
0x2902  isinst   [mscorlib]System.InvalidOperationException
0x2907  brfalse.s loc_293A
0x2909  ldarg.0
0x290a  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x290f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_EventLog()
0x2914  ldc.i4.1
0x2915  ldc.i4   0xC000441A
0x291a  conv.u8
0x291b  ldc.i4.2
0x291c  newarr   [mscorlib]System.Object
0x2921  dup
0x2922  ldc.i4.0
0x2923  ldarg.0
0x2924  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x2929  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x292e  stelem.ref
0x292f  dup
0x2930  ldc.i4.1
0x2931  ldloc.2
0x2932  stelem.ref
0x2933  call     void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogEvent(class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x2938  br.s     loc_293C
0x293a  rethrow
0x293c  leave.s  loc_293E
0x293e  ldloc.0
0x293f  ret
```
