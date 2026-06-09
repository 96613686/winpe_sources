# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::GetRibbonCommandDefinition

- ea: `0x9aad0`
- end: `0x9ad9c`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::GetRibbonCommandDefinition`
- size: `716`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9a6d0`
- `0x9a890`

## callees

- `0x4fbf0`
- `0x9aad0`

## string_xrefs

- `0x9aaf8`: `Mscrm.DynamicMenu.Grid.OpenSource.`
- `0x9ac37`: `DocumentManagement.SharePointOpenLocationCommand.OpenSharePointLocation`

## pseudocode

```c

```

## disassembly

```asm
0x9aad0  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::.ctor()
0x9aad5  stloc.0
0x9aad6  ldloc.0
0x9aad7  ldc.i4.3
0x9aad8  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::ActionType
0x9aadd  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::.ctor()
0x9aae2  stloc.1
0x9aae3  ldarg.0
0x9aae4  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9aae9  stloc.3
0x9aaea  ldloc.3
0x9aaeb  ldstr    aMscrmDynamicme_18// "Mscrm.DynamicMenu.Grid.EditLocation."
0x9aaf0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9aaf5  brtrue.s loc_9AB1C
0x9aaf7  ldloc.3
0x9aaf8  ldstr    aMscrmDynamicme_19// "Mscrm.DynamicMenu.Grid.OpenSource."
0x9aafd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9ab02  brtrue   loc_9AC2B
0x9ab07  ldloc.3
0x9ab08  ldstr    aMscrmDynamicme_17// "Mscrm.DynamicMenu.Grid.ChangeLocation."
0x9ab0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9ab12  brtrue   loc_9AC95
0x9ab17  br       loc_9AD57
0x9ab1c  ldarg.2
0x9ab1d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ab22  brtrue.s loc_9AB37
0x9ab24  ldarg.3
0x9ab25  ldarg.2
0x9ab26  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::get_Item(void)
0x9ab2b  ldstr    aRelativeurl// "relativeurl"
0x9ab30  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9ab35  br.s     loc_9AB3C
0x9ab37  ldsfld   string [mscorlib]System.String::Empty
0x9ab3c  stloc.s  4
0x9ab3e  ldarg.2
0x9ab3f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ab44  brtrue.s loc_9AB59
0x9ab46  ldarg.3
0x9ab47  ldarg.2
0x9ab48  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::get_Item(void)
0x9ab4d  ldstr    aName// "name"
0x9ab52  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9ab57  br.s     loc_9AB5E
0x9ab59  ldsfld   string [mscorlib]System.String::Empty
0x9ab5e  stloc.2
0x9ab5f  ldloc.1
0x9ab60  ldstr    aWebresourceSha// "$Webresource:SharePoint_main_system_lib"...
0x9ab65  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9ab6a  ldloc.1
0x9ab6b  ldstr    aDocumentmanage_1// "DocumentManagement.SharePointAddLocatio"...
0x9ab70  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9ab75  ldloc.0
0x9ab76  ldloc.1
0x9ab77  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x9ab7c  ldloc.0
0x9ab7d  ldc.i4.5
0x9ab7e  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x9ab83  dup
0x9ab84  ldc.i4.0
0x9ab85  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ab8a  stelem.ref
0x9ab8b  dup
0x9ab8c  ldc.i4.1
0x9ab8d  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ab92  stelem.ref
0x9ab93  dup
0x9ab94  ldc.i4.2
0x9ab95  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ab9a  stelem.ref
0x9ab9b  dup
0x9ab9c  ldc.i4.3
0x9ab9d  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9aba2  stelem.ref
0x9aba3  dup
0x9aba4  ldc.i4.4
0x9aba5  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9abaa  stelem.ref
0x9abab  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abb0  ldloc.0
0x9abb1  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abb6  ldc.i4.0
0x9abb7  ldelem.ref
0x9abb8  ldc.i4.s 0xC
0x9abba  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9abbf  ldloc.0
0x9abc0  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abc5  ldc.i4.1
0x9abc6  ldelem.ref
0x9abc7  ldarg.2
0x9abc8  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9abcd  ldloc.0
0x9abce  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abd3  ldc.i4.1
0x9abd4  ldelem.ref
0x9abd5  ldc.i4.s 0x15
0x9abd7  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9abdc  ldloc.0
0x9abdd  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abe2  ldc.i4.2
0x9abe3  ldelem.ref
0x9abe4  ldloc.s  4
0x9abe6  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9abeb  ldloc.0
0x9abec  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9abf1  ldc.i4.2
0x9abf2  ldelem.ref
0x9abf3  ldc.i4.s 0x15
0x9abf5  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9abfa  ldloc.0
0x9abfb  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac00  ldc.i4.3
0x9ac01  ldelem.ref
0x9ac02  ldloc.2
0x9ac03  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9ac08  ldloc.0
0x9ac09  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac0e  ldc.i4.3
0x9ac0f  ldelem.ref
0x9ac10  ldc.i4.s 0x15
0x9ac12  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ac17  ldloc.0
0x9ac18  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac1d  ldc.i4.4
0x9ac1e  ldelem.ref
0x9ac1f  ldc.i4.s 0x11
0x9ac21  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ac26  br       loc_9AD57
0x9ac2b  ldloc.1
0x9ac2c  ldstr    aWebresourceSha// "$Webresource:SharePoint_main_system_lib"...
0x9ac31  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9ac36  ldloc.1
0x9ac37  ldstr    aDocumentmanage_2// "DocumentManagement.SharePointOpenLocati"...
0x9ac3c  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9ac41  ldloc.0
0x9ac42  ldloc.1
0x9ac43  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x9ac48  ldloc.0
0x9ac49  ldc.i4.2
0x9ac4a  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x9ac4f  dup
0x9ac50  ldc.i4.0
0x9ac51  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ac56  stelem.ref
0x9ac57  dup
0x9ac58  ldc.i4.1
0x9ac59  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ac5e  stelem.ref
0x9ac5f  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac64  ldloc.0
0x9ac65  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac6a  ldc.i4.0
0x9ac6b  ldelem.ref
0x9ac6c  ldarg.2
0x9ac6d  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9ac72  ldloc.0
0x9ac73  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac78  ldc.i4.0
0x9ac79  ldelem.ref
0x9ac7a  ldc.i4.s 0x15
0x9ac7c  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ac81  ldloc.0
0x9ac82  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ac87  ldc.i4.1
0x9ac88  ldelem.ref
0x9ac89  ldc.i4.s 0x11
0x9ac8b  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ac90  br       loc_9AD57
0x9ac95  ldarg.2
0x9ac96  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9ac9b  brtrue.s loc_9ACB0
0x9ac9d  ldarg.3
0x9ac9e  ldarg.2
0x9ac9f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::get_Item(void)
0x9aca4  ldstr    aName// "name"
0x9aca9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x9acae  br.s     loc_9ACB5
0x9acb0  ldsfld   string [mscorlib]System.String::Empty
0x9acb5  stloc.2
0x9acb6  ldloc.1
0x9acb7  ldstr    aWebresourceSha// "$Webresource:SharePoint_main_system_lib"...
0x9acbc  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::Library
0x9acc1  ldloc.1
0x9acc2  ldstr    aDocumentmanage_3// "DocumentManagement.SharePointChangeLoca"...
0x9acc7  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.JavaScriptFunctionAttributes::FunctionName
0x9accc  ldloc.0
0x9accd  ldloc.1
0x9acce  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.ActionAttributes [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Attributes
0x9acd3  ldloc.0
0x9acd4  ldc.i4.4
0x9acd5  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter
0x9acda  dup
0x9acdb  ldc.i4.0
0x9acdc  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ace1  stelem.ref
0x9ace2  dup
0x9ace3  ldc.i4.1
0x9ace4  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9ace9  stelem.ref
0x9acea  dup
0x9aceb  ldc.i4.2
0x9acec  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9acf1  stelem.ref
0x9acf2  dup
0x9acf3  ldc.i4.3
0x9acf4  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::.ctor()
0x9acf9  stelem.ref
0x9acfa  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9acff  ldloc.0
0x9ad00  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad05  ldc.i4.0
0x9ad06  ldelem.ref
0x9ad07  ldc.i4.s 0xC
0x9ad09  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ad0e  ldloc.0
0x9ad0f  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad14  ldc.i4.1
0x9ad15  ldelem.ref
0x9ad16  ldarg.2
0x9ad17  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9ad1c  ldloc.0
0x9ad1d  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad22  ldc.i4.1
0x9ad23  ldelem.ref
0x9ad24  ldc.i4.s 0x15
0x9ad26  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ad2b  ldloc.0
0x9ad2c  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad31  ldc.i4.2
0x9ad32  ldelem.ref
0x9ad33  ldloc.2
0x9ad34  stfld    object [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::Value
0x9ad39  ldloc.0
0x9ad3a  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad3f  ldc.i4.2
0x9ad40  ldelem.ref
0x9ad41  ldc.i4.s 0x15
0x9ad43  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ad48  ldloc.0
0x9ad49  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler::Parameters
0x9ad4e  ldc.i4.3
0x9ad4f  ldelem.ref
0x9ad50  ldc.i4.s 0x11
0x9ad52  stfld    valuetype [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameterType [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonParameter::ParameterType
0x9ad57  newobj   instance void [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::.ctor()
0x9ad5c  stloc.s  5
0x9ad5e  ldloc.s  5
0x9ad60  ldarg.1
0x9ad61  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Id
0x9ad66  ldloc.s  5
0x9ad68  ldc.i4.1
0x9ad69  newarr   [mscorlib]System.String
0x9ad6e  dup
0x9ad6f  ldc.i4.0
0x9ad70  ldarg.1
0x9ad71  stelem.ref
0x9ad72  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::DisplayRules
0x9ad77  ldloc.s  5
0x9ad79  ldc.i4.1
0x9ad7a  newarr   [mscorlib]System.String
0x9ad7f  dup
0x9ad80  ldc.i4.0
0x9ad81  ldarg.1
0x9ad82  stelem.ref
0x9ad83  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::EnableRules
0x9ad88  ldloc.s  5
0x9ad8a  ldc.i4.1
0x9ad8b  newarr   [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler
0x9ad90  dup
0x9ad91  ldc.i4.0
0x9ad92  ldloc.0
0x9ad93  stelem.ref
0x9ad94  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonActionHandler[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition::Actions
0x9ad99  ldloc.s  5
0x9ad9b  ret
```
