# Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType

- ea: `0x12c50`
- end: `0x12ddd`
- name: `Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType`
- size: `397`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12c50`
- `0x12e00`
- `0x12eb0`
- `0x12f30`
- `0x12fe0`
- `0x13260`
- `0x13300`
- `0x13370`
- `0x133d0`
- `0x13480`
- `0x13640`
- `0x136f0`
- `0x13780`
- `0x13820`

## callees

- `0x12c50`

## pseudocode

```c

```

## disassembly

```asm
0x12c50  ldarg.1
0x12c51  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x12c56  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c5b  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12c60  brfalse.s loc_12C7E
0x12c62  ldarg.0
0x12c63  ldtoken  [mscorlib]System.Int32
0x12c68  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c6d  ldarg.2
0x12c6e  call     instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType(class [mscorlib]System.Type targetType, object value)
0x12c73  unbox.any [mscorlib]System.Int32
0x12c78  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber::.ctor(int32)
0x12c7d  ret
0x12c7e  ldarg.1
0x12c7f  ldtoken  [mscorlib]System.Int32
0x12c84  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c89  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12c8e  brfalse.s loc_12CB6
0x12c90  ldarg.2
0x12c91  ldtoken  [mscorlib]System.Double
0x12c96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12c9b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12ca0  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type, class [mscorlib]System.IFormatProvider)
0x12ca5  unbox.any [mscorlib]System.Double
0x12caa  call     float64 [mscorlib]System.Math::Floor(float64)
0x12caf  conv.i4
0x12cb0  box      [mscorlib]System.Int32
0x12cb5  ret
0x12cb6  ldarg.1
0x12cb7  ldtoken  [mscorlib]System.Double
0x12cbc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12cc1  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12cc6  brfalse.s loc_12CE8
0x12cc8  ldarg.2
0x12cc9  ldtoken  [mscorlib]System.Double
0x12cce  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12cd3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12cd8  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type, class [mscorlib]System.IFormatProvider)
0x12cdd  unbox.any [mscorlib]System.Double
0x12ce2  box      [mscorlib]System.Double
0x12ce7  ret
0x12ce8  ldarg.1
0x12ce9  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat
0x12cee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12cf3  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12cf8  brfalse.s loc_12D16
0x12cfa  ldarg.0
0x12cfb  ldtoken  [mscorlib]System.Double
0x12d00  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d05  ldarg.2
0x12d06  call     instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType(class [mscorlib]System.Type targetType, object value)
0x12d0b  unbox.any [mscorlib]System.Double
0x12d10  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmFloat::.ctor(float64)
0x12d15  ret
0x12d16  ldarg.1
0x12d17  ldtoken  [mscorlib]System.Decimal
0x12d1c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d21  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12d26  brfalse.s loc_12D48
0x12d28  ldarg.2
0x12d29  ldtoken  [mscorlib]System.Decimal
0x12d2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12d38  call     object [mscorlib]System.Convert::ChangeType(object, class [mscorlib]System.Type, class [mscorlib]System.IFormatProvider)
0x12d3d  unbox.any [mscorlib]System.Decimal
0x12d42  box      [mscorlib]System.Decimal
0x12d47  ret
0x12d48  ldarg.1
0x12d49  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney
0x12d4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d53  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12d58  brfalse.s loc_12D76
0x12d5a  ldarg.0
0x12d5b  ldtoken  [mscorlib]System.Decimal
0x12d60  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d65  ldarg.2
0x12d66  call     instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType(class [mscorlib]System.Type targetType, object value)
0x12d6b  unbox.any [mscorlib]System.Decimal
0x12d70  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmMoney::.ctor(valuetype [mscorlib]System.Decimal)
0x12d75  ret
0x12d76  ldarg.1
0x12d77  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money
0x12d7c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d81  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12d86  brfalse.s loc_12DA4
0x12d88  ldarg.0
0x12d89  ldtoken  [mscorlib]System.Decimal
0x12d8e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12d93  ldarg.2
0x12d94  call     instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType(class [mscorlib]System.Type targetType, object value)
0x12d99  unbox.any [mscorlib]System.Decimal
0x12d9e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money::.ctor(valuetype [mscorlib]System.Decimal)
0x12da3  ret
0x12da4  ldarg.1
0x12da5  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal
0x12daa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12daf  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x12db4  brfalse.s loc_12DD2
0x12db6  ldarg.0
0x12db7  ldtoken  [mscorlib]System.Decimal
0x12dbc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x12dc1  ldarg.2
0x12dc2  call     instance object Microsoft.Crm.Workflow.ValueConverters.ValueConverterBase::CreateCrmType(class [mscorlib]System.Type targetType, object value)
0x12dc7  unbox.any [mscorlib]System.Decimal
0x12dcc  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmDecimal::.ctor(valuetype [mscorlib]System.Decimal)
0x12dd1  ret
0x12dd2  ldstr    aUnsupportedTyp// "Unsupported type conversion"
0x12dd7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x12ddc  throw
```
