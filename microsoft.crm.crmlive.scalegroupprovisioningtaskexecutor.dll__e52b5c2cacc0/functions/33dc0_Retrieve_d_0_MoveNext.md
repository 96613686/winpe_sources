# <Retrieve>d__0::MoveNext

- ea: `0x33dc0`
- end: `0x33ebd`
- name: `<Retrieve>d__0::MoveNext`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x33d50`
- `0x33dc0`
- `0x33ec0`
- `0x33ee0`
- `0x33f00`

## string_xrefs

- `0x33e24`: `SELECT WindowsLiveID \n													FROM SystemUserBase \n													WHERE WindowsLiveID is not NULL \n													AND ((InviteStatusCode <> 4 AND AccessMode = 0) OR AccessMode = 4) \n													AND WindowsLiveId not in \n														(SELECT WindowsLiveID \n														FROM systemuserbase \n														WHERE InviteStatusCode = 4 \n														AND WindowsLiveID is not NULL)`
- `0x33e3c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncUsersWithDO\OrganizationDisabledUsersRetriever.cs`

## pseudocode

```c

```

## disassembly

```asm
0x33dc0  ldarg.0
0x33dc1  ldfld    int32 <Retrieve>d__0::<>1__state
0x33dc6  stloc.1
0x33dc7  ldloc.1
0x33dc8  brfalse.s loc_33DD8
0x33dca  ldloc.1
0x33dcb  ldc.i4.1
0x33dcc  beq      loc_33E74
0x33dd1  ldc.i4.0
0x33dd2  stloc.0
0x33dd3  leave    loc_33EBB
0x33dd8  ldarg.0
0x33dd9  ldc.i4.m1
0x33dda  stfld    int32 <Retrieve>d__0::<>1__state
0x33ddf  ldarg.0
0x33de0  ldarg.0
0x33de1  ldfld    valuetype [mscorlib]System.Guid <Retrieve>d__0::organizationId
0x33de6  ldc.i4.0
0x33de7  ldc.i4.0
0x33de8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x33ded  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <Retrieve>d__0::<connection>5__3
0x33df2  ldarg.0
0x33df3  ldc.i4.s 0xFD
0x33df5  stfld    int32 <Retrieve>d__0::<>1__state
0x33dfa  ldarg.0
0x33dfb  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <Retrieve>d__0::<connection>5__3
0x33e00  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x33e05  ldarg.0
0x33e06  ldarg.0
0x33e07  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <Retrieve>d__0::<connection>5__3
0x33e0c  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand()
0x33e11  stfld    class [System.Data]System.Data.IDbCommand <Retrieve>d__0::<command>5__2
0x33e16  ldarg.0
0x33e17  ldc.i4.s 0xFC
0x33e19  stfld    int32 <Retrieve>d__0::<>1__state
0x33e1e  ldarg.0
0x33e1f  ldfld    class [System.Data]System.Data.IDbCommand <Retrieve>d__0::<command>5__2
0x33e24  ldstr    aSelectWindowsl// "SELECT WindowsLiveID \r\n\t\t\t\t\t\t\t"...
0x33e29  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x33e2e  ldarg.0
0x33e2f  ldarg.0
0x33e30  ldfld    class [System.Data]System.Data.IDbCommand <Retrieve>d__0::<command>5__2
0x33e35  ldc.i4.s 0x1F
0x33e37  ldstr    aRetrieve// "Retrieve"
0x33e3c  ldstr    aDDbsShDccm2110_46// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x33e41  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x33e46  stfld    class [System.Data]System.Data.IDataReader <Retrieve>d__0::<reader>5__1
0x33e4b  ldarg.0
0x33e4c  ldc.i4.s 0xFB
0x33e4e  stfld    int32 <Retrieve>d__0::<>1__state
0x33e53  br.s     loc_33E7C
0x33e55  ldarg.0
0x33e56  ldfld    class [System.Data]System.Data.IDataReader <Retrieve>d__0::<reader>5__1
0x33e5b  ldc.i4.0
0x33e5c  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x33e61  stloc.2
0x33e62  ldarg.0
0x33e63  ldloc.2
0x33e64  stfld    string <Retrieve>d__0::<>2__current
0x33e69  ldarg.0
0x33e6a  ldc.i4.1
0x33e6b  stfld    int32 <Retrieve>d__0::<>1__state
0x33e70  ldc.i4.1
0x33e71  stloc.0
0x33e72  leave.s  loc_33EBB
0x33e74  ldarg.0
0x33e75  ldc.i4.s 0xFB
0x33e77  stfld    int32 <Retrieve>d__0::<>1__state
0x33e7c  ldarg.0
0x33e7d  ldfld    class [System.Data]System.Data.IDataReader <Retrieve>d__0::<reader>5__1
0x33e82  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x33e87  brtrue.s loc_33E55
0x33e89  ldarg.0
0x33e8a  call     instance void <Retrieve>d__0::<>m__Finally3()
0x33e8f  ldarg.0
0x33e90  ldnull
0x33e91  stfld    class [System.Data]System.Data.IDataReader <Retrieve>d__0::<reader>5__1
0x33e96  ldarg.0
0x33e97  call     instance void <Retrieve>d__0::<>m__Finally2()
0x33e9c  ldarg.0
0x33e9d  ldnull
0x33e9e  stfld    class [System.Data]System.Data.IDbCommand <Retrieve>d__0::<command>5__2
0x33ea3  ldarg.0
0x33ea4  call     instance void <Retrieve>d__0::<>m__Finally1()
0x33ea9  ldarg.0
0x33eaa  ldnull
0x33eab  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection <Retrieve>d__0::<connection>5__3
0x33eb0  ldc.i4.0
0x33eb1  stloc.0
0x33eb2  leave.s  loc_33EBB
0x33eb4  ldarg.0
0x33eb5  call     instance void <Retrieve>d__0::System.IDisposable.Dispose()
0x33eba  endfinally
0x33ebb  ldloc.0
0x33ebc  ret
```
