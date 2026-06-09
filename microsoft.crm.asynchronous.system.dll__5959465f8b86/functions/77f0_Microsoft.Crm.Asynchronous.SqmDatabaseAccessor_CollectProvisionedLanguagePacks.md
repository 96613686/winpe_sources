# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectProvisionedLanguagePacks

- ea: `0x77f0`
- end: `0x7840`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectProvisionedLanguagePacks`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5310`

## callees

- `0x77f0`
- `0xee60`

## pseudocode

```c

```

## disassembly

```asm
0x77f0  newobj   instance void <>c__DisplayClass36_0::.ctor()
0x77f5  stloc.0
0x77f6  ldloc.0
0x77f7  ldarg.1
0x77f8  stfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass36_0::session
0x77fd  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x7802  stloc.1
0x7803  ldloc.1
0x7804  ldstr    aSelectLanguage// "select LanguageId from MetadataSchema.O"...
0x7809  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x780e  ldarg.0
0x780f  ldloc.1
0x7810  ldloc.0
0x7811  ldftn    instance void <>c__DisplayClass36_0::<CollectProvisionedLanguagePacks>b__0(object[] values)
0x7817  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x781c  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x7821  stloc.2
0x7822  ldloc.0
0x7823  ldfld    class [Microsoft.Crm]Microsoft.Crm.ISqmSession <>c__DisplayClass36_0::session
0x7828  ldc.i4   0x1ED
0x782d  ldloc.2
0x782e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::set_Item(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32)
0x7833  leave.s  loc_783F
0x7835  ldloc.1
0x7836  brfalse.s loc_783E
0x7838  ldloc.1
0x7839  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x783e  endfinally
0x783f  ret
```
