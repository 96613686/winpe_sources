# Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::OptSystemIntoMicrosoftUpdate

- ea: `0x12160`
- end: `0x121c7`
- name: `Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::OptSystemIntoMicrosoftUpdate`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5d0`

## callees

- `0x12160`
- `0x12200`
- `0x12220`
- `0x12240`

## string_xrefs

- `0x12175`: `SERVER.MSI`
- `0x12182`: `CLIENT.MSI`
- `0x1218f`: `SRSDATACONNECTOR.MSI`
- `0x1219c`: `EMAILROUTER.MSI`

## pseudocode

```c

```

## disassembly

```asm
0x12160  ldarg.0
0x12161  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x12166  ldc.i4.m1
0x12167  conv.i8
0x12168  stloc.0
0x12169  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_PackageName()
0x1216e  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x12173  stloc.1
0x12174  ldloc.1
0x12175  ldstr    aServerMsi// "SERVER.MSI"
0x1217a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1217f  brtrue.s loc_121AA
0x12181  ldloc.1
0x12182  ldstr    aClientMsi// "CLIENT.MSI"
0x12187  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1218c  brtrue.s loc_121B2
0x1218e  ldloc.1
0x1218f  ldstr    aSrsdataconnect// "SRSDATACONNECTOR.MSI"
0x12194  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12199  brtrue.s loc_121B7
0x1219b  ldloc.1
0x1219c  ldstr    aEmailrouterMsi// "EMAILROUTER.MSI"
0x121a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x121a6  brtrue.s loc_121BF
0x121a8  br.s     loc_121C5
0x121aa  call     int64 Microsoft.Crm.Setup.Common.Utility.NativeMethods::Srv_OptSystemInToMicrosoftUpdate()
0x121af  stloc.0
0x121b0  br.s     loc_121C5
0x121b2  ldc.i4.0
0x121b3  conv.i8
0x121b4  stloc.0
0x121b5  br.s     loc_121C5
0x121b7  call     int64 Microsoft.Crm.Setup.Common.Utility.NativeMethods::Srs_OptSystemInToMicrosoftUpdate()
0x121bc  stloc.0
0x121bd  br.s     loc_121C5
0x121bf  call     int64 Microsoft.Crm.Setup.Common.Utility.NativeMethods::Exch_OptSystemInToMicrosoftUpdate()
0x121c4  stloc.0
0x121c5  ldloc.0
0x121c6  ret
```
