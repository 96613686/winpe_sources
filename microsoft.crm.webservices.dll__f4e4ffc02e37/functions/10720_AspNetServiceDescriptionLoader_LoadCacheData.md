# AspNetServiceDescriptionLoader::LoadCacheData

- ea: `0x10720`
- end: `0x10760`
- name: `AspNetServiceDescriptionLoader::LoadCacheData`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0xd650`
- `0xd660`

## string_xrefs

- `0x1074a`: `ServiceDescriptionReflector must return only 1 service description.`

## pseudocode

```c

```

## disassembly

```asm
0x10720  newobj   instance void [System.Web.Services]System.Web.Services.Description.ServiceDescriptionReflector::.ctor()
0x10725  dup
0x10726  ldarg.1
0x10727  callvirt instance string Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey::get_FullyQualifiedTypeName()
0x1072c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x10731  ldarg.1
0x10732  callvirt instance string Microsoft.Crm.WebServices.AspNetServiceDescriptionCacheKey::get_TargetUrl()
0x10737  callvirt instance void [System.Web.Services]System.Web.Services.Description.ServiceDescriptionReflector::Reflect(class [mscorlib]System.Type, string)
0x1073c  dup
0x1073d  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescriptionCollection [System.Web.Services]System.Web.Services.Description.ServiceDescriptionReflector::get_ServiceDescriptions()
0x10742  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x10747  ldc.i4.1
0x10748  ceq
0x1074a  ldstr    aServicedescrip_2// "ServiceDescriptionReflector must return"...
0x1074f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x10754  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescriptionCollection [System.Web.Services]System.Web.Services.Description.ServiceDescriptionReflector::get_ServiceDescriptions()
0x10759  ldc.i4.0
0x1075a  callvirt instance class [System.Web.Services]System.Web.Services.Description.ServiceDescription [System.Web.Services]System.Web.Services.Description.ServiceDescriptionCollection::get_Item(int32)
0x1075f  ret
```
