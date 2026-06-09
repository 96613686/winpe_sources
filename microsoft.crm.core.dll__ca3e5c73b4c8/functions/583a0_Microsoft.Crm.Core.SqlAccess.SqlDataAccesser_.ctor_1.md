# Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::.ctor_1

- ea: `0x583a0`
- end: `0x58446`
- name: `Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::.ctor_1`
- size: `166`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x58340`

## callees

- `0x57cd0`
- `0x583a0`

## string_xrefs

- `0x583a7`: `commandExecuter`
- `0x583be`: `commandRetry`
- `0x58439`: `ISqlDataAccessConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x583a0  ldarg.0
0x583a1  call     instance void [mscorlib]System.Object::.ctor()
0x583a6  ldarg.1
0x583a7  ldstr    aCommandexecute// "commandExecuter"
0x583ac  call     T0x2B0000D6
0x583b1  ldarg.3
0x583b2  ldstr    aConnectionretr_0// "connectionRetry"
0x583b7  call     T0x2B0000CE
0x583bc  ldarg.s  4
0x583be  ldstr    aCommandretry// "commandRetry"
0x583c3  call     T0x2B0000CE
0x583c8  ldarg.0
0x583c9  ldarg.1
0x583ca  stfld    class Microsoft.Crm.Core.SqlAccess.ISqlCommandExecuter Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::commandExecuter
0x583cf  ldarg.0
0x583d0  ldarg.2
0x583d1  stloc.0
0x583d2  ldloca.s 0
0x583d4  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x583d9  brtrue.s loc_583E2
0x583db  ldsfld   int32 Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::defaultCommandTimeout
0x583e0  br.s     loc_583E9
0x583e2  ldloca.s 0
0x583e4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x583e9  stfld    int32 Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::commandTimeout
0x583ee  ldarg.0
0x583ef  ldarg.s  6
0x583f1  dup
0x583f2  brtrue.s loc_583FA
0x583f4  pop
0x583f5  call     class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.Abstractions.NullLogger [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.Abstractions.NullLogger::get_Instance()
0x583fa  stfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::logger
0x583ff  ldarg.0
0x58400  ldarg.3
0x58401  ldarg.0
0x58402  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::logger
0x58407  newobj   instance void Microsoft.Crm.Core.SqlAccess.Retryer::.ctor(class Microsoft.Crm.Core.SqlAccess.RetryStrategy retryStrategy, [opt] class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x5840c  stfld    class Microsoft.Crm.Core.SqlAccess.Retryer Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::connectionRetry
0x58411  ldarg.0
0x58412  ldarg.s  4
0x58414  ldarg.0
0x58415  ldfld    class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::logger
0x5841a  newobj   instance void Microsoft.Crm.Core.SqlAccess.Retryer::.ctor(class Microsoft.Crm.Core.SqlAccess.RetryStrategy retryStrategy, [opt] class [Microsoft.Extensions.Logging.Abstractions]Microsoft.Extensions.Logging.ILogger logger)
0x5841f  stfld    class Microsoft.Crm.Core.SqlAccess.Retryer Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::commandRetry
0x58424  ldarg.0
0x58425  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Action`1<class [System.Data]System.Data.SqlClient.SqlConnection>>::.ctor()
0x5842a  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Action`1<class [System.Data]System.Data.SqlClient.SqlConnection>> Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::setConnectionProperties
0x5842f  ldarg.s  5
0x58431  brfalse.s loc_58445
0x58433  ldarg.0
0x58434  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Action`1<class [System.Data]System.Data.SqlClient.SqlConnection>> Microsoft.Crm.Core.SqlAccess.SqlDataAccesser::setConnectionProperties
0x58439  ldstr    aIsqldataaccess// "ISqlDataAccessConfiguration"
0x5843e  ldarg.s  5
0x58440  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Action`1<class [System.Data]System.Data.SqlClient.SqlConnection>>::Add(var<u1>, !!T0)
0x58445  ret
```
