# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::get_OpenDocumentTemplateInExcelOnlineCommand

- ea: `0x99e10`
- end: `0x99ead`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::get_OpenDocumentTemplateInExcelOnlineCommand`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x99b40`

## callees

- `0x99c30`

## string_xrefs

- `0x99e5e`: `/_static/_common/scripts/RibbonActions.js`
- `0x99e18`: `Mscrm.DocumentTemplate.OpenDocumentTemplateInExcelOnline`
- `0x99e53`: `Mscrm.GridRibbonActions.openDocumentTemplateInExcelOnline`

## pseudocode

```c

```

## disassembly

```asm
0x99e10  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x99e15  stloc.0
0x99e16  ldloc.0
0x99e17  ldarg.0
0x99e18  ldstr    aMscrmDocumentt_1// "Mscrm.DocumentTemplate.OpenDocumentTemp"...
0x99e1d  call     instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.DocumentTemplatesMenuBuilder::NormalizeId(string id)
0x99e22  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x99e27  ldloc.0
0x99e28  ldc.i4.0
0x99e29  newarr   [mscorlib]System.String
0x99e2e  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x99e33  ldloc.0
0x99e34  ldc.i4.0
0x99e35  newarr   [mscorlib]System.String
0x99e3a  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x99e3f  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x99e44  stloc.1
0x99e45  ldloc.1
0x99e46  ldc.i4.3
0x99e47  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x99e4c  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x99e51  stloc.2
0x99e52  ldloc.2
0x99e53  ldstr    aMscrmGridribbo_1// "Mscrm.GridRibbonActions.openDocumentTem"...
0x99e58  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x99e5d  ldloc.2
0x99e5e  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/RibbonActions."...
0x99e63  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x99e68  ldloc.1
0x99e69  ldloc.2
0x99e6a  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x99e6f  ldloc.1
0x99e70  ldc.i4.2
0x99e71  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x99e76  dup
0x99e77  ldc.i4.0
0x99e78  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99e7d  dup
0x99e7e  ldc.i4.s 0x11
0x99e80  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99e85  stelem.ref
0x99e86  dup
0x99e87  ldc.i4.1
0x99e88  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99e8d  dup
0x99e8e  ldc.i4.s 0xC
0x99e90  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99e95  stelem.ref
0x99e96  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99e9b  ldloc.0
0x99e9c  ldc.i4.1
0x99e9d  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x99ea2  dup
0x99ea3  ldc.i4.0
0x99ea4  ldloc.1
0x99ea5  stelem.ref
0x99ea6  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x99eab  ldloc.0
0x99eac  ret
```
