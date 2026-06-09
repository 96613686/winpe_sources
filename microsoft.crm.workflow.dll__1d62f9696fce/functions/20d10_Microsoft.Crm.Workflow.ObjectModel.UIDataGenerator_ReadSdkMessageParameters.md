# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSdkMessageParameters

- ea: `0x20d10`
- end: `0x20f35`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadSdkMessageParameters`
- size: `549`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x20bc0`

## callees

- `0xfb90`
- `0x20d10`
- `0x2e2a0`
- `0x2e2c0`
- `0x2e2e0`
- `0x2e2f0`

## pseudocode

```c

```

## disassembly

```asm
0x20d10  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::.ctor()
0x20d15  stloc.0
0x20d16  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::.ctor()
0x20d1b  stloc.1
0x20d1c  ldarg.1
0x20d1d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Arguments()
0x20d22  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [System.Activities]System.Activities.Argument>::GetEnumerator()
0x20d27  stloc.2
0x20d28  br       loc_20EE8
0x20d2d  ldloca.s 2
0x20d2f  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::get_Current()
0x20d34  stloc.3
0x20d35  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo::.ctor()
0x20d3a  stloc.s  4
0x20d3c  ldloc.s  4
0x20d3e  ldloca.s 3
0x20d40  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x20d45  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Name(string)
0x20d4a  ldloc.s  4
0x20d4c  ldloca.s 3
0x20d4e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Key()
0x20d53  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_DependencyPropertyName(string)
0x20d58  ldloc.s  4
0x20d5a  ldloca.s 3
0x20d5c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x20d61  callvirt instance class [mscorlib]System.Type [System.Activities]System.Activities.Argument::get_ArgumentType()
0x20d66  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Type(class [mscorlib]System.Type)
0x20d6b  ldloc.s  4
0x20d6d  ldarg.1
0x20d6e  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageName()
0x20d73  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo::set_SdkMessageName(string)
0x20d78  ldloca.s 3
0x20d7a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [System.Activities]System.Activities.Argument>::get_Value()
0x20d7f  callvirt instance valuetype [System.Activities]System.Activities.ArgumentDirection [System.Activities]System.Activities.Argument::get_Direction()
0x20d84  stloc.s  5
0x20d86  ldloc.s  4
0x20d88  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x20d8d  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x20d92  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20d97  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20d9c  brfalse.s loc_20DE4
0x20d9e  ldsfld   string [mscorlib]System.String::Empty
0x20da3  stloc.s  6
0x20da5  ldloc.s  4
0x20da7  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo::get_SdkMessageName()
0x20dac  ldstr    asc_3A406// "_"
0x20db1  ldloc.s  4
0x20db3  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x20db8  call     string [mscorlib]System.String::Concat(string, string, string)
0x20dbd  stloc.s  7
0x20dbf  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessagePicklistControlHelper::get_PicklistDictionary()
0x20dc4  ldloc.s  7
0x20dc6  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x20dcb  brfalse.s loc_20DDB
0x20dcd  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Workflow.Utility.SdkMessagePicklistControlHelper::get_PicklistDictionary()
0x20dd2  ldloc.s  7
0x20dd4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x20dd9  stloc.s  6
0x20ddb  ldloc.s  4
0x20ddd  ldloc.s  6
0x20ddf  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_AttributeName(string)
0x20de4  ldloc.s  4
0x20de6  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x20deb  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x20df0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20df5  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20dfa  brtrue.s loc_20E17
0x20dfc  ldloc.s  4
0x20dfe  callvirt instance class [mscorlib]System.Type [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Type()
0x20e03  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x20e08  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x20e0d  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x20e12  brfalse  loc_20EAC
0x20e17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20e1c  ldstr    a01Argumententi// "{0}#{1}ArgumentEntityType"
0x20e21  ldc.i4.2
0x20e22  newarr   [mscorlib]System.Object
0x20e27  dup
0x20e28  ldc.i4.0
0x20e29  ldloc.s  4
0x20e2b  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_Name()
0x20e30  stelem.ref
0x20e31  dup
0x20e32  ldc.i4.1
0x20e33  ldloc.s  5
0x20e35  box      [System.Activities]System.Activities.ArgumentDirection
0x20e3a  stelem.ref
0x20e3b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x20e40  stloc.s  8
0x20e42  ldarg.1
0x20e43  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x20e48  ldloc.s  8
0x20e4a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x20e4f  brfalse.s loc_20E9A
0x20e51  ldarg.1
0x20e52  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x20e57  ldloc.s  8
0x20e59  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x20e5e  isinst   class [mscorlib]System.Collections.ObjectModel.Collection`1<string>
0x20e63  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::GetEnumerator()
0x20e68  stloc.s  9
0x20e6a  br.s     loc_20E83
0x20e6c  ldloc.s  9
0x20e6e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x20e73  stloc.s  0xA
0x20e75  ldloc.s  4
0x20e77  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x20e7c  ldloc.s  0xA
0x20e7e  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x20e83  ldloc.s  9
0x20e85  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20e8a  brtrue.s loc_20E6C
0x20e8c  leave.s  loc_20EAC
0x20e8e  ldloc.s  9
0x20e90  brfalse.s loc_20E99
0x20e92  ldloc.s  9
0x20e94  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20e99  endfinally
0x20e9a  ldloc.s  4
0x20e9c  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<string> [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_EntityNames()
0x20ea1  ldarg.1
0x20ea2  callvirt instance string Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_SdkMessageEntityName()
0x20ea7  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x20eac  ldloc.s  5
0x20eae  brtrue.s loc_20EE0
0x20eb0  ldarg.1
0x20eb1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.Workflow.Activities.InvokeSdkMessageActivity::get_Properties()
0x20eb6  ldloc.s  4
0x20eb8  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::get_DependencyPropertyName()
0x20ebd  ldstr    aInargumentrequ// "#InArgumentRequired"
0x20ec2  call     string [mscorlib]System.String::Concat(string, string)
0x20ec7  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x20ecc  brfalse.s loc_20ED6
0x20ece  ldloc.s  4
0x20ed0  ldc.i4.1
0x20ed1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase::set_Required(bool)
0x20ed6  ldloc.0
0x20ed7  ldloc.s  4
0x20ed9  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::Add(var<u1>)
0x20ede  br.s     loc_20EE8
0x20ee0  ldloc.1
0x20ee1  ldloc.s  4
0x20ee3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::Add(var<u1>)
0x20ee8  ldloca.s 2
0x20eea  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>::MoveNext()
0x20eef  brtrue   loc_20D2D
0x20ef4  leave.s  loc_20F04
0x20ef6  ldloca.s 2
0x20ef8  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class [System.Activities]System.Activities.Argument>
0x20efe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20f03  endfinally
0x20f04  ldarg.2
0x20f05  ldloc.0
0x20f06  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::get_Count()
0x20f0b  brfalse.s loc_20F15
0x20f0d  ldloc.0
0x20f0e  call     T0x2B00001D
0x20f13  br.s     loc_20F1B
0x20f15  ldc.i4.0
0x20f16  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo
0x20f1b  stind.ref
0x20f1c  ldarg.3
0x20f1d  ldloc.1
0x20f1e  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo>::get_Count()
0x20f23  brfalse.s loc_20F2D
0x20f25  ldloc.1
0x20f26  call     T0x2B00001D
0x20f2b  br.s     loc_20F33
0x20f2d  ldc.i4.0
0x20f2e  newarr   [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.InvokeSdkMessageParameterInfo
0x20f33  stind.ref
0x20f34  ret
```
