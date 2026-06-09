# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::LoadJSEventsResourcesForAssociatedGrid

- ea: `0x1dd20`
- end: `0x1dd98`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::LoadJSEventsResourcesForAssociatedGrid`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d330`

## callees

- `0x1dd20`

## string_xrefs

- `0x1dd25`: `/customControlDefaultConfig/formLibraries/Library`

## pseudocode

```c

```

## disassembly

```asm
0x1dd20  ldarg.1
0x1dd21  brtrue.s loc_1DD24
0x1dd23  ret
0x1dd24  ldarg.1
0x1dd25  ldstr    aCustomcontrold_0// "/customControlDefaultConfig/formLibrari"...
0x1dd2a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x1dd2f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x1dd34  stloc.0
0x1dd35  br.s     loc_1DD7C
0x1dd37  ldloc.0
0x1dd38  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1dd3d  castclass [System.Xml]System.Xml.XmlNode
0x1dd42  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1dd47  ldstr    aName// "name"
0x1dd4c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x1dd51  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1dd56  stloc.1
0x1dd57  ldarg.0
0x1dd58  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x1dd5d  ldstr    aWebresource// "$webresource:"
0x1dd62  ldloc.1
0x1dd63  call     string [mscorlib]System.String::Concat(string, string)
0x1dd68  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1dd6d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::CreateWebResourceUri(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1dd72  callvirt instance string [mscorlib]System.Object::ToString()
0x1dd77  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetScriptFile(string)
0x1dd7c  ldloc.0
0x1dd7d  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1dd82  brtrue.s loc_1DD37
0x1dd84  leave.s  loc_1DD97
0x1dd86  ldloc.0
0x1dd87  isinst   [mscorlib]System.IDisposable
0x1dd8c  stloc.2
0x1dd8d  ldloc.2
0x1dd8e  brfalse.s loc_1DD96
0x1dd90  ldloc.2
0x1dd91  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dd96  endfinally
0x1dd97  ret
```
