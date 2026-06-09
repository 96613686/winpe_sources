# Microsoft.Crm.Caching.ComplexControlLoader::LoadCacheData

- ea: `0x12bc0`
- end: `0x12c15`
- name: `Microsoft.Crm.Caching.ComplexControlLoader::LoadCacheData`
- size: `85`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x12ae0`
- `0x12b00`
- `0x12b10`
- `0x59710`
- `0x5be20`

## string_xrefs

- `0x12bc0`: `complexcontrol`
- `0x12bce`: `complexcontrolid`
- `0x12bea`: `complexcontrolid`
- `0x12bd6`: `complexcontrolxml`
- `0x12c00`: `complexcontrolxml`

## pseudocode

```c

```

## disassembly

```asm
0x12bc0  ldstr    aComplexcontrol_0// "complexcontrol"
0x12bc5  ldarg.1
0x12bc6  ldc.i4.2
0x12bc7  newarr   [mscorlib]System.String
0x12bcc  dup
0x12bcd  ldc.i4.0
0x12bce  ldstr    aComplexcontrol_1// "complexcontrolid"
0x12bd3  stelem.ref
0x12bd4  dup
0x12bd5  ldc.i4.1
0x12bd6  ldstr    aComplexcontrol_2// "complexcontrolxml"
0x12bdb  stelem.ref
0x12bdc  ldarg.2
0x12bdd  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x12be2  stloc.0
0x12be3  newobj   instance void Microsoft.Crm.Caching.ComplexControlData::.ctor()
0x12be8  dup
0x12be9  ldloc.0
0x12bea  ldstr    aComplexcontrol_1// "complexcontrolid"
0x12bef  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x12bf4  unbox.any [mscorlib]System.Guid
0x12bf9  callvirt instance void Microsoft.Crm.Caching.ComplexControlData::set_Id(valuetype [mscorlib]System.Guid value)
0x12bfe  dup
0x12bff  ldloc.0
0x12c00  ldstr    aComplexcontrol_2// "complexcontrolxml"
0x12c05  callvirt instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x12c0a  castclass [mscorlib]System.String
0x12c0f  callvirt instance void Microsoft.Crm.Caching.ComplexControlData::set_ComplexControlXml(string value)
0x12c14  ret
```
