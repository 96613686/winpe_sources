# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeSelectControls

- ea: `0x7fe0`
- end: `0x810d`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::InitializeSelectControls`
- size: `301`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x7e60`

## callees

- `0x7fe0`

## pseudocode

```c

```

## disassembly

```asm
0x7fe0  ldarg.0
0x7fe1  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::.ctor()
0x7fe6  stfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x7feb  ldarg.0
0x7fec  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x7ff1  ldstr    aStyle// "style"
0x7ff6  ldstr    aWidth85// "width:85%;"
0x7ffb  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddExpando(string, string)
0x8000  ldarg.0
0x8001  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x8006  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::get_OptionGroups()
0x800b  ldc.i4.0
0x800c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8011  isinst   [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup
0x8016  dup
0x8017  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x801c  ldstr    aImportwizardAt// "ImportWizard.AttributeMapPage.Attribute"...
0x8021  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8026  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_Label(string)
0x802b  dup
0x802c  ldc.i4.1
0x802d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::set_DisplayGrouping(bool)
0x8032  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8037  ldstr    aImportwizardAt_0// "ImportWizard.AttributeMapPage.Attribute"...
0x803c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x8041  ldstr    a1Select// "1-Select"
0x8046  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x804b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8050  ldstr    aImportwizardAt_1// "ImportWizard.AttributeMapPage.Attribute"...
0x8055  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x805a  ldc.i4.1
0x805b  newobj   instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::.ctor(string, valuetype [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionSorting)
0x8060  stloc.0
0x8061  ldarg.0
0x8062  ldfld    class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetMap
0x8067  ldstr    aAttributemapsA_1// "AttributeMaps/AttributeMap[not(@Unused)"...
0x806c  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x8071  stloc.1
0x8072  ldloc.1
0x8073  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x8078  stloc.2
0x8079  br.s     loc_80D8
0x807b  ldloc.2
0x807c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8081  castclass [System.Xml]System.Xml.XmlNode
0x8086  stloc.3
0x8087  ldloc.3
0x8088  ldstr    aSourceattribut// "SourceAttributeName"
0x808d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x8092  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8097  stloc.s  4
0x8099  ldarg.0
0x809a  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x809f  ldloc.s  4
0x80a1  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::IsColumnMultiMapped(string)
0x80a6  brtrue.s loc_80D8
0x80a8  ldarg.0
0x80a9  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_targetEntity
0x80ae  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ImportEntity::get_FunctoidMappedColumns()
0x80b3  ldloc.s  4
0x80b5  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x80ba  brtrue.s loc_80D8
0x80bc  ldloc.3
0x80bd  ldstr    aSourceattribut_0// "SourceAttributeId"
0x80c2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x80c7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x80cc  stloc.s  5
0x80ce  ldloc.0
0x80cf  ldloc.s  4
0x80d1  ldloc.s  5
0x80d3  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup::AddItem(string, string)
0x80d8  ldloc.2
0x80d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x80de  brtrue.s loc_807B
0x80e0  leave.s  loc_8100
0x80e2  ldloc.2
0x80e3  isinst   [mscorlib]System.IDisposable
0x80e8  stloc.s  6
0x80ea  ldloc.s  6
0x80ec  brfalse.s loc_80F5
0x80ee  ldloc.s  6
0x80f0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80f5  endfinally
0x80f6  ldloc.1
0x80f7  brfalse.s loc_80FF
0x80f9  ldloc.1
0x80fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x80ff  endfinally
0x8100  ldarg.0
0x8101  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeMapSectionPainter::_sourceFieldsSelectControl
0x8106  ldloc.0
0x8107  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::AddOptionGroup(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.OptionGroup)
0x810c  ret
```
