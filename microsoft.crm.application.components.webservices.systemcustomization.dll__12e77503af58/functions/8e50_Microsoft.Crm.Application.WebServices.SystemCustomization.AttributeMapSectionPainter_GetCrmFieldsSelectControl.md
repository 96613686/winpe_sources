# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::GetCrmFieldsSelectControl

- ea: `0x8e50`
- end: `0x8f89`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::GetCrmFieldsSelectControl`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x8a00`

## callees

- `0x8e50`

## string_xrefs

- `0x8ed7`: `ImportWizard.AttributeMapPage.AttributeSelector.CreateNew`
- `0x8ee1`: `2-Create`

## pseudocode

```c

```

## disassembly

```asm
0x8e50  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x8e55  stloc.0
0x8e56  ldloc.0
0x8e57  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_ClassNames()
0x8e5c  ldstr    aOtherfieldssel// "OtherFieldsSelectControl"
0x8e61  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8e66  pop
0x8e67  ldloc.0
0x8e68  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x8e6d  ldc.i4.0
0x8e6e  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8e73  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x8e78  stloc.1
0x8e79  ldloc.1
0x8e7a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8e7f  ldstr    aImportwizardAt// "ImportWizard.AttributeMapPage.Attribute"...
0x8e84  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8e89  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_Label(string)
0x8e8e  ldloc.1
0x8e8f  ldc.i4.1
0x8e90  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_DisplayGrouping(bool)
0x8e95  ldloc.1
0x8e96  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8e9b  ldstr    aImportwizardAt_9// "ImportWizard.AttributeMapPage.Attribute"...
0x8ea0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ea5  ldstr    a1Select// "1-Select"
0x8eaa  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8eaf  ldloc.1
0x8eb0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8eb5  ldstr    aImportwizardAt_10// "ImportWizard.AttributeMapPage.Attribute"...
0x8eba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ebf  ldstr    a3Ignore// "3-Ignore"
0x8ec4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8ec9  ldarg.0
0x8eca  ldfld    bool Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::showCreateNew
0x8ecf  brfalse.s loc_8EEB
0x8ed1  ldloc.1
0x8ed2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8ed7  ldstr    aImportwizardAt_11// "ImportWizard.AttributeMapPage.Attribute"...
0x8edc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8ee1  ldstr    a2Create// "2-Create"
0x8ee6  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8eeb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8ef0  ldstr    aImportwizardAt_1// "ImportWizard.AttributeMapPage.Attribute"...
0x8ef5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8efa  ldc.i4.1
0x8efb  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string, valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x8f00  stloc.2
0x8f01  ldloc.2
0x8f02  ldstr    aFieldsoptiongr// "fieldsOptionGroup"
0x8f07  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8f0c  ldarg.1
0x8f0d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x8f12  stloc.s  4
0x8f14  br.s     loc_8F38
0x8f16  ldloca.s 4
0x8f18  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x8f1d  stloc.s  5
0x8f1f  ldarg.0
0x8f20  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x8f25  ldloc.s  5
0x8f27  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::GetAttributeDisplayName(string)
0x8f2c  stloc.s  6
0x8f2e  ldloc.2
0x8f2f  ldloc.s  6
0x8f31  ldloc.s  5
0x8f33  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x8f38  ldloca.s 4
0x8f3a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x8f3f  brtrue.s loc_8F16
0x8f41  leave.s  loc_8F51
0x8f43  ldloca.s 4
0x8f45  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x8f4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8f50  endfinally
0x8f51  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8f56  ldstr    aImportwizardAt_12// "ImportWizard.AttributeMapPage.Attribute"...
0x8f5b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8f60  ldc.i4.1
0x8f61  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string, valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x8f66  stloc.3
0x8f67  ldloc.3
0x8f68  ldc.i4.0
0x8f69  callvirt instance void [System.Web]System.Web.UI.Control::set_Visible(bool)
0x8f6e  ldloc.3
0x8f6f  ldstr    aNewfieldsoptio// "newFieldsOptionGroup"
0x8f74  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x8f79  ldloc.0
0x8f7a  ldloc.3
0x8f7b  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x8f80  ldloc.0
0x8f81  ldloc.2
0x8f82  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x8f87  ldloc.0
0x8f88  ret
```
