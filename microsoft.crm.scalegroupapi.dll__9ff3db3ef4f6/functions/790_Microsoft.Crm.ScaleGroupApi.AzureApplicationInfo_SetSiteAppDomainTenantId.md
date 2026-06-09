# Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::SetSiteAppDomainTenantId

- ea: `0x790`
- end: `0x85b`
- name: `Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::SetSiteAppDomainTenantId`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x510`

## callees

- `0x410`
- `0x460`
- `0x480`
- `0x790`

## string_xrefs

- `0x795`: `AzureAdFederationUrl`
- `0x7db`: `EntityDescriptor`

## pseudocode

```c

```

## disassembly

```asm
0x790  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x795  ldstr    aAzureadfederat// "AzureAdFederationUrl"
0x79a  ldc.i4.0
0x79b  callvirt T0x2B000004
0x7a0  stloc.0
0x7a1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7a6  ldloc.0
0x7a7  ldc.i4.1
0x7a8  newarr   [mscorlib]System.Object
0x7ad  dup
0x7ae  ldc.i4.0
0x7af  ldarg.0
0x7b0  callvirt instance string Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::get_ScaleGroupApiDomain()
0x7b5  stelem.ref
0x7b6  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7bb  stloc.1
0x7bc  newobj   instance void [System]System.Net.WebClient::.ctor()
0x7c1  ldloc.1
0x7c2  callvirt instance string [System]System.Net.WebClient::DownloadString(string)
0x7c7  stloc.2
0x7c8  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x7cd  dup
0x7ce  ldnull
0x7cf  callvirt instance void [System.Xml]System.Xml.XmlDocument::set_XmlResolver(class [System.Xml]System.Xml.XmlResolver)
0x7d4  dup
0x7d5  ldloc.2
0x7d6  callvirt instance void [System.Xml]System.Xml.XmlDocument::LoadXml(string)
0x7db  ldstr    aEntitydescript// "EntityDescriptor"
0x7e0  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlDocument::GetElementsByTagName(string)
0x7e5  stloc.3
0x7e6  ldloc.3
0x7e7  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x7ec  ldc.i4.0
0x7ed  ble.s    loc_85A
0x7ef  ldloc.3
0x7f0  ldc.i4.0
0x7f1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNodeList::get_ItemOf(int32)
0x7f6  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7fb  ldstr    aEntityid// "entityID"
0x800  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x805  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x80a  newobj   instance void [System]System.Uri::.ctor(string)
0x80f  stloc.s  4
0x811  ldarg.0
0x812  ldloc.s  4
0x814  callvirt instance string [System]System.Uri::get_Scheme()
0x819  ldstr    asc_6590// "://"
0x81e  ldloc.s  4
0x820  callvirt instance string [System]System.Uri::get_Host()
0x825  callvirt instance string [mscorlib]System.Object::ToString()
0x82a  ldstr    a0// "/{0}/"
0x82f  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x834  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_Issuer(string value)
0x839  ldarg.0
0x83a  ldloc.s  4
0x83c  callvirt instance string [System]System.Uri::get_LocalPath()
0x841  ldstr    asc_65A4// "/"
0x846  ldstr    asc_65A8// ""
0x84b  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x850  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x855  callvirt instance void Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::set_TenantId(valuetype [mscorlib]System.Guid value)
0x85a  ret
```
