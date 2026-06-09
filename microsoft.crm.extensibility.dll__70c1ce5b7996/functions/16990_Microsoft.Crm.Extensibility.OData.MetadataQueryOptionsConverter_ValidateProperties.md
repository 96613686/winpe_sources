# Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateProperties

- ea: `0x16990`
- end: `0x16a05`
- name: `Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateProperties`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x15f30`
- `0x15f90`

## callees

- `0xf740`
- `0x10050`
- `0x16990`

## string_xrefs

- `0x169da`: ` as it is either write only or not valid`

## pseudocode

```c

```

## disassembly

```asm
0x16990  ldarg.1
0x16991  ldarg.2
0x16992  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType Microsoft.Crm.Extensibility.OData.EdmUtilities::GetEdmEntityType(string edmEntityName, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel edmModel)
0x16997  stloc.0
0x16998  ldarg.0
0x16999  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::GetEnumerator()
0x1699e  stloc.1
0x1699f  br.s     loc_169F0
0x169a1  ldloc.1
0x169a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x169a7  stloc.2
0x169a8  ldloc.0
0x169a9  ldloc.2
0x169aa  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion Microsoft.Crm.Extensibility.OData.ModelUtilities::GetModelVersion()
0x169af  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmEntityType::GetEdmProperty(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVersion)
0x169b4  stloc.3
0x169b5  ldloc.3
0x169b6  brfalse.s loc_169F0
0x169b8  ldloc.3
0x169b9  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmStructuralProperty
0x169be  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.CrmEdmStructuralProperty::GetCustomState()
0x169c3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataAttributeMetadata
0x169c8  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.XrmMetadataAttributeMetadata::get_IsWriteOnly()
0x169cd  brfalse.s loc_169F0
0x169cf  ldc.i4   0x190
0x169d4  ldstr    aCannotQueryOnT// "Cannot query on the Property "
0x169d9  ldloc.2
0x169da  ldstr    aAsItIsEitherWr// " as it is either write only or not vali"...
0x169df  call     string [mscorlib]System.String::Concat(string, string, string)
0x169e4  ldc.i4.0
0x169e5  newarr   [mscorlib]System.Object
0x169ea  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x169ef  throw
0x169f0  ldloc.1
0x169f1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x169f6  brtrue.s loc_169A1
0x169f8  leave.s  loc_16A04
0x169fa  ldloc.1
0x169fb  brfalse.s loc_16A03
0x169fd  ldloc.1
0x169fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16a03  endfinally
0x16a04  ret
```
