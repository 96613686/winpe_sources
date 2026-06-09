# Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::Execute

- ea: `0x2520`
- end: `0x25ee`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::Execute`
- size: `206`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xad90`
- `0xb2a0`

## callees

- `0x2520`
- `0x25f0`

## string_xrefs

- `0x2560`: `http://schemas.microsoft.com/crm/2009/WebServices`

## pseudocode

```c

```

## disassembly

```asm
0x2520  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2525  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x252a  brfalse.s loc_2538
0x252c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2531  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.SystemCustomizationSecurity::CheckPublishCustomizationsPrivileges(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2536  brtrue.s loc_2549
0x2538  ldc.i4   0x80040277
0x253d  ldc.i4.0
0x253e  newarr   [mscorlib]System.Object
0x2543  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2548  throw
0x2549  ldarg.0
0x254a  callvirt instance class [System.Xml]System.Xml.XmlDocument [System.Xml]System.Xml.XmlNode::get_OwnerDocument()
0x254f  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XmlDocument::get_NameTable()
0x2554  newobj   instance void [System.Xml]System.Xml.XmlNamespaceManager::.ctor(class [System.Xml]System.Xml.XmlNameTable)
0x2559  stloc.0
0x255a  ldloc.0
0x255b  ldstr    aMbs// "mbs"
0x2560  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/crm/2009/W"...
0x2565  callvirt instance void [System.Xml]System.Xml.XmlNamespaceManager::AddNamespace(string, string)
0x256a  ldarg.0
0x256b  ldloc.0
0x256c  call     bool Microsoft.Crm.Application.WebServices.SystemCustomization.CustomizationsPublish::ProcessOptionsSet(class [System.Xml]System.Xml.XmlNode data, class [System.Xml]System.Xml.XmlNamespaceManager nsmgr)
0x2571  brtrue.s loc_25DD
0x2573  ldarg.0
0x2574  ldstr    aMbsEntitiesMbs// "//mbs:entities/mbs:entity"
0x2579  ldloc.0
0x257a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string, class [System.Xml]System.Xml.XmlNamespaceManager)
0x257f  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x2584  stloc.1
0x2585  br.s     loc_25BF
0x2587  ldloc.1
0x2588  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x258d  castclass [System.Xml]System.Xml.XmlNode
0x2592  stloc.2
0x2593  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2598  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x259d  ldloc.2
0x259e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x25a3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x25a8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(valuetype [mscorlib]System.Guid)
0x25ad  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_EntityInfo()
0x25b2  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityDescription::get_LogicalName()
0x25b7  stloc.3
0x25b8  ldloc.2
0x25b9  ldloc.3
0x25ba  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x25bf  ldloc.1
0x25c0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x25c5  brtrue.s loc_2587
0x25c7  leave.s  loc_25DD
0x25c9  ldloc.1
0x25ca  isinst   [mscorlib]System.IDisposable
0x25cf  stloc.s  4
0x25d1  ldloc.s  4
0x25d3  brfalse.s loc_25DC
0x25d5  ldloc.s  4
0x25d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x25dc  endfinally
0x25dd  ldarg.0
0x25de  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x25e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25e8  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::PublishXml(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25ed  ret
```
