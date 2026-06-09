# Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PopulateUpdateCommand

- ea: `0x3160`
- end: `0x3268`
- name: `Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::PopulateUpdateCommand`
- size: `264`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2ae0`

## callees

- `0x3160`
- `0x3270`

## string_xrefs

- `0x3166`: `UPDATE {0} SET {1} WHERE {2} = {3}`

## pseudocode

```c

```

## disassembly

```asm
0x3160  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::.ctor()
0x3165  stloc.0
0x3166  ldstr    aUpdate0Set1Whe// "UPDATE {0} SET {1} WHERE {2} = {3}"
0x316b  stloc.1
0x316c  ldstr    a01_0// "{0} = {1}"
0x3171  stloc.2
0x3172  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3177  stloc.3
0x3178  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x317d  stloc.s  4
0x317f  ldc.i4.1
0x3180  stloc.s  5
0x3182  ldarg.s  5
0x3184  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::get_Keys()
0x3189  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, valuetype [mscorlib]System.DateTime>::GetEnumerator()
0x318e  stloc.s  8
0x3190  br.s     loc_31ED
0x3192  ldloca.s 8
0x3194  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>::get_Current()
0x3199  stloc.s  9
0x319b  ldstr    aConverted// "Converted"
0x31a0  ldloc.s  9
0x31a2  call     string [mscorlib]System.String::Concat(string, string)
0x31a7  stloc.s  0xA
0x31a9  ldloc.0
0x31aa  ldloc.s  0xA
0x31ac  ldarg.s  5
0x31ae  ldloc.s  9
0x31b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::get_Item(void)
0x31b5  box      [mscorlib]System.DateTime
0x31ba  ldc.i4.0
0x31bb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, bool)
0x31c0  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x31c5  stloc.s  0xB
0x31c7  ldloc.s  5
0x31c9  brtrue.s loc_31D8
0x31cb  ldloc.s  4
0x31cd  ldstr    asc_1B948// ","
0x31d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x31d7  pop
0x31d8  ldloc.s  4
0x31da  ldloc.2
0x31db  ldloc.s  9
0x31dd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x31e2  ldloc.s  0xB
0x31e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x31e9  pop
0x31ea  ldc.i4.0
0x31eb  stloc.s  5
0x31ed  ldloca.s 8
0x31ef  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>::MoveNext()
0x31f4  brtrue.s loc_3192
0x31f6  leave.s  loc_3206
0x31f8  ldloca.s 8
0x31fa  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<string, valuetype [mscorlib]System.DateTime>
0x3200  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3205  endfinally
0x3206  ldstr    aEntityid// "EntityId"
0x320b  stloc.s  6
0x320d  ldloc.0
0x320e  ldloc.s  6
0x3210  ldarg.s  4
0x3212  box      [mscorlib]System.Guid
0x3217  ldc.i4.0
0x3218  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType::.ctor(object, bool)
0x321d  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager::AddParameterWithName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ParameterValueAndType)
0x3222  stloc.s  7
0x3224  ldloc.3
0x3225  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x322a  ldloc.1
0x322b  ldc.i4.4
0x322c  newarr   [mscorlib]System.Object
0x3231  dup
0x3232  ldc.i4.0
0x3233  ldarg.2
0x3234  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::SqlIdentifierEncode(string)
0x3239  stelem.ref
0x323a  dup
0x323b  ldc.i4.1
0x323c  ldloc.s  4
0x323e  callvirt instance string [mscorlib]System.Object::ToString()
0x3243  stelem.ref
0x3244  dup
0x3245  ldc.i4.2
0x3246  ldarg.3
0x3247  stelem.ref
0x3248  dup
0x3249  ldc.i4.3
0x324a  ldloc.s  7
0x324c  stelem.ref
0x324d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x3252  pop
0x3253  ldarg.1
0x3254  ldloc.3
0x3255  callvirt instance string [mscorlib]System.Object::ToString()
0x325a  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x325f  ldarg.0
0x3260  ldarg.1
0x3261  ldloc.0
0x3262  call     instance void Microsoft.Crm.Asynchronous.ConvertDateAndTimeBehaviorOperation::AddParametersToSqlParameterCollection(class [System.Data]System.Data.IDbCommand command, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.QueryParameterManager parameterManager)
0x3267  ret
```
