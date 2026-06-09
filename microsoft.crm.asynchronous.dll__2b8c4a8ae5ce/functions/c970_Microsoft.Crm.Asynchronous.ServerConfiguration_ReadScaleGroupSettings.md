# Microsoft.Crm.Asynchronous.ServerConfiguration::ReadScaleGroupSettings

- ea: `0xc970`
- end: `0xc9c1`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::ReadScaleGroupSettings`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xc0e0`

## callees

- `0xc970`

## string_xrefs

- `0xc99b`: `ReadScaleGroupSettings`
- `0xc9a0`: `d:\dbs\sh\dccm2\1101_190851\cmd\13\src\Core\ObjectModel\Async\Shared\Configuration.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc970  ldarg.0
0xc971  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetSku()
0xc976  ldc.i4.2
0xc977  beq.s    loc_C97B
0xc979  ldarg.2
0xc97a  ret
0xc97b  ldarg.0
0xc97c  ldstr    aScalegroup// "ScaleGroup"
0xc981  ldarg.0
0xc982  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::GetScaleGroupId()
0xc987  box      [mscorlib]System.Guid
0xc98c  ldc.i4.1
0xc98d  newarr   [mscorlib]System.String
0xc992  dup
0xc993  ldc.i4.0
0xc994  ldarg.1
0xc995  stelem.ref
0xc996  ldc.i4   0x2AA
0xc99b  ldstr    aReadscalegroup// "ReadScaleGroupSettings"
0xc9a0  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\1"...
0xc9a5  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.ILocatorService::RetrieveById(string, object, string[], int32, string, string)
0xc9aa  stloc.0
0xc9ab  ldloc.0
0xc9ac  brfalse.s loc_C9BF
0xc9ae  ldloc.0
0xc9af  ldarg.1
0xc9b0  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xc9b5  brfalse.s loc_C9BF
0xc9b7  ldloc.0
0xc9b8  ldarg.1
0xc9b9  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xc9be  ret
0xc9bf  ldarg.2
0xc9c0  ret
```
