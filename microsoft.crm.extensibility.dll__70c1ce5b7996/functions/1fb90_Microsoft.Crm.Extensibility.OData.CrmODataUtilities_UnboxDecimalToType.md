# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::UnboxDecimalToType

- ea: `0x1fb90`
- end: `0x1fd34`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::UnboxDecimalToType`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1f890`

## callees

- `0x1fb90`

## string_xrefs

- `0x1fd15`: `Unexpected Json Type {0} encountered while deserializing`

## pseudocode

```c

```

## disassembly

```asm
0x1fb90  ldarg.0
0x1fb91  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x1fb96  ldc.i4.6
0x1fb97  bne.un   loc_1FC50
0x1fb9c  ldarg.1
0x1fb9d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1fba2  call     valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::PrimitiveKind(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1fba7  stloc.0
0x1fba8  ldloc.0
0x1fba9  ldc.i4.5
0x1fbaa  sub
0x1fbab  switch   loc_1FBFF, loc_1FC15, loc_1FC27, loc_1FBCA, loc_1FBDC, loc_1FBEE
0x1fbc8  br.s     loc_1FC27
0x1fbca  ldarg.0
0x1fbcb  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fbd0  unbox.any [mscorlib]System.Int64
0x1fbd5  conv.i2
0x1fbd6  box      [mscorlib]System.Int16
0x1fbdb  ret
0x1fbdc  ldarg.0
0x1fbdd  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fbe2  unbox.any [mscorlib]System.Int64
0x1fbe7  conv.i4
0x1fbe8  box      [mscorlib]System.Int32
0x1fbed  ret
0x1fbee  ldarg.0
0x1fbef  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fbf4  unbox.any [mscorlib]System.Int64
0x1fbf9  box      [mscorlib]System.Int64
0x1fbfe  ret
0x1fbff  ldarg.0
0x1fc00  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fc05  unbox.any [mscorlib]System.Int64
0x1fc0a  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Implicit(int64)
0x1fc0f  box      [mscorlib]System.Decimal
0x1fc14  ret
0x1fc15  ldarg.0
0x1fc16  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fc1b  unbox.any [mscorlib]System.Int64
0x1fc20  conv.r8
0x1fc21  box      [mscorlib]System.Double
0x1fc26  ret
0x1fc27  ldc.i4   0x1F4
0x1fc2c  ldstr    aUnexpectedType_0// "Unexpected type {0} encountered while d"...
0x1fc31  ldc.i4.1
0x1fc32  newarr   [mscorlib]System.Object
0x1fc37  dup
0x1fc38  ldc.i4.0
0x1fc39  ldarg.1
0x1fc3a  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1fc3f  call     valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::PrimitiveKind(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1fc44  box      [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind
0x1fc49  stelem.ref
0x1fc4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1fc4f  throw
0x1fc50  ldarg.0
0x1fc51  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x1fc56  ldc.i4.7
0x1fc57  bne.un   loc_1FD10
0x1fc5c  ldarg.1
0x1fc5d  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1fc62  call     valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::PrimitiveKind(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1fc67  stloc.0
0x1fc68  ldloc.0
0x1fc69  ldc.i4.5
0x1fc6a  sub
0x1fc6b  switch   loc_1FCC0, loc_1FCD6, loc_1FCE7, loc_1FC8A, loc_1FC9C, loc_1FCAE
0x1fc88  br.s     loc_1FCE7
0x1fc8a  ldarg.0
0x1fc8b  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fc90  unbox.any [mscorlib]System.Double
0x1fc95  conv.i2
0x1fc96  box      [mscorlib]System.Int16
0x1fc9b  ret
0x1fc9c  ldarg.0
0x1fc9d  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fca2  unbox.any [mscorlib]System.Double
0x1fca7  conv.i4
0x1fca8  box      [mscorlib]System.Int32
0x1fcad  ret
0x1fcae  ldarg.0
0x1fcaf  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fcb4  unbox.any [mscorlib]System.Double
0x1fcb9  conv.i8
0x1fcba  box      [mscorlib]System.Int64
0x1fcbf  ret
0x1fcc0  ldarg.0
0x1fcc1  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fcc6  unbox.any [mscorlib]System.Double
0x1fccb  call     valuetype [mscorlib]System.Decimal [mscorlib]System.Decimal::op_Explicit(float64)
0x1fcd0  box      [mscorlib]System.Decimal
0x1fcd5  ret
0x1fcd6  ldarg.0
0x1fcd7  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.Linq.JValue::get_Value()
0x1fcdc  unbox.any [mscorlib]System.Double
0x1fce1  box      [mscorlib]System.Double
0x1fce6  ret
0x1fce7  ldc.i4   0x1F4
0x1fcec  ldstr    aUnexpectedType_1// "Unexpected type {0} encountered while d"...
0x1fcf1  ldc.i4.1
0x1fcf2  newarr   [mscorlib]System.Object
0x1fcf7  dup
0x1fcf8  ldc.i4.0
0x1fcf9  ldarg.1
0x1fcfa  callvirt instance class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty::get_Type()
0x1fcff  call     valuetype [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmTypeSemantics::PrimitiveKind(class [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmTypeReference)
0x1fd04  box      [Microsoft.OData.Edm]Microsoft.OData.Edm.EdmPrimitiveTypeKind
0x1fd09  stelem.ref
0x1fd0a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1fd0f  throw
0x1fd10  ldc.i4   0x1F4
0x1fd15  ldstr    aUnexpectedJson// "Unexpected Json Type {0} encountered wh"...
0x1fd1a  ldc.i4.1
0x1fd1b  newarr   [mscorlib]System.Object
0x1fd20  dup
0x1fd21  ldc.i4.0
0x1fd22  ldarg.0
0x1fd23  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Type()
0x1fd28  box      [Newtonsoft.Json]Newtonsoft.Json.Linq.JTokenType
0x1fd2d  stelem.ref
0x1fd2e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1fd33  throw
```
