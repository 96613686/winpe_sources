# Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ValidateProperty

- ea: `0x1dd80`
- end: `0x1df47`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ValidateProperty`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1df50`

## callees

- `0x1d630`
- `0x1d7e0`
- `0x1dd80`
- `0x1dfc0`

## string_xrefs

- `0x1de3e`: `The parameter name '{1}' of property {0} already exist, the names must be unique`

## pseudocode

```c

```

## disassembly

```asm
0x1dd80  ldarg.0
0x1dd81  ldstr    aProperty_0// "property"
0x1dd86  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1dd8b  ldarg.1
0x1dd8c  ldstr    aActivityparame// "activityParameters"
0x1dd91  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1dd96  ldsfld   string [mscorlib]System.String::Empty
0x1dd9b  stloc.0
0x1dd9c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1dda1  stloc.1
0x1dda2  ldarg.0
0x1dda3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1dda8  call     class [mscorlib]System.Type Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ExtractPropertyType(class [mscorlib]System.Type type)
0x1ddad  stloc.2
0x1ddae  ldloc.2
0x1ddaf  ldc.i4.1
0x1ddb0  call     bool Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ValidCustomActivityType(class [mscorlib]System.Type type, bool dotNet4)
0x1ddb5  brtrue.s loc_1DDE4
0x1ddb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ddbc  ldstr    aTheType1OfTheP// "The type {1} of the property {0} is not"...
0x1ddc1  ldc.i4.2
0x1ddc2  newarr   [mscorlib]System.Object
0x1ddc7  dup
0x1ddc8  ldc.i4.0
0x1ddc9  ldarg.0
0x1ddca  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1ddcf  stelem.ref
0x1ddd0  dup
0x1ddd1  ldc.i4.1
0x1ddd2  ldarg.0
0x1ddd3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1ddd8  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1dddd  stelem.ref
0x1ddde  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dde3  stloc.0
0x1dde4  ldarg.1
0x1dde5  stloc.3
0x1dde6  ldc.i4.0
0x1dde7  stloc.s  4
0x1dde9  br       loc_1DF35
0x1ddee  ldloc.3
0x1ddef  ldloc.s  4
0x1ddf1  ldelem.ref
0x1ddf2  stloc.s  5
0x1ddf4  ldloc.s  5
0x1ddf6  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1ddfb  brfalse.s loc_1DE0B
0x1ddfd  ldloc.s  5
0x1ddff  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1de04  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1de09  brtrue.s loc_1DE2A
0x1de0b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de10  ldstr    aTheParameterNa// "The parameter name of property {0} cann"...
0x1de15  ldc.i4.1
0x1de16  newarr   [mscorlib]System.Object
0x1de1b  dup
0x1de1c  ldc.i4.0
0x1de1d  ldarg.0
0x1de1e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1de23  stelem.ref
0x1de24  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1de29  stloc.0
0x1de2a  ldloc.1
0x1de2b  ldloc.s  5
0x1de2d  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1de32  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x1de37  brfalse.s loc_1DE62
0x1de39  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de3e  ldstr    aTheParameterNa_0// "The parameter name '{1}' of property {0"...
0x1de43  ldc.i4.2
0x1de44  newarr   [mscorlib]System.Object
0x1de49  dup
0x1de4a  ldc.i4.0
0x1de4b  ldarg.0
0x1de4c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1de51  stelem.ref
0x1de52  dup
0x1de53  ldc.i4.1
0x1de54  ldloc.s  5
0x1de56  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1de5b  stelem.ref
0x1de5c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1de61  stloc.0
0x1de62  ldloc.s  5
0x1de64  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.InputAttribute
0x1de69  brfalse.s loc_1DEC2
0x1de6b  ldarg.0
0x1de6c  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1de71  ldtoken  [System.Activities]System.Activities.InArgument
0x1de76  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1de7b  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1de80  brtrue.s loc_1DEC2
0x1de82  ldarg.0
0x1de83  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1de88  ldtoken  [System.Activities]System.Activities.InOutArgument
0x1de8d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1de92  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1de97  brtrue.s loc_1DEC2
0x1de99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de9e  ldstr    aTheParameterNa_1// "The parameter name '{1}' of property {0"...
0x1dea3  ldc.i4.2
0x1dea4  newarr   [mscorlib]System.Object
0x1dea9  dup
0x1deaa  ldc.i4.0
0x1deab  ldarg.0
0x1deac  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1deb1  stelem.ref
0x1deb2  dup
0x1deb3  ldc.i4.1
0x1deb4  ldloc.s  5
0x1deb6  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1debb  stelem.ref
0x1debc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1dec1  stloc.0
0x1dec2  ldloc.s  5
0x1dec4  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.OutputAttribute
0x1dec9  brfalse.s loc_1DF22
0x1decb  ldarg.0
0x1decc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1ded1  ldtoken  [System.Activities]System.Activities.OutArgument
0x1ded6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1dedb  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1dee0  brtrue.s loc_1DF22
0x1dee2  ldarg.0
0x1dee3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.PropertyInfo::get_PropertyType()
0x1dee8  ldtoken  [System.Activities]System.Activities.InOutArgument
0x1deed  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1def2  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1def7  brtrue.s loc_1DF22
0x1def9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1defe  ldstr    aTheParameterNa_2// "The parameter name '{1}' of property {0"...
0x1df03  ldc.i4.2
0x1df04  newarr   [mscorlib]System.Object
0x1df09  dup
0x1df0a  ldc.i4.0
0x1df0b  ldarg.0
0x1df0c  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x1df11  stelem.ref
0x1df12  dup
0x1df13  ldc.i4.1
0x1df14  ldloc.s  5
0x1df16  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1df1b  stelem.ref
0x1df1c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1df21  stloc.0
0x1df22  ldloc.1
0x1df23  ldloc.s  5
0x1df25  callvirt instance string [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ParameterAttribute::get_Name()
0x1df2a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1df2f  ldloc.s  4
0x1df31  ldc.i4.1
0x1df32  add
0x1df33  stloc.s  4
0x1df35  ldloc.s  4
0x1df37  ldloc.3
0x1df38  ldlen
0x1df39  conv.i4
0x1df3a  blt      loc_1DDEE
0x1df3f  ldloc.2
0x1df40  ldloc.0
0x1df41  newobj   instance void class [mscorlib]System.Tuple`2<class [mscorlib]System.Type, string>::.ctor(var<u1>, !!T0)
0x1df46  ret
```
