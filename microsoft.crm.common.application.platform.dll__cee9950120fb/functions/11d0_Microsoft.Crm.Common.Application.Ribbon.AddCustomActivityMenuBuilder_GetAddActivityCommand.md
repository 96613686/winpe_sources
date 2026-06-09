# Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::GetAddActivityCommand

- ea: `0x11d0`
- end: `0x13e3`
- name: `Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::GetAddActivityCommand`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10a0`

## callees

- `0x11d0`

## string_xrefs

- `0x120b`: `XrmCore.Commands.Add.AddActivityToForm`
- `0x1226`: `XrmCore.Commands.OpenObj.NewCustomActivity`
- `0x123e`: `XrmCore.Commands.Add.AddActivityFromGrid`

## pseudocode

```c

```

## disassembly

```asm
0x11d0  ldarg.0
0x11d1  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x11d6  ldstr    aMscrmDynamicme// "Mscrm.DynamicMenu.Form.AddActivity"
0x11db  ldc.i4.4
0x11dc  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x11e1  stloc.0
0x11e2  ldarg.0
0x11e3  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x11e8  ldstr    aMscrmDynamicme_0// "Mscrm.DynamicMenu.Grid.NewCustomActivit"...
0x11ed  ldc.i4.4
0x11ee  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x11f3  stloc.1
0x11f4  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x11f9  stloc.2
0x11fa  ldloc.2
0x11fb  ldc.i4.3
0x11fc  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x1201  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x1206  stloc.3
0x1207  ldloc.0
0x1208  brfalse.s loc_1222
0x120a  ldloc.3
0x120b  ldstr    aXrmcoreCommand// "XrmCore.Commands.Add.AddActivityToForm"
0x1210  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x1215  ldloc.3
0x1216  ldstr    aWebresourceMai// "$webresource:Main_system_library.js"
0x121b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x1220  br.s     loc_1253
0x1222  ldloc.1
0x1223  brfalse.s loc_123D
0x1225  ldloc.3
0x1226  ldstr    aXrmcoreCommand_0// "XrmCore.Commands.OpenObj.NewCustomActiv"...
0x122b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x1230  ldloc.3
0x1231  ldstr    aWebresourceMai// "$webresource:Main_system_library.js"
0x1236  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x123b  br.s     loc_1253
0x123d  ldloc.3
0x123e  ldstr    aXrmcoreCommand_1// "XrmCore.Commands.Add.AddActivityFromGri"...
0x1243  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x1248  ldloc.3
0x1249  ldstr    aWebresourceMai// "$webresource:Main_system_library.js"
0x124e  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x1253  ldloc.2
0x1254  ldloc.3
0x1255  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x125a  ldloc.1
0x125b  brtrue   loc_1305
0x1260  ldloc.2
0x1261  ldc.i4.3
0x1262  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x1267  dup
0x1268  ldc.i4.0
0x1269  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x126e  stelem.ref
0x126f  dup
0x1270  ldc.i4.1
0x1271  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x1276  stelem.ref
0x1277  dup
0x1278  ldc.i4.2
0x1279  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x127e  stelem.ref
0x127f  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x1284  ldloc.2
0x1285  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x128a  ldc.i4.0
0x128b  ldelem.ref
0x128c  ldarg.1
0x128d  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x1292  ldloc.2
0x1293  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x1298  ldc.i4.0
0x1299  ldelem.ref
0x129a  ldstr    aStringparamete// "StringParameter"
0x129f  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Name
0x12a4  ldloc.2
0x12a5  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12aa  ldc.i4.0
0x12ab  ldelem.ref
0x12ac  ldc.i4.s 0x15
0x12ae  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x12b3  ldloc.2
0x12b4  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12b9  ldc.i4.1
0x12ba  ldelem.ref
0x12bb  ldnull
0x12bc  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x12c1  ldloc.2
0x12c2  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12c7  ldc.i4.1
0x12c8  ldelem.ref
0x12c9  ldstr    aStringparamete// "StringParameter"
0x12ce  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Name
0x12d3  ldloc.2
0x12d4  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12d9  ldc.i4.1
0x12da  ldelem.ref
0x12db  ldc.i4.s 0x15
0x12dd  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x12e2  ldloc.2
0x12e3  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12e8  ldc.i4.2
0x12e9  ldelem.ref
0x12ea  ldc.i4.s 0x18
0x12ec  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x12f1  ldloc.2
0x12f2  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x12f7  ldc.i4.2
0x12f8  ldelem.ref
0x12f9  ldstr    aCrmparameter// "CrmParameter"
0x12fe  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Name
0x1303  br.s     loc_133A
0x1305  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x130a  stloc.s  7
0x130c  ldloc.s  7
0x130e  ldarg.1
0x130f  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x1314  ldloc.s  7
0x1316  ldstr    aStringparamete// "StringParameter"
0x131b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Name
0x1320  ldloc.s  7
0x1322  ldc.i4.s 0x15
0x1324  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x1329  ldloc.2
0x132a  ldc.i4.1
0x132b  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x1330  dup
0x1331  ldc.i4.0
0x1332  ldloc.s  7
0x1334  stelem.ref
0x1335  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x133a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x133f  stloc.s  4
0x1341  ldloc.s  4
0x1343  ldarg.2
0x1344  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x1349  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x134e  stloc.s  5
0x1350  ldloc.s  5
0x1352  ldarg.2
0x1353  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1358  ldloc.0
0x1359  brfalse.s loc_1367
0x135b  ldloc.s  5
0x135d  ldsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_formAddActivityToEntityDisplayRules
0x1362  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1367  ldloc.1
0x1368  brfalse.s loc_1376
0x136a  ldloc.s  5
0x136c  ldsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridNewCustomActivityDisplayRules
0x1371  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1376  ldloc.s  4
0x1378  ldloc.s  5
0x137a  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x137f  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x1384  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1389  stloc.s  6
0x138b  ldloc.s  6
0x138d  ldarg.2
0x138e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1393  ldloc.0
0x1394  brtrue.s loc_13B5
0x1396  ldloc.1
0x1397  brtrue.s loc_13A7
0x1399  ldloc.s  6
0x139b  ldsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridAddActivityToEntityEnableRules
0x13a0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x13a5  br.s     loc_13C1
0x13a7  ldloc.s  6
0x13a9  ldsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_gridNewCustomActivityEnableRules
0x13ae  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x13b3  br.s     loc_13C1
0x13b5  ldloc.s  6
0x13b7  ldsfld   string[] Microsoft.Crm.Common.Application.Ribbon.AddCustomActivityMenuBuilder::_formAddActivityToEntityEnableRules
0x13bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x13c1  ldloc.s  4
0x13c3  ldloc.s  6
0x13c5  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x13ca  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x13cf  ldloc.s  4
0x13d1  ldc.i4.1
0x13d2  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x13d7  dup
0x13d8  ldc.i4.0
0x13d9  ldloc.2
0x13da  stelem.ref
0x13db  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x13e0  ldloc.s  4
0x13e2  ret
```
