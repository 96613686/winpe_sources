# Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounterName

- ea: `0x3f160`
- end: `0x3f1b4`
- name: `Microsoft.Crm.Performance.WebServicePerformanceCountersFactory::GetCounterName`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3f030`

## callees

- `0x1b4d0`
- `0x3f160`

## string_xrefs

- `0x3f178`: `Organization Service`
- `0x3f17e`: `Organization Service Metadata`
- `0x3f184`: `Discovery Service`
- `0x3f18a`: `Internal Organization Service`
- `0x3f195`: `Invalid value '{0}' for WebServiceType.`

## pseudocode

```c

```

## disassembly

```asm
0x3f160  ldarg.0
0x3f161  switch   loc_3F178, loc_3F17E, loc_3F184, loc_3F18A
0x3f176  br.s     loc_3F190
0x3f178  ldstr    aOrganizationSe// "Organization Service"
0x3f17d  ret
0x3f17e  ldstr    aOrganizationSe_0// "Organization Service Metadata"
0x3f183  ret
0x3f184  ldstr    aDiscoveryServi// "Discovery Service"
0x3f189  ret
0x3f18a  ldstr    aInternalOrgani// "Internal Organization Service"
0x3f18f  ret
0x3f190  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3f195  ldstr    aInvalidValue0F// "Invalid value '{0}' for WebServiceType."
0x3f19a  ldc.i4.1
0x3f19b  newarr   [mscorlib]System.Object
0x3f1a0  dup
0x3f1a1  ldc.i4.0
0x3f1a2  ldarg.0
0x3f1a3  box      [mscorlib]System.Int32
0x3f1a8  stelem.ref
0x3f1a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3f1ae  newobj   instance void Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string message)
0x3f1b3  throw
```
