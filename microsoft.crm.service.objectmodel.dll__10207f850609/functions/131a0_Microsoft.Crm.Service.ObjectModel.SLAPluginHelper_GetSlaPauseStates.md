# Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetSlaPauseStates

- ea: `0x131a0`
- end: `0x13284`
- name: `Microsoft.Crm.Service.ObjectModel.SLAPluginHelper::GetSlaPauseStates`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x13660`

## callees

- `0x131a0`

## string_xrefs

- `0x131e0`: `Pause states do not exist in XML format in the DB.`

## pseudocode

```c

```

## disassembly

```asm
0x131a0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x131a5  brfalse.s loc_131AD
0x131a7  ldsfld   string [mscorlib]System.String::Empty
0x131ac  ret
0x131ad  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x131b2  ldarg.0
0x131b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x131b8  ldarg.0
0x131b9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x131be  stloc.0
0x131bf  ldarg.0
0x131c0  call     bool [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ObjectServiceUtility::IsSLAFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x131c5  brfalse  loc_1327A
0x131ca  ldnull
0x131cb  stloc.1
0x131cc  ldloc.0
0x131cd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SlaPauseStates()
0x131d2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x131d7  stloc.1
0x131d8  leave.s  loc_131F6
0x131da  pop
0x131db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x131e0  ldstr    aPauseStatesDoN// "Pause states do not exist in XML format"...
0x131e5  ldc.i4.0
0x131e6  newarr   [mscorlib]System.Object
0x131eb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x131f0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x131f5  throw
0x131f6  ldloc.1
0x131f7  brtrue.s loc_13200
0x131f9  ldloc.0
0x131fa  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SlaPauseStates()
0x131ff  ret
0x13200  ldloc.1
0x13201  ldstr    aEntity// "entity"
0x13206  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x1320b  stloc.2
0x1320c  ldc.i4.0
0x1320d  stloc.3
0x1320e  br.s     loc_1325F
0x13210  ldloc.2
0x13211  ldloc.3
0x13212  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x13217  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x1321c  ldstr    aValue// "value"
0x13221  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNamedNodeMap::GetNamedItem(string)
0x13226  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x1322b  ldstr    aIncident// "Incident"
0x13230  ldc.i4.3
0x13231  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x13236  brfalse.s loc_1325B
0x13238  ldloc.2
0x13239  ldloc.3
0x1323a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1323f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x13244  brfalse.s loc_1325B
0x13246  ldloc.2
0x13247  ldloc.3
0x13248  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x1324d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_FirstChild()
0x13252  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x13257  stloc.s  4
0x13259  leave.s  loc_13281
0x1325b  ldloc.3
0x1325c  ldc.i4.1
0x1325d  add
0x1325e  stloc.3
0x1325f  ldloc.3
0x13260  ldloc.2
0x13261  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x13266  blt.s    loc_13210
0x13268  leave.s  loc_13274
0x1326a  ldloc.2
0x1326b  brfalse.s loc_13273
0x1326d  ldloc.2
0x1326e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13273  endfinally
0x13274  ldsfld   string [mscorlib]System.String::Empty
0x13279  ret
0x1327a  ldloc.0
0x1327b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_SlaPauseStates()
0x13280  ret
0x13281  ldloc.s  4
0x13283  ret
```
