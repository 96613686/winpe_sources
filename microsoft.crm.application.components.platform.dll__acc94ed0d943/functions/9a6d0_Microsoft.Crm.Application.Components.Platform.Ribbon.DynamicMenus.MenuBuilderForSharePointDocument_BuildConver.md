# Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::BuildConvertAsMenu

- ea: `0x9a6d0`
- end: `0x9a886`
- name: `Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::BuildConvertAsMenu`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x9a640`

## callees

- `0x4fb90`
- `0x4fbf0`
- `0x4fc00`
- `0x4fc30`
- `0x50bb0`
- `0x526c0`
- `0x559f0`
- `0x55b60`
- `0x55b80`
- `0x55bb0`
- `0x55ca0`
- `0x9a6d0`
- `0x9a890`
- `0x9aad0`
- `0x9aea0`
- `0x9b140`

## string_xrefs

- `0x9a84a`: `Mscrm.SharePointOpenSource`
- `0x9a82a`: `Mscrm.DynamicMenu.Grid.OpenSource.`

## pseudocode

```c

```

## disassembly

```asm
0x9a6d0  ldarg.0
0x9a6d1  call     instance class Microsoft.Crm.Application.Ribbon.RibbonPageContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_PageContext()
0x9a6d6  brfalse  loc_9A7F6
0x9a6db  ldarg.0
0x9a6dc  call     instance class Microsoft.Crm.Application.Ribbon.RibbonPageContext Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_PageContext()
0x9a6e1  callvirt instance string Microsoft.Crm.Application.Ribbon.RibbonPageContext::get_FormId()
0x9a6e6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9a6eb  brtrue   loc_9A7F6
0x9a6f0  ldarg.0
0x9a6f1  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x9a6f6  brfalse.s loc_9A6F9
0x9a6f8  ret
0x9a6f9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::.ctor()
0x9a6fe  stloc.0
0x9a6ff  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>::.ctor()
0x9a704  stloc.1
0x9a705  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x9a70a  stloc.2
0x9a70b  ldarg.0
0x9a70c  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x9a711  ldstr    aMenu// "Menu"
0x9a716  call     string [mscorlib]System.String::Concat(string, string)
0x9a71b  newobj   instance void Microsoft.Crm.Application.Ribbon.XmlRendering.Menu::.ctor(string id)
0x9a720  stloc.3
0x9a721  ldarg.0
0x9a722  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x9a727  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a72c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a731  ldstr    a0Section1_0// "{0}Section1"
0x9a736  ldc.i4.1
0x9a737  newarr   [mscorlib]System.Object
0x9a73c  dup
0x9a73d  ldc.i4.0
0x9a73e  ldarg.0
0x9a73f  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x9a744  stelem.ref
0x9a745  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a74a  newobj   instance void Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::.ctor(string id)
0x9a74f  stloc.s  4
0x9a751  ldloc.s  4
0x9a753  ldc.i4.s 0xA
0x9a755  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x9a75a  callvirt instance void Microsoft.Crm.Application.Ribbon.XmlRendering.MenuSection::set_Sequence(valuetype [mscorlib]System.Nullable`1<int32> value)
0x9a75f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9a764  ldstr    a0Controls// "{0}Controls"
0x9a769  ldc.i4.1
0x9a76a  newarr   [mscorlib]System.Object
0x9a76f  dup
0x9a770  ldc.i4.0
0x9a771  ldarg.0
0x9a772  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_IdPrefix()
0x9a777  stelem.ref
0x9a778  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9a77d  newobj   instance void Microsoft.Crm.Application.Ribbon.XmlRendering.Controls::.ctor(string id)
0x9a782  stloc.s  5
0x9a784  ldarg.0
0x9a785  call     instance string Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::fetchSharePointDocument()
0x9a78a  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x9a78f  stloc.s  6
0x9a791  ldarg.0
0x9a792  ldloc.s  6
0x9a794  ldloca.s 2
0x9a796  ldloca.s 1
0x9a798  call     instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::ParseSharePointDocumentXml(class [System.Xml]System.Xml.XmlDocument relatedSharePointDoc, class [mscorlib]System.Collections.Generic.List`1<string>& locationIds, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>>& sharePointLocationDocAttr)
0x9a79d  ldarg.0
0x9a79e  ldloc.s  5
0x9a7a0  ldloc.2
0x9a7a1  ldloc.1
0x9a7a2  ldloc.0
0x9a7a3  call     instance void Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::AddDocumentLocationButtons(class Microsoft.Crm.Application.Ribbon.XmlRendering.Controls menuControls, class [mscorlib]System.Collections.Generic.List`1<string> locationIds, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> sharePointAttr, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition> commands)
0x9a7a8  ldloc.s  4
0x9a7aa  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9a7af  ldloc.s  5
0x9a7b1  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9a7b6  ldloc.3
0x9a7b7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer> Microsoft.Crm.Application.Ribbon.XmlRendering.RibbonXmlRenderer::get_Children()
0x9a7bc  ldloc.s  4
0x9a7be  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer>::Add(var<u1>)
0x9a7c3  ldarg.0
0x9a7c4  ldloc.0
0x9a7c5  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::ToArray()
0x9a7ca  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x9a7cf  ldarg.0
0x9a7d0  ldloc.3
0x9a7d1  call     string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::RenderXml(class Microsoft.Crm.Application.Ribbon.XmlRendering.IRibbonXmlRenderer renderer)
0x9a7d6  stfld    string Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_layoutXml
0x9a7db  ldarg.0
0x9a7dc  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x9a7e1  brfalse.s loc_9A7EF
0x9a7e3  ldarg.0
0x9a7e4  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x9a7e9  ldlen
0x9a7ea  brtrue   loc_9A885
0x9a7ef  ldarg.0
0x9a7f0  call     instance void Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::AddRootNodeDisableDisplayRule()
0x9a7f5  ret
0x9a7f6  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::.ctor()
0x9a7fb  stloc.s  7
0x9a7fd  ldsfld   string [mscorlib]System.String::Empty
0x9a802  stloc.s  8
0x9a804  ldarg.0
0x9a805  call     instance string Microsoft.Crm.Application.Ribbon.DynamicMenuBuilder::get_CommandPrefix()
0x9a80a  stloc.s  9
0x9a80c  ldloc.s  9
0x9a80e  ldstr    aMscrmDynamicme_17// "Mscrm.DynamicMenu.Grid.ChangeLocation."
0x9a813  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a818  brtrue.s loc_9A838
0x9a81a  ldloc.s  9
0x9a81c  ldstr    aMscrmDynamicme_18// "Mscrm.DynamicMenu.Grid.EditLocation."
0x9a821  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a826  brtrue.s loc_9A841
0x9a828  ldloc.s  9
0x9a82a  ldstr    aMscrmDynamicme_19// "Mscrm.DynamicMenu.Grid.OpenSource."
0x9a82f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9a834  brtrue.s loc_9A84A
0x9a836  br.s     loc_9A851
0x9a838  ldstr    aMscrmSharepoin// "Mscrm.SharePointChangeLocation"
0x9a83d  stloc.s  8
0x9a83f  br.s     loc_9A851
0x9a841  ldstr    aMscrmSharepoin_0// "Mscrm.SharePointEditLocation"
0x9a846  stloc.s  8
0x9a848  br.s     loc_9A851
0x9a84a  ldstr    aMscrmSharepoin_1// "Mscrm.SharePointOpenSource"
0x9a84f  stloc.s  8
0x9a851  ldloc.s  7
0x9a853  ldarg.0
0x9a854  ldloc.s  8
0x9a856  ldsfld   string [mscorlib]System.String::Empty
0x9a85b  ldnull
0x9a85c  call     instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition Microsoft.Crm.Application.Components.Platform.Ribbon.DynamicMenus.MenuBuilderForSharePointDocument::GetRibbonCommandDefinition(string commandId, string locationId, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>> sharePointAttr)
0x9a861  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::Add(var<u1>)
0x9a866  ldarg.0
0x9a867  ldnull
0x9a868  stfld    string Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_layoutXml
0x9a86d  ldarg.0
0x9a86e  ldloc.s  7
0x9a870  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition>::ToArray()
0x9a875  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.RibbonCommandDefinition[] Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_commands
0x9a87a  ldarg.0
0x9a87b  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x9a880  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Ribbon.NewRecordMenuBuilderBase::_controlToCommandMap
0x9a885  ret
```
