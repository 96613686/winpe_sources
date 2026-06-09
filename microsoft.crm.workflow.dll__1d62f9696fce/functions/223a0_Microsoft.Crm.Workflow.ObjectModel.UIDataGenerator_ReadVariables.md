# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables

- ea: `0x223a0`
- end: `0x22476`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadVariables`
- size: `214`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f710`
- `0x1f990`
- `0x21a20`
- `0x22480`

## callees

- `0x223a0`

## pseudocode

```c

```

## disassembly

```asm
0x223a0  ldarg.1
0x223a1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Activities]System.Activities.Variable>::GetEnumerator()
0x223a6  stloc.0
0x223a7  br       loc_2245E
0x223ac  ldloc.0
0x223ad  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.Variable>::get_Current()
0x223b2  stloc.1
0x223b3  ldloc.1
0x223b4  callvirt instance class [System.Activities]System.Activities.ActivityWithResult [System.Activities]System.Activities.Variable::get_Default()
0x223b9  dup
0x223ba  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<bool>
0x223bf  stloc.2
0x223c0  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>
0x223c5  stloc.3
0x223c6  ldloc.2
0x223c7  brfalse.s loc_223E7
0x223c9  ldarg.0
0x223ca  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x223cf  ldloc.1
0x223d0  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x223d5  ldloc.2
0x223d6  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<bool>::get_Value()
0x223db  box      [mscorlib]System.Boolean
0x223e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x223e5  br.s     loc_2245E
0x223e7  ldloc.3
0x223e8  brfalse.s loc_2245E
0x223ea  ldloca.s 4
0x223ec  ldloc.3
0x223ed  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>::get_Value()
0x223f2  stloc.s  6
0x223f4  ldloca.s 6
0x223f6  call     instance int32 [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan::get_Years()
0x223fb  ldloc.3
0x223fc  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>::get_Value()
0x22401  stloc.s  6
0x22403  ldloca.s 6
0x22405  call     instance int32 [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan::get_Months()
0x2240a  ldloc.3
0x2240b  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>::get_Value()
0x22410  stloc.s  6
0x22412  ldloca.s 6
0x22414  call     instance int32 [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan::get_Days()
0x22419  ldloc.3
0x2241a  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>::get_Value()
0x2241f  stloc.s  6
0x22421  ldloca.s 6
0x22423  call     instance int32 [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan::get_Hours()
0x22428  ldloc.3
0x22429  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan>::get_Value()
0x2242e  stloc.s  6
0x22430  ldloca.s 6
0x22432  call     instance int32 [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.XrmTimeSpan::get_Minutes()
0x22437  call     instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.CrmTimeSpan::.ctor(int32, int32, int32, int32, int32)
0x2243c  ldarg.0
0x2243d  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22442  ldloc.s  4
0x22444  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.TimeSpanExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Workflow.CrmTimeSpan)
0x22449  stloc.s  5
0x2244b  ldarg.0
0x2244c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x22451  ldloc.1
0x22452  callvirt instance string [System.Activities]System.Activities.Variable::get_Name()
0x22457  ldloc.s  5
0x22459  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2245e  ldloc.0
0x2245f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22464  brtrue   loc_223AC
0x22469  leave.s  loc_22475
0x2246b  ldloc.0
0x2246c  brfalse.s loc_22474
0x2246e  ldloc.0
0x2246f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x22474  endfinally
0x22475  ret
```
