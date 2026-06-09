# Microsoft.Crm.Sdk.SchemaBuilderFactory::Create

- ea: `0x67b0`
- end: `0x688b`
- name: `Microsoft.Crm.Sdk.SchemaBuilderFactory::Create`
- size: `219`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xe00`
- `0xf40`
- `0x1080`
- `0x1170`
- `0x16c0`
- `0x1710`
- `0x17f0`
- `0x1970`
- `0x1c80`
- `0x2560`
- `0x7550`
- `0x77d0`
- `0x78f0`
- `0x7f80`
- `0xa480`

## callees

- `0x67b0`
- `0x7220`
- `0x7590`
- `0x77b0`
- `0x7eb0`

## pseudocode

```c

```

## disassembly

```asm
0x67b0  ldarg.0
0x67b1  ldtoken  Microsoft.Crm.Sdk.Crm2007.Request
0x67b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67bb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67c0  brfalse.s loc_67C8
0x67c2  newobj   instance void Microsoft.Crm.Sdk.RequestWithOptionalParametersSchemaBuilder::.ctor()
0x67c7  ret
0x67c8  ldarg.0
0x67c9  ldtoken  Microsoft.Crm.Sdk.Crm2007.Response
0x67ce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67d3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67d8  brfalse.s loc_67E0
0x67da  newobj   instance void Microsoft.Crm.Sdk.ResponseSchemaBuilder::.ctor()
0x67df  ret
0x67e0  ldarg.0
0x67e1  ldtoken  Microsoft.Crm.Sdk.Crm2006.BusinessEntity
0x67e6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67eb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x67f0  brtrue.s loc_6816
0x67f2  ldarg.0
0x67f3  ldtoken  Microsoft.Crm.Sdk.Crm2007.BusinessEntity
0x67f8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x67fd  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6802  brtrue.s loc_6816
0x6804  ldarg.0
0x6805  ldtoken  Microsoft.Crm.Sdk.Crm2009.BusinessEntity
0x680a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x680f  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6814  brfalse.s loc_6826
0x6816  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntity
0x681b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6820  newobj   instance void Microsoft.Crm.Sdk.DotNetSerializableSchemaBuilder::.ctor(class [mscorlib]System.Type type)
0x6825  ret
0x6826  ldarg.0
0x6827  ldtoken  Microsoft.Crm.Sdk.Crm2006.BusinessEntityCollection
0x682c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6831  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6836  brtrue.s loc_685C
0x6838  ldarg.0
0x6839  ldtoken  Microsoft.Crm.Sdk.Crm2007.BusinessEntityCollection
0x683e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6843  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6848  brtrue.s loc_685C
0x684a  ldarg.0
0x684b  ldtoken  Microsoft.Crm.Sdk.Crm2009.BusinessEntityCollection
0x6850  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6855  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x685a  brfalse.s loc_686C
0x685c  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.BusinessEntityCollection
0x6861  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6866  newobj   instance void Microsoft.Crm.Sdk.DotNetSerializableSchemaBuilder::.ctor(class [mscorlib]System.Type type)
0x686b  ret
0x686c  ldarg.0
0x686d  ldtoken  [Microsoft.Crm]Microsoft.Crm.BusinessEntities.EntityName
0x6872  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6877  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x687c  brfalse.s loc_6884
0x687e  newobj   instance void Microsoft.Crm.Sdk.EntityNameSchemaBuilder::.ctor()
0x6883  ret
0x6884  ldarg.0
0x6885  newobj   instance void Microsoft.Crm.Sdk.DotNetSerializableSchemaBuilder::.ctor(class [mscorlib]System.Type type)
0x688a  ret
```
