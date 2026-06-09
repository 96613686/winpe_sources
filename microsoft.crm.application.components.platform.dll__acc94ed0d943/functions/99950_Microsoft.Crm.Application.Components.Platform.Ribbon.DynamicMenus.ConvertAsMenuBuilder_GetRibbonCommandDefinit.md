# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::GetRibbonCommandDefinition

- ea: `0x99950`
- end: `0x99aac`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::GetRibbonCommandDefinition`
- size: `348`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x996d0`

## callees

- `0x99950`

## string_xrefs

- `0x9997f`: `Mscrm.LeadCommandActions.disqualifyLeadAs`
- `0x99986`: `Mscrm.LeadCommandActions.qualifyLeadAs`
- `0x9999b`: `Mscrm.LeadGridCommandActions.disqualifyLeadAs`
- `0x999a2`: `Mscrm.LeadGridCommandActions.qualifyLeadAs`

## pseudocode

```c

```

## disassembly

```asm
0x99950  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x99955  stloc.0
0x99956  ldloc.0
0x99957  ldc.i4.3
0x99958  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x9995d  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x99962  stloc.1
0x99963  ldloc.1
0x99964  ldstr    aWebresourceMar// "$webresource:MarketingSales/Lead/Lead_m"...
0x99969  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9996e  ldarg.0
0x9996f  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::_isForm
0x99974  brfalse.s loc_99992
0x99976  ldloc.1
0x99977  ldarg.0
0x99978  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::_isQualify
0x9997d  brtrue.s loc_99986
0x9997f  ldstr    aMscrmLeadcomma// "Mscrm.LeadCommandActions.disqualifyLead"...
0x99984  br.s     loc_9998B
0x99986  ldstr    aMscrmLeadcomma_0// "Mscrm.LeadCommandActions.qualifyLeadAs"
0x9998b  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x99990  br.s     loc_999AC
0x99992  ldloc.1
0x99993  ldarg.0
0x99994  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::_isQualify
0x99999  brtrue.s loc_999A2
0x9999b  ldstr    aMscrmLeadgridc// "Mscrm.LeadGridCommandActions.disqualify"...
0x999a0  br.s     loc_999A7
0x999a2  ldstr    aMscrmLeadgridc_0// "Mscrm.LeadGridCommandActions.qualifyLea"...
0x999a7  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x999ac  ldloc.0
0x999ad  ldloc.1
0x999ae  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x999b3  ldarg.0
0x999b4  ldfld    bool Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.ConvertAsMenuBuilder::_isForm
0x999b9  brfalse.s loc_999F3
0x999bb  ldloc.0
0x999bc  ldc.i4.1
0x999bd  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x999c2  dup
0x999c3  ldc.i4.0
0x999c4  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x999c9  stelem.ref
0x999ca  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x999cf  ldloc.0
0x999d0  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x999d5  ldc.i4.0
0x999d6  ldelem.ref
0x999d7  ldarg.2
0x999d8  box      [mscorlib]System.Int32
0x999dd  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x999e2  ldloc.0
0x999e3  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x999e8  ldc.i4.0
0x999e9  ldelem.ref
0x999ea  ldc.i4.s 0x14
0x999ec  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x999f1  br.s     loc_99A6D
0x999f3  ldloc.0
0x999f4  ldc.i4.4
0x999f5  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x999fa  dup
0x999fb  ldc.i4.0
0x999fc  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99a01  stelem.ref
0x99a02  dup
0x99a03  ldc.i4.1
0x99a04  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99a09  stelem.ref
0x99a0a  dup
0x99a0b  ldc.i4.2
0x99a0c  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99a11  stelem.ref
0x99a12  dup
0x99a13  ldc.i4.3
0x99a14  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x99a19  stelem.ref
0x99a1a  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a1f  ldloc.0
0x99a20  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a25  ldc.i4.0
0x99a26  ldelem.ref
0x99a27  ldc.i4.s 0xC
0x99a29  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99a2e  ldloc.0
0x99a2f  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a34  ldc.i4.1
0x99a35  ldelem.ref
0x99a36  ldc.i4.s 0x18
0x99a38  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99a3d  ldloc.0
0x99a3e  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a43  ldc.i4.2
0x99a44  ldelem.ref
0x99a45  ldc.i4.7
0x99a46  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99a4b  ldloc.0
0x99a4c  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a51  ldc.i4.3
0x99a52  ldelem.ref
0x99a53  ldarg.2
0x99a54  box      [mscorlib]System.Int32
0x99a59  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x99a5e  ldloc.0
0x99a5f  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x99a64  ldc.i4.3
0x99a65  ldelem.ref
0x99a66  ldc.i4.s 0x14
0x99a68  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x99a6d  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x99a72  stloc.2
0x99a73  ldloc.2
0x99a74  ldarg.1
0x99a75  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x99a7a  ldloc.2
0x99a7b  ldc.i4.1
0x99a7c  newarr   [mscorlib]System.String
0x99a81  dup
0x99a82  ldc.i4.0
0x99a83  ldarg.1
0x99a84  stelem.ref
0x99a85  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x99a8a  ldloc.2
0x99a8b  ldc.i4.1
0x99a8c  newarr   [mscorlib]System.String
0x99a91  dup
0x99a92  ldc.i4.0
0x99a93  ldarg.1
0x99a94  stelem.ref
0x99a95  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x99a9a  ldloc.2
0x99a9b  ldc.i4.1
0x99a9c  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x99aa1  dup
0x99aa2  ldc.i4.0
0x99aa3  ldloc.0
0x99aa4  stelem.ref
0x99aa5  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x99aaa  ldloc.2
0x99aab  ret
```
