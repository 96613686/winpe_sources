# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSubscriptionCount

- ea: `0x6780`
- end: `0x67ac`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSubscriptionCount`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4be0`

## callees

- `0x67f0`

## pseudocode

```c

```

## disassembly

```asm
0x6780  ldstr    aSelectCountFro// "SELECT COUNT(*) FROM  Subscription WHER"...
0x6785  stloc.0
0x6786  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x678b  ldloc.0
0x678c  ldc.i4.1
0x678d  newarr   [mscorlib]System.Object
0x6792  dup
0x6793  ldc.i4.0
0x6794  ldarg.1
0x6795  box      [mscorlib]System.Int32
0x679a  stelem.ref
0x679b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x67a0  stloc.1
0x67a1  ldc.i4.1
0x67a2  stloc.2
0x67a3  ldarg.0
0x67a4  ldloc.1
0x67a5  ldloc.2
0x67a6  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::RetrieveOneInteger(string sqlCommand, valuetype [System.Data]System.Data.CommandType commandType)
0x67ab  ret
```
