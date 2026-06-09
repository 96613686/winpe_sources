# Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::ImportItem

- ea: `0x53c50`
- end: `0x54487`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::ImportItem`
- size: `2103`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x35970`
- `0x53af0`
- `0x53b20`
- `0x53c50`
- `0x54490`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x53c56`: `/ImportExportXml/OrganizationSettings`
- `0x53f76`: `trackingtokenidbase`
- `0x53f92`: `trackingtokeniddigits`
- `0x5408e`: `acknowledgementtemplateid`
- `0x540fe`: `allowoutlookscheduledsyncs`
- `0x54152`: `allowofflinescheduledsyncs`
- `0x5434a`: `createproductswithoutparentinactivestate`

## pseudocode

```c

```

## disassembly

```asm
0x53c50  ldarg.0
0x53c51  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x53c56  ldstr    aImportexportxm_130// "/ImportExportXml/OrganizationSettings"
0x53c5b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x53c60  stloc.0
0x53c61  ldloc.0
0x53c62  brfalse.s loc_53C71
0x53c64  ldloc.0
0x53c65  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x53c6a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x53c6f  brtrue.s loc_53C72
0x53c71  ret
0x53c72  nop
0x53c73  ldstr    aOrganization// "Organization"
0x53c78  ldarg.0
0x53c79  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::_context
0x53c7e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x53c83  stloc.1
0x53c84  ldarg.0
0x53c85  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::_context
0x53c8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x53c8f  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization::.ctor(valuetype [mscorlib]System.Guid)
0x53c94  stloc.2
0x53c95  ldloc.2
0x53c96  ldstr    aOrganizationid// "organizationid"
0x53c9b  ldarg.0
0x53c9c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::_context
0x53ca1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x53ca6  box      [mscorlib]System.Guid
0x53cab  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x53cb0  ldarg.0
0x53cb1  ldloc.0
0x53cb2  ldloc.2
0x53cb3  ldstr    aGeneral// "general"
0x53cb8  ldstr    aFullnameconven// "fullnameconventioncode"
0x53cbd  ldtoken  [mscorlib]System.Int32
0x53cc2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53cc7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ccc  ldarg.0
0x53ccd  ldloc.0
0x53cce  ldloc.2
0x53ccf  ldstr    aGeneral// "general"
0x53cd4  ldstr    aNumberformat// "numberformat"
0x53cd9  ldtoken  [mscorlib]System.String
0x53cde  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ce3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ce8  ldarg.0
0x53ce9  ldloc.0
0x53cea  ldloc.2
0x53ceb  ldstr    aGeneral// "general"
0x53cf0  ldstr    aNegativeformat// "negativeformatcode"
0x53cf5  ldtoken  [mscorlib]System.Int32
0x53cfa  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53cff  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d04  ldarg.0
0x53d05  ldloc.0
0x53d06  ldloc.2
0x53d07  ldstr    aGeneral// "general"
0x53d0c  ldstr    aCurrencysymbol// "currencysymbol"
0x53d11  ldtoken  [mscorlib]System.String
0x53d16  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d1b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d20  ldarg.0
0x53d21  ldloc.0
0x53d22  ldloc.2
0x53d23  ldstr    aGeneral// "general"
0x53d28  ldstr    aCurrencyformat// "currencyformatcode"
0x53d2d  ldtoken  [mscorlib]System.Int32
0x53d32  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d37  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d3c  ldarg.0
0x53d3d  ldloc.0
0x53d3e  ldloc.2
0x53d3f  ldstr    aGeneral// "general"
0x53d44  ldstr    aPricingdecimal// "pricingdecimalprecision"
0x53d49  ldtoken  [mscorlib]System.Int32
0x53d4e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d53  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d58  ldarg.0
0x53d59  ldloc.0
0x53d5a  ldloc.2
0x53d5b  ldstr    aGeneral// "general"
0x53d60  ldstr    aSharetopreviou// "sharetopreviousowneronassign"
0x53d65  ldtoken  [mscorlib]System.Boolean
0x53d6a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d6f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d74  ldarg.0
0x53d75  ldloc.0
0x53d76  ldloc.2
0x53d77  ldstr    aGeneral// "general"
0x53d7c  ldstr    aBlockedattachm// "blockedattachments"
0x53d81  ldtoken  [mscorlib]System.String
0x53d86  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53d8b  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53d90  ldarg.0
0x53d91  ldloc.0
0x53d92  ldloc.2
0x53d93  ldstr    aGeneral// "general"
0x53d98  ldstr    aGetstartedpane_0// "getstartedpanecontentenabled"
0x53d9d  ldtoken  [mscorlib]System.Boolean
0x53da2  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53da7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53dac  ldarg.0
0x53dad  ldloc.0
0x53dae  ldloc.2
0x53daf  ldstr    aGeneral// "general"
0x53db4  ldstr    aIspresenceenab// "ispresenceenabled"
0x53db9  ldtoken  [mscorlib]System.Boolean
0x53dbe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53dc3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53dc8  ldarg.0
0x53dc9  ldloc.0
0x53dca  ldloc.2
0x53dcb  ldstr    aGeneral// "general"
0x53dd0  ldstr    aIsautosaveenab// "isautosaveenabled"
0x53dd5  ldtoken  [mscorlib]System.Boolean
0x53dda  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ddf  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53de4  ldarg.0
0x53de5  ldloc.0
0x53de6  ldloc.2
0x53de7  ldstr    aGeneral// "general"
0x53dec  ldstr    aGlobalhelpurl// "globalhelpurl"
0x53df1  ldtoken  [mscorlib]System.String
0x53df6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53dfb  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e00  ldarg.0
0x53e01  ldloc.0
0x53e02  ldloc.2
0x53e03  ldstr    aGeneral// "general"
0x53e08  ldstr    aGlobalhelpurle// "globalhelpurlenabled"
0x53e0d  ldtoken  [mscorlib]System.Boolean
0x53e12  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53e17  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e1c  ldarg.0
0x53e1d  ldloc.0
0x53e1e  ldloc.2
0x53e1f  ldstr    aGeneral// "general"
0x53e24  ldstr    aGlobalappendur// "globalappendurlparametersenabled"
0x53e29  ldtoken  [mscorlib]System.Boolean
0x53e2e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53e33  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e38  ldarg.0
0x53e39  ldloc.0
0x53e3a  ldloc.2
0x53e3b  ldstr    aGeneral// "general"
0x53e40  ldstr    aIstextwrapenab// "istextwrapenabled"
0x53e45  ldtoken  [mscorlib]System.Boolean
0x53e4a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53e4f  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e54  ldarg.0
0x53e55  ldloc.0
0x53e56  ldloc.2
0x53e57  ldstr    aGeneral// "general"
0x53e5c  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x53e61  ldtoken  [mscorlib]System.Boolean
0x53e66  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53e6b  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::TrySetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e70  pop
0x53e71  ldarg.0
0x53e72  ldloc.0
0x53e73  ldloc.2
0x53e74  ldstr    aCalendar// "calendar"
0x53e79  ldstr    aWeekstartdayco// "weekstartdaycode"
0x53e7e  ldtoken  [mscorlib]System.Int32
0x53e83  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53e88  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53e8d  ldarg.0
0x53e8e  ldloc.0
0x53e8f  ldloc.2
0x53e90  ldstr    aCalendar// "calendar"
0x53e95  ldstr    aCalendartype// "calendartype"
0x53e9a  ldtoken  [mscorlib]System.Int32
0x53e9f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ea4  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ea9  ldarg.0
0x53eaa  ldloc.0
0x53eab  ldloc.2
0x53eac  ldstr    aCalendar// "calendar"
0x53eb1  ldstr    aDateformatcode// "dateformatcode"
0x53eb6  ldtoken  [mscorlib]System.Int32
0x53ebb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ec0  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ec5  ldarg.0
0x53ec6  ldloc.0
0x53ec7  ldloc.2
0x53ec8  ldstr    aCalendar// "calendar"
0x53ecd  ldstr    aDateseparator// "dateseparator"
0x53ed2  ldtoken  [mscorlib]System.String
0x53ed7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53edc  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ee1  ldarg.0
0x53ee2  ldloc.0
0x53ee3  ldloc.2
0x53ee4  ldstr    aCalendar// "calendar"
0x53ee9  ldstr    aTimeformatcode// "timeformatcode"
0x53eee  ldtoken  [mscorlib]System.Int32
0x53ef3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ef8  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53efd  ldarg.0
0x53efe  ldloc.0
0x53eff  ldloc.2
0x53f00  ldstr    aCalendar// "calendar"
0x53f05  ldstr    aShowweeknumber// "showweeknumber"
0x53f0a  ldtoken  [mscorlib]System.Boolean
0x53f0f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53f14  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53f19  ldarg.0
0x53f1a  ldloc.0
0x53f1b  ldloc.2
0x53f1c  ldstr    aCalendar// "calendar"
0x53f21  ldstr    aMaxappointment// "maxappointmentdurationdays"
0x53f26  ldtoken  [mscorlib]System.Int32
0x53f2b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53f30  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53f35  ldarg.0
0x53f36  ldloc.0
0x53f37  ldloc.2
0x53f38  ldstr    aCalendar// "calendar"
0x53f3d  ldstr    aSchedulingengi// "schedulingengine"
0x53f42  ldtoken  [mscorlib]System.Int32
0x53f47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53f4c  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::TrySetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53f51  pop
0x53f52  ldarg.0
0x53f53  ldloc.0
0x53f54  ldloc.2
0x53f55  ldstr    aEmail_0// "email"
0x53f5a  ldstr    aTrackingprefix// "trackingprefix"
0x53f5f  ldtoken  [mscorlib]System.String
0x53f64  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53f69  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53f6e  ldarg.0
0x53f6f  ldloc.0
0x53f70  ldloc.2
0x53f71  ldstr    aEmail_0// "email"
0x53f76  ldstr    aTrackingtokeni// "trackingtokenidbase"
0x53f7b  ldtoken  [mscorlib]System.Int32
0x53f80  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53f85  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53f8a  ldarg.0
0x53f8b  ldloc.0
0x53f8c  ldloc.2
0x53f8d  ldstr    aEmail_0// "email"
0x53f92  ldstr    aTrackingtokeni_0// "trackingtokeniddigits"
0x53f97  ldtoken  [mscorlib]System.Byte
0x53f9c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53fa1  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53fa6  ldarg.0
0x53fa7  ldloc.0
0x53fa8  ldloc.2
0x53fa9  ldstr    aEmail_0// "email"
0x53fae  ldstr    aMaximumtrackin// "maximumtrackingnumber"
0x53fb3  ldtoken  [mscorlib]System.Int32
0x53fb8  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53fbd  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53fc2  ldarg.0
0x53fc3  ldloc.0
0x53fc4  ldloc.2
0x53fc5  ldstr    aEmail_0// "email"
0x53fca  ldstr    aIgnoreinternal// "ignoreinternalemail"
0x53fcf  ldtoken  [mscorlib]System.Boolean
0x53fd4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53fd9  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53fde  ldarg.0
0x53fdf  ldloc.0
0x53fe0  ldloc.2
0x53fe1  ldstr    aEmail_0// "email"
0x53fe6  ldstr    aRendersecureif// "rendersecureiframeforemail"
0x53feb  ldtoken  [mscorlib]System.Boolean
0x53ff0  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x53ff5  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x53ffa  ldarg.0
0x53ffb  ldloc.0
0x53ffc  ldloc.2
0x53ffd  ldstr    aEmail_0// "email"
0x54002  ldstr    aAllowunresolve// "allowunresolvedpartiesonemailsend"
0x54007  ldtoken  [mscorlib]System.Boolean
0x5400c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x54011  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x54016  ldarg.0
0x54017  ldloc.0
0x54018  ldloc.2
0x54019  ldstr    aMarketing// "marketing"
0x5401e  ldstr    aAllowmarketing// "allowmarketingemailexecution"
0x54023  ldtoken  [mscorlib]System.Boolean
0x54028  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5402d  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x54032  ldarg.0
0x54033  ldloc.0
0x54034  ldloc.2
0x54035  ldstr    aMarketing// "marketing"
0x5403a  ldstr    aAllowautorespo// "allowautoresponsecreation"
0x5403f  ldtoken  [mscorlib]System.Boolean
0x54044  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x54049  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportOrgSettingsHandler::SetAttributeValue(class [System.Xml]System.Xml.XmlNode orgSettingsNode, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, string subtype, string attributeName, class [mscorlib]System.Type type)
0x5404e  ldarg.0
0x5404f  ldloc.0
0x54050  ldloc.2
0x54051  ldstr    aMarketing// "marketing"
  ... truncated ...
```
