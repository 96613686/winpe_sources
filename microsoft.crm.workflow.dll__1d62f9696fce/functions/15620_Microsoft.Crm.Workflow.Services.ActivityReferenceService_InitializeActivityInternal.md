# Microsoft.Crm.Workflow.Services.ActivityReferenceService::InitializeActivityInternal

- ea: `0x15620`
- end: `0x1590b`
- name: `Microsoft.Crm.Workflow.Services.ActivityReferenceService::InitializeActivityInternal`
- size: `747`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x14f50`
- `0x155d0`

## callees

- `0x151b0`
- `0x15210`
- `0x15230`
- `0x15620`
- `0x15910`
- `0x1d3e0`

## pseudocode

```c

```

## disassembly

```asm
0x15620  ldnull
0x15621  stloc.1
0x15622  ldnull
0x15623  stloc.2
0x15624  ldc.i4.0
0x15625  stloc.3
0x15626  ldarg.1
0x15627  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item2()
0x1562c  brtrue.s loc_15640
0x1562e  ldarg.1
0x1562f  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item6()
0x15634  ldc.i4.2
0x15635  beq.s    loc_15650
0x15637  ldarg.1
0x15638  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item6()
0x1563d  ldc.i4.3
0x1563e  beq.s    loc_15650
0x15640  ldarg.1
0x15641  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item1()
0x15646  stloc.2
0x15647  ldloc.2
0x15648  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x1564d  stloc.1
0x1564e  br.s     loc_1568E
0x15650  call     bool Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::IsSandboxCustomActivityFeatureEnabled()
0x15655  brtrue.s loc_15667
0x15657  ldstr    aCustomWorkflow// "Custom Workflow Activities are not supp"...
0x1565c  ldc.i4   0x80045051
0x15661  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x15666  throw
0x15667  ldtoken  Microsoft.Crm.Workflow.Services.ProxyCustomActivity
0x1566c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x15671  stloc.2
0x15672  ldarg.1
0x15673  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item3()
0x15678  ldarg.1
0x15679  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item4()
0x1567e  ldarg.1
0x1567f  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item5()
0x15684  ldarg.s  5
0x15686  newobj   instance void Microsoft.Crm.Workflow.Services.ProxyCustomActivity::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData pluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData pluginTypeData, valuetype [mscorlib]System.Guid pluginTypeId, string assemblyQualifiedName)
0x1568b  stloc.1
0x1568c  ldc.i4.1
0x1568d  stloc.3
0x1568e  ldnull
0x1568f  stloc.s  4
0x15691  ldc.i4.0
0x15692  stloc.s  5
0x15694  ldloc.2
0x15695  ldtoken  [System.Activities]System.Activities.Activity
0x1569a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1569f  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x156a4  brtrue.s loc_156BD
0x156a6  newobj   instance void [System.Workflow.Runtime]System.Activities.Statements.Interop::.ctor()
0x156ab  stloc.s  4
0x156ad  ldloc.s  4
0x156af  ldloc.2
0x156b0  callvirt instance void [System.Workflow.Runtime]System.Activities.Statements.Interop::set_ActivityType(class [mscorlib]System.Type)
0x156b5  ldloc.s  4
0x156b7  stloc.0
0x156b8  ldc.i4.1
0x156b9  stloc.s  5
0x156bb  br.s     loc_156C4
0x156bd  ldloc.1
0x156be  castclass [System.Activities]System.Activities.Activity
0x156c3  stloc.0
0x156c4  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::.ctor()
0x156c9  stloc.s  6
0x156cb  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::.ctor()
0x156d0  stloc.s  7
0x156d2  ldarg.2
0x156d3  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x156d8  stloc.s  9
0x156da  br       loc_1585C
0x156df  ldloca.s 9
0x156e1  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x156e6  stloc.s  0xA
0x156e8  ldloca.s 0xA
0x156ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x156ef  brfalse  loc_1585C
0x156f4  ldloca.s 0xA
0x156f6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x156fb  isinst   [System.Activities]System.Activities.OutArgument
0x15700  brtrue.s loc_15719
0x15702  ldloc.s  6
0x15704  ldloca.s 0xA
0x15706  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x1570b  ldloca.s 0xA
0x1570d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15712  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::Add(var<u1>, !!T0)
0x15717  br.s     loc_1572E
0x15719  ldloc.s  7
0x1571b  ldloca.s 0xA
0x1571d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15722  ldloca.s 0xA
0x15724  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15729  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::Add(var<u1>, !!T0)
0x1572e  ldloca.s 0xA
0x15730  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15735  stloc.s  0xB
0x15737  ldloca.s 0xA
0x15739  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x1573e  isinst   [System.Activities]System.Activities.OutArgument
0x15743  ldnull
0x15744  cgt.un
0x15746  ldloc.s  5
0x15748  and
0x15749  brfalse.s loc_1577C
0x1574b  ldloca.s 0xA
0x1574d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15752  ldstr    aOut// "Out"
0x15757  ldc.i4.4
0x15758  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x1575d  brfalse.s loc_1577C
0x1575f  ldloca.s 0xA
0x15761  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x15766  ldc.i4.0
0x15767  ldloca.s 0xA
0x15769  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x1576e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x15773  ldc.i4.3
0x15774  sub
0x15775  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1577a  stloc.s  0xB
0x1577c  ldarg.1
0x1577d  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item2()
0x15782  brtrue.s loc_1579C
0x15784  ldarg.1
0x15785  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item6()
0x1578a  ldc.i4.2
0x1578b  beq      loc_1585C
0x15790  ldarg.1
0x15791  callvirt instance var<u1> class [mscorlib]System.Tuple`6<class [mscorlib]System.Type, bool, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginAssemblyData, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.PluginTypeData, valuetype [mscorlib]System.Guid, int32>::get_Item6()
0x15796  ldc.i4.3
0x15797  beq      loc_1585C
0x1579c  ldloc.2
0x1579d  ldloc.s  0xB
0x1579f  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x157a4  stloc.s  0xC
0x157a6  ldloc.s  0xC
0x157a8  ldnull
0x157a9  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x157ae  brfalse  loc_1585C
0x157b3  ldloc.s  5
0x157b5  brfalse.s loc_157ED
0x157b7  ldloc.s  0xC
0x157b9  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x157be  ldloca.s 0xA
0x157c0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x157c5  callvirt instance class [mscorlib]System.Type [System.Activities]System.Activities.Argument::get_ArgumentType()
0x157ca  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x157cf  brfalse.s loc_157ED
0x157d1  ldloc.s  4
0x157d3  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Activities]System.Activities.Argument> [System.Workflow.Runtime]System.Activities.Statements.Interop::get_ActivityProperties()
0x157d8  ldloca.s 0xA
0x157da  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x157df  ldloca.s 0xA
0x157e1  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x157e6  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [System.Activities]System.Activities.Argument>::set_Item(var<u1>, !!T0)
0x157eb  br.s     loc_1585C
0x157ed  ldloc.s  0xC
0x157ef  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x157f4  ldloca.s 0xA
0x157f6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x157fb  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x15800  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x15805  brfalse.s loc_1585C
0x15807  ldloca.s 0xA
0x15809  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x1580e  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x15813  isinst   class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>
0x15818  brfalse.s loc_1584C
0x1581a  ldloca.s 0xA
0x1581c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15821  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x15826  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>
0x1582b  ldarg.0
0x1582c  ldloca.s 0xA
0x1582e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15833  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Argument::get_Expression()
0x15838  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>
0x1583d  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>::get_ExpressionText()
0x15842  call     instance string Microsoft.Crm.Workflow.Services.ActivityReferenceService::AdjustString(string expressionText)
0x15847  callvirt instance void class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>::set_ExpressionText(string)
0x1584c  ldloc.s  0xC
0x1584e  ldloc.0
0x1584f  ldloca.s 0xA
0x15851  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x15856  ldnull
0x15857  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x1585c  ldloca.s 9
0x1585e  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x15863  brtrue   loc_156DF
0x15868  leave.s  loc_15878
0x1586a  ldloca.s 9
0x1586c  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x15872  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15877  endfinally
0x15878  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x1587d  stloc.s  8
0x1587f  ldarg.3
0x15880  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::GetEnumerator()
0x15885  stloc.s  0xD
0x15887  br.s     loc_158D0
0x15889  ldloca.s 0xD
0x1588b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::get_Current()
0x15890  stloc.s  0xE
0x15892  ldloc.2
0x15893  ldloca.s 0xE
0x15895  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x1589a  callvirt instance class [mscorlib]System.Reflection.PropertyInfo [mscorlib]System.Type::GetProperty(string)
0x1589f  stloc.s  0xF
0x158a1  ldloc.s  0xF
0x158a3  ldnull
0x158a4  call     bool [mscorlib]System.Reflection.PropertyInfo::op_Inequality(class [mscorlib]System.Reflection.PropertyInfo, class [mscorlib]System.Reflection.PropertyInfo)
0x158a9  brfalse.s loc_158D0
0x158ab  ldloc.s  0xF
0x158ad  ldloc.0
0x158ae  ldloca.s 0xE
0x158b0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x158b5  ldnull
0x158b6  callvirt instance void [mscorlib]System.Reflection.PropertyInfo::SetValue(object, object, object[])
0x158bb  ldloc.s  8
0x158bd  ldloca.s 0xE
0x158bf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Key()
0x158c4  ldloca.s 0xE
0x158c6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>::get_Value()
0x158cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x158d0  ldloca.s 0xD
0x158d2  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>::MoveNext()
0x158d7  brtrue.s loc_15889
0x158d9  leave.s  loc_158E9
0x158db  ldloca.s 0xD
0x158dd  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, object>
0x158e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x158e8  endfinally
0x158e9  ldloc.3
0x158ea  brfalse.s loc_15901
0x158ec  ldloc.0
0x158ed  isinst   Microsoft.Crm.Workflow.Services.ProxyCustomActivity
0x158f2  dup
0x158f3  ldloc.s  6
0x158f5  callvirt instance void Microsoft.Crm.Workflow.Services.ProxyCustomActivity::set_ArgumentsFromReference(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> value)
0x158fa  ldloc.s  7
0x158fc  callvirt instance void Microsoft.Crm.Workflow.Services.ProxyCustomActivity::set_OutArgumentsFromReference(class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> value)
0x15901  ldloc.0
0x15902  ldarg.s  4
0x15904  callvirt instance void [System.Activities]System.Activities.Activity::set_DisplayName(string)
0x15909  ldloc.0
0x1590a  ret
```
