# Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection_0

- ea: `0x2950`
- end: `0x296c`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::CreateConnection_0`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2940`
- `0x2ae0`
- `0x2b30`

## callees

- `0x2950`

## pseudocode

```c

```

## disassembly

```asm
0x2950  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x2955  stloc.0
0x2956  ldloc.0
0x2957  ldarg.1
0x2958  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::CreateConnection(valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigScope)
0x295d  stloc.1
0x295e  leave.s  loc_296A
0x2960  ldloc.0
0x2961  brfalse.s loc_2969
0x2963  ldloc.0
0x2964  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2969  endfinally
0x296a  ldloc.1
0x296b  ret
```
