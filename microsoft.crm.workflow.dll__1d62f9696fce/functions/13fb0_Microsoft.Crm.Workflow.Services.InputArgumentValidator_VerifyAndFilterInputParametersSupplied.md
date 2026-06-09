# Microsoft.Crm.Workflow.Services.InputArgumentValidator::VerifyAndFilterInputParametersSupplied

- ea: `0x13fb0`
- end: `0x14141`
- name: `Microsoft.Crm.Workflow.Services.InputArgumentValidator::VerifyAndFilterInputParametersSupplied`
- size: `401`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5df0`
- `0x16120`

## callees

- `0x13fb0`

## pseudocode

```c

```

## disassembly

```asm
0x13fb0  ldc.i4.0
0x13fb1  stloc.0
0x13fb2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x13fb7  stloc.1
0x13fb8  ldarg.0
0x13fb9  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Count()
0x13fbe  ldarg.1
0x13fbf  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Count()
0x13fc4  ble.s    loc_13FCD
0x13fc6  ldc.i4.1
0x13fc7  stloc.0
0x13fc8  br       loc_140F7
0x13fcd  ldarg.0
0x13fce  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x13fd3  stloc.2
0x13fd4  br       loc_140DB
0x13fd9  ldloca.s 2
0x13fdb  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x13fe0  stloc.3
0x13fe1  ldarg.1
0x13fe2  ldloca.s 3
0x13fe4  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x13fe9  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::ContainsKey(var<u1>)
0x13fee  brfalse  loc_140D7
0x13ff3  ldloca.s 3
0x13ff5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x13ffa  brtrue.s loc_1400E
0x13ffc  ldloc.1
0x13ffd  ldloca.s 3
0x13fff  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x14004  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x14009  br       loc_140DB
0x1400e  ldloca.s 3
0x14010  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x14015  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1401a  stloc.s  4
0x1401c  ldloc.s  4
0x1401e  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x14023  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14028  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1402d  brfalse.s loc_14066
0x1402f  ldloca.s 3
0x14031  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x14036  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition
0x1403b  stloc.s  7
0x1403d  ldloca.s 7
0x1403f  call     instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_HasValue()
0x14044  brtrue.s loc_14058
0x14046  ldloc.1
0x14047  ldloca.s 3
0x14049  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1404e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x14053  br       loc_140DB
0x14058  ldloca.s 7
0x1405a  call     instance object [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Value()
0x1405f  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14064  stloc.s  4
0x14066  ldarg.1
0x14067  ldloca.s 3
0x14069  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1406e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Type>::get_Item(void)
0x14073  stloc.s  5
0x14075  ldloc.s  5
0x14077  ldloc.s  4
0x14079  newobj   instance void class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Type>::.ctor(var<u1>, !!T0)
0x1407e  stloc.s  6
0x14080  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool> Microsoft.Crm.Workflow.Services.InputArgumentValidator::_typeAssignmentCompatibility
0x14085  ldloc.s  6
0x14087  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool>::ContainsKey(var<u1>)
0x1408c  brtrue.s loc_140C5
0x1408e  ldnull
0x1408f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x14094  ldc.i4.s 0x1E
0x14096  ldstr    aUnsupportedTyp_0// "Unsupported type of input argument rece"...
0x1409b  ldc.i4.3
0x1409c  newarr   [mscorlib]System.Object
0x140a1  dup
0x140a2  ldc.i4.0
0x140a3  ldloca.s 3
0x140a5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x140aa  stelem.ref
0x140ab  dup
0x140ac  ldc.i4.1
0x140ad  ldloc.s  5
0x140af  stelem.ref
0x140b0  dup
0x140b1  ldc.i4.2
0x140b2  ldloc.s  4
0x140b4  stelem.ref
0x140b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x140ba  ldstr    aTypeNotSupport// "Type not supported for child dialog inp"...
0x140bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x140c4  throw
0x140c5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool> Microsoft.Crm.Workflow.Services.InputArgumentValidator::_typeAssignmentCompatibility
0x140ca  ldloc.s  6
0x140cc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, class [mscorlib]System.Type>, bool>::get_Item(void)
0x140d1  brtrue.s loc_140DB
0x140d3  ldc.i4.1
0x140d4  stloc.0
0x140d5  leave.s  loc_140F7
0x140d7  ldc.i4.1
0x140d8  stloc.0
0x140d9  leave.s  loc_140F7
0x140db  ldloca.s 2
0x140dd  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x140e2  brtrue   loc_13FD9
0x140e7  leave.s  loc_140F7
0x140e9  ldloca.s 2
0x140eb  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x140f1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x140f6  endfinally
0x140f7  ldloc.0
0x140f8  brfalse.s loc_1410B
0x140fa  ldc.i4   0x80045048
0x140ff  ldc.i4.0
0x14100  newarr   [mscorlib]System.Object
0x14105  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1410a  throw
0x1410b  ldloc.1
0x1410c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x14111  stloc.s  8
0x14113  br.s     loc_14127
0x14115  ldloca.s 8
0x14117  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1411c  stloc.s  9
0x1411e  ldarg.0
0x1411f  ldloc.s  9
0x14121  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Remove(var<u1>)
0x14126  pop
0x14127  ldloca.s 8
0x14129  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x1412e  brtrue.s loc_14115
0x14130  leave.s  loc_14140
0x14132  ldloca.s 8
0x14134  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x1413a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1413f  endfinally
0x14140  ret
```
