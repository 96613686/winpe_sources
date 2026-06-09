# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInputParameters

- ea: `0x1eb50`
- end: `0x1edbe`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadInputParameters`
- size: `622`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1ea20`

## callees

- `0x1eb50`

## pseudocode

```c

```

## disassembly

```asm
0x1eb50  ldarg.1
0x1eb51  brfalse  loc_1EDBD
0x1eb56  ldarg.1
0x1eb57  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Activities]System.Activities.DynamicActivityProperty>::GetEnumerator()
0x1eb5c  stloc.0
0x1eb5d  br       loc_1EDA6
0x1eb62  ldloc.0
0x1eb63  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Activities]System.Activities.DynamicActivityProperty>::get_Current()
0x1eb68  stloc.1
0x1eb69  ldloc.1
0x1eb6a  callvirt instance string [System.Activities]System.Activities.DynamicActivityProperty::get_Name()
0x1eb6f  ldstr    aUiscriptInput// "UIScript_Input_"
0x1eb74  ldc.i4.4
0x1eb75  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1eb7a  brfalse  loc_1EDA6
0x1eb7f  ldloc.1
0x1eb80  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x1eb85  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1eb8a  stloc.2
0x1eb8b  ldloc.2
0x1eb8c  ldtoken  class [System.Activities]System.Activities.InArgument`1<string>
0x1eb91  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1eb96  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1eb9b  brfalse.s loc_1EBE8
0x1eb9d  ldloc.1
0x1eb9e  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x1eba3  castclass class [System.Activities]System.Activities.InArgument`1<string>
0x1eba8  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<string>::get_Expression()
0x1ebad  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<string>
0x1ebb2  stloc.3
0x1ebb3  ldloc.3
0x1ebb4  ldnull
0x1ebb5  cgt.un
0x1ebb7  ldstr    aInputArgumentV// "Input argument value is missing"
0x1ebbc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ebc1  ldarg.0
0x1ebc2  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ebc7  ldloc.1
0x1ebc8  callvirt instance string [System.Activities]System.Activities.DynamicActivityProperty::get_Name()
0x1ebcd  ldtoken  [mscorlib]System.String
0x1ebd2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ebd7  ldloc.3
0x1ebd8  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<string>::get_Value()
0x1ebdd  ldc.i4.1
0x1ebde  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1ebe3  br       loc_1EDA6
0x1ebe8  ldloc.2
0x1ebe9  ldtoken  class [System.Activities]System.Activities.InArgument`1<float64>
0x1ebee  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ebf3  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1ebf8  brfalse.s loc_1EC4D
0x1ebfa  ldloc.1
0x1ebfb  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x1ec00  castclass class [System.Activities]System.Activities.InArgument`1<float64>
0x1ec05  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<float64>::get_Expression()
0x1ec0a  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<float64>
0x1ec0f  stloc.s  4
0x1ec11  ldloc.s  4
0x1ec13  ldnull
0x1ec14  cgt.un
0x1ec16  ldstr    aInputArgumentV// "Input argument value is missing"
0x1ec1b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ec20  ldarg.0
0x1ec21  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ec26  ldloc.1
0x1ec27  callvirt instance string [System.Activities]System.Activities.DynamicActivityProperty::get_Name()
0x1ec2c  ldtoken  [mscorlib]System.Double
0x1ec31  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ec36  ldloc.s  4
0x1ec38  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<float64>::get_Value()
0x1ec3d  box      [mscorlib]System.Double
0x1ec42  ldc.i4.1
0x1ec43  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1ec48  br       loc_1EDA6
0x1ec4d  ldloc.2
0x1ec4e  ldtoken  class [System.Activities]System.Activities.InArgument`1<int32>
0x1ec53  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ec58  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1ec5d  brfalse.s loc_1ECB2
0x1ec5f  ldloc.1
0x1ec60  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x1ec65  castclass class [System.Activities]System.Activities.InArgument`1<int32>
0x1ec6a  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<int32>::get_Expression()
0x1ec6f  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<int32>
0x1ec74  stloc.s  5
0x1ec76  ldloc.s  5
0x1ec78  ldnull
0x1ec79  cgt.un
0x1ec7b  ldstr    aInputArgumentV// "Input argument value is missing"
0x1ec80  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1ec85  ldarg.0
0x1ec86  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ec8b  ldloc.1
0x1ec8c  callvirt instance string [System.Activities]System.Activities.DynamicActivityProperty::get_Name()
0x1ec91  ldtoken  [mscorlib]System.Int32
0x1ec96  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ec9b  ldloc.s  5
0x1ec9d  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<int32>::get_Value()
0x1eca2  box      [mscorlib]System.Int32
0x1eca7  ldc.i4.1
0x1eca8  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(string, class [mscorlib]System.Type, object, bool)
0x1ecad  br       loc_1EDA6
0x1ecb2  ldloc.2
0x1ecb3  ldtoken  class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1ecb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1ecbd  callvirt instance bool [mscorlib]System.Type::Equals(class [mscorlib]System.Type)
0x1ecc2  brfalse  loc_1ED95
0x1ecc7  ldloc.1
0x1ecc8  callvirt instance object [System.Activities]System.Activities.DynamicActivityProperty::get_Value()
0x1eccd  castclass class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1ecd2  callvirt instance class [System.Activities]System.Activities.Activity`1<var<u1>> class [System.Activities]System.Activities.InArgument`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Expression()
0x1ecd7  isinst   class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>
0x1ecdc  stloc.s  6
0x1ecde  ldloc.s  6
0x1ece0  ldnull
0x1ece1  cgt.un
0x1ece3  ldstr    aInputArgumentD// "Input argument definition information i"...
0x1ece8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1eced  ldloc.s  6
0x1ecef  callvirt instance var<u1> class [System.Activities]System.Activities.Expressions.Literal`1<valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition>::get_Value()
0x1ecf4  stloc.s  7
0x1ecf6  ldarg.0
0x1ecf7  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ecfc  ldloc.s  7
0x1ecfe  ldc.i4.1
0x1ecff  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::AddVariable(valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition, bool)
0x1ed04  ldloca.s 7
0x1ed06  call     instance int32 [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_DataType()
0x1ed0b  ldc.i4.5
0x1ed0c  bne.un   loc_1EDA6
0x1ed11  ldloca.s 7
0x1ed13  call     instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_IsMetadataBound()
0x1ed18  brfalse  loc_1EDA6
0x1ed1d  ldarg.0
0x1ed1e  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ed23  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_MetadataProvider()
0x1ed28  ldloca.s 7
0x1ed2a  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_MetadataSource()
0x1ed2f  stloc.s  0xA
0x1ed31  ldloca.s 0xA
0x1ed33  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_EntityName()
0x1ed38  ldloca.s 7
0x1ed3a  call     instance valuetype [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_MetadataSource()
0x1ed3f  stloc.s  0xA
0x1ed41  ldloca.s 0xA
0x1ed43  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.MetadataSource::get_AttributeName()
0x1ed48  callvirt instance string[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IMetadataProvider::GetEntitiesReferencedByLookup(string, string)
0x1ed4d  stloc.s  8
0x1ed4f  ldc.i4.0
0x1ed50  stloc.s  9
0x1ed52  br.s     loc_1ED8B
0x1ed54  ldloc.s  8
0x1ed56  ldloc.s  9
0x1ed58  ldelem.ref
0x1ed59  stloc.s  0xB
0x1ed5b  ldarg.0
0x1ed5c  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1ed61  ldloc.s  0xB
0x1ed63  ldloca.s 7
0x1ed65  call     instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.IdentifierDefinition::get_Name()
0x1ed6a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x1ed6f  stloc.s  0xC
0x1ed71  ldarg.0
0x1ed72  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x1ed77  ldloc.s  0xC
0x1ed79  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::get_ParameterName()
0x1ed7e  ldloc.s  0xC
0x1ed80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::Add(var<u1>, !!T0)
0x1ed85  ldloc.s  9
0x1ed87  ldc.i4.1
0x1ed88  add
0x1ed89  stloc.s  9
0x1ed8b  ldloc.s  9
0x1ed8d  ldloc.s  8
0x1ed8f  ldlen
0x1ed90  conv.i4
0x1ed91  blt.s    loc_1ED54
0x1ed93  br.s     loc_1EDA6
0x1ed95  ldstr    aUnsupportedTyp_1// "Unsupported type of input argument in t"...
0x1ed9a  ldloc.2
0x1ed9b  call     string [mscorlib]System.String::Concat(object, object)
0x1eda0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmNotSupportedException::.ctor(string)
0x1eda5  throw
0x1eda6  ldloc.0
0x1eda7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1edac  brtrue   loc_1EB62
0x1edb1  leave.s  loc_1EDBD
0x1edb3  ldloc.0
0x1edb4  brfalse.s loc_1EDBC
0x1edb6  ldloc.0
0x1edb7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1edbc  endfinally
0x1edbd  ret
```
