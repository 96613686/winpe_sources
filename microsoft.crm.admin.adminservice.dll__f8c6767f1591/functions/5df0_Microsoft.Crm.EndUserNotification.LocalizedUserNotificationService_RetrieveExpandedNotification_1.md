# Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::RetrieveExpandedNotification_1

- ea: `0x5df0`
- end: `0x61c1`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::RetrieveExpandedNotification_1`
- size: `977`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x5b70`
- `0x5c10`

## callees

- `0x4a90`
- `0x5df0`
- `0x61d0`
- `0x65f0`
- `0x66f0`
- `0x6790`
- `0x6890`
- `0x6930`
- `0x6c90`
- `0x6cf0`
- `0x6d80`
- `0x6e60`
- `0x6ec0`
- `0x6ed0`
- `0x7250`
- `0x78a0`
- `0x7940`
- `0x7aa0`
- `0x7fb0`

## string_xrefs

- `0x5e67`: `TemplateName`
- `0x5ea2`: `TemplateXml`
- `0x6010`: `SlugXml for template name [{0}] version [{1}] not present`

## pseudocode

```c

```

## disassembly

```asm
0x5df0  ldarg.1
0x5df1  ldstr    aNotificationba// "notificationBag"
0x5df6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x5dfb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5e00  stloc.0
0x5e01  ldarg.1
0x5e02  ldstr    aId// "Id"
0x5e07  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x5e0c  brfalse.s loc_5E1F
0x5e0e  ldarg.1
0x5e0f  ldstr    aId// "Id"
0x5e14  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5e19  unbox.any [mscorlib]System.Guid
0x5e1e  stloc.0
0x5e1f  ldloc.0
0x5e20  ldstr    aNotificationid// "notificationId"
0x5e25  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x5e2a  ldarg.s  5
0x5e2c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e31  brfalse.s loc_5E3A
0x5e33  ldsfld   string [mscorlib]System.String::Empty
0x5e38  starg.s  5
0x5e3a  ldarg.s  6
0x5e3c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e41  brfalse.s loc_5E4A
0x5e43  ldsfld   string [mscorlib]System.String::Empty
0x5e48  starg.s  6
0x5e4a  ldarg.s  7
0x5e4c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e51  brfalse.s loc_5E5A
0x5e53  ldsfld   string [mscorlib]System.String::Empty
0x5e58  starg.s  7
0x5e5a  ldarg.1
0x5e5b  ldarg.0
0x5e5c  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x5e61  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetTemplateInfoForNotification(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag notification, valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext locatorServiceContext)
0x5e66  dup
0x5e67  ldstr    aTemplatename// "TemplateName"
0x5e6c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5e71  castclass [mscorlib]System.String
0x5e76  stloc.1
0x5e77  ldstr    aVersion// "Version"
0x5e7c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5e81  unbox.any [mscorlib]System.Int32
0x5e86  stloc.2
0x5e87  ldarg.0
0x5e88  ldloc.1
0x5e89  ldloc.2
0x5e8a  ldarg.s  4
0x5e8c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::RetrieveTemplate(string templateName, int32 templateVersion, int32[] languageCodes)
0x5e91  dup
0x5e92  ldstr    aLocale// "Locale"
0x5e97  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5e9c  unbox.any [mscorlib]System.Int32
0x5ea1  stloc.3
0x5ea2  ldstr    aTemplatexml_0// "TemplateXml"
0x5ea7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5eac  castclass [mscorlib]System.String
0x5eb1  stloc.s  4
0x5eb3  newobj   instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::.ctor()
0x5eb8  stloc.s  5
0x5eba  ldloc.s  5
0x5ebc  ldloc.1
0x5ebd  ldloc.2
0x5ebe  ldloca.s 0xC
0x5ec0  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x5ec6  ldloc.s  0xC
0x5ec8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::GetLocalizedTemplate(string templateName, int32 templateVersion, valuetype [mscorlib]System.Nullable`1<int32> languageCode)
0x5ecd  ldstr    aNotificationty// "NotificationType"
0x5ed2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5ed7  unbox.any [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationType
0x5edc  stloc.s  6
0x5ede  ldc.i4.0
0x5edf  stloc.s  7
0x5ee1  ldarg.2
0x5ee2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5ee7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5eec  brtrue.s loc_5EF1
0x5eee  ldc.i4.0
0x5eef  br.s     loc_5F02
0x5ef1  ldarg.0
0x5ef2  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::_context
0x5ef7  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x5efc  ldarg.2
0x5efd  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::IsOsdpOrganization(valuetype [mscorlib]System.Guid)
0x5f02  stloc.s  8
0x5f04  ldarg.2
0x5f05  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5f0a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5f0f  brfalse.s loc_5F27
0x5f11  ldarg.0
0x5f12  ldloc.s  8
0x5f14  call     instance class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetInvalidTemplatesForOrganization(bool isOsdpOrganization)
0x5f19  stloc.s  0xD
0x5f1b  ldloc.1
0x5f1c  ldloc.s  0xD
0x5f1e  call     bool Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::IsNotificationTemplateValidForOrganization(string notificationTemplateName, class [System.Core]System.Collections.Generic.HashSet`1<string> invalidTemplates)
0x5f23  brtrue.s loc_5F27
0x5f25  ldnull
0x5f26  ret
0x5f27  ldarg.0
0x5f28  ldloc.s  6
0x5f2a  ldarg.3
0x5f2b  ldloca.s 7
0x5f2d  call     instance bool Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::IsNotificationValidForClient(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationType notiType, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Discovery.EndUserNotificationClient client, [out] valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationSeverity& notiSeverity)
0x5f32  brtrue.s loc_5F36
0x5f34  ldnull
0x5f35  ret
0x5f36  ldloc.s  5
0x5f38  ldloc.1
0x5f39  ldloc.2
0x5f3a  callvirt instance string Microsoft.Crm.EndUserNotification.LocalizedUserNotificationTemplateService::RetrieveSlugXml(string templateName, int32 version)
0x5f3f  stloc.s  9
0x5f41  ldarg.0
0x5f42  ldloc.0
0x5f43  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::GetParamsForNotification(valuetype [mscorlib]System.Guid notificationId)
0x5f48  stloc.s  0xA
0x5f4a  ldloc.s  0xA
0x5f4c  brtrue.s loc_5F55
0x5f4e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0x5f53  stloc.s  0xA
0x5f55  ldloc.s  9
0x5f57  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5f5c  brtrue   loc_6010
0x5f61  ldloc.s  9
0x5f63  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x5f68  stloc.s  0xE
0x5f6a  newobj   instance void Microsoft.Crm.EndUserNotification.SlugService::.ctor()
0x5f6f  stloc.s  0xF
0x5f71  ldloc.s  0xA
0x5f73  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x5f78  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x5f7d  stloc.s  0x10
0x5f7f  br.s     loc_5FF7
0x5f81  ldloca.s 0x10
0x5f83  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x5f88  stloc.s  0x11
0x5f8a  ldloc.s  0x11
0x5f8c  ldstr    aName// "Name"
0x5f91  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5f96  castclass [mscorlib]System.String
0x5f9b  stloc.s  0x12
0x5f9d  ldloc.s  0x11
0x5f9f  ldstr    aValue_0// "Value"
0x5fa4  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5fa9  castclass [mscorlib]System.String
0x5fae  stloc.s  0x13
0x5fb0  ldloc.s  0xF
0x5fb2  ldloc.s  0xE
0x5fb4  ldloc.s  0x12
0x5fb6  callvirt instance string Microsoft.Crm.EndUserNotification.SlugService::GetSlugType(class [System.Xml]System.Xml.XmlDocument slugXml, string slugName)
0x5fbb  ldstr    aDatetime// "datetime"
0x5fc0  ldc.i4.5
0x5fc1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x5fc6  brfalse.s loc_5FF7
0x5fc8  ldloc.s  0x13
0x5fca  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5fcf  ldc.i4.0
0x5fd0  ldloca.s 0x14
0x5fd2  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x5fd7  brfalse.s loc_5FF7
0x5fd9  ldloc.s  0x11
0x5fdb  ldstr    aValue_0// "Value"
0x5fe0  ldloca.s 0x14
0x5fe2  ldstr    aF// "f"
0x5fe7  ldloc.3
0x5fe8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::GetCultureInfo(int32)
0x5fed  call     instance string [mscorlib]System.DateTime::ToString(string, class [mscorlib]System.IFormatProvider)
0x5ff2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x5ff7  ldloca.s 0x10
0x5ff9  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x5ffe  brtrue.s loc_5F81
0x6000  leave.s  loc_602D
0x6002  ldloca.s 0x10
0x6004  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x600a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x600f  endfinally
0x6010  ldstr    aSlugxmlForTemp// "SlugXml for template name [{0}] version"...
0x6015  ldc.i4.2
0x6016  newarr   [mscorlib]System.Object
0x601b  dup
0x601c  ldc.i4.0
0x601d  ldloc.1
0x601e  stelem.ref
0x601f  dup
0x6020  ldc.i4.1
0x6021  ldloc.2
0x6022  box      [mscorlib]System.Int32
0x6027  stelem.ref
0x6028  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Warning(string, object[])
0x602d  ldloc.s  0xA
0x602f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x6034  box      [mscorlib]System.Guid
0x6039  ldstr    aUserFirstName// "USER_FIRST_NAME"
0x603e  ldarg.s  5
0x6040  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x6045  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x604a  ldloc.s  0xA
0x604c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x6051  box      [mscorlib]System.Guid
0x6056  ldstr    aUserLastName// "USER_LAST_NAME"
0x605b  ldarg.s  6
0x605d  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x6062  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6067  ldloc.s  0xA
0x6069  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x606e  box      [mscorlib]System.Guid
0x6073  ldstr    aUserWlid// "USER_WLID"
0x6078  ldarg.s  7
0x607a  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildParamPropertyBag(string name, string value)
0x607f  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6084  ldarg.2
0x6085  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x608a  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x608f  brfalse.s loc_60D6
0x6091  ldarg.0
0x6092  ldarg.2
0x6093  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildOrganizationDynamicParameter(valuetype [mscorlib]System.Guid organizationId)
0x6098  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x609d  stloc.s  0x15
0x609f  br.s     loc_60BD
0x60a1  ldloca.s 0x15
0x60a3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x60a8  stloc.s  0x16
0x60aa  ldloc.s  0xA
0x60ac  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x60b1  box      [mscorlib]System.Guid
0x60b6  ldloc.s  0x16
0x60b8  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x60bd  ldloca.s 0x15
0x60bf  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x60c4  brtrue.s loc_60A1
0x60c6  leave.s  loc_60D6
0x60c8  ldloca.s 0x15
0x60ca  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x60d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x60d5  endfinally
0x60d6  ldarg.0
0x60d7  ldloc.s  8
0x60d9  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildLinkDynamicParameters(bool isOsdpOrganization)
0x60de  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x60e3  stloc.s  0x15
0x60e5  br.s     loc_6103
0x60e7  ldloca.s 0x15
0x60e9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x60ee  stloc.s  0x17
0x60f0  ldloc.s  0xA
0x60f2  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x60f7  box      [mscorlib]System.Guid
0x60fc  ldloc.s  0x17
0x60fe  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6103  ldloca.s 0x15
0x6105  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x610a  brtrue.s loc_60E7
0x610c  leave.s  loc_611C
0x610e  ldloca.s 0x15
0x6110  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x6116  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x611b  endfinally
0x611c  ldarg.0
0x611d  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildPortalDynamicParameters()
0x6122  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x6127  stloc.s  0x15
0x6129  br.s     loc_6147
0x612b  ldloca.s 0x15
0x612d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x6132  stloc.s  0x18
0x6134  ldloc.s  0xA
0x6136  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x613b  box      [mscorlib]System.Guid
0x6140  ldloc.s  0x18
0x6142  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x6147  ldloca.s 0x15
0x6149  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x614e  brtrue.s loc_612B
0x6150  leave.s  loc_6160
0x6152  ldloca.s 0x15
0x6154  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x615a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x615f  endfinally
0x6160  ldarg.0
0x6161  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag> Microsoft.Crm.EndUserNotification.LocalizedUserNotificationService::BuildStorageDynamicParameters()
0x6166  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x616b  stloc.s  0x15
0x616d  br.s     loc_618B
0x616f  ldloca.s 0x15
0x6171  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x6176  stloc.s  0x19
0x6178  ldloc.s  0xA
0x617a  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x617f  box      [mscorlib]System.Guid
0x6184  ldloc.s  0x19
0x6186  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0x618b  ldloca.s 0x15
0x618d  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x6192  brtrue.s loc_616F
0x6194  leave.s  loc_61A4
0x6196  ldloca.s 0x15
0x6198  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x619e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
  ... truncated ...
```
