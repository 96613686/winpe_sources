# Microsoft.Crm.Workflow.WorkflowDataAccess::RetrieveWorkflowInstanceState

- ea: `0x23d0`
- end: `0x2433`
- name: `Microsoft.Crm.Workflow.WorkflowDataAccess::RetrieveWorkflowInstanceState`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x23d0`
- `0x3700`

## pseudocode

```c

```

## disassembly

```asm
0x23d0  newobj   instance void <>c__DisplayClass6_0::.ctor()
0x23d5  stloc.0
0x23d6  ldloc.0
0x23d7  ldnull
0x23d8  stfld    string <>c__DisplayClass6_0::workflowStateAsText
0x23dd  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x23e2  stloc.1
0x23e3  ldloc.1
0x23e4  ldstr    aSelectWorkflow// "select WorkflowState\r\nfrom AsyncOpera"...
0x23e9  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x23ee  ldloc.1
0x23ef  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x23f4  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x23f9  ldstr    aId// "@id"
0x23fe  ldarg.1
0x23ff  box      [mscorlib]System.Guid
0x2404  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x2409  pop
0x240a  ldarg.0
0x240b  ldloc.1
0x240c  ldloc.0
0x240d  ldftn    instance void <>c__DisplayClass6_0::<RetrieveWorkflowInstanceState>b__0(object[] values)
0x2413  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x2418  ldc.i4.1
0x2419  call     instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor, int32)
0x241e  ldloc.0
0x241f  ldfld    string <>c__DisplayClass6_0::workflowStateAsText
0x2424  stloc.2
0x2425  leave.s  loc_2431
0x2427  ldloc.1
0x2428  brfalse.s loc_2430
0x242a  ldloc.1
0x242b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2430  endfinally
0x2431  ldloc.2
0x2432  ret
```
