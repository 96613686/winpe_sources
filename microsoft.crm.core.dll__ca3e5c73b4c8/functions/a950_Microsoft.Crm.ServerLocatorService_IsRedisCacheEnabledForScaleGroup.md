# Microsoft.Crm.ServerLocatorService::IsRedisCacheEnabledForScaleGroup

- ea: `0xa950`
- end: `0xaa5b`
- name: `Microsoft.Crm.ServerLocatorService::IsRedisCacheEnabledForScaleGroup`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3100`
- `0x3120`
- `0x92c0`
- `0xa950`
- `0x1be90`
- `0x1f510`
- `0x444f0`
- `0x44670`

## string_xrefs

- `0xa9cd`: `IsRedisCacheEnabledForScaleGroup`
- `0xa9d2`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xa9c2`: `RedisCacheStatus`
- `0xa9e1`: `RedisCacheStatus`
- `0xaa03`: `RedisCacheStatus`
- `0xaa19`: `RedisCacheStatus`
- `0xa9f5`: `RedisCacheStatus return:{0}`

## pseudocode

```c

```

## disassembly

```asm
0xa950  ldarg.1
0xa951  ldstr    aScalegroupid// "scaleGroupId"
0xa956  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xa95b  ldc.i4.0
0xa95c  stloc.0
0xa95d  ldarg.0
0xa95e  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0xa963  ldc.i4.s 0x15
0xa965  ldc.i4.1
0xa966  newarr   [mscorlib]System.Object
0xa96b  dup
0xa96c  ldc.i4.0
0xa96d  ldarg.1
0xa96e  box      [mscorlib]System.Guid
0xa973  stelem.ref
0xa974  callvirt instance object Microsoft.Crm.ILocatorCache::LookupEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object[] keys)
0xa979  stloc.1
0xa97a  ldnull
0xa97b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa980  ldc.i4.s 0x14
0xa982  ldstr    aSg0Scalegroupr// "SG:{0} ScaleGroupRedisEnabledKey {1}"
0xa987  ldc.i4.2
0xa988  newarr   [mscorlib]System.Object
0xa98d  dup
0xa98e  ldc.i4.0
0xa98f  ldarg.1
0xa990  box      [mscorlib]System.Guid
0xa995  stelem.ref
0xa996  dup
0xa997  ldc.i4.1
0xa998  ldloc.1
0xa999  stelem.ref
0xa99a  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xa99f  ldloc.1
0xa9a0  brfalse.s loc_A9AE
0xa9a2  ldloc.1
0xa9a3  unbox.any [mscorlib]System.Boolean
0xa9a8  stloc.0
0xa9a9  br       loc_AA59
0xa9ae  ldarg.0
0xa9af  ldstr    aScalegroup// "ScaleGroup"
0xa9b4  ldarg.1
0xa9b5  box      [mscorlib]System.Guid
0xa9ba  ldc.i4.1
0xa9bb  newarr   [mscorlib]System.String
0xa9c0  dup
0xa9c1  ldc.i4.0
0xa9c2  ldstr    aRediscachestat// "RedisCacheStatus"
0xa9c7  stelem.ref
0xa9c8  ldc.i4   0xA37
0xa9cd  ldstr    aIsrediscacheen// "IsRedisCacheEnabledForScaleGroup"
0xa9d2  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xa9d7  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveById(string tableName, object primaryKey, string[] columns, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xa9dc  stloc.2
0xa9dd  ldloc.2
0xa9de  brfalse.s loc_AA37
0xa9e0  ldloc.2
0xa9e1  ldstr    aRediscachestat// "RedisCacheStatus"
0xa9e6  callvirt instance bool Microsoft.Crm.Data.PropertyBag::Contains(string propertyName)
0xa9eb  brfalse.s loc_AA37
0xa9ed  ldnull
0xa9ee  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa9f3  ldc.i4.s 0x14
0xa9f5  ldstr    aRediscachestat_0// "RedisCacheStatus return:{0}"
0xa9fa  ldc.i4.1
0xa9fb  newarr   [mscorlib]System.Object
0xaa00  dup
0xaa01  ldc.i4.0
0xaa02  ldloc.2
0xaa03  ldstr    aRediscachestat// "RedisCacheStatus"
0xaa08  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xaa0d  castclass [mscorlib]System.String
0xaa12  stelem.ref
0xaa13  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0xaa18  ldloc.2
0xaa19  ldstr    aRediscachestat// "RedisCacheStatus"
0xaa1e  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0xaa23  castclass [mscorlib]System.String
0xaa28  ldstr    aEnabled_0// "enabled"
0xaa2d  ldc.i4.1
0xaa2e  call     int32 [mscorlib]System.String::Compare(string, string, bool)
0xaa33  ldc.i4.0
0xaa34  ceq
0xaa36  stloc.0
0xaa37  ldarg.0
0xaa38  ldfld    class Microsoft.Crm.ILocatorCache Microsoft.Crm.ServerLocatorService::_cache
0xaa3d  ldc.i4.s 0x15
0xaa3f  ldarg.1
0xaa40  box      [mscorlib]System.Guid
0xaa45  ldc.i4.1
0xaa46  newarr   [mscorlib]System.Object
0xaa4b  dup
0xaa4c  ldc.i4.0
0xaa4d  ldloc.0
0xaa4e  box      [mscorlib]System.Boolean
0xaa53  stelem.ref
0xaa54  callvirt instance void Microsoft.Crm.ILocatorCache::AddEntry(valuetype Microsoft.Crm.LocatorKeyType keyType, object value, object[] keys)
0xaa59  ldloc.0
0xaa5a  ret
```
