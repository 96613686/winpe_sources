# Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::.cctor

- ea: `0xdfb0`
- end: `0xe0d6`
- name: `Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::.cctor`
- size: `294`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0xe007`: `A severe error occurred on the current command`
- `0xe01f`: `This SqlTransaction has completed`
- `0xe031`: `Please open the connection before executing the command`
- `0xe043`: `The timeout period elapsed prior to completion of the operation or the server is not responding`
- `0xe070`: `The service has encountered an error processing your request`
- `0xe079`: `The service is currently busy`
- `0xe094`: `Too many create or update operations in progress for subscription`

## pseudocode

```c

```

## disassembly

```asm
0xdfb0  ldstr    aAZaZ09// "[^a-zA-Z0-9]+"
0xdfb5  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string)
0xdfba  stsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::MatchLettersNumbers
0xdfbf  ldc.i4.s 0xC
0xdfc1  newarr   [mscorlib]System.Int32
0xdfc6  dup
0xdfc7  ldtoken  valuetype __StaticArrayInitTypeSize=48 <PrivateImplementationDetails>::'2C6E59E7D2FBF3BEE4E02B44C1ABFFF40121851B'
0xdfcc  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0xdfd1  stsfld   int32[] Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::RetriableSqlErrorCodes
0xdfd6  ldc.i4.s 0x1C
0xdfd8  newarr   [mscorlib]System.String
0xdfdd  dup
0xdfde  ldc.i4.0
0xdfdf  ldstr    aTheConnectionI// "The connection is broken and recovery i"...
0xdfe4  stelem.ref
0xdfe5  dup
0xdfe6  ldc.i4.1
0xdfe7  ldstr    aBecauseItsRepl// "because its replica role is RESOLVING w"...
0xdfec  stelem.ref
0xdfed  dup
0xdfee  ldc.i4.2
0xdfef  ldstr    aTheSpecifiedNe// "The specified network name is no longer"...
0xdff4  stelem.ref
0xdff5  dup
0xdff6  ldc.i4.3
0xdff7  ldstr    aTheWaitOperati// "The wait operation timed out"
0xdffc  stelem.ref
0xdffd  dup
0xdffe  ldc.i4.4
0xdfff  ldstr    aThePipeHasBeen// "The pipe has been ended"
0xe004  stelem.ref
0xe005  dup
0xe006  ldc.i4.5
0xe007  ldstr    aASevereErrorOc// "A severe error occurred on the current "...
0xe00c  stelem.ref
0xe00d  dup
0xe00e  ldc.i4.6
0xe00f  ldstr    aCannotContinue// "Cannot continue the execution because t"...
0xe014  stelem.ref
0xe015  dup
0xe016  ldc.i4.7
0xe017  ldstr    aPermittedOnlyW// "permitted only when the database replic"...
0xe01c  stelem.ref
0xe01d  dup
0xe01e  ldc.i4.8
0xe01f  ldstr    aThisSqltransac// "This SqlTransaction has completed"
0xe024  stelem.ref
0xe025  dup
0xe026  ldc.i4.s 9
0xe028  ldstr    aAnExistingConn// "An existing connection was forcibly clo"...
0xe02d  stelem.ref
0xe02e  dup
0xe02f  ldc.i4.s 0xA
0xe031  ldstr    aPleaseOpenTheC// "Please open the connection before execu"...
0xe036  stelem.ref
0xe037  dup
0xe038  ldc.i4.s 0xB
0xe03a  ldstr    aMicrosoftCrmCr// "Microsoft.Crm.CrmReportingException: An"...
0xe03f  stelem.ref
0xe040  dup
0xe041  ldc.i4.s 0xC
0xe043  ldstr    aTheTimeoutPeri// "The timeout period elapsed prior to com"...
0xe048  stelem.ref
0xe049  dup
0xe04a  ldc.i4.s 0xD
0xe04c  ldstr    aSystemDataSqlc// "System.Data.SqlClient.SqlException: Exe"...
0xe051  stelem.ref
0xe052  dup
0xe053  ldc.i4.s 0xE
0xe055  ldstr    aWasDeadlockedO// "was deadlocked on lock resources with a"...
0xe05a  stelem.ref
0xe05b  dup
0xe05c  ldc.i4.s 0xF
0xe05e  ldstr    aTheSemaphoreTi// "The semaphore timeout period has expire"...
0xe063  stelem.ref
0xe064  dup
0xe065  ldc.i4.s 0x10
0xe067  ldstr    aNoSuchHostIsKn// "No such host is known"
0xe06c  stelem.ref
0xe06d  dup
0xe06e  ldc.i4.s 0x11
0xe070  ldstr    aTheServiceHasE// "The service has encountered an error pr"...
0xe075  stelem.ref
0xe076  dup
0xe077  ldc.i4.s 0x12
0xe079  ldstr    aTheServiceIsCu// "The service is currently busy"
0xe07e  stelem.ref
0xe07f  dup
0xe080  ldc.i4.s 0x13
0xe082  ldstr    aPleaseRetryThe// "Please retry the connection later"
0xe087  stelem.ref
0xe088  dup
0xe089  ldc.i4.s 0x14
0xe08b  ldstr    aNotEnoughResou// "Not enough resources to process request"
0xe090  stelem.ref
0xe091  dup
0xe092  ldc.i4.s 0x15
0xe094  ldstr    aTooManyCreateO// "Too many create or update operations in"...
0xe099  stelem.ref
0xe09a  dup
0xe09b  ldc.i4.s 0x16
0xe09d  ldstr    aTooManyOperati// "Too many operations in progress for sub"...
0xe0a2  stelem.ref
0xe0a3  dup
0xe0a4  ldc.i4.s 0x17
0xe0a6  ldstr    aTheLoginFailed// "The login failed"
0xe0ab  stelem.ref
0xe0ac  dup
0xe0ad  ldc.i4.s 0x18
0xe0af  ldstr    aTheReplicaIsNo// "The replica is not available for login "...
0xe0b4  stelem.ref
0xe0b5  dup
0xe0b6  ldc.i4.s 0x19
0xe0b8  ldstr    aTheTargetPrinc// "The target principal name is incorrect"
0xe0bd  stelem.ref
0xe0be  dup
0xe0bf  ldc.i4.s 0x1A
0xe0c1  ldstr    aTheRpcServerIs// "The RPC server is unavailable"
0xe0c6  stelem.ref
0xe0c7  dup
0xe0c8  ldc.i4.s 0x1B
0xe0ca  ldstr    aInternalNetFra// "Internal .Net Framework Data Provider e"...
0xe0cf  stelem.ref
0xe0d0  stsfld   string[] Microsoft.Crm.Extensibility.Retry.Policy.SqlExceptionRetryMapping::RetriableSqlErrorMessages
0xe0d5  ret
```
