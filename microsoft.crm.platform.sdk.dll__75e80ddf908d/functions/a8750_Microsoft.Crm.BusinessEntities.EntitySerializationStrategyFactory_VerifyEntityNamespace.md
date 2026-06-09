# Microsoft.Crm.BusinessEntities.EntitySerializationStrategyFactory::VerifyEntityNamespace

- ea: `0xa8750`
- end: `0xa8797`
- name: `Microsoft.Crm.BusinessEntities.EntitySerializationStrategyFactory::VerifyEntityNamespace`
- size: `71`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa8710`
- `0xa8720`
- `0xa8740`

## callees

- `0xa8750`

## string_xrefs

- `0xa8751`: `http://schemas.microsoft.com/crm/2006/WebServices`
- `0xa875e`: `http://schemas.microsoft.com/crm/2007/WebServices`
- `0xa876b`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0xa8750  ldarg.0
0xa8751  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/crm/2006/W"...
0xa8756  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa875b  brtrue.s loc_A8777
0xa875d  ldarg.0
0xa875e  ldstr    aHttpSchemasMic_2// "http://schemas.microsoft.com/crm/2007/W"...
0xa8763  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8768  brtrue.s loc_A8777
0xa876a  ldarg.0
0xa876b  ldstr    aHttpSchemasMic_3// "http://schemas.microsoft.com/crm/2009/W"...
0xa8770  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8775  brfalse.s loc_A8778
0xa8777  ret
0xa8778  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa877d  ldstr    aNamespace0IsNo// "Namespace {0} is not supported."
0xa8782  ldc.i4.1
0xa8783  newarr   [mscorlib]System.Object
0xa8788  dup
0xa8789  ldc.i4.0
0xa878a  ldarg.0
0xa878b  stelem.ref
0xa878c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa8791  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xa8796  throw
```
