# Microsoft.Crm.OfflineWatcher::GetRCOfflineValue

- ea: `0x21860`
- end: `0x218e3`
- name: `Microsoft.Crm.OfflineWatcher::GetRCOfflineValue`
- size: `131`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x217f0`
- `0x218f0`

## callees

- `0x21860`

## string_xrefs

- `0x2187d`: `Unable to Open Hive: {0}`
- `0x218bd`: `Unable to Read RCOffline registry value`

## pseudocode

```c

```

## disassembly

```asm
0x21860  ldnull
0x21861  stloc.0
0x21862  call     class [mscorlib]Microsoft.Win32.RegistryKey [Microsoft.Crm.Core]Microsoft.Crm.RegControl::GetCrmTargetKeyHive()
0x21867  ldsfld   string Microsoft.Crm.OfflineWatcher::hiveToMonitor
0x2186c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x21871  stloc.0
0x21872  ldloc.0
0x21873  brtrue.s loc_21899
0x21875  ldnull
0x21876  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2187b  ldc.i4.s 0x14
0x2187d  ldstr    aUnableToOpenHi// "Unable to Open Hive: {0}"
0x21882  ldc.i4.1
0x21883  newarr   [mscorlib]System.Object
0x21888  dup
0x21889  ldc.i4.0
0x2188a  ldsfld   string Microsoft.Crm.OfflineWatcher::hiveToMonitor
0x2188f  stelem.ref
0x21890  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21895  ldc.i4.m1
0x21896  stloc.2
0x21897  leave.s  loc_218E1
0x21899  ldloc.0
0x2189a  ldstr    aRcoffline// "RCOffline"
0x2189f  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x218a4  stloc.1
0x218a5  ldloc.1
0x218a6  brtrue.s loc_218CC
0x218a8  ldnull
0x218a9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x218ae  ldc.i4.s 0x14
0x218b0  ldstr    a0_0// "{0}"
0x218b5  ldc.i4.1
0x218b6  newarr   [mscorlib]System.Object
0x218bb  dup
0x218bc  ldc.i4.0
0x218bd  ldstr    aUnableToReadRc// "Unable to Read RCOffline registry value"
0x218c2  stelem.ref
0x218c3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x218c8  ldc.i4.m1
0x218c9  stloc.2
0x218ca  leave.s  loc_218E1
0x218cc  ldloc.1
0x218cd  unbox.any [mscorlib]System.Int32
0x218d2  stloc.2
0x218d3  leave.s  loc_218E1
0x218d5  ldloc.0
0x218d6  brfalse.s loc_218E0
0x218d8  ldloc.0
0x218d9  callvirt instance void [mscorlib]Microsoft.Win32.RegistryKey::Close()
0x218de  ldnull
0x218df  stloc.0
0x218e0  endfinally
0x218e1  ldloc.2
0x218e2  ret
```
