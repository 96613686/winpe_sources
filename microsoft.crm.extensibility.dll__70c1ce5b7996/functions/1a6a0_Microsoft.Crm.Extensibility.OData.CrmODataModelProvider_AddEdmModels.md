# Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::AddEdmModels

- ea: `0x1a6a0`
- end: `0x1a70c`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::AddEdmModels`
- size: `108`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a480`

## callees

- `0x1a670`
- `0x1a6a0`

## string_xrefs

- `0x1a6c9`: `http://vocabularies.odata.org/OData.Community.Display.V1.xml`

## pseudocode

```c

```

## disassembly

```asm
0x1a6a0  ldtoken  [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility
0x1a6a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1a6aa  call     class [mscorlib]System.Array [mscorlib]System.Enum::GetValues(class [mscorlib]System.Type)
0x1a6af  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Array::GetEnumerator()
0x1a6b4  stloc.0
0x1a6b5  br.s     loc_1A6ED
0x1a6b7  ldloc.0
0x1a6b8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1a6bd  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility
0x1a6c2  stloc.1
0x1a6c3  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmModel::.ctor()
0x1a6c8  stloc.2
0x1a6c9  ldstr    aHttpVocabulari_0// "http://vocabularies.odata.org/OData.Com"...
0x1a6ce  newobj   instance void [System]System.Uri::.ctor(string)
0x1a6d3  call     class [System.Xml]System.Xml.XmlReader Microsoft.Crm.Extensibility.OData.CrmODataModelProvider::GetReferencedModelReader(class [System]System.Uri uri)
0x1a6d8  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel [Microsoft.OData.Edm]Microsoft.OData.Edm.Csdl.CsdlReader::Parse(class [System.Xml]System.Xml.XmlReader)
0x1a6dd  stloc.3
0x1a6de  ldloc.2
0x1a6df  ldloc.3
0x1a6e0  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmModel::AddReferencedModel(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel)
0x1a6e5  ldarg.0
0x1a6e6  ldloc.1
0x1a6e7  ldloc.2
0x1a6e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ModelVisibility, class [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmModel>::Add(var<u1>, !!T0)
0x1a6ed  ldloc.0
0x1a6ee  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1a6f3  brtrue.s loc_1A6B7
0x1a6f5  leave.s  loc_1A70B
0x1a6f7  ldloc.0
0x1a6f8  isinst   [mscorlib]System.IDisposable
0x1a6fd  stloc.s  4
0x1a6ff  ldloc.s  4
0x1a701  brfalse.s loc_1A70A
0x1a703  ldloc.s  4
0x1a705  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1a70a  endfinally
0x1a70b  ret
```
