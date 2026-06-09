# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateRowCountForEntityAttributes

- ea: `0x2ed0`
- end: `0x2f46`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateRowCountForEntityAttributes`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ae0`

## callees

- `0x2ac0`
- `0x2ed0`
- `0x2f50`
- `0x2f70`
- `0x2f90`

## pseudocode

```c

```

## disassembly

```asm
0x2ed0  ldarg.1
0x2ed1  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x2ed6  stloc.0
0x2ed7  br.s     loc_2F2C
0x2ed9  ldloca.s 0
0x2edb  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x2ee0  stloc.1
0x2ee1  ldarg.0
0x2ee2  ldarg.2
0x2ee3  ldloc.1
0x2ee4  call     instance string Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::GetEntityAttributeKey(string entityName, string attributeName)
0x2ee9  stloc.2
0x2eea  ldarg.3
0x2eeb  ldstr    aAutoconvertedr// "AutoConvertedRows"
0x2ef0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2ef5  brtrue.s loc_2F13
0x2ef7  ldarg.3
0x2ef8  ldstr    aRowsconvertedu// "RowsConvertedUsingRule"
0x2efd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f02  brtrue.s loc_2F1C
0x2f04  ldarg.3
0x2f05  ldstr    aNotconvertedro// "NotConvertedRows"
0x2f0a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2f0f  brtrue.s loc_2F25
0x2f11  br.s     loc_2F2C
0x2f13  ldarg.0
0x2f14  ldloc.2
0x2f15  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateAutoConvertedRowCount(string entityAttributeKey)
0x2f1a  br.s     loc_2F2C
0x2f1c  ldarg.0
0x2f1d  ldloc.2
0x2f1e  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateRowsConvertedUsingRuleCount(string entityAttributeKey)
0x2f23  br.s     loc_2F2C
0x2f25  ldarg.0
0x2f26  ldloc.2
0x2f27  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::UpdateNotConvertedRowsCount(string entityAttributeKey)
0x2f2c  ldloca.s 0
0x2f2e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x2f33  brtrue.s loc_2ED9
0x2f35  leave.s  loc_2F45
0x2f37  ldloca.s 0
0x2f39  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x2f3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f44  endfinally
0x2f45  ret
```
