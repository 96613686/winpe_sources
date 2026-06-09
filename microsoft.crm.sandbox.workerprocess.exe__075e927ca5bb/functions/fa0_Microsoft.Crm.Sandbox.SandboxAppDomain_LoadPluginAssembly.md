# Microsoft.Crm.Sandbox.SandboxAppDomain::LoadPluginAssembly

- ea: `0xfa0`
- end: `0x14d5`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::LoadPluginAssembly`
- size: `1333`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x3470`

## callees

- `0xfa0`
- `0x1520`
- `0x1750`
- `0x3a60`
- `0x3a80`
- `0x4820`

## string_xrefs

- `0xfce`: `{0}-{1}.dll`
- `0xfa8`: `SandboxAppDomain.LoadPluginAssembly`
- `0x103f`: `SandboxAppDomain.LoadPluginAssembly: existing helper: already has plugin assembly loaded`
- `0x105c`: `SandboxAppDomain.LoadPluginAssembly: no existing helper - read assembly file bytes`
- `0x1076`: `SandboxAppDomain.LoadPluginAssembly: Attempting to read assembly content at {0}`
- `0x10e6`: `SandboxAppDomain.LoadPluginAssembly: Failed to read all assembly bytes at {0}. Shutting down workerprocess.`
- `0x113c`: `SandboxAppDomain.LoadPluginAssembly: Failed to read assembly content at {0} due to exception {1}`
- `0x115f`: `SandboxAppDomain.LoadPluginAssembly: Expecting to always find assembly content. The drawbridge symbolic link might be broken. Shutting down worker process `
- `0x1192`: `SandboxAppDomain.LoadPluginAssembly: assembly short name: {0}`
- `0x11a9`: `CRM_Server_InstallDir`
- `0x11ef`: `SandboxAppDomain.LoadPluginAssembly: Trying to load assembly symbols path: {0}`
- `0x121b`: `SandboxAppDomain.LoadPluginAssembly: symbols file found`
- `0x128c`: `SandboxAppDomain.LoadPluginAssembly: Failed to read all assembly symbols bytes at {0}. Continuing without symbols`
- `0x12ae`: `SandboxAppDomain.LoadPluginAssembly: symbols file read OK`
- `0x1332`: `SandboxAppDomain.LoadPluginAssembly: EXCEPTION: failed to read symbols file: {0}`
- `0x135c`: `SandboxAppDomain.LoadPluginAssembly: no symbols file found`
- `0x1396`: `SandboxAppDomain.LoadPluginAssembly: Creating a new helper in Partial Trust App Domain`
- `0x13f2`: `SandboxAppDomain.LoadPluginAssembly: crashFile Name: {0}`
- `0x142c`: `SandboxAppDomain.LoadPluginAssembly: Call LoadPluginAssembly on new SandboxAppDomainHelper`
- `0x144e`: `SandboxAppDomain.LoadPluginAssembly: Return OK from LoadPluginAssembly on new SandboxAppDomainHelper`
- `0x146e`: `SandboxAppDomain.LoadPluginAssembly: new SandboxAppDomainHelper: VerifyPluginAssembly signature`
- `0x1492`: `SandboxAppDomain.LoadPluginAssembly: new SandboxAppDomainHelper: VerifyPluginAssembly signature done`
- `0x14b7`: `SandboxAppDomain.LoadPluginAssembly: new SandboxAppDomainHelper added to dictionary for the assemblyPath`

## pseudocode

```c

```

## disassembly

```asm
0xfa0  ldarg.0
0xfa1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0xfa6  ldc.i4.s 0x21
0xfa8  ldstr    aSandboxappdoma_0// "SandboxAppDomain.LoadPluginAssembly"
0xfad  ldc.i4.0
0xfae  newarr   [mscorlib]System.Object
0xfb3  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfb8  ldarg.3
0xfb9  ldstr    aAssemblyname// "assemblyName"
0xfbe  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0xfc3  ldarg.0
0xfc4  ldfld    string Microsoft.Crm.Sandbox.SandboxAppDomain::_pluginAssemblyBase
0xfc9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfce  ldstr    a01Dll// "{0}-{1}.dll"
0xfd3  ldc.i4.2
0xfd4  newarr   [mscorlib]System.Object
0xfd9  dup
0xfda  ldc.i4.0
0xfdb  ldarga.s 1
0xfdd  ldstr    aB// "B"
0xfe2  call     instance string [mscorlib]System.Guid::ToString(string)
0xfe7  stelem.ref
0xfe8  dup
0xfe9  ldc.i4.1
0xfea  ldarg.2
0xfeb  box      [mscorlib]System.Int32
0xff0  stelem.ref
0xff1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xff6  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xffb  stloc.0
0xffc  ldarg.0
0xffd  ldfld    class [System.Core]System.Threading.ReaderWriterLockSlim Microsoft.Crm.Sandbox.SandboxAppDomain::_helperLookUpLock
0x1002  ldc.i4.0
0x1003  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLockSlim::.ctor(class [System.Core]System.Threading.ReaderWriterLockSlim, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LockMode)
0x1008  stloc.2
0x1009  ldarg.0
0x100a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper> Microsoft.Crm.Sandbox.SandboxAppDomain::_helperLookUp
0x100f  ldloc.0
0x1010  ldloca.s 1
0x1012  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper>::TryGetValue(var<u1>, !!T0)
0x1017  pop
0x1018  leave.s  loc_1024
0x101a  ldloc.2
0x101b  brfalse.s loc_1023
0x101d  ldloc.2
0x101e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1023  endfinally
0x1024  ldloc.1
0x1025  brfalse.s loc_1054
0x1027  ldloc.1
0x1028  ldarg.s  4
0x102a  callvirt instance void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::set_TrackingId(valuetype [mscorlib]System.Guid)
0x102f  ldloc.1
0x1030  ldarg.s  5
0x1032  callvirt instance void [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper::set_Depth(int32)
0x1037  ldarg.0
0x1038  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x103d  ldc.i4.s 0x21
0x103f  ldstr    aSandboxappdoma_1// "SandboxAppDomain.LoadPluginAssembly: ex"...
0x1044  ldc.i4.0
0x1045  newarr   [mscorlib]System.Object
0x104a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x104f  br       loc_14D3
0x1054  ldarg.0
0x1055  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x105a  ldc.i4.s 0x21
0x105c  ldstr    aSandboxappdoma_2// "SandboxAppDomain.LoadPluginAssembly: no"...
0x1061  ldc.i4.0
0x1062  newarr   [mscorlib]System.Object
0x1067  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x106c  ldnull
0x106d  stloc.3
0x106e  ldarg.0
0x106f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x1074  ldc.i4.s 0x21
0x1076  ldstr    aSandboxappdoma_3// "SandboxAppDomain.LoadPluginAssembly: At"...
0x107b  ldc.i4.1
0x107c  newarr   [mscorlib]System.Object
0x1081  dup
0x1082  ldc.i4.0
0x1083  ldloc.0
0x1084  stelem.ref
0x1085  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x108a  ldloc.0
0x108b  ldc.i4.3
0x108c  ldc.i4.1
0x108d  ldc.i4.3
0x108e  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x1093  stloc.s  7
0x1095  ldloc.s  7
0x1097  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x109c  call     int32 [mscorlib]System.Convert::ToInt32(int64)
0x10a1  stloc.s  8
0x10a3  ldloc.s  8
0x10a5  newarr   [mscorlib]System.Byte
0x10aa  stloc.3
0x10ab  ldc.i4.0
0x10ac  stloc.s  9
0x10ae  br.s     loc_10D0
0x10b0  ldloc.s  7
0x10b2  ldloc.3
0x10b3  ldloc.s  9
0x10b5  ldloc.s  8
0x10b7  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x10bc  stloc.s  0xA
0x10be  ldloc.s  0xA
0x10c0  brfalse.s loc_10D5
0x10c2  ldloc.s  9
0x10c4  ldloc.s  0xA
0x10c6  add
0x10c7  stloc.s  9
0x10c9  ldloc.s  8
0x10cb  ldloc.s  0xA
0x10cd  sub
0x10ce  stloc.s  8
0x10d0  ldloc.s  8
0x10d2  ldc.i4.0
0x10d3  bgt.s    loc_10B0
0x10d5  ldloc.s  9
0x10d7  conv.i8
0x10d8  ldloc.s  7
0x10da  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x10df  beq.s    loc_1120
0x10e1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x10e6  ldstr    aSandboxappdoma_4// "SandboxAppDomain.LoadPluginAssembly: Fa"...
0x10eb  ldc.i4.1
0x10ec  newarr   [mscorlib]System.Object
0x10f1  dup
0x10f2  ldc.i4.0
0x10f3  ldloc.0
0x10f4  stelem.ref
0x10f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10fa  stloc.s  0xB
0x10fc  ldnull
0x10fd  ldarg.0
0x10fe  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x1103  ldc.i4.s 0x21
0x1105  ldloc.s  0xB
0x1107  ldc.i4.0
0x1108  newarr   [mscorlib]System.Object
0x110d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1112  ldc.i4.1
0x1113  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::set_ShutdownForMissingAssembly(bool value)
0x1118  ldloc.s  0xB
0x111a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x111f  throw
0x1120  leave.s  loc_112E
0x1122  ldloc.s  7
0x1124  brfalse.s loc_112D
0x1126  ldloc.s  7
0x1128  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x112d  endfinally
0x112e  leave.s  loc_1177
0x1130  stloc.s  0xC
0x1132  ldloc.s  0xC
0x1134  ldarg.0
0x1135  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x113a  ldc.i4.s 0x21
0x113c  ldstr    aSandboxappdoma_5// "SandboxAppDomain.LoadPluginAssembly: Fa"...
0x1141  ldc.i4.2
0x1142  newarr   [mscorlib]System.Object
0x1147  dup
0x1148  ldc.i4.0
0x1149  ldloc.0
0x114a  stelem.ref
0x114b  dup
0x114c  ldc.i4.1
0x114d  ldloc.s  0xC
0x114f  stelem.ref
0x1150  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1155  ldloc.s  0xC
0x1157  ldarg.0
0x1158  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x115d  ldc.i4.s 0x21
0x115f  ldstr    aSandboxappdoma_6// "SandboxAppDomain.LoadPluginAssembly: Ex"...
0x1164  ldc.i4.0
0x1165  newarr   [mscorlib]System.Object
0x116a  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x116f  ldc.i4.1
0x1170  call     void Microsoft.Crm.Sandbox.SandboxWorkerMain::set_ShutdownForMissingAssembly(bool value)
0x1175  rethrow
0x1177  ldarg.3
0x1178  ldc.i4.1
0x1179  newarr   [mscorlib]System.Char
0x117e  dup
0x117f  ldc.i4.0
0x1180  ldc.i4.s 0x2C
0x1182  stelem.i2
0x1183  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1188  stloc.s  4
0x118a  ldarg.0
0x118b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x1190  ldc.i4.s 0x21
0x1192  ldstr    aSandboxappdoma_7// "SandboxAppDomain.LoadPluginAssembly: as"...
0x1197  ldc.i4.1
0x1198  newarr   [mscorlib]System.Object
0x119d  dup
0x119e  ldc.i4.0
0x119f  ldloc.s  4
0x11a1  ldc.i4.0
0x11a2  ldelem.ref
0x11a3  stelem.ref
0x11a4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x11a9  ldstr    aCrmServerInsta// "CRM_Server_InstallDir"
0x11ae  ldc.i4.s 0xC
0x11b0  ldstr    aCMscrmRo_0// "C:\\MSCRM_RO"
0x11b5  call     T0x2B000007
0x11ba  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x11bf  castclass [mscorlib]System.String
0x11c4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11c9  ldstr    aServerBinAssem// "Server\\bin\\assembly\\{0}.pdb"
0x11ce  ldc.i4.1
0x11cf  newarr   [mscorlib]System.Object
0x11d4  dup
0x11d5  ldc.i4.0
0x11d6  ldloc.s  4
0x11d8  ldc.i4.0
0x11d9  ldelem.ref
0x11da  stelem.ref
0x11db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x11e0  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x11e5  stloc.s  5
0x11e7  ldarg.0
0x11e8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x11ed  ldc.i4.s 0x21
0x11ef  ldstr    aSandboxappdoma_8// "SandboxAppDomain.LoadPluginAssembly: Tr"...
0x11f4  ldc.i4.1
0x11f5  newarr   [mscorlib]System.Object
0x11fa  dup
0x11fb  ldc.i4.0
0x11fc  ldloc.s  5
0x11fe  stelem.ref
0x11ff  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1204  ldnull
0x1205  stloc.s  6
0x1207  ldloc.s  5
0x1209  call     bool [mscorlib]System.IO.File::Exists(string)
0x120e  brfalse  loc_1354
0x1213  ldarg.0
0x1214  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x1219  ldc.i4.s 0x21
0x121b  ldstr    aSandboxappdoma_9// "SandboxAppDomain.LoadPluginAssembly: sy"...
0x1220  ldc.i4.0
0x1221  newarr   [mscorlib]System.Object
0x1226  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x122b  ldloc.s  5
0x122d  ldc.i4.3
0x122e  ldc.i4.1
0x122f  ldc.i4.3
0x1230  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::Open(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess, valuetype [mscorlib]System.IO.FileShare)
0x1235  stloc.s  0xD
0x1237  ldloc.s  0xD
0x1239  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x123e  call     int32 [mscorlib]System.Convert::ToInt32(int64)
0x1243  stloc.s  0xE
0x1245  ldloc.s  0xE
0x1247  newarr   [mscorlib]System.Byte
0x124c  stloc.s  6
0x124e  ldc.i4.0
0x124f  stloc.s  0xF
0x1251  br.s     loc_1273
0x1253  ldloc.s  0xD
0x1255  ldloc.3
0x1256  ldloc.s  0xF
0x1258  ldloc.s  0xE
0x125a  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x125f  stloc.s  0x10
0x1261  ldloc.s  0x10
0x1263  brfalse.s loc_1278
0x1265  ldloc.s  0xF
0x1267  ldloc.s  0x10
0x1269  add
0x126a  stloc.s  0xF
0x126c  ldloc.s  0xE
0x126e  ldloc.s  0x10
0x1270  sub
0x1271  stloc.s  0xE
0x1273  ldloc.s  0xE
0x1275  ldc.i4.0
0x1276  bgt.s    loc_1253
0x1278  ldloc.s  0xF
0x127a  conv.i8
0x127b  ldloc.s  0xD
0x127d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1282  beq.s    loc_12A6
0x1284  ldarg.0
0x1285  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAppDomain::_organizationId
0x128a  ldc.i4.s 0x21
0x128c  ldstr    aSandboxappdoma_10// "SandboxAppDomain.LoadPluginAssembly: Fa"...
0x1291  ldc.i4.1
0x1292  newarr   [mscorlib]System.Object
0x1297  dup
0x1298  ldc.i4.0
0x1299  ldloc.s  5
0x129b  stelem.ref
0x129c  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x12a1  ldnull
0x12a2  stloc.s  6
0x12a4  br.s     loc_12BE
0x12a6  ldarg.0
  ... truncated ...
```
