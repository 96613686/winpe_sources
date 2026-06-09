# Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::HandleCommandUiDefinition

- ea: `0x714d0`
- end: `0x716ce`
- name: `Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::HandleCommandUiDefinition`
- size: `510`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x70ee0`

## callees

- `0x36900`
- `0x39070`
- `0x39140`
- `0x714d0`
- `0x716d0`
- `0x717a0`

## string_xrefs

- `0x71533`: `Command`
- `0x71570`: `Command`
- `0x714e5`: `SolutionComponentType.RibbonItem`
- `0x714f1`: `SolutionComponentType.RibbonCommand`
- `0x714fe`: `.//*[@Command]`
- `0x715f6`: `ImageSideArrow`
- `0x71622`: `ImageLeftSide`
- `0x7162d`: `ImageLeftSideHover`
- `0x71638`: `ImageLeftSideDown`
- `0x71643`: `ImageRightSide`
- `0x7164e`: `ImageRightSideHover`
- `0x71659`: `ImageRightSideDown`

## pseudocode

```c

```

## disassembly

```asm
0x714d0  ldarg.1
0x714d1  brtrue.s loc_714D4
0x714d3  ret
0x714d4  ldarg.0
0x714d5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::_context
0x714da  callvirt instance int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerLanguageCode()
0x714df  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x714e4  stloc.0
0x714e5  ldstr    aSolutioncompon_5// "SolutionComponentType.RibbonItem"
0x714ea  ldloc.0
0x714eb  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x714f0  stloc.1
0x714f1  ldstr    aSolutioncompon_6// "SolutionComponentType.RibbonCommand"
0x714f6  ldloc.0
0x714f7  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x714fc  stloc.2
0x714fd  ldarg.1
0x714fe  ldstr    aCommand_1// ".//*[@Command]"
0x71503  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x71508  stloc.3
0x71509  ldloc.3
0x7150a  brfalse  loc_715AD
0x7150f  ldloc.3
0x71510  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x71515  stloc.s  4
0x71517  br.s     loc_7158D
0x71519  ldloc.s  4
0x7151b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x71520  castclass [System.Xml]System.Xml.XmlNode
0x71525  stloc.s  5
0x71527  call     class Microsoft.Crm.Tools.ImportExportPublish.SolutionComponentChanges Microsoft.Crm.Tools.ImportExportPublish.SolutionComponentChanges::get_Instance()
0x7152c  ldloc.s  5
0x7152e  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x71533  ldstr    aCommand_0// "Command"
0x71538  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7153d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x71542  ldc.i4.1
0x71543  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.SolutionComponentChanges::IsNew(string id, valuetype Microsoft.Crm.Tools.ImportExportPublish.SolutionComponentChangeType type)
0x71548  brfalse.s loc_7158D
0x7154a  ldarg.0
0x7154b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::_context
0x71550  ldarg.2
0x71551  ldloc.1
0x71552  ldloc.s  5
0x71554  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x71559  ldstr    aId_0// "Id"
0x7155e  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x71563  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x71568  ldloc.2
0x71569  ldloc.s  5
0x7156b  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x71570  ldstr    aCommand_0// "Command"
0x71575  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7157a  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7157f  call     void Microsoft.Crm.Tools.ImportExportPublish.ExportAsHelper::AddRemovedComment(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent currentFilteredComponent, string componentType, string componentId, string dependentType, string dependentId)
0x71584  ldarg.0
0x71585  ldloc.s  5
0x71587  ldarg.2
0x71588  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::RemoveRibbonCustomActionItem(class [System.Xml]System.Xml.XmlNode item, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent filteredComponent)
0x7158d  ldloc.s  4
0x7158f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x71594  brtrue.s loc_71519
0x71596  leave.s  loc_715B9
0x71598  ldloc.s  4
0x7159a  isinst   [mscorlib]System.IDisposable
0x7159f  stloc.s  6
0x715a1  ldloc.s  6
0x715a3  brfalse.s loc_715AC
0x715a5  ldloc.s  6
0x715a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x715ac  endfinally
0x715ad  leave.s  loc_715B9
0x715af  ldloc.3
0x715b0  brfalse.s loc_715B8
0x715b2  ldloc.3
0x715b3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x715b8  endfinally
0x715b9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x715be  dup
0x715bf  ldstr    aImage16by16// "Image16by16"
0x715c4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x715c9  dup
0x715ca  ldstr    aImage32by32// "Image32by32"
0x715cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x715d4  dup
0x715d5  ldstr    aTooltipimage32// "ToolTipImage32by32"
0x715da  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x715df  dup
0x715e0  ldstr    aImage_0// "Image"
0x715e5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x715ea  dup
0x715eb  ldstr    aImagedownarrow// "ImageDownArrow"
0x715f0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x715f5  dup
0x715f6  ldstr    aImagesidearrow// "ImageSideArrow"
0x715fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71600  dup
0x71601  ldstr    aImageuparrow// "ImageUpArrow"
0x71606  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7160b  dup
0x7160c  ldstr    aImagehover// "ImageHover"
0x71611  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71616  dup
0x71617  ldstr    aImagedown// "ImageDown"
0x7161c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71621  dup
0x71622  ldstr    aImageleftside// "ImageLeftSide"
0x71627  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7162c  dup
0x7162d  ldstr    aImageleftsideh// "ImageLeftSideHover"
0x71632  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71637  dup
0x71638  ldstr    aImageleftsided// "ImageLeftSideDown"
0x7163d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71642  dup
0x71643  ldstr    aImagerightside// "ImageRightSide"
0x71648  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x7164d  dup
0x7164e  ldstr    aImagerightside_0// "ImageRightSideHover"
0x71653  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71658  dup
0x71659  ldstr    aImagerightside_1// "ImageRightSideDown"
0x7165e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x71663  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x71668  stloc.s  7
0x7166a  br.s     loc_716B4
0x7166c  ldloca.s 7
0x7166e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x71673  stloc.s  8
0x71675  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7167a  ldstr    a0_3// ".//*[@{0}]"
0x7167f  ldc.i4.1
0x71680  newarr   [mscorlib]System.Object
0x71685  dup
0x71686  ldc.i4.0
0x71687  ldloc.s  8
0x71689  stelem.ref
0x7168a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7168f  stloc.s  9
0x71691  ldarg.1
0x71692  ldloc.s  9
0x71694  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x71699  stloc.s  0xA
0x7169b  ldarg.0
0x7169c  ldloc.s  0xA
0x7169e  ldloc.s  8
0x716a0  ldarg.2
0x716a1  call     instance void Microsoft.Crm.Tools.ImportExportPublish.RibbonPostExportFilterHandler::HandleImageWebResourceDependency(class [System.Xml]System.Xml.XmlNodeList itemsWithImageAttribute, string attributeName, class Microsoft.Crm.Tools.ImportExportPublish.FilteredComponent filteredComponent)
0x716a6  leave.s  loc_716B4
0x716a8  ldloc.s  0xA
0x716aa  brfalse.s loc_716B3
0x716ac  ldloc.s  0xA
0x716ae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x716b3  endfinally
0x716b4  ldloca.s 7
0x716b6  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x716bb  brtrue.s loc_7166C
0x716bd  leave.s  loc_716CD
0x716bf  ldloca.s 7
0x716c1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x716c7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x716cc  endfinally
0x716cd  ret
```
