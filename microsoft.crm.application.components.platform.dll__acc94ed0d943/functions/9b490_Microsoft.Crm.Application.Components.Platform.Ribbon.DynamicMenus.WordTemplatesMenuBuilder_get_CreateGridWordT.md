# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.WordTemplatesMenuBuilder::get_CreateGridWordTemplateCommand

- ea: `0x9b490`
- end: `0x9b556`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.WordTemplatesMenuBuilder::get_CreateGridWordTemplateCommand`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x9b3a0`

## string_xrefs

- `0x9b4d8`: `/_static/_common/scripts/RibbonActions.js`
- `0x9b497`: `Mscrm.WordTemplate.CreateWordTemplate.Grid`
- `0x9b4cd`: `Mscrm.GridRibbonActions.createWordTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9b490  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x9b495  stloc.0
0x9b496  ldloc.0
0x9b497  ldstr    aMscrmWordtempl_0// "Mscrm.WordTemplate.CreateWordTemplate.G"...
0x9b49c  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9b4a1  ldloc.0
0x9b4a2  ldc.i4.0
0x9b4a3  newarr   [mscorlib]System.String
0x9b4a8  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x9b4ad  ldloc.0
0x9b4ae  ldc.i4.0
0x9b4af  newarr   [mscorlib]System.String
0x9b4b4  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x9b4b9  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x9b4be  stloc.1
0x9b4bf  ldloc.1
0x9b4c0  ldc.i4.3
0x9b4c1  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x9b4c6  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x9b4cb  stloc.2
0x9b4cc  ldloc.2
0x9b4cd  ldstr    aMscrmGridribbo_3// "Mscrm.GridRibbonActions.createWordTempl"...
0x9b4d2  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9b4d7  ldloc.2
0x9b4d8  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/RibbonActions."...
0x9b4dd  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9b4e2  ldloc.1
0x9b4e3  ldloc.2
0x9b4e4  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x9b4e9  ldloc.1
0x9b4ea  ldc.i4.4
0x9b4eb  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x9b4f0  dup
0x9b4f1  ldc.i4.0
0x9b4f2  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b4f7  dup
0x9b4f8  ldc.i4.s 0x11
0x9b4fa  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b4ff  stelem.ref
0x9b500  dup
0x9b501  ldc.i4.1
0x9b502  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b507  dup
0x9b508  ldc.i4.7
0x9b509  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b50e  stelem.ref
0x9b50f  dup
0x9b510  ldc.i4.2
0x9b511  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b516  dup
0x9b517  ldc.i4.s 0xC
0x9b519  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b51e  stelem.ref
0x9b51f  dup
0x9b520  ldc.i4.3
0x9b521  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b526  dup
0x9b527  ldc.i4.s 0x14
0x9b529  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b52e  dup
0x9b52f  ldc.i4   0x26D5
0x9b534  box      [mscorlib]System.Int32
0x9b539  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9b53e  stelem.ref
0x9b53f  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9b544  ldloc.0
0x9b545  ldc.i4.1
0x9b546  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x9b54b  dup
0x9b54c  ldc.i4.0
0x9b54d  ldloc.1
0x9b54e  stelem.ref
0x9b54f  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x9b554  ldloc.0
0x9b555  ret
```
