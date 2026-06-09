# Microsoft.Crm.Query.OutlookSyncStageQuerySqlCommandStrategy::GetCommandString

- ea: `0x2cc10`
- end: `0x2cce5`
- name: `Microsoft.Crm.Query.OutlookSyncStageQuerySqlCommandStrategy::GetCommandString`
- size: `213`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x23cd0`
- `0x23d80`
- `0x23ea0`
- `0x2a5a0`
- `0x2cc10`
- `0x66ff0`

## string_xrefs

- `0x2cc39`: `IsParenthsisOpenRequired`
- `0x2cc50`: `IsParenthsisOpenRequired`

## pseudocode

```c

```

## disassembly

```asm
0x2cc10  ldarg.0
0x2cc11  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_WhereClause()
0x2cc16  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2cc1b  brtrue.s loc_2CC2E
0x2cc1d  ldarg.0
0x2cc1e  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_WhereClause()
0x2cc23  ldstr    a11// "1=1"
0x2cc28  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2cc2d  pop
0x2cc2e  ldarg.0
0x2cc2f  call     instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_ExecutionContext()
0x2cc34  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x2cc39  ldstr    aIsparenthsisop// "IsParenthsisOpenRequired"
0x2cc3e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x2cc43  brfalse.s loc_2CC61
0x2cc45  ldarg.0
0x2cc46  call     instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_ExecutionContext()
0x2cc4b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x2cc50  ldstr    aIsparenthsisop// "IsParenthsisOpenRequired"
0x2cc55  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2cc5a  unbox.any [mscorlib]System.Boolean
0x2cc5f  br.s     loc_2CC62
0x2cc61  ldc.i4.0
0x2cc62  brfalse.s loc_2CC76
0x2cc64  ldarg.0
0x2cc65  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_WhereClause()
0x2cc6a  ldc.i4.0
0x2cc6b  ldstr    asc_CC172// "("
0x2cc70  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Insert(int32, string)
0x2cc75  pop
0x2cc76  ldarg.0
0x2cc77  call     instance string Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::GenerateFromClause()
0x2cc7c  dup
0x2cc7d  ldstr    aNolock// "(NOLOCK)"
0x2cc82  ldc.i4.5
0x2cc83  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2cc88  ldstr    aNolock// "(NOLOCK)"
0x2cc8d  call     instance int32 [mscorlib]System.String::get_Length()
0x2cc92  add
0x2cc93  stloc.0
0x2cc94  ldloc.0
0x2cc95  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2cc9a  stloc.1
0x2cc9b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2cca0  stloc.2
0x2cca1  ldloc.2
0x2cca2  ldstr    a0Where1// " {0} where {1}"
0x2cca7  ldloc.1
0x2cca8  ldarg.0
0x2cca9  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_WhereClause()
0x2ccae  callvirt instance string [mscorlib]System.Object::ToString()
0x2ccb3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2ccb8  pop
0x2ccb9  ldarg.0
0x2ccba  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_OrderByClause()
0x2ccbf  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x2ccc4  ldc.i4.0
0x2ccc5  ble.s    loc_2CCDE
0x2ccc7  ldloc.2
0x2ccc8  ldstr    aOrderBy0_1// " order by {0}"
0x2cccd  ldarg.0
0x2ccce  call     instance class [mscorlib]System.Text.StringBuilder Microsoft.Crm.Query.CrmSqlSelectCommandStrategy::get_OrderByClause()
0x2ccd3  callvirt instance string [mscorlib]System.Object::ToString()
0x2ccd8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x2ccdd  pop
0x2ccde  ldloc.2
0x2ccdf  callvirt instance string [mscorlib]System.Object::ToString()
0x2cce4  ret
```
