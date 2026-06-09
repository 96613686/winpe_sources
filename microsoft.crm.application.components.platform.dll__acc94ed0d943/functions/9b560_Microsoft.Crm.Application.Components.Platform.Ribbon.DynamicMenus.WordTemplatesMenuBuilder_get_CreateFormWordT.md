# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.WordTemplatesMenuBuilder::get_CreateFormWordTemplateCommand

- ea: `0x9b560`
- end: `0x9b625`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.WordTemplatesMenuBuilder::get_CreateFormWordTemplateCommand`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x9b3a0`

## string_xrefs

- `0x9b5a8`: `/_static/_common/scripts/RibbonActions.js`
- `0x9b567`: `Mscrm.WordTemplate.CreateWordTemplate.Form`
- `0x9b59d`: `Mscrm.GridRibbonActions.createWordTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x9b560  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x9b565  stloc.0
0x9b566  ldloc.0
0x9b567  ldstr    aMscrmWordtempl// "Mscrm.WordTemplate.CreateWordTemplate.F"...
0x9b56c  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9b571  ldloc.0
0x9b572  ldc.i4.0
0x9b573  newarr   [mscorlib]System.String
0x9b578  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x9b57d  ldloc.0
0x9b57e  ldc.i4.0
0x9b57f  newarr   [mscorlib]System.String
0x9b584  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x9b589  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x9b58e  stloc.1
0x9b58f  ldloc.1
0x9b590  ldc.i4.3
0x9b591  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x9b596  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x9b59b  stloc.2
0x9b59c  ldloc.2
0x9b59d  ldstr    aMscrmGridribbo_3// "Mscrm.GridRibbonActions.createWordTempl"...
0x9b5a2  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9b5a7  ldloc.2
0x9b5a8  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/RibbonActions."...
0x9b5ad  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9b5b2  ldloc.1
0x9b5b3  ldloc.2
0x9b5b4  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x9b5b9  ldloc.1
0x9b5ba  ldc.i4.4
0x9b5bb  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x9b5c0  dup
0x9b5c1  ldc.i4.0
0x9b5c2  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b5c7  dup
0x9b5c8  ldc.i4.s 0x11
0x9b5ca  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b5cf  stelem.ref
0x9b5d0  dup
0x9b5d1  ldc.i4.1
0x9b5d2  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b5d7  dup
0x9b5d8  ldc.i4.1
0x9b5d9  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b5de  stelem.ref
0x9b5df  dup
0x9b5e0  ldc.i4.2
0x9b5e1  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b5e6  dup
0x9b5e7  ldc.i4.5
0x9b5e8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b5ed  stelem.ref
0x9b5ee  dup
0x9b5ef  ldc.i4.3
0x9b5f0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9b5f5  dup
0x9b5f6  ldc.i4.s 0x14
0x9b5f8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9b5fd  dup
0x9b5fe  ldc.i4   0x26D5
0x9b603  box      [mscorlib]System.Int32
0x9b608  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9b60d  stelem.ref
0x9b60e  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9b613  ldloc.0
0x9b614  ldc.i4.1
0x9b615  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x9b61a  dup
0x9b61b  ldc.i4.0
0x9b61c  ldloc.1
0x9b61d  stelem.ref
0x9b61e  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x9b623  ldloc.0
0x9b624  ret
```
