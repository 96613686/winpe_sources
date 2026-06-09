# Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ApplyDisplayNames

- ea: `0xa330`
- end: `0xa4eb`
- name: `Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::ApplyDisplayNames`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xa4f0`

## callees

- `0xa330`

## pseudocode

```c

```

## disassembly

```asm
0xa330  ldarg.1
0xa331  ldstr    aSlug// "//slug"
0xa336  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0xa33b  stloc.0
0xa33c  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa341  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa346  stloc.s  7
0xa348  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa34d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xa352  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xa357  stloc.s  8
0xa359  ldloc.0
0xa35a  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0xa35f  stloc.s  9
0xa361  br       loc_A4BD
0xa366  ldloc.s  9
0xa368  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xa36d  castclass [System.Xml]System.Xml.XmlNode
0xa372  dup
0xa373  ldstr    aEntity// "entity"
0xa378  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa37d  stloc.3
0xa37e  ldloc.s  8
0xa380  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa385  ldloc.3
0xa386  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa38b  ldc.i4.1
0xa38c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xa391  stloc.1
0xa392  ldarg.1
0xa393  ldstr    aDisplayname// "displayname"
0xa398  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa39d  stloc.s  5
0xa39f  ldloc.1
0xa3a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LocalizedName()
0xa3a5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xa3aa  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xa3af  ldloc.s  8
0xa3b1  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa3b6  stloc.s  0xA
0xa3b8  ldloc.s  0xA
0xa3ba  brtrue.s loc_A3C4
0xa3bc  ldloc.1
0xa3bd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xa3c2  stloc.s  0xA
0xa3c4  ldloc.s  5
0xa3c6  ldloc.s  0xA
0xa3c8  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa3cd  ldloc.3
0xa3ce  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa3d3  ldloc.s  5
0xa3d5  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa3da  pop
0xa3db  ldstr    aAttribute// "attribute"
0xa3e0  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa3e5  stloc.s  4
0xa3e7  ldloc.s  4
0xa3e9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa3ee  ldc.i4.s 0x2F
0xa3f0  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xa3f5  dup
0xa3f6  stloc.s  6
0xa3f8  ldc.i4.m1
0xa3f9  bne.un.s loc_A410
0xa3fb  ldloc.1
0xa3fc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa401  ldloc.s  4
0xa403  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa408  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xa40d  stloc.2
0xa40e  br.s     loc_A42B
0xa410  ldloc.1
0xa411  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xa416  ldloc.s  4
0xa418  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa41d  ldc.i4.0
0xa41e  ldloc.s  6
0xa420  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xa425  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xa42a  stloc.2
0xa42b  ldarg.1
0xa42c  ldstr    aDisplayname// "displayname"
0xa431  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0xa436  stloc.s  5
0xa438  ldloc.2
0xa439  brtrue.s loc_A493
0xa43b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xa440  ldstr    aMsgMissingAttr// "Msg_Missing_Attribute_Error"
0xa445  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xa44a  ldc.i4.2
0xa44b  newarr   [mscorlib]System.Object
0xa450  dup
0xa451  ldc.i4.0
0xa452  ldloc.s  0xA
0xa454  stelem.ref
0xa455  dup
0xa456  ldc.i4.1
0xa457  ldloc.s  4
0xa459  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa45e  stelem.ref
0xa45f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, object[])
0xa464  stloc.s  0xB
0xa466  ldarg.0
0xa467  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::notifications
0xa46c  ldloc.s  0xB
0xa46e  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::Contains(string)
0xa473  brtrue.s loc_A483
0xa475  ldarg.0
0xa476  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications Microsoft.Crm.Common.Web.Tools.EmailTemplateEditor.EmailTemplateEditorPage::notifications
0xa47b  ldc.i4.1
0xa47c  ldloc.s  0xB
0xa47e  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppNotifications::AddNotification(int32, string)
0xa483  ldloc.s  5
0xa485  ldloc.s  4
0xa487  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0xa48c  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa491  br.s     loc_A4AE
0xa493  ldloc.s  5
0xa495  ldloc.2
0xa496  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xa49b  ldloc.s  7
0xa49d  ldloc.s  8
0xa49f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xa4a4  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xa4a9  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0xa4ae  ldloc.s  4
0xa4b0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xa4b5  ldloc.s  5
0xa4b7  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0xa4bc  pop
0xa4bd  ldloc.s  9
0xa4bf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa4c4  brtrue   loc_A366
0xa4c9  leave.s  loc_A4EA
0xa4cb  ldloc.s  9
0xa4cd  isinst   [mscorlib]System.IDisposable
0xa4d2  stloc.s  0xC
0xa4d4  ldloc.s  0xC
0xa4d6  brfalse.s loc_A4DF
0xa4d8  ldloc.s  0xC
0xa4da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4df  endfinally
0xa4e0  ldloc.0
0xa4e1  brfalse.s loc_A4E9
0xa4e3  ldloc.0
0xa4e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa4e9  endfinally
0xa4ea  ret
```
