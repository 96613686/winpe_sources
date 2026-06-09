# Microsoft.Crm.Extensibility.CrmODataCollectionSerializer::WriteObject

- ea: `0x31b0`
- end: `0x3220`
- name: `Microsoft.Crm.Extensibility.CrmODataCollectionSerializer::WriteObject`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x31b4`: `message Writer null`
- `0x31c3`: `write Context null`
- `0x31e1`: `write Context Path EdmType should be EdmCollectionType`

## pseudocode

```c

```

## disassembly

```asm
0x31b0  ldarg.3
0x31b1  ldnull
0x31b2  cgt.un
0x31b4  ldstr    aMessageWriterN// "message Writer null"
0x31b9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x31be  ldarg.s  4
0x31c0  ldnull
0x31c1  cgt.un
0x31c3  ldstr    aWriteContextNu// "write Context null"
0x31c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x31cd  ldarg.s  4
0x31cf  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Path()
0x31d4  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.Routing.ODataPath::get_EdmType()
0x31d9  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x31de  ldnull
0x31df  cgt.un
0x31e1  ldstr    aWriteContextPa// "write Context Path EdmType should be Ed"...
0x31e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x31eb  ldarg.s  4
0x31ed  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext::get_Path()
0x31f2  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmType [System.Web.OData]System.Web.OData.Routing.ODataPath::get_EdmType()
0x31f7  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionType
0x31fc  newobj   instance void [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmCollectionTypeReference::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionType)
0x3201  stloc.0
0x3202  ldloc.0
0x3203  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.ExtensionMethods::ElementType(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference)
0x3208  stloc.1
0x3209  ldarg.0
0x320a  ldarg.3
0x320b  ldloc.1
0x320c  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataCollectionWriter [Microsoft.OData.Core]Microsoft.OData.ODataMessageWriter::CreateODataCollectionWriter(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x3211  ldarg.1
0x3212  ldloc.0
0x3213  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmCollectionTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x3218  ldarg.s  4
0x321a  call     instance void [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataCollectionSerializer::WriteCollection(class [Microsoft.OData.Core]Microsoft.OData.ODataCollectionWriter, object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Serialization.ODataSerializerContext)
0x321f  ret
```
