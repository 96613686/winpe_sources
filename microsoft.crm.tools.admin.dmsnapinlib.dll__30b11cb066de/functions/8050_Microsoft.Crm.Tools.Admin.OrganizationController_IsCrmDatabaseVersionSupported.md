# Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported

- ea: `0x8050`
- end: `0x8159`
- name: `Microsoft.Crm.Tools.Admin.OrganizationController::IsCrmDatabaseVersionSupported`
- size: `265`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x73d0`
- `0x7f00`
- `0xcb90`
- `0x15840`

## callees

- `0x8050`

## string_xrefs

- `0x805a`: `Database install.Xml path must be specified`

## pseudocode

```c

```

## disassembly

```asm
0x8050  ldarg.s  4
0x8052  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8057  ldc.i4.0
0x8058  ceq
0x805a  ldstr    aDatabaseInstal// "Database install.Xml path must be speci"...
0x805f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8064  ldc.i4.0
0x8065  stloc.0
0x8066  ldarg.0
0x8067  ldarg.1
0x8068  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.CrmServerUtility::GetCrmDatabaseVersion(string, string)
0x806d  stloc.1
0x806e  ldnull
0x806f  ldloc.1
0x8070  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x8075  brfalse.s loc_808D
0x8077  ldstr    aUnableToRetrie// "Unable to retrieve version from databas"...
0x807c  ldc.i4.1
0x807d  newarr   [mscorlib]System.Object
0x8082  dup
0x8083  ldc.i4.0
0x8084  ldarg.1
0x8085  stelem.ref
0x8086  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x808b  ldc.i4.0
0x808c  ret
0x808d  ldstr    aDatabase0Versi// "Database {0} version is {1}"
0x8092  ldc.i4.2
0x8093  newarr   [mscorlib]System.Object
0x8098  dup
0x8099  ldc.i4.0
0x809a  ldarg.1
0x809b  stelem.ref
0x809c  dup
0x809d  ldc.i4.1
0x809e  ldloc.1
0x809f  stelem.ref
0x80a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x80a5  ldarg.s  4
0x80a7  call     class [mscorlib]System.Version [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::GetLatestVersion(string)
0x80ac  ldloc.1
0x80ad  call     bool [mscorlib]System.Version::op_Equality(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x80b2  brfalse.s loc_80C8
0x80b4  ldstr    aDatabaseIsDire// "Database is directly importable into th"...
0x80b9  ldc.i4.0
0x80ba  newarr   [mscorlib]System.Object
0x80bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x80c4  ldc.i4.1
0x80c5  stloc.0
0x80c6  br.s     loc_8140
0x80c8  ldarga.s 2
0x80ca  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x80cf  brfalse.s loc_8104
0x80d1  ldarg.2
0x80d2  stloc.2
0x80d3  ldloc.1
0x80d4  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x80d9  stloc.3
0x80da  ldloca.s 2
0x80dc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x80e1  ldloc.3
0x80e2  beq.s    loc_80E7
0x80e4  ldc.i4.0
0x80e5  br.s     loc_80EE
0x80e7  ldloca.s 2
0x80e9  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x80ee  brfalse.s loc_8104
0x80f0  ldstr    aDatabaseIsSupp// "Database is supported for import into d"...
0x80f5  ldc.i4.0
0x80f6  newarr   [mscorlib]System.Object
0x80fb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x8100  ldc.i4.2
0x8101  stloc.0
0x8102  br.s     loc_8140
0x8104  ldarg.3
0x8105  brfalse.s loc_8140
0x8107  ldarg.0
0x8108  ldarg.1
0x8109  call     string [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.Helpers::GetConnectionString(string, string)
0x810e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDirectSqlConnection::.ctor(string)
0x8113  stloc.s  4
0x8115  ldarg.s  4
0x8117  ldloc.s  4
0x8119  call     bool [Microsoft.Crm.Setup.DatabaseInstaller]Microsoft.Crm.Setup.Database.DatabaseInstaller::IsValidForUpgrade(string, class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection)
0x811e  brfalse.s loc_8132
0x8120  ldstr    aDatabaseMayBeI// "Database may be imported into the deplo"...
0x8125  ldc.i4.0
0x8126  newarr   [mscorlib]System.Object
0x812b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x8130  ldc.i4.3
0x8131  stloc.0
0x8132  leave.s  loc_8140
0x8134  ldloc.s  4
0x8136  brfalse.s loc_813F
0x8138  ldloc.s  4
0x813a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x813f  endfinally
0x8140  ldloc.0
0x8141  brtrue.s loc_8157
0x8143  ldstr    aDatabase0Versi_0// "Database {0} version is not supported."
0x8148  ldc.i4.1
0x8149  newarr   [mscorlib]System.Object
0x814e  dup
0x814f  ldc.i4.0
0x8150  ldarg.1
0x8151  stelem.ref
0x8152  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarningFormat(string, object[])
0x8157  ldloc.0
0x8158  ret
```
