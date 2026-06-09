# Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnectionString

- ea: `0x4a710`
- end: `0x4a808`
- name: `Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnectionString`
- size: `248`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4a700`
- `0x4dcc0`

## callees

- `0xa00`
- `0xde0`
- `0x1f80`
- `0x4640`
- `0x4c00`
- `0x4c40`
- `0x444f0`
- `0x4a650`
- `0x4a710`
- `0x4a840`
- `0x4a940`

## string_xrefs

- `0x4a792`: `GetSiteConfigDBConnectionString`
- `0x4a7b3`: `GetSiteConfigDBConnectionString`
- `0x4a797`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\Cache\StaticConfigCache.cs`
- `0x4a7b8`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\Cache\StaticConfigCache.cs`

## pseudocode

```c

```

## disassembly

```asm
0x4a710  ldsfld   string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::_overrideSiteConnectionString
0x4a715  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4a71a  brtrue.s loc_4A722
0x4a71c  ldsfld   string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::_overrideSiteConnectionString
0x4a721  ret
0x4a722  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x4a727  ldc.i4.2
0x4a728  beq.s    loc_4A737
0x4a72a  call     class Microsoft.Crm.ConfigurationDatabase.ConfigMetadataLoadOptions Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::get_LoadOptions()
0x4a72f  brtrue.s loc_4A737
0x4a731  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetGeoConfigDBConnectionString()
0x4a736  ret
0x4a737  ldarg.0
0x4a738  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4a73d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4a742  brfalse.s loc_4A760
0x4a744  call     string Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConnectionStringFromRegistry()
0x4a749  stloc.1
0x4a74a  ldloc.1
0x4a74b  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4a750  brtrue.s loc_4A754
0x4a752  ldloc.1
0x4a753  ret
0x4a754  call     class Microsoft.Crm.IDataCenterInfoProvider Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x4a759  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x4a75e  starg.s  0
0x4a760  ldnull
0x4a761  stloc.0
0x4a762  ldarg.0
0x4a763  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4a768  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4a76d  brfalse.s loc_4A7A4
0x4a76f  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4a774  ldstr    aDatacenter// "Datacenter"
0x4a779  ldarg.0
0x4a77a  box      [mscorlib]System.Guid
0x4a77f  ldc.i4.1
0x4a780  newarr   [mscorlib]System.String
0x4a785  dup
0x4a786  ldc.i4.0
0x4a787  ldstr    aSitewideconnec_0// "SiteWideConnectionString"
0x4a78c  stelem.ref
0x4a78d  ldc.i4   0xB5
0x4a792  ldstr    aGetsiteconfigd// "GetSiteConfigDBConnectionString"
0x4a797  ldstr    aDA1SSrcPlatfor_33// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4a79c  callvirt instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.LocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4a7a1  stloc.0
0x4a7a2  br.s     loc_4A7F7
0x4a7a4  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x4a7a9  ldstr    aDatacenter// "Datacenter"
0x4a7ae  ldc.i4   0xBE
0x4a7b3  ldstr    aGetsiteconfigd// "GetSiteConfigDBConnectionString"
0x4a7b8  ldstr    aDA1SSrcPlatfor_33// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x4a7bd  callvirt instance class Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.LocatorService::Retrieve(string tableName, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x4a7c2  stloc.2
0x4a7c3  ldloc.2
0x4a7c4  brfalse.s loc_4A7F7
0x4a7c6  ldloc.2
0x4a7c7  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class Microsoft.Crm.Data.PropertyBag>::get_Values()
0x4a7cc  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x4a7d1  stloc.3
0x4a7d2  br.s     loc_4A7DE
0x4a7d4  ldloca.s 3
0x4a7d6  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::get_Current()
0x4a7db  stloc.0
0x4a7dc  leave.s  loc_4A7F7
0x4a7de  ldloca.s 3
0x4a7e0  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x4a7e5  brtrue.s loc_4A7D4
0x4a7e7  leave.s  loc_4A7F7
0x4a7e9  ldloca.s 3
0x4a7eb  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class Microsoft.Crm.Data.PropertyBag>
0x4a7f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a7f6  endfinally
0x4a7f7  ldloc.0
0x4a7f8  ldstr    aSitewideconnec_0// "SiteWideConnectionString"
0x4a7fd  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x4a802  castclass [mscorlib]System.String
0x4a807  ret
```
