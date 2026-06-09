# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GenerateWorkflowObjectModelFromFormXml

- ea: `0x1e970`
- end: `0x1ea1b`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::GenerateWorkflowObjectModelFromFormXml`
- size: `171`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1e6b0`
- `0x1e700`
- `0x1e730`

## callees

- `0xf2d0`
- `0x1e970`
- `0x25180`
- `0x251b0`

## pseudocode

```c

```

## disassembly

```asm
0x1e970  ldarg.1
0x1e971  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e976  brfalse.s loc_1E979
0x1e978  ret
0x1e979  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep>::.ctor()
0x1e97e  stloc.0
0x1e97f  ldarg.0
0x1e980  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1e985  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepDictionary [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep::get_StepDictionary()
0x1e98a  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::GetEnumerator()
0x1e98f  stloc.2
0x1e990  br.s     loc_1E9D8
0x1e992  ldloca.s 2
0x1e994  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Current()
0x1e999  stloc.3
0x1e99a  ldloca.s 3
0x1e99c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::get_Value()
0x1e9a1  isinst   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep
0x1e9a6  stloc.s  4
0x1e9a8  ldloc.s  4
0x1e9aa  brfalse.s loc_1E9D8
0x1e9ac  ldloc.s  4
0x1e9ae  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep::get_PageLayoutId()
0x1e9b3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e9b8  brtrue.s loc_1E9D8
0x1e9ba  ldloc.0
0x1e9bb  ldloc.s  4
0x1e9bd  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep::get_PageLayoutId()
0x1e9c2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep>::ContainsKey(var<u1>)
0x1e9c7  brtrue.s loc_1E9D8
0x1e9c9  ldloc.0
0x1e9ca  ldloc.s  4
0x1e9cc  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep::get_PageLayoutId()
0x1e9d1  ldloc.s  4
0x1e9d3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep>::set_Item(var<u1>, !!T0)
0x1e9d8  ldloca.s 2
0x1e9da  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>::MoveNext()
0x1e9df  brtrue.s loc_1E992
0x1e9e1  leave.s  loc_1E9F1
0x1e9e3  ldloca.s 2
0x1e9e5  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.StepBase>
0x1e9eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e9f0  endfinally
0x1e9f1  ldarg.0
0x1e9f2  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x1e9f7  ldarg.0
0x1e9f8  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Workflow.ObjectModel.IServerMetadataProvider Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_servermetadataProvider
0x1e9fd  newobj   instance void Microsoft.Crm.Workflow.Utility.WorkflowRelationshipResolver::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep workflow, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Workflow.ObjectModel.IServerMetadataProvider serverMetadataProvider)
0x1ea02  stloc.1
0x1ea03  ldarg.1
0x1ea04  ldloc.0
0x1ea05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x1ea0a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x1ea0f  ldloc.1
0x1ea10  newobj   instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::.ctor(string formXml, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.PageStep> pages, int32 languageCode, class Microsoft.Crm.Workflow.Utility.WorkflowRelationshipResolver workflowRelationshipResolver)
0x1ea15  callvirt instance void Microsoft.Crm.Workflow.ObjectModel.FormXmlParser::Parse()
0x1ea1a  ret
```
