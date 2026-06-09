# Microsoft.Crm.Extensibility.RetryHelper::.ctor

- ea: `0xc050`
- end: `0xc2e3`
- name: `Microsoft.Crm.Extensibility.RetryHelper::.ctor`
- size: `659`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xc620`
- `0x2f960`
- `0x2f9a0`

## string_xrefs

- `0xc1a5`: `A severe error occurred on the current command`
- `0xc1d8`: `This SqlTransaction has completed`
- `0xc1fa`: `Please open the connection before executing the command`
- `0xc20b`: `The timeout period elapsed prior to completion of the operation or the server is not responding`
- `0xc260`: `The service has encountered an error processing your request`
- `0xc271`: `The service is currently busy`
- `0xc2a4`: `Too many create or update operations in progress for subscription`

## pseudocode

```c

```

## disassembly

```asm
0xc050  ldarg.0
0xc051  ldc.i4.0
0xc052  ldc.i4.0
0xc053  ldc.i4.s 0x1E
0xc055  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0xc05a  stfld    valuetype [mscorlib]System.TimeSpan Microsoft.Crm.Extensibility.RetryHelper::_interval
0xc05f  ldarg.0
0xc060  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::.ctor()
0xc065  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc06a  ldarg.0
0xc06b  ldc.i4.2
0xc06c  newobj   instance void ExceptionStringMatch::.ctor(int32 defaultRetries)
0xc071  stfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc076  ldarg.0
0xc077  call     instance void [mscorlib]System.Object::.ctor()
0xc07c  ldarg.0
0xc07d  ldarg.1
0xc07e  call     instance int32 Microsoft.Crm.Extensibility.RetryHelper::GetDefaultSolutionImportRetryAttempts(valuetype [mscorlib]System.Guid organizationId)
0xc083  stloc.0
0xc084  ldarg.0
0xc085  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc08a  ldc.i4.s 0xFE
0xc08c  ldloc.0
0xc08d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc092  ldarg.0
0xc093  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc098  ldc.i4.s 0x79
0xc09a  ldloc.0
0xc09b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0a0  ldarg.0
0xc0a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0a6  ldc.i4   0x4B5
0xc0ab  ldloc.0
0xc0ac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0b1  ldarg.0
0xc0b2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0b7  ldc.i4   0x107D
0xc0bc  ldloc.0
0xc0bd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0c2  ldarg.0
0xc0c3  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0c8  ldc.i4   0x2AF9
0xc0cd  ldloc.0
0xc0ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0d3  ldarg.0
0xc0d4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0d9  ldc.i4   0x9CCF
0xc0de  ldloc.0
0xc0df  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0e4  ldarg.0
0xc0e5  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0ea  ldc.i4   0x9D05
0xc0ef  ldloc.0
0xc0f0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc0f5  ldarg.0
0xc0f6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc0fb  ldc.i4   0x9E35
0xc100  ldloc.0
0xc101  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc106  ldarg.0
0xc107  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc10c  ldc.i4   0x9EA5
0xc111  ldloc.0
0xc112  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc117  ldarg.0
0xc118  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc11d  ldc.i4   0xC2FE
0xc122  ldloc.0
0xc123  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc128  ldarg.0
0xc129  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc12e  ldc.i4   0xC2FF
0xc133  ldloc.0
0xc134  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc139  ldarg.0
0xc13a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32> Microsoft.Crm.Extensibility.RetryHelper::retriableSqlErrorCodeMapping
0xc13f  ldc.i4   0xC300
0xc144  ldloc.0
0xc145  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, int32>::Add(var<u1>, !!T0)
0xc14a  ldarg.0
0xc14b  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc150  ldstr    aTheConnectionI// "The connection is broken and recovery i"...
0xc155  ldloc.0
0xc156  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc15b  ldarg.0
0xc15c  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc161  ldstr    aBecauseItsRepl// "because its replica role is RESOLVING w"...
0xc166  ldloc.0
0xc167  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc16c  ldarg.0
0xc16d  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc172  ldstr    aTheSpecifiedNe// "The specified network name is no longer"...
0xc177  ldloc.0
0xc178  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc17d  ldarg.0
0xc17e  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc183  ldstr    aTheWaitOperati// "The wait operation timed out"
0xc188  ldloc.0
0xc189  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc18e  ldarg.0
0xc18f  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc194  ldstr    aThePipeHasBeen// "The pipe has been ended"
0xc199  ldloc.0
0xc19a  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc19f  ldarg.0
0xc1a0  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1a5  ldstr    aASevereErrorOc// "A severe error occurred on the current "...
0xc1aa  ldloc.0
0xc1ab  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc1b0  ldarg.0
0xc1b1  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1b6  ldstr    aCannotContinue// "Cannot continue the execution because t"...
0xc1bb  ldloc.0
0xc1bc  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc1c1  ldarg.0
0xc1c2  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1c7  ldstr    aPermittedOnlyW// "permitted only when the database replic"...
0xc1cc  ldloc.0
0xc1cd  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc1d2  ldarg.0
0xc1d3  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1d8  ldstr    aThisSqltransac// "This SqlTransaction has completed"
0xc1dd  ldloc.0
0xc1de  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc1e3  ldarg.0
0xc1e4  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1e9  ldstr    aAnExistingConn// "An existing connection was forcibly clo"...
0xc1ee  ldloc.0
0xc1ef  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc1f4  ldarg.0
0xc1f5  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc1fa  ldstr    aPleaseOpenTheC// "Please open the connection before execu"...
0xc1ff  ldloc.0
0xc200  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc205  ldarg.0
0xc206  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc20b  ldstr    aTheTimeoutPeri// "The timeout period elapsed prior to com"...
0xc210  ldloc.0
0xc211  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc216  ldarg.0
0xc217  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc21c  ldstr    aSystemDataSqlc// "System.Data.SqlClient.SqlException: Exe"...
0xc221  ldloc.0
0xc222  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc227  ldarg.0
0xc228  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc22d  ldstr    aWasDeadlockedO// "was deadlocked on lock resources with a"...
0xc232  ldloc.0
0xc233  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc238  ldarg.0
0xc239  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc23e  ldstr    aTheSemaphoreTi// "The semaphore timeout period has expire"...
0xc243  ldloc.0
0xc244  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc249  ldarg.0
0xc24a  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc24f  ldstr    aNoSuchHostIsKn// "No such host is known"
0xc254  ldloc.0
0xc255  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc25a  ldarg.0
0xc25b  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc260  ldstr    aTheServiceHasE// "The service has encountered an error pr"...
0xc265  ldloc.0
0xc266  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc26b  ldarg.0
0xc26c  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc271  ldstr    aTheServiceIsCu// "The service is currently busy"
0xc276  ldloc.0
0xc277  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc27c  ldarg.0
0xc27d  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc282  ldstr    aPleaseRetryThe// "Please retry the connection later"
0xc287  ldloc.0
0xc288  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc28d  ldarg.0
0xc28e  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc293  ldstr    aNotEnoughResou// "Not enough resources to process request"
0xc298  ldloc.0
0xc299  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc29e  ldarg.0
0xc29f  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc2a4  ldstr    aTooManyCreateO// "Too many create or update operations in"...
0xc2a9  ldloc.0
0xc2aa  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc2af  ldarg.0
0xc2b0  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc2b5  ldstr    aTooManyOperati// "Too many operations in progress for sub"...
0xc2ba  ldloc.0
0xc2bb  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc2c0  ldarg.0
0xc2c1  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc2c6  ldstr    aTheLoginFailed// "The login failed"
0xc2cb  ldloc.0
0xc2cc  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc2d1  ldarg.0
0xc2d2  ldfld    class ExceptionStringMatch Microsoft.Crm.Extensibility.RetryHelper::retriableErrorMsgMapping
0xc2d7  ldstr    aTheReplicaIsNo// "The replica is not available for login "...
0xc2dc  ldloc.0
0xc2dd  callvirt instance void ExceptionStringMatch::Add(string stringToMatch, int32 retries)
0xc2e2  ret
```
