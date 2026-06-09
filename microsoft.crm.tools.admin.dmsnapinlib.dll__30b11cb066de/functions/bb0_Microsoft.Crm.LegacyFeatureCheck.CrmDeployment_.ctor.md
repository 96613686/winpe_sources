# Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::.ctor

- ea: `0xbb0`
- end: `0xbfc`
- name: `Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::.ctor`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x590`

## callees

- `0xbb0`
- `0xe30`

## string_xrefs

- `0xbd1`: `Could not find connection information for MSCRM_CONFIG. Please provide Database Server name using "/s" parameter`
- `0xbe2`: `Data Source={0};Initial Catalog=MSCRM_CONFIG;Integrated Security=SSPI;Connect Timeout=90`

## pseudocode

```c

```

## disassembly

```asm
0xbb0  ldarg.0
0xbb1  call     instance void [mscorlib]System.Object::.ctor()
0xbb6  ldarg.0
0xbb7  call     instance void Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::TryFindConnectionStringFromRegistry()
0xbbc  ldarg.0
0xbbd  ldfld    string Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::_connectionString
0xbc2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xbc7  brfalse.s loc_BFB
0xbc9  ldarg.1
0xbca  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xbcf  brfalse.s loc_BDC
0xbd1  ldstr    aCouldNotFindCo// "Could not find connection information f"...
0xbd6  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0xbdb  throw
0xbdc  ldarg.0
0xbdd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbe2  ldstr    aDataSource0Ini// "Data Source={0};Initial Catalog=MSCRM_C"...
0xbe7  ldc.i4.1
0xbe8  newarr   [mscorlib]System.Object
0xbed  dup
0xbee  ldc.i4.0
0xbef  ldarg.1
0xbf0  stelem.ref
0xbf1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xbf6  stfld    string Microsoft.Crm.LegacyFeatureCheck.CrmDeployment::_connectionString
0xbfb  ret
```
