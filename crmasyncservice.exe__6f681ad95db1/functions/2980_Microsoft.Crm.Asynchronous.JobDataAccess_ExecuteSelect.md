# Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSelect

- ea: `0x2980`
- end: `0x2a10`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSelect`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x2860`

## callees

- `0x9d0`
- `0x22a0`
- `0x2980`
- `0xa840`

## pseudocode

```c

```

## disassembly

```asm
0x2980  newobj   instance void <>c__DisplayClass23_0::.ctor()
0x2985  stloc.0
0x2986  ldloc.0
0x2987  ldarg.0
0x2988  stfld    class Microsoft.Crm.Asynchronous.JobDataAccess <>c__DisplayClass23_0::<>4__this
0x298d  ldloc.0
0x298e  ldnull
0x298f  stfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x2994  ldarg.0
0x2995  ldarg.1
0x2996  ldloc.0
0x2997  ldftn    instance void <>c__DisplayClass23_0::<ExecuteSelect>b__0(object[] values)
0x299d  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x29a2  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x29a7  stloc.1
0x29a8  ldloc.0
0x29a9  ldfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x29ae  brfalse.s loc_29DF
0x29b0  ldloc.0
0x29b1  ldfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x29b6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x29bb  pop
0x29bc  ldloc.0
0x29bd  ldfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x29c2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncJob::get_OrganizationId()
0x29c7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29cc  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x29d1  brfalse.s loc_29DF
0x29d3  ldarg.0
0x29d4  ldloc.0
0x29d5  ldfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x29da  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::UpdateJobTargetServer(class Microsoft.Crm.Asynchronous.AsyncJob job)
0x29df  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x29e4  ldc.i4.s 0x15
0x29e6  ldarg.2
0x29e7  ldc.i4.2
0x29e8  newarr   [mscorlib]System.Object
0x29ed  dup
0x29ee  ldc.i4.0
0x29ef  ldarg.0
0x29f0  ldfld    class Microsoft.Crm.Asynchronous.JobManager Microsoft.Crm.Asynchronous.JobDataAccess::_jobManager
0x29f5  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_InstanceName()
0x29fa  stelem.ref
0x29fb  dup
0x29fc  ldc.i4.1
0x29fd  ldloc.1
0x29fe  box      [mscorlib]System.Int32
0x2a03  stelem.ref
0x2a04  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2a09  ldloc.0
0x2a0a  ldfld    class Microsoft.Crm.Asynchronous.AsyncJob <>c__DisplayClass23_0::job
0x2a0f  ret
```
