# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateExression

- ea: `0x23fa0`
- end: `0x2439e`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEvaluateExression`
- size: `1022`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x22ce0`

## callees

- `0x23fa0`
- `0x243a0`
- `0x246a0`
- `0x246d0`
- `0x24ae0`
- `0x24da0`
- `0x25150`
- `0x2cd50`
- `0x2dac0`
- `0x2dae0`

## pseudocode

```c

```

## disassembly

```asm
0x23fa0  ldarg.1
0x23fa1  callvirt instance class [System.Activities]System.Activities.InArgument`1<string> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_ExpressionOperator()
0x23fa6  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x23fab  castclass class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x23fb0  stloc.0
0x23fb1  ldarg.1
0x23fb2  callvirt instance class [System.Activities]System.Activities.InArgument`1<object[]> Microsoft.Crm.Workflow.Activities.EvaluateExpression::get_Parameters()
0x23fb7  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<object[]>::get_Expression()
0x23fbc  castclass class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>
0x23fc1  ldtoken  [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator
0x23fc6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x23fcb  ldloc.0
0x23fcc  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x23fd1  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x23fd6  unbox.any [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator
0x23fdb  stloc.1
0x23fdc  callvirt instance string class [System.Activities]Microsoft.VisualBasic.Activities.VisualBasicValue`1<object[]>::get_ExpressionText()
0x23fe1  stloc.2
0x23fe2  ldarg.0
0x23fe3  ldloc.2
0x23fe4  ldc.i4.1
0x23fe5  newarr   [mscorlib]System.String
0x23fea  dup
0x23feb  ldc.i4.0
0x23fec  ldstr    asc_39DD8// ", "
0x23ff1  stelem.ref
0x23ff2  call     instance string[] Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::SplitParameters(string parametersFlat, string[] delimiters)
0x23ff7  stloc.3
0x23ff8  ldc.i4.0
0x23ff9  stloc.s  6
0x23ffb  br.s     loc_2401D
0x23ffd  ldloc.3
0x23ffe  ldloc.s  6
0x24000  ldloc.3
0x24001  ldloc.s  6
0x24003  ldelem.ref
0x24004  call     string Microsoft.Crm.Workflow.ObjectModel.XamlVBEncodeDecode::Decode(string encoded)
0x24009  stelem.ref
0x2400a  ldloc.3
0x2400b  ldloc.s  6
0x2400d  ldloc.3
0x2400e  ldloc.s  6
0x24010  ldelem.ref
0x24011  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlDecode(string)
0x24016  stelem.ref
0x24017  ldloc.s  6
0x24019  ldc.i4.1
0x2401a  add
0x2401b  stloc.s  6
0x2401d  ldloc.s  6
0x2401f  ldloc.3
0x24020  ldlen
0x24021  conv.i4
0x24022  blt.s    loc_23FFD
0x24024  ldnull
0x24025  stloc.s  4
0x24027  ldloc.1
0x24028  switch   loc_24086, loc_24086, loc_24086, loc_24086, loc_240DB, loc_24391, loc_24391, loc_24120, loc_2415D, loc_24391, loc_24391, loc_24391, loc_24391, loc_24391, loc_24391, loc_24391, loc_240DB, loc_2430B, loc_24086
0x24079  ldloc.1
0x2407a  ldc.i4.s 0x15
0x2407c  beq      loc_2434E
0x24081  br       loc_24391
0x24086  ldloc.3
0x24087  ldlen
0x24088  conv.i4
0x24089  ldc.i4.1
0x2408a  add
0x2408b  newarr   [mscorlib]System.Object
0x24090  stloc.s  5
0x24092  ldloc.s  5
0x24094  ldc.i4.0
0x24095  ldloc.1
0x24096  box      [Microsoft.Crm]Microsoft.Crm.Workflow.Activities.ExpressionOperator
0x2409b  stelem.ref
0x2409c  ldc.i4.1
0x2409d  stloc.s  0xC
0x2409f  br.s     loc_240BD
0x240a1  ldloc.s  5
0x240a3  ldloc.s  0xC
0x240a5  ldarg.0
0x240a6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x240ab  ldloc.3
0x240ac  ldloc.s  0xC
0x240ae  ldc.i4.1
0x240af  sub
0x240b0  ldelem.ref
0x240b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x240b6  stelem.ref
0x240b7  ldloc.s  0xC
0x240b9  ldc.i4.1
0x240ba  add
0x240bb  stloc.s  0xC
0x240bd  ldloc.s  0xC
0x240bf  ldloc.3
0x240c0  ldlen
0x240c1  conv.i4
0x240c2  ldc.i4.1
0x240c3  add
0x240c4  blt.s    loc_240A1
0x240c6  ldarg.0
0x240c7  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x240cc  ldc.i4.3
0x240cd  ldloc.s  5
0x240cf  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x240d4  stloc.s  4
0x240d6  br       loc_2439B
0x240db  ldloc.3
0x240dc  ldlen
0x240dd  conv.i4
0x240de  newarr   [mscorlib]System.Object
0x240e3  stloc.s  5
0x240e5  ldc.i4.0
0x240e6  stloc.s  0xD
0x240e8  br.s     loc_24104
0x240ea  ldloc.s  5
0x240ec  ldloc.s  0xD
0x240ee  ldarg.0
0x240ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x240f4  ldloc.3
0x240f5  ldloc.s  0xD
0x240f7  ldelem.ref
0x240f8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x240fd  stelem.ref
0x240fe  ldloc.s  0xD
0x24100  ldc.i4.1
0x24101  add
0x24102  stloc.s  0xD
0x24104  ldloc.s  0xD
0x24106  ldloc.3
0x24107  ldlen
0x24108  conv.i4
0x24109  blt.s    loc_240EA
0x2410b  ldarg.0
0x2410c  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24111  ldc.i4.0
0x24112  ldloc.s  5
0x24114  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24119  stloc.s  4
0x2411b  br       loc_2439B
0x24120  ldarg.0
0x24121  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x24126  ldloc.3
0x24127  ldc.i4.0
0x24128  ldelem.ref
0x24129  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2412e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24133  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x24138  stloc.s  7
0x2413a  ldarg.0
0x2413b  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x24140  ldc.i4.5
0x24141  ldc.i4.1
0x24142  newarr   [mscorlib]System.Object
0x24147  dup
0x24148  ldc.i4.0
0x24149  ldloc.s  7
0x2414b  box      [mscorlib]System.Boolean
0x24150  stelem.ref
0x24151  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCallExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.MethodCall, object[])
0x24156  stloc.s  4
0x24158  br       loc_2439B
0x2415d  ldloc.3
0x2415e  ldc.i4.0
0x2415f  ldelem.ref
0x24160  ldstr    asc_37668// "."
0x24165  ldc.i4.4
0x24166  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x2416b  ldc.i4.1
0x2416c  add
0x2416d  stloc.s  8
0x2416f  ldloc.3
0x24170  ldc.i4.0
0x24171  ldelem.ref
0x24172  ldloc.s  8
0x24174  callvirt instance string [mscorlib]System.String::Substring(int32)
0x24179  stloc.s  9
0x2417b  ldloc.3
0x2417c  ldloc.3
0x2417d  ldlen
0x2417e  conv.i4
0x2417f  ldc.i4.1
0x24180  sub
0x24181  ldelem.ref
0x24182  stloc.s  0xA
0x24184  ldarg.0
0x24185  ldloc.s  9
0x24187  ldloc.s  0xA
0x24189  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::CreateWorkflowAttributeType(string expressionTypeString, string tieBreaker)
0x2418e  stloc.s  0xB
0x24190  ldloc.s  0xB
0x24192  ldc.i4.8
0x24193  bne.un.s loc_241B9
0x24195  ldarg.0
0x24196  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2419b  ldloc.3
0x2419c  ldc.i4.1
0x2419d  ldelem.ref
0x2419e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x241a3  brfalse.s loc_241B9
0x241a5  ldarg.0
0x241a6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x241ab  ldloc.3
0x241ac  ldc.i4.1
0x241ad  ldelem.ref
0x241ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x241b3  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x241b8  ret
0x241b9  ldloc.s  0xB
0x241bb  ldc.i4.6
0x241bc  bne.un   loc_24250
0x241c1  ldloc.3
0x241c2  ldlen
0x241c3  conv.i4
0x241c4  ldc.i4.5
0x241c5  bne.un   loc_24250
0x241ca  ldc.i4.6
0x241cb  stloc.s  0xE
0x241cd  ldarg.2
0x241ce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x241d3  brtrue.s loc_241EC
0x241d5  ldarg.3
0x241d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x241db  brtrue.s loc_241EC
0x241dd  ldarg.0
0x241de  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_metadataProvider
0x241e3  ldarg.3
0x241e4  ldarg.2
0x241e5  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider::TryGetAttributeValueType(string, string)
0x241ea  stloc.s  0xE
0x241ec  ldloc.3
0x241ed  ldc.i4.2
0x241ee  ldelem.ref
0x241ef  stloc.s  0xF
0x241f1  ldloc.s  0xF
0x241f3  ldstr    asc_36150// "["
0x241f8  ldc.i4.4
0x241f9  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x241fe  brtrue.s loc_2420F
0x24200  ldloc.s  0xF
0x24202  ldstr    asc_3BC5E// "\""
0x24207  ldc.i4.4
0x24208  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2420d  brfalse.s loc_2421A
0x2420f  ldarg.0
0x24210  ldloc.3
0x24211  ldc.i4.2
0x24212  ldelem.ref
0x24213  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x24218  stloc.s  0xF
0x2421a  ldarg.0
0x2421b  ldloc.3
0x2421c  ldc.i4.1
0x2421d  ldelem.ref
0x2421e  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x24223  stloc.s  0x10
0x24225  ldarg.0
0x24226  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x2422b  ldarg.0
0x2422c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x24231  ldloc.3
0x24232  ldc.i4.3
0x24233  ldelem.ref
0x24234  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x24239  castclass [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase
0x2423e  ldloc.s  0xE
0x24240  ldloc.s  0x10
0x24242  ldloc.s  0xF
0x24244  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase, valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.WorkflowAttributeType, string, string)
0x24249  stloc.s  4
0x2424b  br       loc_2439B
0x24250  ldloc.s  0xB
0x24252  ldc.i4.s 9
0x24254  bne.un   loc_242F3
0x24259  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification>::.ctor()
0x2425e  stloc.s  0x11
0x24260  ldc.i4.1
0x24261  stloc.s  0x12
0x24263  br.s     loc_242D1
0x24265  ldarg.0
0x24266  ldfld    class Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_uiDataHelper
0x2426b  ldc.i4.2
0x2426c  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.IUIDataHelper::GetObjectName(valuetype Microsoft.Crm.Workflow.ObjectModel.ObjectName objectName)
0x24271  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::.ctor(string)
0x24276  stloc.s  0x13
0x24278  ldarg.0
0x24279  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_stepVariables
0x2427e  ldloc.3
0x2427f  ldloc.s  0x12
0x24281  ldelem.ref
0x24282  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x24287  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.LookupExpression
0x2428c  stloc.s  0x14
0x2428e  ldloc.s  0x14
0x24290  brfalse.s loc_242A2
0x24292  ldloc.s  0x13
0x24294  ldstr    aPartyid// "partyid"
0x24299  ldloc.s  0x14
0x2429b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntitySpecification::AddProperty(string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.ExpressionBase)
0x242a0  br.s     loc_242C2
0x242a2  ldloc.s  0x13
  ... truncated ...
```
