# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::get_CreateDocumentTemplateCommand

- ea: `0x99d30`
- end: `0x99e04`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::get_CreateDocumentTemplateCommand`
- size: `212`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x99b40`

## callees

- `0x99c30`

## string_xrefs

- `0x99d86`: `/_static/_common/scripts/RibbonActions.js`
- `0x99d38`: `Mscrm.DocumentTemplate.CreateDocumentTemplate`
- `0x99d7b`: `Mscrm.GridRibbonActions.createDocumentTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x99d30  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x99d35  stloc.0
0x99d36  ldloc.0
0x99d37  ldarg.0
0x99d38  ldstr    aMscrmDocumentt_0// "Mscrm.DocumentTemplate.CreateDocumentTe"...
0x99d3d  call     instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::NormalizeId(string id)
0x99d42  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x99d47  ldloc.0
0x99d48  ldc.i4.1
0x99d49  newarr   [mscorlib]System.String
0x99d4e  dup
0x99d4f  ldc.i4.0
0x99d50  ldstr    aMscrmExporttoe// "Mscrm.ExportToExcel.ValidForXlsxExport"
0x99d55  stelem.ref
0x99d56  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x99d5b  ldloc.0
0x99d5c  ldc.i4.0
0x99d5d  newarr   [mscorlib]System.String
0x99d62  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x99d67  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x99d6c  stloc.1
0x99d6d  ldloc.1
0x99d6e  ldc.i4.3
0x99d6f  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x99d74  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x99d79  stloc.2
0x99d7a  ldloc.2
0x99d7b  ldstr    aMscrmGridribbo_0// "Mscrm.GridRibbonActions.createDocumentT"...
0x99d80  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x99d85  ldloc.2
0x99d86  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/RibbonActions."...
0x99d8b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x99d90  ldloc.1
0x99d91  ldloc.2
0x99d92  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x99d97  ldloc.1
0x99d98  ldc.i4.4
0x99d99  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x99d9e  dup
0x99d9f  ldc.i4.0
0x99da0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99da5  dup
0x99da6  ldc.i4.s 0x11
0x99da8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99dad  stelem.ref
0x99dae  dup
0x99daf  ldc.i4.1
0x99db0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99db5  dup
0x99db6  ldc.i4.7
0x99db7  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99dbc  stelem.ref
0x99dbd  dup
0x99dbe  ldc.i4.2
0x99dbf  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99dc4  dup
0x99dc5  ldc.i4.s 0xC
0x99dc7  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99dcc  stelem.ref
0x99dcd  dup
0x99dce  ldc.i4.3
0x99dcf  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99dd4  dup
0x99dd5  ldc.i4.s 0x14
0x99dd7  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99ddc  dup
0x99ddd  ldc.i4   0x26D5
0x99de2  box      [mscorlib]System.Int32
0x99de7  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x99dec  stelem.ref
0x99ded  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99df2  ldloc.0
0x99df3  ldc.i4.1
0x99df4  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x99df9  dup
0x99dfa  ldc.i4.0
0x99dfb  ldloc.1
0x99dfc  stelem.ref
0x99dfd  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x99e02  ldloc.0
0x99e03  ret
```
