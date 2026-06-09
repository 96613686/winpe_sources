# Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetCustomProperties

- ea: `0x68df0`
- end: `0x6909d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportXml::GetCustomProperties`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x67560`

## callees

- `0x68df0`

## string_xrefs

- `0x68e68`: `OverwriteUnmanagedCustomizations`
- `0x68ecc`: `SkipProductUpdateDependencies`
- `0x69069`: `ComponentCount`

## pseudocode

```c

```

## disassembly

```asm
0x68df0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x68df5  ldarg.s  8
0x68df7  brtrue.s loc_68E00
0x68df9  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::.ctor()
0x68dfe  br.s     loc_68E07
0x68e00  ldarg.s  0xB
0x68e02  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionTelemetryHelper::GetExceptionDetails(class [mscorlib]System.Exception)
0x68e07  stloc.0
0x68e08  ldsfld   string [mscorlib]System.String::Empty
0x68e0d  stloc.1
0x68e0e  ldloc.0
0x68e0f  brfalse.s loc_68E52
0x68e11  ldloc.0
0x68e12  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ExceptionString
0x68e17  brfalse.s loc_68E52
0x68e19  ldloc.0
0x68e1a  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ExceptionString
0x68e1f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x68e24  brtrue.s loc_68E38
0x68e26  ldloc.0
0x68e27  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ExceptionString
0x68e2c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x68e31  ldc.i4   0x3A98
0x68e36  bgt.s    loc_68E40
0x68e38  ldloc.0
0x68e39  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ExceptionString
0x68e3e  br.s     loc_68E51
0x68e40  ldloc.0
0x68e41  ldfld    string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ExceptionString
0x68e46  ldc.i4.0
0x68e47  ldc.i4   0x3A98
0x68e4c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x68e51  stloc.1
0x68e52  dup
0x68e53  ldstr    aDatabaseversio// "DatabaseVersion"
0x68e58  ldarg.1
0x68e59  dup
0x68e5a  brtrue.s loc_68E62
0x68e5c  pop
0x68e5d  ldsfld   string [mscorlib]System.String::Empty
0x68e62  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68e67  dup
0x68e68  ldstr    aOverwriteunman// "OverwriteUnmanagedCustomizations"
0x68e6d  ldarg.2
0x68e6e  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68e73  stloc.2
0x68e74  ldloca.s 2
0x68e76  call     instance string [mscorlib]System.Int32::ToString()
0x68e7b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68e80  dup
0x68e81  ldstr    aPublishworkflo_1// "PublishWorkflows"
0x68e86  ldarg.3
0x68e87  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68e8c  stloc.2
0x68e8d  ldloca.s 2
0x68e8f  call     instance string [mscorlib]System.Int32::ToString()
0x68e94  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68e99  dup
0x68e9a  ldstr    aImportjobid_0// "ImportJobId"
0x68e9f  ldarga.s 4
0x68ea1  constrained. [mscorlib]System.Guid
0x68ea7  callvirt instance string [mscorlib]System.Object::ToString()
0x68eac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68eb1  dup
0x68eb2  ldstr    aConverttomanag// "ConvertToManaged"
0x68eb7  ldarg.s  5
0x68eb9  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68ebe  stloc.2
0x68ebf  ldloca.s 2
0x68ec1  call     instance string [mscorlib]System.Int32::ToString()
0x68ec6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68ecb  dup
0x68ecc  ldstr    aSkipproductupd// "SkipProductUpdateDependencies"
0x68ed1  ldarg.s  6
0x68ed3  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68ed8  stloc.2
0x68ed9  ldloca.s 2
0x68edb  call     instance string [mscorlib]System.Int32::ToString()
0x68ee0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68ee5  dup
0x68ee6  ldstr    aSolutionname_0// "SolutionName"
0x68eeb  ldarg.s  7
0x68eed  dup
0x68eee  brtrue.s loc_68EF6
0x68ef0  pop
0x68ef1  ldsfld   string [mscorlib]System.String::Empty
0x68ef6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68efb  dup
0x68efc  ldstr    aHasimportfaile// "HasImportFailed"
0x68f01  ldarg.s  8
0x68f03  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68f08  stloc.2
0x68f09  ldloca.s 2
0x68f0b  call     instance string [mscorlib]System.Int32::ToString()
0x68f10  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f15  dup
0x68f16  ldstr    aImportcontext_0// "ImportContext"
0x68f1b  ldarg.s  9
0x68f1d  dup
0x68f1e  brtrue.s loc_68F26
0x68f20  pop
0x68f21  ldsfld   string [mscorlib]System.String::Empty
0x68f26  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f2b  dup
0x68f2c  ldstr    aOperationconte_0// "OperationContext"
0x68f31  ldarg.s  0xA
0x68f33  dup
0x68f34  brtrue.s loc_68F3C
0x68f36  pop
0x68f37  ldsfld   string [mscorlib]System.String::Empty
0x68f3c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f41  dup
0x68f42  ldstr    aImportexceptio// "ImportException"
0x68f47  ldloc.1
0x68f48  dup
0x68f49  brtrue.s loc_68F51
0x68f4b  pop
0x68f4c  ldsfld   string [mscorlib]System.String::Empty
0x68f51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f56  dup
0x68f57  ldstr    aIsinternal_0// "IsInternal"
0x68f5c  ldarg.s  0xC
0x68f5e  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68f63  stloc.2
0x68f64  ldloca.s 2
0x68f66  call     instance string [mscorlib]System.Int32::ToString()
0x68f6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f70  dup
0x68f71  ldstr    aIsmanaged_0// "IsManaged"
0x68f76  ldarg.s  0xD
0x68f78  call     int32 [mscorlib]System.Convert::ToInt32(bool)
0x68f7d  stloc.2
0x68f7e  ldloca.s 2
0x68f80  call     instance string [mscorlib]System.Int32::ToString()
0x68f85  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68f8a  dup
0x68f8b  ldstr    aSolutionpackag_0// "SolutionPackageVersion"
0x68f90  ldarg.s  0xE
0x68f92  dup
0x68f93  brtrue.s loc_68F9B
0x68f95  pop
0x68f96  ldsfld   string [mscorlib]System.String::Empty
0x68f9b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68fa0  dup
0x68fa1  ldstr    aSolutionversio// "SolutionVersion"
0x68fa6  ldarg.s  0xF
0x68fa8  dup
0x68fa9  brtrue.s loc_68FB1
0x68fab  pop
0x68fac  ldsfld   string [mscorlib]System.String::Empty
0x68fb1  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68fb6  dup
0x68fb7  ldstr    aHandlertype// "HandlerType"
0x68fbc  ldarg.s  0x10
0x68fbe  dup
0x68fbf  brtrue.s loc_68FC7
0x68fc1  pop
0x68fc2  ldsfld   string [mscorlib]System.String::Empty
0x68fc7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68fcc  dup
0x68fcd  ldstr    aErrorcode// "ErrorCode"
0x68fd2  ldloc.0
0x68fd3  ldfld    int32 [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::ErrorCode
0x68fd8  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x68fdd  stloc.2
0x68fde  ldloca.s 2
0x68fe0  call     instance string [mscorlib]System.Int32::ToString()
0x68fe5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x68fea  dup
0x68feb  ldstr    aErrorcategory// "ErrorCategory"
0x68ff0  ldloc.0
0x68ff1  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x68ff6  brfalse.s loc_69005
0x68ff8  ldloc.0
0x68ff9  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x68ffe  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory::get_Category()
0x69003  brtrue.s loc_6900C
0x69005  ldsfld   string [mscorlib]System.String::Empty
0x6900a  br.s     loc_69017
0x6900c  ldloc.0
0x6900d  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x69012  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory::get_Category()
0x69017  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6901c  dup
0x6901d  ldstr    aErrorsubcatego// "ErrorSubCategory"
0x69022  ldloc.0
0x69023  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x69028  brfalse.s loc_69037
0x6902a  ldloc.0
0x6902b  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x69030  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory::get_SubCategory()
0x69035  brtrue.s loc_6903E
0x69037  ldsfld   string [mscorlib]System.String::Empty
0x6903c  br.s     loc_69049
0x6903e  ldloc.0
0x6903f  callvirt instance class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ExceptionDetails::get_Category()
0x69044  callvirt instance string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ErrorCategory::get_SubCategory()
0x69049  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6904e  dup
0x6904f  ldstr    aEntitycount// "EntityCount"
0x69054  ldarg.s  0x11
0x69056  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x6905b  stloc.2
0x6905c  ldloca.s 2
0x6905e  call     instance string [mscorlib]System.Int32::ToString()
0x69063  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69068  dup
0x69069  ldstr    aComponentcount// "ComponentCount"
0x6906e  ldarg.s  0x12
0x69070  call     int32 [mscorlib]System.Convert::ToInt32(int32)
0x69075  stloc.2
0x69076  ldloca.s 2
0x69078  call     instance string [mscorlib]System.Int32::ToString()
0x6907d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x69082  dup
0x69083  ldstr    aCustomizationf// "CustomizationFileSize"
0x69088  ldarg.s  0x13
0x6908a  call     int32 [mscorlib]System.Convert::ToInt32(int64)
0x6908f  stloc.2
0x69090  ldloca.s 2
0x69092  call     instance string [mscorlib]System.Int32::ToString()
0x69097  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x6909c  ret
```
