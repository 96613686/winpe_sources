# Microsoft.Crm.Workflow.Services.InputArgumentValidator::FixInputParametersType

- ea: `0x14150`
- end: `0x1435e`
- name: `Microsoft.Crm.Workflow.Services.InputArgumentValidator::FixInputParametersType`
- size: `526`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5df0`
- `0x16120`

## callees

- `0x14150`

## pseudocode

```c

```

## disassembly

```asm
0x14150  ldarg.0
0x14151  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Count()
0x14156  ldarg.1
0x14157  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Count()
0x1415c  cgt
0x1415e  ldc.i4.0
0x1415f  ceq
0x14161  ldstr    aUnexpectedInpu// "Unexpected input argument count"
0x14166  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1416b  ldarg.1
0x1416c  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::GetEnumerator()
0x14171  stloc.0
0x14172  br       loc_14341
0x14177  ldloca.s 0
0x14179  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>::get_Current()
0x1417e  stloc.1
0x1417f  ldarg.0
0x14180  ldloca.s 1
0x14182  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x14187  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x1418c  brfalse  loc_14341
0x14191  ldloca.s 1
0x14193  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Value()
0x14198  stloc.2
0x14199  ldarg.0
0x1419a  ldloca.s 1
0x1419c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x141a1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x141a6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x141ab  stloc.3
0x141ac  ldloc.3
0x141ad  ldtoken  [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x141b2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141b7  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x141bc  brfalse.s loc_141E9
0x141be  ldarg.0
0x141bf  ldloca.s 1
0x141c1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x141c6  ldarg.0
0x141c7  ldloca.s 1
0x141c9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x141ce  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x141d3  castclass [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber
0x141d8  callvirt instance int32 [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmNumber::get_Value()
0x141dd  box      [mscorlib]System.Int32
0x141e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x141e7  br.s     loc_14224
0x141e9  ldloc.3
0x141ea  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money
0x141ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x141f4  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x141f9  brfalse.s loc_14224
0x141fb  ldarg.0
0x141fc  ldloca.s 1
0x141fe  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x14203  ldarg.0
0x14204  ldloca.s 1
0x14206  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x1420b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x14210  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money
0x14215  callvirt instance valuetype [mscorlib]System.Decimal [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Money::get_Value()
0x1421a  box      [mscorlib]System.Decimal
0x1421f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x14224  ldloc.2
0x14225  ldtoken  [mscorlib]System.String
0x1422a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1422f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x14234  brfalse.s loc_1425B
0x14236  ldarg.0
0x14237  ldloca.s 1
0x14239  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x1423e  ldarg.0
0x1423f  ldloca.s 1
0x14241  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x14246  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x1424b  ldarg.2
0x1424c  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x14251  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x14256  br       loc_142DE
0x1425b  ldloc.2
0x1425c  ldtoken  [mscorlib]System.Int32
0x14261  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14266  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1426b  brfalse.s loc_14294
0x1426d  ldarg.0
0x1426e  ldloca.s 1
0x14270  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x14275  ldarg.0
0x14276  ldloca.s 1
0x14278  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x1427d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x14282  ldarg.2
0x14283  call     int32 [mscorlib]System.Convert::ToInt32(object, class [mscorlib]System.IFormatProvider)
0x14288  box      [mscorlib]System.Int32
0x1428d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x14292  br.s     loc_142DE
0x14294  ldloc.2
0x14295  ldtoken  [mscorlib]System.Double
0x1429a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1429f  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x142a4  brfalse.s loc_142CD
0x142a6  ldarg.0
0x142a7  ldloca.s 1
0x142a9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x142ae  ldarg.0
0x142af  ldloca.s 1
0x142b1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x142b6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x142bb  ldarg.2
0x142bc  call     float64 [mscorlib]System.Convert::ToDouble(object, class [mscorlib]System.IFormatProvider)
0x142c1  box      [mscorlib]System.Double
0x142c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x142cb  br.s     loc_142DE
0x142cd  ldloc.2
0x142ce  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x142d3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x142d8  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x142dd  pop
0x142de  leave.s  loc_14341
0x142e0  stloc.s  4
0x142e2  ldloc.s  4
0x142e4  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x142e9  ldc.i4.s 0x1E
0x142eb  ldstr    aExceptionWhile_0// "Exception while converting parameter {0"...
0x142f0  ldc.i4.4
0x142f1  newarr   [mscorlib]System.Object
0x142f6  dup
0x142f7  ldc.i4.0
0x142f8  ldloca.s 1
0x142fa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x142ff  stelem.ref
0x14300  dup
0x14301  ldc.i4.1
0x14302  ldloc.2
0x14303  stelem.ref
0x14304  dup
0x14305  ldc.i4.2
0x14306  ldarg.0
0x14307  ldloca.s 1
0x14309  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x1430e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x14313  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14318  stelem.ref
0x14319  dup
0x1431a  ldc.i4.3
0x1431b  ldloc.s  4
0x1431d  callvirt instance string [mscorlib]System.Exception::get_Message()
0x14322  stelem.ref
0x14323  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14328  ldstr    aErrorWhileConv// "Error while converting processing input"...
0x1432d  ldloca.s 1
0x1432f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Type>::get_Key()
0x14334  call     string [mscorlib]System.String::Concat(string, string)
0x14339  ldloc.s  4
0x1433b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string, class [mscorlib]System.Exception)
0x14340  throw
0x14341  ldloca.s 0
0x14343  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>::MoveNext()
0x14348  brtrue   loc_14177
0x1434d  leave.s  loc_1435D
0x1434f  ldloca.s 0
0x14351  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [mscorlib]System.Type>
0x14357  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1435c  endfinally
0x1435d  ret
```
