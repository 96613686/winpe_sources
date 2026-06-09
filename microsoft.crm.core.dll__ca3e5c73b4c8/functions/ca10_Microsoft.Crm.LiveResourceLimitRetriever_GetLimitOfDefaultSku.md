# Microsoft.Crm.LiveResourceLimitRetriever::GetLimitOfDefaultSku

- ea: `0xca10`
- end: `0xcae0`
- name: `Microsoft.Crm.LiveResourceLimitRetriever::GetLimitOfDefaultSku`
- size: `208`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xc600`

## callees

- `0x1840`
- `0x4640`
- `0x4c60`
- `0xca10`
- `0x44400`
- `0x444f0`
- `0x44510`

## string_xrefs

- `0xca46`: `ServiceComponentSku`
- `0xca53`: `ServiceComponentId`
- `0xca87`: `ServiceComponentId`
- `0xca8d`: `ServiceComponentId`
- `0xca64`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xcabf`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\ObjectModel\LiveResourceLimitRetriever.cs`
- `0xcaa1`: `ServiceComponentResourceLimits`

## pseudocode

```c

```

## disassembly

```asm
0xca10  call     class Microsoft.Crm.ISiteSettingsProvider Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xca15  ldstr    aDefaultsku// "DefaultSku"
0xca1a  ldc.i4.0
0xca1b  callvirt T0x2B000034
0xca20  stloc.0
0xca21  ldloc.0
0xca22  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xca27  brfalse.s loc_CA2F
0xca29  ldstr    aCrmotrial// "crmoTrial"
0xca2e  stloc.0
0xca2f  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xca34  stloc.1
0xca35  ldloc.1
0xca36  ldstr    aName// "Name"
0xca3b  ldloc.0
0xca3c  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xca41  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xca46  ldstr    aServicecompone// "ServiceComponentSku"
0xca4b  ldc.i4.1
0xca4c  newarr   [mscorlib]System.String
0xca51  dup
0xca52  ldc.i4.0
0xca53  ldstr    aServicecompone_0// "ServiceComponentId"
0xca58  stelem.ref
0xca59  ldloc.1
0xca5a  ldc.i4   0xBA
0xca5f  ldstr    aGetlimitofdefa// "GetLimitOfDefaultSku"
0xca64  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xca69  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xca6e  stloc.2
0xca6f  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xca74  stloc.1
0xca75  ldloc.1
0xca76  ldstr    aResourcetypeid// "ResourceTypeId"
0xca7b  ldarg.0
0xca7c  box      [mscorlib]System.Int32
0xca81  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xca86  ldloc.1
0xca87  ldstr    aServicecompone_0// "ServiceComponentId"
0xca8c  ldloc.2
0xca8d  ldstr    aServicecompone_0// "ServiceComponentId"
0xca92  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xca97  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xca9c  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0xcaa1  ldstr    aServicecompone_1// "ServiceComponentResourceLimits"
0xcaa6  ldc.i4.1
0xcaa7  newarr   [mscorlib]System.String
0xcaac  dup
0xcaad  ldc.i4.0
0xcaae  ldstr    aMaximum// "Maximum"
0xcab3  stelem.ref
0xcab4  ldloc.1
0xcab5  ldc.i4   0xBF
0xcaba  ldstr    aGetlimitofdefa// "GetLimitOfDefaultSku"
0xcabf  ldstr    aDA1SSrcPlatfor_2// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xcac4  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xcac9  ldstr    aMaximum// "Maximum"
0xcace  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xcad3  unbox.any [mscorlib]System.Int32
0xcad8  ldarg.1
0xcad9  add
0xcada  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0xcadf  ret
```
