# Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::SaveSyncMappingChanges

- ea: `0x15a60`
- end: `0x15c44`
- name: `Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::SaveSyncMappingChanges`
- size: `484`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x15240`

## callees

- `0x15a60`
- `0x15c50`
- `0x15d40`

## pseudocode

```c

```

## disassembly

```asm
0x15a60  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15a65  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15a6a  ldc.i4.0
0x15a6b  ldc.i4.0
0x15a6c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x15a71  stloc.0
0x15a72  ldloc.0
0x15a73  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15a78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_UserId()
0x15a7d  ldc.i4.1
0x15a7e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(valuetype [mscorlib]System.Guid, bool)
0x15a83  ldarg.0
0x15a84  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::PopulateMappingList()
0x15a89  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SyncAttributeMappingService::.ctor()
0x15a8e  stloc.1
0x15a8f  ldarg.1
0x15a90  callvirt instance bool [System.Xml]System.Xml.XmlNode::get_HasChildNodes()
0x15a95  brfalse  loc_15C19
0x15a9a  ldstr    aSyncattributem// "SyncAttributeMapping"
0x15a9f  ldloc.0
0x15aa0  call     string class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SyncAttributeMappingServiceInternal`1<class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ProvisioningOff>::GetEntityTypeCodeAttributeName(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15aa5  stloc.2
0x15aa6  ldc.i4.0
0x15aa7  stloc.3
0x15aa8  br       loc_15C08
0x15aad  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15ab2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x15ab7  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SyncAttributeMapping::.ctor(valuetype [mscorlib]System.Guid)
0x15abc  stloc.s  4
0x15abe  ldarg.1
0x15abf  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x15ac4  ldloc.3
0x15ac5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x15aca  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Name()
0x15acf  stloc.s  5
0x15ad1  ldloc.s  5
0x15ad3  ldstr    asc_31504// "_"
0x15ad8  ldc.i4.5
0x15ad9  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x15ade  stloc.s  6
0x15ae0  ldc.i4.2
0x15ae1  newarr   [mscorlib]System.String
0x15ae6  dup
0x15ae7  ldc.i4.0
0x15ae8  ldloc.s  5
0x15aea  ldc.i4.0
0x15aeb  ldloc.s  6
0x15aed  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x15af2  stelem.ref
0x15af3  dup
0x15af4  ldc.i4.1
0x15af5  ldloc.s  5
0x15af7  ldloc.s  6
0x15af9  ldc.i4.1
0x15afa  add
0x15afb  callvirt instance string [mscorlib]System.String::Substring(int32)
0x15b00  stelem.ref
0x15b01  dup
0x15b02  ldc.i4.1
0x15b03  ldelem.ref
0x15b04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b09  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x15b0e  stloc.s  7
0x15b10  ldc.i4.0
0x15b11  ldelem.ref
0x15b12  stloc.s  8
0x15b14  ldarg.1
0x15b15  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x15b1a  ldloc.3
0x15b1b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x15b20  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x15b25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x15b2a  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x15b2f  stloc.s  9
0x15b31  ldarg.1
0x15b32  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x15b37  ldloc.3
0x15b38  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x15b3d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x15b42  ldc.i4.0
0x15b43  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(int32)
0x15b48  stloc.s  0xA
0x15b4a  ldloc.s  4
0x15b4c  ldloc.2
0x15b4d  ldloc.s  7
0x15b4f  box      [mscorlib]System.Int32
0x15b54  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x15b59  ldloc.s  4
0x15b5b  ldsfld   string [Microsoft.Crm]Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapMappingName
0x15b60  ldloc.s  8
0x15b62  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x15b67  ldloc.s  0xA
0x15b69  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x15b6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x15b73  brfalse.s loc_15B8A
0x15b75  ldloc.s  4
0x15b77  ldsfld   string [Microsoft.Crm]Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapSyncDirection
0x15b7c  ldloc.s  9
0x15b7e  box      [mscorlib]System.Int32
0x15b83  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x15b88  br.s     loc_15BFB
0x15b8a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping::.ctor()
0x15b8f  stloc.s  0xB
0x15b91  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping>::.ctor()
0x15b96  stloc.s  0xC
0x15b98  ldarg.0
0x15b99  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping>> Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::mappingCollection
0x15b9e  ldloc.s  7
0x15ba0  ldloca.s 0xC
0x15ba2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping>>::TryGetValue(var<u1>, !!T0)
0x15ba7  brfalse.s loc_15BFB
0x15ba9  ldloc.s  0xC
0x15bab  ldloc.s  8
0x15bad  ldloca.s 0xB
0x15baf  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping>::TryGetValue(var<u1>, !!T0)
0x15bb4  brfalse.s loc_15BFB
0x15bb6  ldloc.s  9
0x15bb8  ldloc.s  0xB
0x15bba  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeMapping::get_DefaultSyncDirection()
0x15bbf  and
0x15bc0  stloc.s  0xD
0x15bc2  ldloc.s  4
0x15bc4  ldsfld   string [Microsoft.Crm]Microsoft.Crm.SyncAttributeMappingConstants::PrincipalSyncAttrMapSyncDirection
0x15bc9  ldloc.s  0xD
0x15bcb  box      [mscorlib]System.Int32
0x15bd0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x15bd5  ldloc.s  0xA
0x15bd7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x15bdc  ldc.i4.1
0x15bdd  newarr   [mscorlib]System.Char
0x15be2  dup
0x15be3  ldc.i4.0
0x15be4  ldc.i4.s 0x2C
0x15be6  stelem.i2
0x15be7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x15bec  stloc.s  0xE
0x15bee  ldarg.0
0x15bef  ldloc.s  0xE
0x15bf1  ldloc.s  7
0x15bf3  ldloc.s  9
0x15bf5  ldloc.0
0x15bf6  call     instance void Microsoft.Crm.Common.Application.Pages.Tools.Common.OrganizationSettingsXmlAcceptor::UpdateChildMappings(string[] childMappingNames, int32 entityName, int32 uiSyncDirection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x15bfb  ldloc.1
0x15bfc  ldloc.s  4
0x15bfe  ldloc.0
0x15bff  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x15c04  ldloc.3
0x15c05  ldc.i4.1
0x15c06  add
0x15c07  stloc.3
0x15c08  ldloc.3
0x15c09  ldarg.1
0x15c0a  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::get_ChildNodes()
0x15c0f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x15c14  blt      loc_15AAD
0x15c19  ldloc.0
0x15c1a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x15c1f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.SyncAttributeMappingsCache::Instance()
0x15c24  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x15c29  callvirt instance void class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISyncAttributeMappingsData>::Flush(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x15c2e  leave.s  loc_15C43
0x15c30  pop
0x15c31  ldloc.0
0x15c32  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x15c37  rethrow
0x15c39  ldloc.0
0x15c3a  brfalse.s loc_15C42
0x15c3c  ldloc.0
0x15c3d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15c42  endfinally
0x15c43  ret
```
