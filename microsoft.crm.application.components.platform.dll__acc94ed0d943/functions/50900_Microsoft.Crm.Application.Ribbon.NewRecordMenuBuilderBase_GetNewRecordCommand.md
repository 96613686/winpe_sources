# Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewRecordCommand

- ea: `0x50900`
- end: `0x50a7f`
- name: `Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::GetNewRecordCommand`
- size: `383`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x50380`

## callees

- `0x46630`
- `0x4fbf0`
- `0x50900`

## string_xrefs

- `0x5094d`: `XrmCore.Commands.Add.addActivityToFormFromsubgrid`
- `0x509e0`: `Mscrm.RibbonActions.openNewRecord`
- `0x509eb`: `/_static/_common/scripts/RibbonActions.js`

## pseudocode

```c

```

## disassembly

```asm
0x50900  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x50905  stloc.0
0x50906  ldloc.0
0x50907  ldc.i4.3
0x50908  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x5090d  ldc.i4.0
0x5090e  stloc.1
0x5090f  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x50914  stloc.2
0x50915  ldarg.0
0x50916  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x5091b  ldstr    aMscrmDynamicme_8// "Mscrm.DynamicMenu.Subgrid.NewActivityMe"...
0x50920  ldc.i4.4
0x50921  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x50926  brfalse  loc_509DF
0x5092b  ldarg.2
0x5092c  ldnull
0x5092d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Utility.Util::GetEntityMetadata(string name, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x50932  stloc.s  4
0x50934  ldloc.s  4
0x50936  brfalse.s loc_5094C
0x50938  ldloc.s  4
0x5093a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsVisibleInMobileClient()
0x5093f  brfalse.s loc_5094A
0x50941  ldloc.s  4
0x50943  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReadOnlyInMobileClient()
0x50948  brfalse.s loc_5094C
0x5094a  ldc.i4.1
0x5094b  stloc.1
0x5094c  ldloc.2
0x5094d  ldstr    aXrmcoreCommand_1// "XrmCore.Commands.Add.addActivityToFormF"...
0x50952  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x50957  ldloc.2
0x50958  ldstr    aWebresourceMai// "$webresource:Main_system_library.js"
0x5095d  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x50962  ldloc.0
0x50963  ldloc.2
0x50964  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x50969  ldloc.0
0x5096a  ldc.i4.4
0x5096b  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x50970  dup
0x50971  ldc.i4.0
0x50972  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x50977  stelem.ref
0x50978  dup
0x50979  ldc.i4.1
0x5097a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x5097f  stelem.ref
0x50980  dup
0x50981  ldc.i4.2
0x50982  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x50987  stelem.ref
0x50988  dup
0x50989  ldc.i4.3
0x5098a  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x5098f  stelem.ref
0x50990  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x50995  ldloc.0
0x50996  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x5099b  ldc.i4.0
0x5099c  ldelem.ref
0x5099d  ldarg.2
0x5099e  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x509a3  ldloc.0
0x509a4  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x509a9  ldc.i4.0
0x509aa  ldelem.ref
0x509ab  ldc.i4.s 0x15
0x509ad  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x509b2  ldloc.0
0x509b3  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x509b8  ldc.i4.1
0x509b9  ldelem.ref
0x509ba  ldc.i4.4
0x509bb  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x509c0  ldloc.0
0x509c1  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x509c6  ldc.i4.2
0x509c7  ldelem.ref
0x509c8  ldc.i4.2
0x509c9  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x509ce  ldloc.0
0x509cf  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x509d4  ldc.i4.3
0x509d5  ldelem.ref
0x509d6  ldc.i4.s 0xC
0x509d8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x509dd  br.s     loc_50A25
0x509df  ldloc.2
0x509e0  ldstr    aMscrmRibbonact_0// "Mscrm.RibbonActions.openNewRecord"
0x509e5  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x509ea  ldloc.2
0x509eb  ldstr    aStaticCommonSc_7// "/_static/_common/scripts/RibbonActions."...
0x509f0  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x509f5  ldloc.0
0x509f6  ldloc.2
0x509f7  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x509fc  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x50a01  stloc.s  5
0x50a03  ldloc.s  5
0x50a05  ldarg.2
0x50a06  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x50a0b  ldloc.s  5
0x50a0d  ldc.i4.s 0x15
0x50a0f  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x50a14  ldloc.0
0x50a15  ldc.i4.1
0x50a16  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x50a1b  dup
0x50a1c  ldc.i4.0
0x50a1d  ldloc.s  5
0x50a1f  stelem.ref
0x50a20  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x50a25  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x50a2a  stloc.3
0x50a2b  ldloc.3
0x50a2c  ldarg.3
0x50a2d  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x50a32  ldloc.3
0x50a33  ldc.i4.1
0x50a34  newarr   [mscorlib]System.String
0x50a39  dup
0x50a3a  ldc.i4.0
0x50a3b  ldarg.3
0x50a3c  stelem.ref
0x50a3d  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x50a42  ldloc.3
0x50a43  ldc.i4.1
0x50a44  newarr   [mscorlib]System.String
0x50a49  dup
0x50a4a  ldc.i4.0
0x50a4b  ldarg.3
0x50a4c  stelem.ref
0x50a4d  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x50a52  ldloc.3
0x50a53  ldc.i4.1
0x50a54  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x50a59  dup
0x50a5a  ldc.i4.0
0x50a5b  ldloc.0
0x50a5c  stelem.ref
0x50a5d  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x50a62  ldloc.1
0x50a63  brfalse.s loc_50A7D
0x50a65  ldloc.3
0x50a66  ldc.i4.2
0x50a67  newarr   [mscorlib]System.String
0x50a6c  dup
0x50a6d  ldc.i4.0
0x50a6e  ldarg.3
0x50a6f  stelem.ref
0x50a70  dup
0x50a71  ldc.i4.1
0x50a72  ldstr    aMscrmHideonmod// "Mscrm.HideOnModern"
0x50a77  stelem.ref
0x50a78  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x50a7d  ldloc.3
0x50a7e  ret
```
