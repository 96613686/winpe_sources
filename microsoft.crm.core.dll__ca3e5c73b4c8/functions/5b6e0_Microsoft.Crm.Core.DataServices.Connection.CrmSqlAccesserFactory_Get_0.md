# Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get_0

- ea: `0x5b6e0`
- end: `0x5b781`
- name: `Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get_0`
- size: `161`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x43a10`
- `0x4a2b0`
- `0x4a390`
- `0x4a3e0`
- `0x4a430`
- `0x4a950`
- `0x4dcc0`
- `0x5a690`

## callees

- `0xf260`
- `0xf450`
- `0x4ee30`
- `0x58320`
- `0x5b6e0`
- `0x5b7e0`
- `0x5b890`

## string_xrefs

- `0x5b726`: `ISqlDataAccess`
- `0x5b74f`: `Constructing ISqlDataAccess instance. SQL connection string: `

## pseudocode

```c

```

## disassembly

```asm
0x5b6e0  ldarg.0
0x5b6e1  ldarg.1
0x5b6e2  ldarg.2
0x5b6e3  ldarg.3
0x5b6e4  ldarg.s  5
0x5b6e6  ldarg.s  4
0x5b6e8  ldarg.s  6
0x5b6ea  ldarg.s  7
0x5b6ec  call     instance class Microsoft.Crm.CrmSqlAccessConfigurationBuilder Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::CreateSqlAccessConfigBuilder(string connectionString, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> organizationId, [opt] valuetype Microsoft.Crm.ConnectionAccessType accessType, [opt] string workloadGroup, [opt] int32 sqlMaxPoolSize, [opt] bool enableMars, [opt] int32 defaultCommandTimeout)
0x5b6f1  stloc.0
0x5b6f2  ldarga.s 2
0x5b6f4  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5b6f9  brfalse.s loc_5B749
0x5b6fb  ldarga.s 2
0x5b6fd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5b702  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5b707  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5b70c  brfalse.s loc_5B749
0x5b70e  ldarg.0
0x5b70f  ldarga.s 2
0x5b711  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x5b716  call     instance void Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::UpdateCrmDbQueryDetails(valuetype [mscorlib]System.Guid organizationId)
0x5b71b  ldarg.0
0x5b71c  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::logger
0x5b721  ldstr    aConstructing0I_0// "Constructing {0} instance for Organizat"...
0x5b726  ldstr    aIsqldataaccess_0// "ISqlDataAccess"
0x5b72b  ldarg.2
0x5b72c  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x5b731  ldloc.0
0x5b732  callvirt instance string Microsoft.Crm.CrmSqlAccessConfigurationBuilder::get_ConnectionStringWithPasswordMashed()
0x5b737  call     string [mscorlib]System.String::Format(string, object, object, object)
0x5b73c  ldc.i4.0
0x5b73d  newarr   [mscorlib]System.Object
0x5b742  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5b747  br.s     loc_5B76A
0x5b749  ldarg.0
0x5b74a  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::logger
0x5b74f  ldstr    aConstructingIs// "Constructing ISqlDataAccess instance. S"...
0x5b754  ldloc.0
0x5b755  callvirt instance string Microsoft.Crm.CrmSqlAccessConfigurationBuilder::get_ConnectionStringWithPasswordMashed()
0x5b75a  call     string [mscorlib]System.String::Concat(string, string)
0x5b75f  ldc.i4.0
0x5b760  newarr   [mscorlib]System.Object
0x5b765  call     void [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.LoggerExtensions::LogInformation(class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger, string, object[])
0x5b76a  ldloc.0
0x5b76b  callvirt instance class Microsoft.Crm.Core.SqlAccess.ISqlDataAccessConfiguration Microsoft.Crm.CrmSqlAccessConfigurationBuilder::Build()
0x5b770  ldarg.0
0x5b771  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::logger
0x5b776  newobj   instance void Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::.ctor(class Microsoft.Crm.Core.SqlAccess.ISqlDataAccessConfiguration sqlDataAccessConfig, class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x5b77b  newobj   instance void Microsoft.Crm.Core.CrmSqlDataAccesser::.ctor(class Microsoft.Crm.Core.SqlAccess.ISqlDataAccess sqlDataAccesser)
0x5b780  ret
```
