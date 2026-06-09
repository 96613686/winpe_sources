# Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::IsSystemOptedIntoMicrosoftUpdate

- ea: `0x120f0`
- end: `0x12155`
- name: `Microsoft.Crm.Setup.Common.Utility.UnmanagedSetupMethods::IsSystemOptedIntoMicrosoftUpdate`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5d0`
- `0x9ed0`

## callees

- `0x120f0`
- `0x121f0`
- `0x12210`
- `0x12230`

## string_xrefs

- `0x12104`: `SERVER.MSI`
- `0x12111`: `CLIENT.MSI`
- `0x1211e`: `SRSDATACONNECTOR.MSI`
- `0x1212b`: `EMAILROUTER.MSI`

## pseudocode

```c

```

## disassembly

```asm
0x120f0  ldarg.0
0x120f1  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::.ctor(class [mscorlib]System.Collections.IDictionary)
0x120f6  ldc.i4.0
0x120f7  stloc.0
0x120f8  callvirt instance string [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.InstallInfo::get_PackageName()
0x120fd  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x12102  stloc.1
0x12103  ldloc.1
0x12104  ldstr    aServerMsi// "SERVER.MSI"
0x12109  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1210e  brtrue.s loc_12139
0x12110  ldloc.1
0x12111  ldstr    aClientMsi// "CLIENT.MSI"
0x12116  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1211b  brtrue.s loc_12141
0x1211d  ldloc.1
0x1211e  ldstr    aSrsdataconnect// "SRSDATACONNECTOR.MSI"
0x12123  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12128  brtrue.s loc_12145
0x1212a  ldloc.1
0x1212b  ldstr    aEmailrouterMsi// "EMAILROUTER.MSI"
0x12130  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12135  brtrue.s loc_1214D
0x12137  br.s     loc_12153
0x12139  call     bool Microsoft.Crm.Setup.Common.Utility.NativeMethods::Srv_IsSystemOptedInToMicrosoftUpdate()
0x1213e  stloc.0
0x1213f  br.s     loc_12153
0x12141  ldc.i4.1
0x12142  stloc.0
0x12143  br.s     loc_12153
0x12145  call     bool Microsoft.Crm.Setup.Common.Utility.NativeMethods::Srs_IsSystemOptedInToMicrosoftUpdate()
0x1214a  stloc.0
0x1214b  br.s     loc_12153
0x1214d  call     bool Microsoft.Crm.Setup.Common.Utility.NativeMethods::Exch_IsSystemOptedInToMicrosoftUpdate()
0x12152  stloc.0
0x12153  ldloc.0
0x12154  ret
```
