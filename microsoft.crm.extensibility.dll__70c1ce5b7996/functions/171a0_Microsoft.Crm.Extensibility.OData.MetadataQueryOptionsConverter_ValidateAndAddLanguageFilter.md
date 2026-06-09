# Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateAndAddLanguageFilter

- ea: `0x171a0`
- end: `0x17226`
- name: `Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateAndAddLanguageFilter`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x17150`

## callees

- `0x171a0`

## string_xrefs

- `0x17215`: `Label Language parameter should be comma seperated integer values`

## pseudocode

```c

```

## disassembly

```asm
0x171a0  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::ValidateLabelLanguage
0x171a5  ldarg.1
0x171a6  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x171ab  brfalse.s loc_17210
0x171ad  ldarg.1
0x171ae  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x171b3  brtrue.s loc_17210
0x171b5  ldarg.0
0x171b6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.LabelQueryExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::get_LabelQuery()
0x171bb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<int32> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.LabelQueryExpression::get_FilterLanguages()
0x171c0  ldarg.1
0x171c1  ldc.i4.1
0x171c2  newarr   [mscorlib]System.Char
0x171c7  dup
0x171c8  ldc.i4.0
0x171c9  ldc.i4.s 0x2C
0x171cb  stelem.i2
0x171cc  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x171d1  ldsfld   class [mscorlib]System.Converter`2<string, int32> <>c::<>9__49_0
0x171d6  dup
0x171d7  brtrue.s loc_171F0
0x171d9  pop
0x171da  ldsfld   class <>c <>c::<>9
0x171df  ldftn    instance int32 <>c::<ValidateAndAddLanguageFilter>b__49_0(string languageCode)
0x171e5  newobj   instance void class [mscorlib]System.Converter`2<string, int32>::.ctor(object, native int)
0x171ea  dup
0x171eb  stsfld   class [mscorlib]System.Converter`2<string, int32> <>c::<>9__49_0
0x171f0  call     T0x2B00008D
0x171f5  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<int32>::AddRange(var<u1>[])
0x171fa  ldarg.0
0x171fb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.LabelQueryExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.EntityQueryExpression::get_LabelQuery()
0x17200  ldsfld   int32 Microsoft.Crm.Extensibility.OData.MetadataQueryOptionsConverter::LabelQueryMissingLabelReplaceBehavior
0x17205  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1720a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.Query.LabelQueryExpression::set_MissingLabelBehavior(valuetype [mscorlib]System.Nullable`1<int32>)
0x1720f  ret
0x17210  ldc.i4   0x190
0x17215  ldstr    aLabelLanguageP// "Label Language parameter should be comm"...
0x1721a  ldc.i4.0
0x1721b  newarr   [mscorlib]System.Object
0x17220  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x17225  throw
```
