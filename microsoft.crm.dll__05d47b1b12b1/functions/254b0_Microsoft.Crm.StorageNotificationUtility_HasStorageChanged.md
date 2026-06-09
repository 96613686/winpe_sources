# Microsoft.Crm.StorageNotificationUtility::HasStorageChanged

- ea: `0x254b0`
- end: `0x2558d`
- name: `Microsoft.Crm.StorageNotificationUtility::HasStorageChanged`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x252e0`

## callees

- `0x254b0`

## string_xrefs

- `0x25505`: `Org not found in organization table, assuming deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x254b0  ldc.i4.0
0x254b1  stloc.0
0x254b2  ldc.i4.0
0x254b3  stloc.1
0x254b4  ldnull
0x254b5  stloc.2
0x254b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x254bb  stloc.3
0x254bc  ldloc.3
0x254bd  ldstr    aOrganization// "Organization"
0x254c2  ldarg.0
0x254c3  box      [mscorlib]System.Guid
0x254c8  ldc.i4.2
0x254c9  newarr   [mscorlib]System.String
0x254ce  dup
0x254cf  ldc.i4.0
0x254d0  ldstr    aDatasizemb// "DataSizeMB"
0x254d5  stelem.ref
0x254d6  dup
0x254d7  ldc.i4.1
0x254d8  ldstr    aIndexsizemb// "IndexSizeMB"
0x254dd  stelem.ref
0x254de  ldc.i4   0x31B
0x254e3  ldstr    aHasstoragechan// "HasStorageChanged"
0x254e8  ldstr    aDA1SSrcSharedS_4// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x254ed  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x254f2  stloc.2
0x254f3  leave.s  loc_254FF
0x254f5  ldloc.3
0x254f6  brfalse.s loc_254FE
0x254f8  ldloc.3
0x254f9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x254fe  endfinally
0x254ff  ldloc.2
0x25500  brtrue.s loc_25517
0x25502  ldarg.0
0x25503  ldc.i4.s 0x14
0x25505  ldstr    aOrgNotFoundInO// "Org not found in organization table, as"...
0x2550a  ldc.i4.0
0x2550b  newarr   [mscorlib]System.Object
0x25510  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x25515  ldc.i4.0
0x25516  ret
0x25517  ldloc.2
0x25518  ldstr    aDatasizemb// "DataSizeMB"
0x2551d  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x25522  brfalse.s loc_25542
0x25524  ldloc.2
0x25525  ldstr    aDatasizemb// "DataSizeMB"
0x2552a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2552f  brfalse.s loc_25542
0x25531  ldloc.2
0x25532  ldstr    aDatasizemb// "DataSizeMB"
0x25537  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2553c  unbox.any [mscorlib]System.Int32
0x25541  stloc.0
0x25542  ldloc.2
0x25543  ldstr    aIndexsizemb// "IndexSizeMB"
0x25548  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x2554d  brfalse.s loc_2556D
0x2554f  ldloc.2
0x25550  ldstr    aIndexsizemb// "IndexSizeMB"
0x25555  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2555a  brfalse.s loc_2556D
0x2555c  ldloc.2
0x2555d  ldstr    aIndexsizemb// "IndexSizeMB"
0x25562  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x25567  unbox.any [mscorlib]System.Int32
0x2556c  stloc.1
0x2556d  ldloc.0
0x2556e  brfalse.s loc_25589
0x25570  ldloc.1
0x25571  brfalse.s loc_25589
0x25573  ldloc.0
0x25574  ldarg.1
0x25575  sub
0x25576  call     int32 [mscorlib]System.Math::Abs(int32)
0x2557b  ldc.i4.5
0x2557c  bgt.s    loc_25589
0x2557e  ldloc.1
0x2557f  ldarg.2
0x25580  sub
0x25581  call     int32 [mscorlib]System.Math::Abs(int32)
0x25586  ldc.i4.5
0x25587  ble.s    loc_2558B
0x25589  ldc.i4.1
0x2558a  ret
0x2558b  ldc.i4.0
0x2558c  ret
```
