# Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::ToJson

- ea: `0x2ec80`
- end: `0x2ed96`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::ToJson`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x2e6c0`
- `0x2ec00`
- `0x2ec20`
- `0x2ec40`
- `0x2ec80`
- `0x30be0`
- `0x35ae0`
- `0x3a390`
- `0x3a3e0`

## string_xrefs

- `0x2ecff`: `isWebPluginActivity`

## pseudocode

```c

```

## disassembly

```asm
0x2ec80  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2ec85  stloc.0
0x2ec86  ldloc.0
0x2ec87  ldstr    asc_6E6E6// "{"
0x2ec8c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ec91  pop
0x2ec92  ldloc.0
0x2ec93  ldarg.0
0x2ec94  call     instance string Microsoft.Crm.Workflow.ObjectModel.StepBase::ToJson()
0x2ec99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ec9e  pop
0x2ec9f  ldarg.0
0x2eca0  call     instance class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x2eca5  brfalse.s loc_2ECC4
0x2eca7  ldloc.0
0x2eca8  ldstr    aActivityinfo// "activityInfo"
0x2ecad  ldarg.0
0x2ecae  call     instance class Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_ActivityInfo()
0x2ecb3  callvirt instance string Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::ToJson()
0x2ecb8  ldc.i4.1
0x2ecb9  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2ecbe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ecc3  pop
0x2ecc4  ldloc.0
0x2ecc5  ldstr    aHasoutputs// "hasOutputs"
0x2ecca  ldarg.0
0x2eccb  call     instance bool Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_HasOutputs()
0x2ecd0  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x2ecd5  ldc.i4.1
0x2ecd6  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2ecdb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ece0  pop
0x2ece1  ldloc.0
0x2ece2  ldstr    aIsinvalid// "isInvalid"
0x2ece7  ldarg.0
0x2ece8  call     instance bool Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_IsInvalid()
0x2eced  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x2ecf2  ldc.i4.1
0x2ecf3  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2ecf8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ecfd  pop
0x2ecfe  ldloc.0
0x2ecff  ldstr    aIswebpluginact// "isWebPluginActivity"
0x2ed04  ldarg.0
0x2ed05  ldfld    bool Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::isWebPluginActivity
0x2ed0a  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetJson(bool value)
0x2ed0f  ldc.i4.1
0x2ed10  call     string Microsoft.Crm.Workflow.ObjectModel.JsonBuilder::GetObjectJson(string propertyName, string propertyValueJson, bool prependComma)
0x2ed15  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ed1a  pop
0x2ed1b  ldloc.0
0x2ed1c  ldstr    asc_6B1E0// ","
0x2ed21  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ed26  pop
0x2ed27  ldloc.0
0x2ed28  ldstr    aOutputs// "\"outputs\":"
0x2ed2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ed32  pop
0x2ed33  ldloc.0
0x2ed34  ldarg.0
0x2ed35  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase> Microsoft.Crm.Workflow.ObjectModel.CustomStepBase::get_Outputs()
0x2ed3a  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__31_0
0x2ed3f  dup
0x2ed40  brtrue.s loc_2ED59
0x2ed42  pop
0x2ed43  ldsfld   class <>c <>c::<>9
0x2ed48  ldftn    instance string <>c::<ToJson>b__31_0(string property)
0x2ed4e  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x2ed53  dup
0x2ed54  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__31_0
0x2ed59  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, string> <>c::<>9__31_1
0x2ed5e  dup
0x2ed5f  brtrue.s loc_2ED78
0x2ed61  pop
0x2ed62  ldsfld   class <>c <>c::<>9
0x2ed67  ldftn    instance string <>c::<ToJson>b__31_1(class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase parameter)
0x2ed6d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, string>::.ctor(object, native int)
0x2ed72  dup
0x2ed73  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase, string> <>c::<>9__31_1
0x2ed78  call     T0x2B00002C
0x2ed7d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ed82  pop
0x2ed83  ldloc.0
0x2ed84  ldstr    asc_6E70E// "}"
0x2ed89  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2ed8e  pop
0x2ed8f  ldloc.0
0x2ed90  callvirt instance string [mscorlib]System.Object::ToString()
0x2ed95  ret
```
