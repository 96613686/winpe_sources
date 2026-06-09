# Microsoft.Crm.Workflow.ObjectModel.CustomOperationUIDataGenerator::ReadInputParameters

- ea: `0x24f20`
- end: `0x2513b`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomOperationUIDataGenerator::ReadInputParameters`
- size: `539`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x24df0`
- `0x24e00`
- `0x24ee0`
- `0x24f20`

## pseudocode

```c

```

## disassembly

```asm
0x24f20  ldc.i4.0
0x24f21  stloc.0
0x24f22  ldarg.1
0x24f23  brfalse  loc_2513A
0x24f28  ldarg.1
0x24f29  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Activities]System.Activities.DynamicActivityProperty>::GetEnumerator()
0x24f2e  stloc.1
0x24f2f  br       loc_2507C
0x24f34  ldloc.1
0x24f35  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.DynamicActivityProperty>::get_Current()
0x24f3a  stloc.2
0x24f3b  ldloc.2
0x24f3c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Attribute> [System.Activities]System.Activities.DynamicActivityProperty::get_Attributes()
0x24f41  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [mscorlib]System.Attribute>::get_Count()
0x24f46  ldc.i4.0
0x24f47  ble      loc_2507C
0x24f4c  newobj   instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::.ctor()
0x24f51  stloc.3
0x24f52  ldloc.3
0x24f53  ldarg.0
0x24f54  ldloc.2
0x24f55  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentRequiredAttribute
0x24f5a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24f5f  call     T0x2B00003F
0x24f64  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Required(bool)
0x24f69  ldloc.3
0x24f6a  ldarg.0
0x24f6b  ldloc.2
0x24f6c  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentTargetAttribute
0x24f71  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24f76  call     T0x2B00003F
0x24f7b  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Target(bool)
0x24f80  ldloc.3
0x24f81  ldarg.0
0x24f82  ldloc.2
0x24f83  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDescriptionAttribute
0x24f88  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24f8d  call     T0x2B000040
0x24f92  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Description(string)
0x24f97  ldloc.3
0x24f98  ldarg.0
0x24f99  ldloc.2
0x24f9a  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirectionAttribute
0x24f9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24fa4  call     T0x2B000041
0x24fa9  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Direction(valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection)
0x24fae  ldloc.3
0x24faf  ldarg.0
0x24fb0  ldloc.2
0x24fb1  ldtoken  [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentEntityAttribute
0x24fb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x24fbb  call     T0x2B000040
0x24fc0  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_EntityName(string)
0x24fc5  ldloc.3
0x24fc6  ldloc.2
0x24fc7  callvirt instance string [System.Activities]System.Activities.DynamicActivityProperty::get_Name()
0x24fcc  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Name(string)
0x24fd1  ldloc.2
0x24fd2  callvirt instance class [mscorlib]System.Type [System.Activities]System.Activities.DynamicActivityProperty::get_Type()
0x24fd7  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x24fdc  stloc.s  4
0x24fde  ldloc.3
0x24fdf  callvirt instance valuetype [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ArgumentDirection [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Direction()
0x24fe4  brtrue.s loc_2501A
0x24fe6  ldloc.s  4
0x24fe8  isinst   [System.Activities]System.Activities.InArgument
0x24fed  stloc.s  5
0x24fef  ldloc.s  5
0x24ff1  brtrue.s loc_24FFE
0x24ff3  ldstr    aArgumentValueH// "Argument value has to be InArgument for"...
0x24ff8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x24ffd  throw
0x24ffe  ldloc.3
0x24fff  ldloc.s  5
0x25001  callvirt instance class [mscorlib]System.Type [System.Activities]System.Activities.Argument::get_ArgumentType()
0x25006  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_ArgumentType(class [mscorlib]System.Type)
0x2500b  ldloc.3
0x2500c  ldloc.s  5
0x2500e  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x25013  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_ContainerType(class [mscorlib]System.Type)
0x25018  br.s     loc_2504C
0x2501a  ldloc.s  4
0x2501c  isinst   [System.Activities]System.Activities.OutArgument
0x25021  stloc.s  6
0x25023  ldloc.s  6
0x25025  brtrue.s loc_25032
0x25027  ldstr    aArgumentValueH_0// "Argument value has to be OutArgument fo"...
0x2502c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x25031  throw
0x25032  ldloc.3
0x25033  ldloc.s  6
0x25035  callvirt instance class [mscorlib]System.Type [System.Activities]System.Activities.Argument::get_ArgumentType()
0x2503a  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_ArgumentType(class [mscorlib]System.Type)
0x2503f  ldloc.3
0x25040  ldloc.s  6
0x25042  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x25047  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_ContainerType(class [mscorlib]System.Type)
0x2504c  ldloc.3
0x2504d  ldloc.2
0x2504e  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x25053  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::set_Value(object)
0x25058  ldloc.3
0x25059  callvirt instance bool [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Target()
0x2505e  brfalse.s loc_2506B
0x25060  ldarg.0
0x25061  ldloc.3
0x25062  call     instance bool Microsoft.Crm.Workflow.ObjectModel.CustomOperationUIDataGenerator::ValidTargetArgument(class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument targetArgument)
0x25067  brfalse.s loc_2506B
0x25069  ldc.i4.1
0x2506a  stloc.0
0x2506b  ldarg.0
0x2506c  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x25071  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_Arguments()
0x25076  ldloc.3
0x25077  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::Add(var<u1>)
0x2507c  ldloc.1
0x2507d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25082  brtrue   loc_24F34
0x25087  leave.s  loc_25093
0x25089  ldloc.1
0x2508a  brfalse.s loc_25092
0x2508c  ldloc.1
0x2508d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25092  endfinally
0x25093  ldloc.0
0x25094  brtrue.s loc_250C3
0x25096  ldarg.0
0x25097  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x2509c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_PrimaryEntityName()
0x250a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x250a6  brtrue.s loc_250C3
0x250a8  ldarg.0
0x250a9  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x250ae  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_Arguments()
0x250b3  ldarg.0
0x250b4  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x250b9  callvirt instance class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_TargetArgument()
0x250be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::Add(var<u1>)
0x250c3  ldarg.0
0x250c4  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x250c9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::GetEntityTypeWorkflowArguments()
0x250ce  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::GetEnumerator()
0x250d3  stloc.s  7
0x250d5  br.s     loc_25121
0x250d7  ldloca.s 7
0x250d9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::get_Current()
0x250de  stloc.s  8
0x250e0  ldarg.0
0x250e1  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_Workflow()
0x250e6  ldloc.s  8
0x250e8  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_EntityName()
0x250ed  ldloc.s  8
0x250ef  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Name()
0x250f4  ldc.i4.1
0x250f5  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, bool)
0x250fa  stloc.s  9
0x250fc  ldarg.0
0x250fd  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::get_CreatedEntities()
0x25102  ldloc.s  8
0x25104  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_Name()
0x25109  ldstr    asc_3068C// "#"
0x2510e  ldloc.s  8
0x25110  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument::get_EntityName()
0x25115  call     string [mscorlib]System.String::Concat(string, string, string)
0x2511a  ldloc.s  9
0x2511c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x25121  ldloca.s 7
0x25123  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>::MoveNext()
0x25128  brtrue.s loc_250D7
0x2512a  leave.s  loc_2513A
0x2512c  ldloca.s 7
0x2512e  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.WorkflowArgument>
0x25134  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25139  endfinally
0x2513a  ret
```
