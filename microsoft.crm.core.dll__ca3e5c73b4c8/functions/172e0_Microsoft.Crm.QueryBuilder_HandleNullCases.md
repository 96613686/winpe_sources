# Microsoft.Crm.QueryBuilder::HandleNullCases

- ea: `0x172e0`
- end: `0x17394`
- name: `Microsoft.Crm.QueryBuilder::HandleNullCases`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x174d0`

## callees

- `0x172e0`
- `0x1a860`
- `0x368f0`
- `0x43b60`
- `0x5f120`

## string_xrefs

- `0x172e3`: `Unexpected, propertyComparison is null`
- `0x1736f`: `Unsupported comparison for null value : `

## pseudocode

```c

```

## disassembly

```asm
0x172e0  ldarg.0
0x172e1  brtrue.s loc_172EE
0x172e3  ldstr    aUnexpectedProp// "Unexpected, propertyComparison is null"
0x172e8  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x172ed  throw
0x172ee  ldarg.0
0x172ef  callvirt instance valuetype Microsoft.Crm.Data.ConditionalOperator Microsoft.Crm.Data.PropertyComparison::get_Comparison()
0x172f4  ldc.i4.5
0x172f5  bne.un.s loc_1732F
0x172f7  ldarg.1
0x172f8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x172fd  ldstr    a01IsNotNull// "{0}({1} is not null)"
0x17302  ldc.i4.2
0x17303  newarr   [mscorlib]System.Object
0x17308  dup
0x17309  ldc.i4.0
0x1730a  ldarg.2
0x1730b  brtrue.s loc_17314
0x1730d  ldstr    aAnd// " AND "
0x17312  br.s     loc_17319
0x17314  ldsfld   string [mscorlib]System.String::Empty
0x17319  stelem.ref
0x1731a  dup
0x1731b  ldc.i4.1
0x1731c  ldarg.3
0x1731d  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x17322  call     string Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string input)
0x17327  stelem.ref
0x17328  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1732d  pop
0x1732e  ret
0x1732f  ldarg.0
0x17330  callvirt instance valuetype Microsoft.Crm.Data.ConditionalOperator Microsoft.Crm.Data.PropertyComparison::get_Comparison()
0x17335  brtrue.s loc_1736F
0x17337  ldarg.1
0x17338  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1733d  ldstr    a01IsNull// "{0}({1} is null)"
0x17342  ldc.i4.2
0x17343  newarr   [mscorlib]System.Object
0x17348  dup
0x17349  ldc.i4.0
0x1734a  ldarg.2
0x1734b  brtrue.s loc_17354
0x1734d  ldstr    aAnd// " AND "
0x17352  br.s     loc_17359
0x17354  ldsfld   string [mscorlib]System.String::Empty
0x17359  stelem.ref
0x1735a  dup
0x1735b  ldc.i4.1
0x1735c  ldarg.3
0x1735d  callvirt instance string Microsoft.Crm.SharedDatabase.Column::get_Name()
0x17362  call     string Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string input)
0x17367  stelem.ref
0x17368  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1736d  pop
0x1736e  ret
0x1736f  ldstr    aUnsupportedCom// "Unsupported comparison for null value :"...
0x17374  ldarg.0
0x17375  callvirt instance valuetype Microsoft.Crm.Data.ConditionalOperator Microsoft.Crm.Data.PropertyComparison::get_Comparison()
0x1737a  box      Microsoft.Crm.Data.ConditionalOperator
0x1737f  ldstr    aG// "G"
0x17384  call     instance string [mscorlib]System.Enum::ToString(string)
0x17389  call     string [mscorlib]System.String::Concat(string, string)
0x1738e  newobj   instance void Microsoft.Crm.CrmException::.ctor(string message)
0x17393  throw
```
