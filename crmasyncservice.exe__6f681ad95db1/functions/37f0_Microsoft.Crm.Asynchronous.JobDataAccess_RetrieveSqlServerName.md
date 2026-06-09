# Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveSqlServerName

- ea: `0x37f0`
- end: `0x3846`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::RetrieveSqlServerName`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x22a0`

## callees

- `0x2a10`
- `0x37f0`
- `0xa8b0`

## pseudocode

```c

```

## disassembly

```asm
0x37f0  newobj   instance void <>c__DisplayClass39_0::.ctor()
0x37f5  stloc.0
0x37f6  ldloc.0
0x37f7  ldsfld   string [mscorlib]System.String::Empty
0x37fc  stfld    string <>c__DisplayClass39_0::sqlServerName
0x3801  ldstr    aSelectServerna// "SELECT  @@servername"
0x3806  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand(string)
0x380b  stloc.1
0x380c  ldarg.0
0x380d  ldloc.1
0x380e  ldarg.1
0x380f  ldloc.0
0x3810  ldftn    instance void <>c__DisplayClass39_0::<RetrieveSqlServerName>b__0(object[] values)
0x3816  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x381b  call     instance void Microsoft.Crm.Asynchronous.JobDataAccess::ExecuteSqlOrganizationScopeAndProcessRecords(class [System.Data]System.Data.IDbCommand command, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor recordProcessor)
0x3820  ldloc.0
0x3821  ldfld    string <>c__DisplayClass39_0::sqlServerName
0x3826  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x382b  brfalse.s loc_3831
0x382d  ldnull
0x382e  stloc.2
0x382f  leave.s  loc_3844
0x3831  ldloc.0
0x3832  ldfld    string <>c__DisplayClass39_0::sqlServerName
0x3837  stloc.2
0x3838  leave.s  loc_3844
0x383a  ldloc.1
0x383b  brfalse.s loc_3843
0x383d  ldloc.1
0x383e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3843  endfinally
0x3844  ldloc.2
0x3845  ret
```
