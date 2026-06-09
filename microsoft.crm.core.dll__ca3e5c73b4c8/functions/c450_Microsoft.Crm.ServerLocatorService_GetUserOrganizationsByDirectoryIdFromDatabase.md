# Microsoft.Crm.ServerLocatorService::GetUserOrganizationsByDirectoryIdFromDatabase

- ea: `0xc450`
- end: `0xc4df`
- name: `Microsoft.Crm.ServerLocatorService::GetUserOrganizationsByDirectoryIdFromDatabase`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc3f0`

## callees

- `0x94f0`
- `0xc450`
- `0x1be90`
- `0x44400`
- `0x44510`

## string_xrefs

- `0xc49a`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xc451`: `directoryId`
- `0xc462`: `DirectoryObjectId`
- `0xc495`: `GetUserOrganizationsByDirectoryIdFromDatabase`

## pseudocode

```c

```

## disassembly

```asm
0xc450  ldarg.1
0xc451  ldstr    aDirectoryid// "directoryId"
0xc456  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xc45b  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xc460  stloc.0
0xc461  ldloc.0
0xc462  ldstr    aDirectoryobjec// "DirectoryObjectId"
0xc467  ldarg.1
0xc468  box      [mscorlib]System.Guid
0xc46d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xc472  ldarg.0
0xc473  ldstr    aSystemuserorga// "SystemUserOrganizations"
0xc478  ldc.i4.1
0xc479  newarr   [mscorlib]System.String
0xc47e  dup
0xc47f  ldc.i4.0
0xc480  ldstr    aOrganizationid_1// "OrganizationId"
0xc485  stelem.ref
0xc486  ldc.i4.1
0xc487  newarr   Microsoft.Crm.Data.PropertyBag
0xc48c  dup
0xc48d  ldc.i4.0
0xc48e  ldloc.0
0xc48f  stelem.ref
0xc490  ldc.i4   0xE55
0xc495  ldstr    aGetuserorganiz_1// "GetUserOrganizationsByDirectoryIdFromDa"...
0xc49a  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xc49f  call     instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.ServerLocatorService::Retrieve(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag[] conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xc4a4  stloc.1
0xc4a5  ldloc.1
0xc4a6  brtrue.s loc_C4AF
0xc4a8  ldc.i4.0
0xc4a9  newarr   [mscorlib]System.Guid
0xc4ae  ret
0xc4af  ldloc.1
0xc4b0  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0xc4b5  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__168_0
0xc4ba  dup
0xc4bb  brtrue.s loc_C4D4
0xc4bd  pop
0xc4be  ldsfld   class <>c <>c::<>9
0xc4c3  ldftn    instance valuetype [mscorlib]System.Guid <>c::<GetUserOrganizationsByDirectoryIdFromDatabase>b__168_0(class Microsoft.Crm.Data.PropertyBag x)
0xc4c9  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0xc4ce  dup
0xc4cf  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__168_0
0xc4d4  call     T0x2B000032
0xc4d9  call     T0x2B000033
0xc4de  ret
```
