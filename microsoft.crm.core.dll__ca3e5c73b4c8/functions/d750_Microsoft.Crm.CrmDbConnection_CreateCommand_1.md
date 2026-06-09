# Microsoft.Crm.CrmDbConnection::CreateCommand_1

- ea: `0xd750`
- end: `0xd7ac`
- name: `Microsoft.Crm.CrmDbConnection::CreateCommand_1`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0xd2c0`
- `0xd2d0`
- `0xd750`
- `0xddb0`
- `0xe850`
- `0x1a880`
- `0x1b8d0`

## string_xrefs

- `0xd75d`: `CreateCommand - Encountered disposed CrmDbConnection when it should not be disposed`
- `0xd771`: `CreateCommand on CrmDbConnection called without opening the GetCreateConnection()`

## pseudocode

```c

```

## disassembly

```asm
0xd750  ldarg.0
0xd751  ldfld    bool Microsoft.Crm.CrmDbConnection::_disposed
0xd756  brfalse.s loc_D768
0xd758  ldstr    aCrmdbconnectio// "CrmDbConnection"
0xd75d  ldstr    aCreatecommandE// "CreateCommand - Encountered disposed Cr"...
0xd762  newobj   instance void Microsoft.Crm.CrmObjectDisposedException::.ctor(string objectName, string message)
0xd767  throw
0xd768  ldarg.0
0xd769  ldfld    int32 Microsoft.Crm.CrmDbConnection::_openCount
0xd76e  ldc.i4.0
0xd76f  bgt.s    loc_D781
0xd771  ldstr    aCreatecommandO// "CreateCommand on CrmDbConnection called"...
0xd776  ldc.i4   0x8004023B
0xd77b  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message, int32 errorCode)
0xd780  throw
0xd781  ldarg.0
0xd782  ldarg.0
0xd783  call     instance class [System.Data]System.Data.SqlClient.SqlConnection Microsoft.Crm.CrmDbConnection::GetCreateConnection()
0xd788  ldarg.1
0xd789  call     instance void Microsoft.Crm.CrmDbConnection::CreateCommand(class [System.Data]System.Data.IDbConnection connection, class [System.Data]System.Data.IDbCommand& command)
0xd78e  ldarg.1
0xd78f  ldind.ref
0xd790  ldarg.0
0xd791  ldfld    int32 Microsoft.Crm.CrmDbConnection::_commandTimeout
0xd796  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandTimeout(int32)
0xd79b  ldarg.0
0xd79c  call     instance int32 Microsoft.Crm.CrmDbConnection::get_NumberOfCommandsCreated()
0xd7a1  stloc.0
0xd7a2  ldarg.0
0xd7a3  ldloc.0
0xd7a4  ldc.i4.1
0xd7a5  add
0xd7a6  call     instance void Microsoft.Crm.CrmDbConnection::set_NumberOfCommandsCreated(int32 value)
0xd7ab  ret
```
