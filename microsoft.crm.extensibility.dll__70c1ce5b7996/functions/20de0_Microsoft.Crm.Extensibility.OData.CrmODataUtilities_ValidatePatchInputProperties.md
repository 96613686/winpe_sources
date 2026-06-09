# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidatePatchInputProperties

- ea: `0x20de0`
- end: `0x20e84`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::ValidatePatchInputProperties`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11c90`

## callees

- `0xfba0`
- `0x19c80`
- `0x20de0`
- `0x24e60`

## string_xrefs

- `0x20e52`: `Property {0} cannot be updated to null. The reference property can only be deleted.`

## pseudocode

```c

```

## disassembly

```asm
0x20de0  ldarg.0
0x20de1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [System.Web.OData]System.Web.OData.Delta::GetChangedPropertyNames()
0x20de6  ldnull
0x20de7  stloc.0
0x20de8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x20ded  stloc.1
0x20dee  br.s     loc_20E6C
0x20df0  ldloc.1
0x20df1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x20df6  stloc.2
0x20df7  ldarg.0
0x20df8  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmStructuredType [System.Web.OData]System.Web.OData.EdmStructuredObject::get_ActualEdmType()
0x20dfd  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmEntityType
0x20e02  ldloc.2
0x20e03  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmStructuredType::FindProperty(string)
0x20e08  stloc.3
0x20e09  ldloc.3
0x20e0a  callvirt instance valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPropertyKind [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_PropertyKind()
0x20e0f  ldc.i4.1
0x20e10  bne.un.s loc_20E6C
0x20e12  ldloc.3
0x20e13  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Extensibility.OData.EdmUtilities::GetCrmAttributeMetadata(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty edmProperty)
0x20e18  stloc.s  4
0x20e1a  ldarg.0
0x20e1b  ldloc.2
0x20e1c  ldloca.s 0
0x20e1e  callvirt instance bool [System.Web.OData]System.Web.OData.Delta::TryGetPropertyValue(string, object&)
0x20e23  brfalse.s loc_20E6C
0x20e25  ldarg.1
0x20e26  callvirt instance class Microsoft.Crm.Extensibility.OData.CrmODataHeaders Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::get_Headers()
0x20e2b  callvirt instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_AutoDisassociate()
0x20e30  brtrue.s loc_20E6C
0x20e32  ldloc.s  4
0x20e34  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x20e39  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x20e3e  ldstr    aLookup// "lookup"
0x20e43  callvirt instance bool [mscorlib]System.String::Equals(string)
0x20e48  brfalse.s loc_20E6C
0x20e4a  ldloc.0
0x20e4b  brtrue.s loc_20E6C
0x20e4d  ldc.i4   0x190
0x20e52  ldstr    aProperty0Canno// "Property {0} cannot be updated to null."...
0x20e57  ldc.i4.1
0x20e58  newarr   [mscorlib]System.Object
0x20e5d  dup
0x20e5e  ldc.i4.0
0x20e5f  ldloc.3
0x20e60  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x20e65  stelem.ref
0x20e66  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x20e6b  throw
0x20e6c  ldloc.1
0x20e6d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20e72  brtrue   loc_20DF0
0x20e77  leave.s  loc_20E83
0x20e79  ldloc.1
0x20e7a  brfalse.s loc_20E82
0x20e7c  ldloc.1
0x20e7d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20e82  endfinally
0x20e83  ret
```
