# Microsoft.Crm.Asynchronous.JobDataAccess::GetNumJobsCurrentlyRunningPerServer

- ea: `0x36a0`
- end: `0x3725`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetNumJobsCurrentlyRunningPerServer`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2b30`

## callees

- `0x36a0`

## pseudocode

```c

```

## disassembly

```asm
0x36a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor()
0x36a5  stloc.0
0x36a6  ldarg.1
0x36a7  callvirt instance class [System.Data]System.Data.IDbCommand [System.Data]System.Data.IDbConnection::CreateCommand()
0x36ac  stloc.1
0x36ad  ldstr    aSelectTargetse// "SELECT TargetServer, Count(*) as curren"...
0x36b2  stloc.2
0x36b3  ldloc.1
0x36b4  ldloc.2
0x36b5  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x36ba  ldloc.1
0x36bb  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x36c0  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x36c5  ldstr    aLockedstate// "@lockedState"
0x36ca  ldc.i4.1
0x36cb  box      [mscorlib]System.Int32
0x36d0  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x36d5  pop
0x36d6  ldloc.1
0x36d7  callvirt instance class [System.Data]System.Data.IDataReader [System.Data]System.Data.IDbCommand::ExecuteReader()
0x36dc  stloc.3
0x36dd  br.s     loc_3705
0x36df  ldloc.0
0x36e0  ldloc.3
0x36e1  ldstr    aTargetserver// "TargetServer"
0x36e6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x36eb  castclass [mscorlib]System.String
0x36f0  ldloc.3
0x36f1  ldstr    aCurrentjobs// "currentJobs"
0x36f6  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x36fb  unbox.any [mscorlib]System.Int32
0x3700  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3705  ldloc.3
0x3706  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x370b  brtrue.s loc_36DF
0x370d  leave.s  loc_3723
0x370f  ldloc.3
0x3710  brfalse.s loc_3718
0x3712  ldloc.3
0x3713  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3718  endfinally
0x3719  ldloc.1
0x371a  brfalse.s loc_3722
0x371c  ldloc.1
0x371d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3722  endfinally
0x3723  ldloc.0
0x3724  ret
```
