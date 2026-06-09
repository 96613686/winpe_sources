# Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::RetrieveMultiple

- ea: `0x24fa0`
- end: `0x2504f`
- name: `Microsoft.Crm.Admin.AdminService.CrmUpdateHistoryService::RetrieveMultiple`
- size: `175`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x24fa0`

## string_xrefs

- `0x24fc2`: `UpdateHistory`
- `0x24fd3`: `D:\a\1\s\src\CrmLive\Admin\UpdateHistory\CrmUpdateHistoryService.cs`
- `0x24fa7`: `Retrieve multiple UpdateHistorys`
- `0x25031`: `Exception in retrieve multiple UpdateHistory {0}`

## pseudocode

```c

```

## disassembly

```asm
0x24fa0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x24fa5  ldc.i4.s 9
0x24fa7  ldstr    aRetrieveMultip_5// "Retrieve multiple UpdateHistorys"
0x24fac  ldc.i4.0
0x24fad  newarr   [mscorlib]System.Object
0x24fb2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x24fb7  ldnull
0x24fb8  stloc.0
0x24fb9  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x24fbe  stloc.1
0x24fbf  ldnull
0x24fc0  stloc.2
0x24fc1  ldloc.1
0x24fc2  ldstr    aUpdatehistory// "UpdateHistory"
0x24fc7  ldnull
0x24fc8  ldnull
0x24fc9  ldc.i4   0xC0
0x24fce  ldstr    aRetrievemultip// "RetrieveMultiple"
0x24fd3  ldstr    aDA1SSrcCrmlive_49// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Updat"...
0x24fd8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x24fdd  stloc.2
0x24fde  ldloc.2
0x24fdf  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x24fe4  brtrue.s loc_25013
0x24fe6  ldloc.2
0x24fe7  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class Microsoft.Crm.Admin.AdminService.UpdateHistoryData> <>c::<>9__5_0
0x24fec  dup
0x24fed  brtrue.s loc_25006
0x24fef  pop
0x24ff0  ldsfld   class <>c <>c::<>9
0x24ff5  ldftn    instance class Microsoft.Crm.Admin.AdminService.UpdateHistoryData <>c::<RetrieveMultiple>b__5_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> bag)
0x24ffb  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class Microsoft.Crm.Admin.AdminService.UpdateHistoryData>::.ctor(object, native int)
0x25000  dup
0x25001  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>, class Microsoft.Crm.Admin.AdminService.UpdateHistoryData> <>c::<>9__5_0
0x25006  call     T0x2B000097
0x2500b  call     T0x2B000098
0x25010  stloc.0
0x25011  br.s     loc_2501A
0x25013  ldc.i4.0
0x25014  newarr   Microsoft.Crm.Admin.AdminService.UpdateHistoryData
0x25019  stloc.0
0x2501a  ldloc.0
0x2501b  stloc.3
0x2501c  leave.s  loc_2504D
0x2501e  ldloc.1
0x2501f  brfalse.s loc_25027
0x25021  ldloc.1
0x25022  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25027  endfinally
0x25028  stloc.s  4
0x2502a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2502f  ldc.i4.s 9
0x25031  ldstr    aExceptionInRet_13// "Exception in retrieve multiple UpdateHi"...
0x25036  ldc.i4.1
0x25037  newarr   [mscorlib]System.Object
0x2503c  dup
0x2503d  ldc.i4.0
0x2503e  ldloc.s  4
0x25040  callvirt instance string [mscorlib]System.Exception::get_Message()
0x25045  stelem.ref
0x25046  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2504b  rethrow
0x2504d  ldloc.3
0x2504e  ret
```
