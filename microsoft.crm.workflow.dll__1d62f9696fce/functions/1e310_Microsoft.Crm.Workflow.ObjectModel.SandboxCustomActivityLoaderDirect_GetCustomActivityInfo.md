# Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityLoaderDirect::GetCustomActivityInfo

- ea: `0x1e310`
- end: `0x1e47f`
- name: `Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityLoaderDirect::GetCustomActivityInfo`
- size: `367`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1bc90`

## callees

- `0x1d460`
- `0x1df50`
- `0x1dfc0`
- `0x1e250`
- `0x1e310`

## string_xrefs

- `0x1e326`: `publicKeyToken`
- `0x1e3dc`: `Unable to find file '{0}'. Please ensure that the custom activity is compiled against the correct version of SDK and that it does not have any external dependencies.`

## pseudocode

```c

```

## disassembly

```asm
0x1e310  ldarg.1
0x1e311  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Name()
0x1e316  ldstr    aName// "name"
0x1e31b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e320  ldarg.1
0x1e321  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_PublicKeyToken()
0x1e326  ldstr    aPublickeytoken_0// "publicKeyToken"
0x1e32b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e330  ldarg.1
0x1e331  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Culture()
0x1e336  ldstr    aCulture// "culture"
0x1e33b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e340  ldarg.1
0x1e341  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Version()
0x1e346  ldstr    aVersion// "version"
0x1e34b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e350  ldarg.1
0x1e351  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_TypeName()
0x1e356  ldstr    aTypename_0// "typeName"
0x1e35b  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ThrowIfNull(object parameter, string name)
0x1e360  ldnull
0x1e361  stloc.0
0x1e362  ldnull
0x1e363  stloc.1
0x1e364  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::.ctor()
0x1e369  stloc.2
0x1e36a  ldarg.0
0x1e36b  ldarg.1
0x1e36c  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityLoaderDirect::LoadCustomActivityAssembly(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo activityInfo)
0x1e371  stloc.1
0x1e372  leave.s  loc_1E393
0x1e374  pop
0x1e375  ldloc.2
0x1e376  ldstr    aReferencedAsse// "Referenced assembly '{0}' requires a st"...
0x1e37b  ldarg.1
0x1e37c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Name()
0x1e381  call     string [mscorlib]System.String::Format(string, object)
0x1e386  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_ValidationError(string)
0x1e38b  ldloc.2
0x1e38c  stloc.s  5
0x1e38e  leave    loc_1E47C
0x1e393  ldloc.1
0x1e394  ldnull
0x1e395  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x1e39a  brfalse.s loc_1E3AB
0x1e39c  ldloc.1
0x1e39d  ldarg.1
0x1e39e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_TypeName()
0x1e3a3  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x1e3a8  stloc.0
0x1e3a9  br.s     loc_1E3B8
0x1e3ab  ldloc.2
0x1e3ac  ldstr    aAssemblyCanNot// "Assembly can not be loaded."
0x1e3b1  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_ValidationError(string)
0x1e3b6  ldloc.2
0x1e3b7  ret
0x1e3b8  ldloc.0
0x1e3b9  ldtoken  [System.Activities]System.Activities.Activity
0x1e3be  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1e3c3  callvirt instance bool [mscorlib]System.Type::IsSubclassOf(class [mscorlib]System.Type)
0x1e3c8  stloc.3
0x1e3c9  ldloc.3
0x1e3ca  brfalse.s loc_1E405
0x1e3cc  ldloc.2
0x1e3cd  ldloc.0
0x1e3ce  call     string Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::ValidateDotNet4CustomActivity(class [mscorlib]System.Type activityType)
0x1e3d3  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_ValidationError(string)
0x1e3d8  leave.s  loc_1E405
0x1e3da  stloc.s  6
0x1e3dc  ldstr    aUnableToFindFi// "Unable to find file '{0}'. Please ensur"...
0x1e3e1  ldloc.s  6
0x1e3e3  callvirt instance string [mscorlib]System.IO.FileNotFoundException::get_FileName()
0x1e3e8  dup
0x1e3e9  brtrue.s loc_1E3F1
0x1e3eb  pop
0x1e3ec  ldsfld   string [mscorlib]System.String::Empty
0x1e3f1  call     string [mscorlib]System.String::Format(string, object)
0x1e3f6  stloc.s  7
0x1e3f8  ldloc.2
0x1e3f9  ldloc.s  7
0x1e3fb  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_ValidationError(string)
0x1e400  ldloc.2
0x1e401  stloc.s  5
0x1e403  leave.s  loc_1E47C
0x1e405  ldarg.1
0x1e406  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_ActivityName()
0x1e40b  ldarg.1
0x1e40c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_ActivityGroupName()
0x1e411  ldarg.1
0x1e412  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_TypeName()
0x1e417  ldarg.1
0x1e418  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_PluginTypeId()
0x1e41d  ldarg.1
0x1e41e  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Name()
0x1e423  ldarg.1
0x1e424  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_PublicKeyToken()
0x1e429  ldarg.1
0x1e42a  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Culture()
0x1e42f  ldarg.1
0x1e430  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::get_Version()
0x1e435  ldloc.3
0x1e436  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo::.ctor(string, string, string, valuetype [mscorlib]System.Guid, string, string, string, string, bool)
0x1e43b  stloc.s  4
0x1e43d  ldloc.2
0x1e43e  ldloc.s  4
0x1e440  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_CustomActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo)
0x1e445  ldloc.2
0x1e446  ldloc.0
0x1e447  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0x1e44c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_AssemblyQualifiedName(string)
0x1e451  ldloc.2
0x1e452  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_ValidationError()
0x1e457  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1e45c  brfalse.s loc_1E47A
0x1e45e  ldloc.2
0x1e45f  ldloc.0
0x1e460  ldc.i4.1
0x1e461  ldarg.2
0x1e462  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::GetParametersInfo(class [mscorlib]System.Type activityType, bool input, valuetype [mscorlib]System.Guid organizationId)
0x1e467  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_Inputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[])
0x1e46c  ldloc.2
0x1e46d  ldloc.0
0x1e46e  ldc.i4.0
0x1e46f  ldarg.2
0x1e470  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::GetParametersInfo(class [mscorlib]System.Type activityType, bool input, valuetype [mscorlib]System.Guid organizationId)
0x1e475  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_Outputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[])
0x1e47a  ldloc.2
0x1e47b  ret
0x1e47c  ldloc.s  5
0x1e47e  ret
```
