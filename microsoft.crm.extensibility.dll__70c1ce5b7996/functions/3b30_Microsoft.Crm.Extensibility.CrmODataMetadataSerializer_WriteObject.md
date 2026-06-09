# Microsoft.Crm.Extensibility.CrmODataMetadataSerializer::WriteObject

- ea: `0x3b30`
- end: `0x3be2`
- name: `Microsoft.Crm.Extensibility.CrmODataMetadataSerializer::WriteObject`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3b30`

## string_xrefs

- `0x3b53`: `http://vocabularies.odata.org/OData.Community.Keys.V1.xml`
- `0x3b69`: `OData.Community.Keys.V1`
- `0x3b79`: `OData.Community.Keys.V1`
- `0x3b8a`: `http://vocabularies.odata.org/OData.Community.Display.V1.xml`
- `0x3ba0`: `OData.Community.Display.V1`
- `0x3bb0`: `OData.Community.Display.V1`

## pseudocode

```c

```

## disassembly

```asm
0x3b30  ldarg.1
0x3b31  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel
0x3b36  stloc.0
0x3b37  ldloc.0
0x3b38  brfalse  loc_3BE1
0x3b3d  ldloc.0
0x3b3e  ldstr    aMicrosoftDynam_0// "Microsoft.Dynamics.CRM"
0x3b43  ldstr    aMscrm// "mscrm"
0x3b48  call     void [Microsoft.OData.Edm]Microsoft.OData.Edm.Csdl.SerializationExtensionMethods::SetNamespaceAlias(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, string, string)
0x3b4d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmReference>::.ctor()
0x3b52  stloc.1
0x3b53  ldstr    aHttpVocabulari// "http://vocabularies.odata.org/OData.Com"...
0x3b58  newobj   instance void [System]System.Uri::.ctor(string)
0x3b5d  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::.ctor(class [System]System.Uri)
0x3b62  stloc.2
0x3b63  ldloc.2
0x3b64  ldstr    aKeys// "Keys"
0x3b69  ldstr    aOdataCommunity_0// "OData.Community.Keys.V1"
0x3b6e  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmInclude::.ctor(string, string)
0x3b73  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::AddInclude(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmInclude)
0x3b78  ldloc.2
0x3b79  ldstr    aOdataCommunity_0// "OData.Community.Keys.V1"
0x3b7e  ldnull
0x3b7f  ldnull
0x3b80  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmIncludeAnnotations::.ctor(string, string, string)
0x3b85  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::AddIncludeAnnotations(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmIncludeAnnotations)
0x3b8a  ldstr    aHttpVocabulari_0// "http://vocabularies.odata.org/OData.Com"...
0x3b8f  newobj   instance void [System]System.Uri::.ctor(string)
0x3b94  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::.ctor(class [System]System.Uri)
0x3b99  stloc.3
0x3b9a  ldloc.3
0x3b9b  ldstr    aDisplay// "Display"
0x3ba0  ldstr    aOdataCommunity_1// "OData.Community.Display.V1"
0x3ba5  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmInclude::.ctor(string, string)
0x3baa  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::AddInclude(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmInclude)
0x3baf  ldloc.3
0x3bb0  ldstr    aOdataCommunity_1// "OData.Community.Display.V1"
0x3bb5  ldnull
0x3bb6  ldnull
0x3bb7  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmIncludeAnnotations::.ctor(string, string, string)
0x3bbc  callvirt instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmReference::AddIncludeAnnotations(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmIncludeAnnotations)
0x3bc1  ldloc.1
0x3bc2  ldloc.2
0x3bc3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmReference>::Add(var<u1>)
0x3bc8  ldloc.1
0x3bc9  ldloc.3
0x3bca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmReference>::Add(var<u1>)
0x3bcf  ldloc.0
0x3bd0  ldloc.1
0x3bd1  call     void [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::SetEdmReferences(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmModel, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmReference>)
0x3bd6  ldarg.0
0x3bd7  ldloc.0
0x3bd8  ldarg.2
0x3bd9  ldarg.3
0x3bda  ldarg.s  4
0x3bdc  call     instance void [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataMetadataSerializer::WriteObject(object, class [mscorlib]System.Type, class [Microsoft.OData.Core]Microsoft.OData.ODataMessageWriter, class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext)
0x3be1  ret
```
