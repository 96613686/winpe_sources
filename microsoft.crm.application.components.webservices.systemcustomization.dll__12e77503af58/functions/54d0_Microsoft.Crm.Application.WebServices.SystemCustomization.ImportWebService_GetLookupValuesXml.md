# Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetLookupValuesXml

- ea: `0x54d0`
- end: `0x5666`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.ImportWebService::GetLookupValuesXml`
- size: `406`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x54d0`
- `0x7b10`
- `0x7d30`

## pseudocode

```c

```

## disassembly

```asm
0x54d0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x54d5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x54da  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x54df  stloc.0
0x54e0  ldnull
0x54e1  stloc.1
0x54e2  ldloc.0
0x54e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x54e8  ldarg.1
0x54e9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x54ee  stloc.1
0x54ef  leave.s  loc_54FC
0x54f1  stloc.s  6
0x54f3  ldarg.0
0x54f4  ldloc.s  6
0x54f6  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x54fb  throw
0x54fc  ldloc.1
0x54fd  ldarg.2
0x54fe  ldc.i4.1
0x54ff  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x5504  stloc.2
0x5505  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::.ctor()
0x550a  stloc.3
0x550b  ldloc.2
0x550c  brfalse.s loc_5535
0x550e  newobj   instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::.ctor()
0x5513  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x5518  ldloc.1
0x5519  ldloc.2
0x551a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0x551f  ldloc.0
0x5520  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x5525  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x552a  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x552f  ldloc.3
0x5530  callvirt instance void Microsoft.Crm.Application.WebServices.SystemCustomization.LookupImportHelper::GetLookupList(valuetype [mscorlib]System.Guid columnMappingId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata entityMetadata, string schemaName, valuetype [mscorlib]System.Guid orgId, int32 languageCode, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity> lookupList)
0x5535  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument()
0x553a  stloc.s  4
0x553c  ldloc.s  4
0x553e  ldc.i4.1
0x553f  ldstr    aLookupmaps// "LookupMaps"
0x5544  ldnull
0x5545  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x554a  stloc.s  5
0x554c  ldloc.3
0x554d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::GetEnumerator()
0x5552  stloc.s  7
0x5554  br       loc_5638
0x5559  ldloca.s 7
0x555b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::get_Current()
0x5560  stloc.s  8
0x5562  ldloc.s  4
0x5564  ldc.i4.1
0x5565  ldstr    aLookupmap// "LookupMap"
0x556a  ldnull
0x556b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x5570  stloc.s  9
0x5572  ldloc.s  5
0x5574  ldloc.s  9
0x5576  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x557b  pop
0x557c  ldloc.s  4
0x557e  ldc.i4.1
0x557f  ldstr    aLookuptype// "LookupType"
0x5584  ldnull
0x5585  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x558a  stloc.s  0xA
0x558c  ldloc.s  9
0x558e  ldloc.s  0xA
0x5590  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5595  pop
0x5596  ldloc.s  4
0x5598  ldc.i4.1
0x5599  ldstr    aLookupentityna// "LookupEntityName"
0x559e  ldnull
0x559f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x55a4  stloc.s  0xB
0x55a6  ldloc.s  9
0x55a8  ldloc.s  0xB
0x55aa  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x55af  pop
0x55b0  ldloc.s  4
0x55b2  ldc.i4.1
0x55b3  ldstr    aLookupattribut// "LookupAttributeName"
0x55b8  ldnull
0x55b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x55be  stloc.s  0xC
0x55c0  ldloc.s  9
0x55c2  ldloc.s  0xC
0x55c4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x55c9  pop
0x55ca  ldloc.s  4
0x55cc  ldc.i4.1
0x55cd  ldstr    aProcesscode// "ProcessCode"
0x55d2  ldnull
0x55d3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlDocument::CreateNode(valuetype [System.Xml]System.Xml.XmlNodeType, string, string)
0x55d8  stloc.s  0xD
0x55da  ldloc.s  9
0x55dc  ldloc.s  0xD
0x55de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x55e3  pop
0x55e4  ldloc.s  0xD
0x55e6  ldstr    aProcess// "Process"
0x55eb  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x55f0  ldloc.s  0xB
0x55f2  ldloc.s  8
0x55f4  ldstr    aLookupentityna_0// "lookupentityname"
0x55f9  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Item(string)
0x55fe  callvirt instance string [mscorlib]System.Object::ToString()
0x5603  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5608  ldloc.s  0xC
0x560a  ldloc.s  8
0x560c  ldstr    aLookupattribut_0// "lookupattributename"
0x5611  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Item(string)
0x5616  callvirt instance string [mscorlib]System.Object::ToString()
0x561b  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5620  ldloc.s  0xA
0x5622  ldloc.s  8
0x5624  ldstr    aLookupsourceco// "lookupsourcecode"
0x5629  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity::get_Item(string)
0x562e  callvirt instance string [mscorlib]System.Object::ToString()
0x5633  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5638  ldloca.s 7
0x563a  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>::MoveNext()
0x563f  brtrue   loc_5559
0x5644  leave.s  loc_5654
0x5646  ldloca.s 7
0x5648  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.DynamicEntity>
0x564e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5653  endfinally
0x5654  ldloc.s  4
0x5656  ldloc.s  5
0x5658  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x565d  pop
0x565e  ldloc.s  4
0x5660  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5665  ret
```
