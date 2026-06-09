# Microsoft.Crm.Asynchronous.SizeCollectorBase::WriteValueToOrganizationTable

- ea: `0xc050`
- end: `0xc088`
- name: `Microsoft.Crm.Asynchronous.SizeCollectorBase::WriteValueToOrganizationTable`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xbfe0`

## callees

- `0xc690`

## string_xrefs

- `0xc077`: `WriteValueToOrganizationTable`

## pseudocode

```c

```

## disassembly

```asm
0xc050  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc055  stloc.0
0xc056  ldloc.0
0xc057  ldarg.2
0xc058  ldarg.3
0xc059  box      [mscorlib]System.Int32
0xc05e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc063  ldarg.1
0xc064  ldstr    aOrganization// "Organization"
0xc069  ldarg.0
0xc06a  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.StatisticsSqmCollectorBase::get_OrganizationId()
0xc06f  box      [mscorlib]System.Guid
0xc074  ldloc.0
0xc075  ldc.i4.s 0x39
0xc077  ldstr    aWritevaluetoor// "WriteValueToOrganizationTable"
0xc07c  ldstr    aDDbsShDccm2110_15// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0xc081  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0xc086  pop
0xc087  ret
```
