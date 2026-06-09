# Microsoft.Crm.Extensibility.ODataV4.CrmODataActionPayloadDeserializer::Read

- ea: `0x27ef0`
- end: `0x28174`
- name: `Microsoft.Crm.Extensibility.ODataV4.CrmODataActionPayloadDeserializer::Read`
- size: `644`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x27ef0`
- `0x28180`
- `0x281e0`
- `0x340b0`

## string_xrefs

- `0x27f02`: `ArgumentNull readContext`
- `0x27ef4`: `ArgumentNull message reader`
- `0x27f15`: `ArgumentNull readContext.Path`
- `0x27f32`: `ArgumentNull readContext.Path.Segments==0`

## pseudocode

```c

```

## disassembly

```asm
0x27ef0  ldarg.1
0x27ef1  ldnull
0x27ef2  cgt.un
0x27ef4  ldstr    aArgumentnullMe// "ArgumentNull message reader"
0x27ef9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27efe  ldarg.3
0x27eff  ldnull
0x27f00  cgt.un
0x27f02  ldstr    aArgumentnullRe// "ArgumentNull readContext"
0x27f07  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27f0c  ldarg.3
0x27f0d  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Path()
0x27f12  ldnull
0x27f13  cgt.un
0x27f15  ldstr    aArgumentnullRe_0// "ArgumentNull readContext.Path"
0x27f1a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27f1f  ldarg.3
0x27f20  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Path()
0x27f25  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x27f2a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment>::get_Count()
0x27f2f  ldc.i4.0
0x27f30  cgt
0x27f32  ldstr    aArgumentnullRe_1// "ArgumentNull readContext.Path.Segments="...
0x27f37  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x27f3c  ldarg.3
0x27f3d  callvirt instance class [System.Web.OData]System.Web.OData.Routing.ODataPath [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext::get_Path()
0x27f42  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.OData.Core]Microsoft.OData.UriParser.ODataPathSegment> [System.Web.OData]System.Web.OData.Routing.ODataPath::get_Segments()
0x27f47  call     T0x2B0000EA
0x27f4c  stloc.0
0x27f4d  ldloc.0
0x27f4e  isinst   [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment
0x27f53  brtrue.s loc_27F67
0x27f55  ldloc.0
0x27f56  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegment
0x27f5b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperation> [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationSegment::get_Operations()
0x27f60  call     T0x2B000065
0x27f65  br.s     loc_27F7C
0x27f67  ldloc.0
0x27f68  castclass [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment
0x27f6d  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationImport> [Microsoft.OData.Core]Microsoft.OData.UriParser.OperationImportSegment::get_OperationImports()
0x27f72  call     T0x2B0000EB
0x27f77  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperation [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationImport::get_Operation()
0x27f7c  stloc.1
0x27f7d  ldarg.1
0x27f7e  ldloc.1
0x27f7f  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader [Microsoft.OData.Core]Microsoft.OData.ODataMessageReader::CreateODataParameterReader(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperation)
0x27f84  stloc.2
0x27f85  ldloc.1
0x27f86  castclass [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmAction
0x27f8b  newobj   instance void [System.Web.OData]System.Web.OData.ODataUntypedActionParameters::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmAction)
0x27f90  stloc.3
0x27f91  br       loc_28167
0x27f96  newobj   instance void <>c__DisplayClass1_0::.ctor()
0x27f9b  stloc.s  4
0x27f9d  ldloc.s  4
0x27f9f  ldloc.2
0x27fa0  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_Name()
0x27fa5  stfld    string <>c__DisplayClass1_0::parameterName
0x27faa  ldloc.1
0x27fab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter> [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperation::get_Parameters()
0x27fb0  ldloc.s  4
0x27fb2  ldftn    instance bool <>c__DisplayClass1_0::<Read>b__0(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter p)
0x27fb8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter, bool>::.ctor(object, native int)
0x27fbd  call     T0x2B0000EC
0x27fc2  stloc.s  5
0x27fc4  ldloc.2
0x27fc5  callvirt instance valuetype [Microsoft.OData.Core]Microsoft.OData.ODataParameterReaderState [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_State()
0x27fca  stloc.s  6
0x27fcc  ldloc.s  6
0x27fce  ldc.i4.1
0x27fcf  sub
0x27fd0  switch   loc_27FF2, loc_28094, loc_28167, loc_28167, loc_28117, loc_28130
0x27fed  br       loc_28167
0x27ff2  ldloc.s  5
0x27ff4  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x27ff9  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsPrimitive(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x27ffe  brfalse.s loc_28018
0x28000  ldloc.3
0x28001  ldloc.s  4
0x28003  ldfld    string <>c__DisplayClass1_0::parameterName
0x28008  ldloc.2
0x28009  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_Value()
0x2800e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28013  br       loc_28167
0x28018  ldloc.s  5
0x2801a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x2801f  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsEnum(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x28024  brfalse.s loc_2805D
0x28026  ldloc.2
0x28027  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_Value()
0x2802c  castclass [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue
0x28031  stloc.s  7
0x28033  ldloc.3
0x28034  ldloc.s  5
0x28036  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x2803b  ldloc.s  5
0x2803d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x28042  call     class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::AsEnum(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x28047  ldloc.s  7
0x28049  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue::get_Value()
0x2804e  newobj   instance void [System.Web.OData]System.Web.OData.EdmEnumObject::.ctor(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmEnumTypeReference, string)
0x28053  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28058  br       loc_28167
0x2805d  ldloc.3
0x2805e  ldloc.s  5
0x28060  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x28065  ldarg.0
0x28066  call     instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataActionPayloadDeserializer::get_DeserializerProvider()
0x2806b  ldloc.s  5
0x2806d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x28072  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider::GetEdmTypeDeserializer(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x28077  ldloc.2
0x28078  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_Value()
0x2807d  ldloc.s  5
0x2807f  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x28084  ldarg.3
0x28085  callvirt instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer::ReadInline(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x2808a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2808f  br       loc_28167
0x28094  ldloc.s  5
0x28096  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x2809b  call     bool [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::IsCollection(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x280a0  brfalse.s loc_280E3
0x280a2  ldarg.0
0x280a3  ldloc.2
0x280a4  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataCollectionReader [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::CreateCollectionReader()
0x280a9  call     instance class [Microsoft.OData.Core]Microsoft.OData.ODataCollectionValue Microsoft.Crm.Extensibility.ODataV4.CrmODataActionPayloadDeserializer::ReadCollection(class [Microsoft.OData.Core]Microsoft.OData.ODataCollectionReader reader)
0x280ae  stloc.s  8
0x280b0  ldloc.3
0x280b1  ldloc.s  5
0x280b3  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x280b8  ldarg.0
0x280b9  call     instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataActionPayloadDeserializer::get_DeserializerProvider()
0x280be  ldloc.s  5
0x280c0  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x280c5  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider::GetEdmTypeDeserializer(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x280ca  ldloc.s  8
0x280cc  ldloc.s  5
0x280ce  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x280d3  ldarg.3
0x280d4  callvirt instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer::ReadInline(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x280d9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x280de  br       loc_28167
0x280e3  ldloc.3
0x280e4  ldloc.s  5
0x280e6  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x280eb  ldarg.0
0x280ec  call     instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataActionPayloadDeserializer::get_DeserializerProvider()
0x280f1  ldloc.s  5
0x280f3  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x280f8  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider::GetEdmTypeDeserializer(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x280fd  ldloc.2
0x280fe  callvirt instance object [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::get_Value()
0x28103  ldloc.s  5
0x28105  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x2810a  ldarg.3
0x2810b  callvirt instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer::ReadInline(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x28110  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28115  br.s     loc_28167
0x28117  ldloc.3
0x28118  ldloc.s  5
0x2811a  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x2811f  ldarg.0
0x28120  ldarg.3
0x28121  ldloc.2
0x28122  ldloc.s  5
0x28124  call     instance object Microsoft.Crm.Extensibility.ODataV4.CrmODataActionPayloadDeserializer::ReadEntry(class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext readContext, class [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader reader, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter parameter)
0x28129  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2812e  br.s     loc_28167
0x28130  ldloc.3
0x28131  ldloc.s  5
0x28133  callvirt instance string [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmNamedElement::get_Name()
0x28138  ldarg.0
0x28139  call     instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataActionPayloadDeserializer::get_DeserializerProvider()
0x2813e  ldloc.s  5
0x28140  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x28145  callvirt instance class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerProvider::GetEdmTypeDeserializer(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x2814a  ldloc.2
0x2814b  callvirt instance class [Microsoft.OData.Core]Microsoft.OData.ODataReader [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::CreateResourceSetReader()
0x28150  call     class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataItemBase [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataReaderExtensions::ReadResourceOrResourceSet(class [Microsoft.OData.Core]Microsoft.OData.ODataReader)
0x28155  ldloc.s  5
0x28157  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmOperationParameter::get_Type()
0x2815c  ldarg.3
0x2815d  callvirt instance object [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataEdmTypeDeserializer::ReadInline(object, class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference, class [System.Web.OData]System.Web.OData.Formatter.Deserialization.ODataDeserializerContext)
0x28162  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x28167  ldloc.2
0x28168  callvirt instance bool [Microsoft.OData.Core]Microsoft.OData.ODataParameterReader::Read()
0x2816d  brtrue   loc_27F96
0x28172  ldloc.3
0x28173  ret
```
