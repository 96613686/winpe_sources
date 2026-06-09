# Microsoft.Crm.Service.ObjectModel.IncidentService::CheckMaxChildAssosciationLimit

- ea: `0x1f30`
- end: `0x1fca`
- name: `Microsoft.Crm.Service.ObjectModel.IncidentService::CheckMaxChildAssosciationLimit`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xfb0`

## callees

- `0x1d10`
- `0x1f30`

## string_xrefs

- `0x1f4a`: `d:\dbs\sh\dccm2\1101_190851\cmd\5\src\Service\ObjectModel\Services\CS\IncidentService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1f30  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x1f35  ldarg.2
0x1f36  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1f3b  ldstr    aMaxchildincide// "MaxChildIncidentNumber"
0x1f40  ldc.i4   0x2ED
0x1f45  ldstr    aCheckmaxchilda// "CheckMaxChildAssosciationLimit"
0x1f4a  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x1f4f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x1f54  stloc.0
0x1f55  ldloc.0
0x1f56  brtrue.s loc_1F5B
0x1f58  ldc.i4.0
0x1f59  br.s     loc_1F61
0x1f5b  ldloc.0
0x1f5c  unbox.any [mscorlib]System.Int32
0x1f61  stloc.1
0x1f62  ldarg.1
0x1f63  ldstr    aParentcaseid// "parentcaseid"
0x1f68  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1f6d  unbox.any [mscorlib]System.Guid
0x1f72  ldarg.0
0x1f73  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x1f78  ldarg.2
0x1f79  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f7e  stloc.2
0x1f7f  ldarg.0
0x1f80  ldloc.2
0x1f81  ldarg.2
0x1f82  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Service.ObjectModel.IncidentService::RetrieveActiveChildRecords(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1f87  stloc.3
0x1f88  ldloc.1
0x1f89  ldloc.3
0x1f8a  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x1f8f  bgt.s    loc_1FC9
0x1f91  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1f96  ldstr    aAParentCaseCan_0// "A Parent Case cannot have more than {0}"...
0x1f9b  ldc.i4.1
0x1f9c  newarr   [mscorlib]System.Object
0x1fa1  dup
0x1fa2  ldc.i4.0
0x1fa3  ldloc.1
0x1fa4  box      [mscorlib]System.Int32
0x1fa9  stelem.ref
0x1faa  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1faf  ldc.i4   0x8003F454
0x1fb4  ldc.i4.1
0x1fb5  newarr   [mscorlib]System.Object
0x1fba  dup
0x1fbb  ldc.i4.0
0x1fbc  ldloc.1
0x1fbd  box      [mscorlib]System.Int32
0x1fc2  stelem.ref
0x1fc3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32, object[])
0x1fc8  throw
0x1fc9  ret
```
