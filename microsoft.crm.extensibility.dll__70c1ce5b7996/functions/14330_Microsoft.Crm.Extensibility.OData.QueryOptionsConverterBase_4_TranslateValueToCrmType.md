# Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::TranslateValueToCrmType

- ea: `0x14330`
- end: `0x143cf`
- name: `Microsoft.Crm.Extensibility.OData.QueryOptionsConverterBase`4::TranslateValueToCrmType`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14330`

## string_xrefs

- `0x1433d`: `The right side of the "{0}" operator must be a constant value.`

## pseudocode

```c

```

## disassembly

```asm
0x14330  ldarg.1
0x14331  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.IEdmProperty
0x14336  brfalse.s loc_14352
0x14338  ldc.i4   0x1F5
0x1433d  ldstr    aTheRightSideOf// "The right side of the \"{0}\" operator "...
0x14342  ldc.i4.1
0x14343  newarr   [mscorlib]System.Object
0x14348  dup
0x14349  ldc.i4.0
0x1434a  ldarg.2
0x1434b  stelem.ref
0x1434c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x14351  throw
0x14352  ldarg.1
0x14353  isinst   [mscorlib]System.DateTimeOffset
0x14358  brfalse.s loc_14377
0x1435a  ldarg.1
0x1435b  unbox.any [mscorlib]System.DateTimeOffset
0x14360  stloc.0
0x14361  ldloca.s 0
0x14363  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_DateTime()
0x14368  ldc.i4.1
0x14369  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x1436e  box      [mscorlib]System.DateTime
0x14373  starg.s  1
0x14375  br.s     loc_143CD
0x14377  ldarg.1
0x14378  isinst   [Microsoft.OData.Edm]Microsoft.OData.Edm.Date
0x1437d  brfalse.s loc_143A9
0x1437f  ldarg.1
0x14380  unbox.any [Microsoft.OData.Edm]Microsoft.OData.Edm.Date
0x14385  stloc.1
0x14386  ldloca.s 1
0x14388  call     instance int32 [Microsoft.OData.Edm]Microsoft.OData.Edm.Date::get_Year()
0x1438d  ldloca.s 1
0x1438f  call     instance int32 [Microsoft.OData.Edm]Microsoft.OData.Edm.Date::get_Month()
0x14394  ldloca.s 1
0x14396  call     instance int32 [Microsoft.OData.Edm]Microsoft.OData.Edm.Date::get_Day()
0x1439b  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32)
0x143a0  box      [mscorlib]System.DateTime
0x143a5  starg.s  1
0x143a7  br.s     loc_143CD
0x143a9  ldarg.1
0x143aa  isinst   [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue
0x143af  brfalse.s loc_143CD
0x143b1  ldarg.1
0x143b2  castclass [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue
0x143b7  callvirt instance string [Microsoft.OData.Core]Microsoft.OData.ODataEnumValue::get_Value()
0x143bc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x143c1  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x143c6  box      [mscorlib]System.Int32
0x143cb  starg.s  1
0x143cd  ldarg.1
0x143ce  ret
```
