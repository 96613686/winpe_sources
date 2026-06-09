# Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::ReadKeys

- ea: `0x780`
- end: `0x7d8`
- name: `Microsoft.Crm.Common.Application.WebServices.YammerConfigWebService::ReadKeys`
- size: `88`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180`

## string_xrefs

- `0x7c8`: `ReadKeys`
- `0x7cd`: `d:\dbs\sh\dccm2\1101_190851\cmd\72\src\Common\Application\WebServices\YammerConfigWebService.asmx.cs`

## pseudocode

```c

```

## disassembly

```asm
0x780  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x785  ldstr    aId// "Id"
0x78a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.ExternalKeyConstants::YammerApplication
0x78f  box      [mscorlib]System.Guid
0x794  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x799  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x79e  ldstr    aExternalkey// "ExternalKey"
0x7a3  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.ExternalKeyConstants::YammerApplication
0x7a8  box      [mscorlib]System.Guid
0x7ad  ldc.i4.2
0x7ae  newarr   [mscorlib]System.String
0x7b3  dup
0x7b4  ldc.i4.0
0x7b5  ldstr    aApplicationid// "ApplicationId"
0x7ba  stelem.ref
0x7bb  dup
0x7bc  ldc.i4.1
0x7bd  ldstr    aApplicationsec// "ApplicationSecret"
0x7c2  stelem.ref
0x7c3  ldc.i4   0x1AB
0x7c8  ldstr    aReadkeys// "ReadKeys"
0x7cd  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x7d2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x7d7  ret
```
