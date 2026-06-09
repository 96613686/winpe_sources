# Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::ExportItem

- ea: `0x6f9b0`
- end: `0x70152`
- name: `Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::ExportItem`
- size: `1954`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x3b380`
- `0x3b3c0`
- `0x6f7e0`
- `0x6f800`
- `0x6f820`
- `0x6f840`
- `0x6f860`
- `0x6f880`
- `0x6f8c0`
- `0x6f8e0`
- `0x6f940`
- `0x6f9b0`

## string_xrefs

- `0x6fd63`: `trackingtokenidbase`
- `0x6fd7d`: `trackingtokeniddigits`
- `0x6fe8d`: `acknowledgementtemplateid`
- `0x6ff3e`: `allowoutlookscheduledsyncs`
- `0x6ff8c`: `allowofflinescheduledsyncs`
- `0x7009c`: `createproductswithoutparentinactivestate`

## pseudocode

```c

```

## disassembly

```asm
0x6f9b0  ldarg.1
0x6f9b1  ldstr    aOrganizationse_11// "OrganizationSettings"
0x6f9b6  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6f9bb  stloc.0
0x6f9bc  ldarg.1
0x6f9bd  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x6f9c2  ldloc.0
0x6f9c3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6f9c8  pop
0x6f9c9  ldstr    aOrganization// "Organization"
0x6f9ce  ldarg.0
0x6f9cf  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6f9d4  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ServiceClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f9d9  ldarg.0
0x6f9da  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6f9df  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6f9e4  ldstr    aOrganization// "Organization"
0x6f9e9  ldarg.0
0x6f9ea  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6f9ef  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6f9f4  stloc.1
0x6f9f5  ldloc.1
0x6f9f6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x6f9fb  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x6fa00  ldarg.0
0x6fa01  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6fa06  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x6fa0b  stloc.2
0x6fa0c  ldloc.2
0x6fa0d  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6fa12  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddAllColumns()
0x6fa17  ldloc.1
0x6fa18  ldloc.2
0x6fa19  ldarg.0
0x6fa1a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6fa1f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6fa24  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization
0x6fa29  stloc.3
0x6fa2a  ldarg.0
0x6fa2b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_orgSettingsParameters
0x6fa30  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters::get_ExportGeneralSettings()
0x6fa35  brfalse  loc_6FC0C
0x6fa3a  ldarg.1
0x6fa3b  ldstr    aGeneral// "general"
0x6fa40  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6fa45  stloc.s  4
0x6fa47  ldloc.0
0x6fa48  ldloc.s  4
0x6fa4a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6fa4f  pop
0x6fa50  ldarg.0
0x6fa51  ldarg.1
0x6fa52  ldloc.3
0x6fa53  ldloc.s  4
0x6fa55  ldstr    aFullnameconven// "fullnameconventioncode"
0x6fa5a  ldtoken  [mscorlib]System.Int32
0x6fa5f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fa64  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fa69  pop
0x6fa6a  ldarg.0
0x6fa6b  ldarg.1
0x6fa6c  ldloc.3
0x6fa6d  ldloc.s  4
0x6fa6f  ldstr    aNumberformat// "numberformat"
0x6fa74  ldtoken  [mscorlib]System.String
0x6fa79  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fa7e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fa83  pop
0x6fa84  ldarg.0
0x6fa85  ldarg.1
0x6fa86  ldloc.3
0x6fa87  ldloc.s  4
0x6fa89  ldstr    aNegativeformat// "negativeformatcode"
0x6fa8e  ldtoken  [mscorlib]System.Int32
0x6fa93  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fa98  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fa9d  pop
0x6fa9e  ldarg.0
0x6fa9f  ldarg.1
0x6faa0  ldloc.3
0x6faa1  ldloc.s  4
0x6faa3  ldstr    aCurrencysymbol// "currencysymbol"
0x6faa8  ldtoken  [mscorlib]System.String
0x6faad  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fab2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fab7  pop
0x6fab8  ldarg.0
0x6fab9  ldarg.1
0x6faba  ldloc.3
0x6fabb  ldloc.s  4
0x6fabd  ldstr    aCurrencyformat// "currencyformatcode"
0x6fac2  ldtoken  [mscorlib]System.Int32
0x6fac7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6facc  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fad1  pop
0x6fad2  ldarg.0
0x6fad3  ldarg.1
0x6fad4  ldloc.3
0x6fad5  ldloc.s  4
0x6fad7  ldstr    aPricingdecimal// "pricingdecimalprecision"
0x6fadc  ldtoken  [mscorlib]System.Int32
0x6fae1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fae6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6faeb  pop
0x6faec  ldarg.0
0x6faed  ldarg.1
0x6faee  ldloc.3
0x6faef  ldloc.s  4
0x6faf1  ldstr    aSharetopreviou// "sharetopreviousowneronassign"
0x6faf6  ldtoken  [mscorlib]System.Boolean
0x6fafb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb00  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb05  pop
0x6fb06  ldarg.0
0x6fb07  ldarg.1
0x6fb08  ldloc.3
0x6fb09  ldloc.s  4
0x6fb0b  ldstr    aBlockedattachm// "blockedattachments"
0x6fb10  ldtoken  [mscorlib]System.String
0x6fb15  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb1a  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb1f  pop
0x6fb20  ldarg.0
0x6fb21  ldarg.1
0x6fb22  ldloc.3
0x6fb23  ldloc.s  4
0x6fb25  ldstr    aGetstartedpane_0// "getstartedpanecontentenabled"
0x6fb2a  ldtoken  [mscorlib]System.Boolean
0x6fb2f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb34  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb39  pop
0x6fb3a  ldarg.0
0x6fb3b  ldarg.1
0x6fb3c  ldloc.3
0x6fb3d  ldloc.s  4
0x6fb3f  ldstr    aIspresenceenab// "ispresenceenabled"
0x6fb44  ldtoken  [mscorlib]System.Boolean
0x6fb49  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb4e  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb53  pop
0x6fb54  ldarg.0
0x6fb55  ldarg.1
0x6fb56  ldloc.3
0x6fb57  ldloc.s  4
0x6fb59  ldstr    aIsautosaveenab// "isautosaveenabled"
0x6fb5e  ldtoken  [mscorlib]System.Boolean
0x6fb63  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb68  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb6d  pop
0x6fb6e  ldarg.0
0x6fb6f  ldarg.1
0x6fb70  ldloc.3
0x6fb71  ldloc.s  4
0x6fb73  ldstr    aGlobalhelpurl// "globalhelpurl"
0x6fb78  ldtoken  [mscorlib]System.String
0x6fb7d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb82  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fb87  pop
0x6fb88  ldarg.0
0x6fb89  ldarg.1
0x6fb8a  ldloc.3
0x6fb8b  ldloc.s  4
0x6fb8d  ldstr    aGlobalhelpurle// "globalhelpurlenabled"
0x6fb92  ldtoken  [mscorlib]System.Boolean
0x6fb97  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fb9c  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fba1  pop
0x6fba2  ldarg.0
0x6fba3  ldarg.1
0x6fba4  ldloc.3
0x6fba5  ldloc.s  4
0x6fba7  ldstr    aGlobalappendur// "globalappendurlparametersenabled"
0x6fbac  ldtoken  [mscorlib]System.Boolean
0x6fbb1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fbb6  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fbbb  pop
0x6fbbc  ldarg.0
0x6fbbd  ldarg.1
0x6fbbe  ldloc.3
0x6fbbf  ldloc.s  4
0x6fbc1  ldstr    aIstextwrapenab// "istextwrapenabled"
0x6fbc6  ldtoken  [mscorlib]System.Boolean
0x6fbcb  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fbd0  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fbd5  pop
0x6fbd6  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x6fbdb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x6fbe0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ExportAppointmentRichEditorExperienceOrgSetting()
0x6fbe5  ldarg.0
0x6fbe6  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6fbeb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6fbf0  brfalse.s loc_6FC0C
0x6fbf2  ldarg.0
0x6fbf3  ldarg.1
0x6fbf4  ldloc.3
0x6fbf5  ldloc.s  4
0x6fbf7  ldstr    aAppointmentric// "appointmentricheditorexperience"
0x6fbfc  ldtoken  [mscorlib]System.Boolean
0x6fc01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc06  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fc0b  pop
0x6fc0c  ldarg.0
0x6fc0d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_orgSettingsParameters
0x6fc12  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters::get_ExportCalendarSettings()
0x6fc17  brfalse  loc_6FD1E
0x6fc1c  ldarg.1
0x6fc1d  ldstr    aCalendar// "calendar"
0x6fc22  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6fc27  stloc.s  5
0x6fc29  ldloc.0
0x6fc2a  ldloc.s  5
0x6fc2c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6fc31  pop
0x6fc32  ldarg.0
0x6fc33  ldarg.1
0x6fc34  ldloc.3
0x6fc35  ldloc.s  5
0x6fc37  ldstr    aWeekstartdayco// "weekstartdaycode"
0x6fc3c  ldtoken  [mscorlib]System.Int32
0x6fc41  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc46  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fc4b  pop
0x6fc4c  ldarg.0
0x6fc4d  ldarg.1
0x6fc4e  ldloc.3
0x6fc4f  ldloc.s  5
0x6fc51  ldstr    aCalendartype// "calendartype"
0x6fc56  ldtoken  [mscorlib]System.Int32
0x6fc5b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc60  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fc65  pop
0x6fc66  ldarg.0
0x6fc67  ldarg.1
0x6fc68  ldloc.3
0x6fc69  ldloc.s  5
0x6fc6b  ldstr    aDateformatcode// "dateformatcode"
0x6fc70  ldtoken  [mscorlib]System.Int32
0x6fc75  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc7a  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fc7f  pop
0x6fc80  ldarg.0
0x6fc81  ldarg.1
0x6fc82  ldloc.3
0x6fc83  ldloc.s  5
0x6fc85  ldstr    aDateseparator// "dateseparator"
0x6fc8a  ldtoken  [mscorlib]System.String
0x6fc8f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fc94  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fc99  pop
0x6fc9a  ldarg.0
0x6fc9b  ldarg.1
0x6fc9c  ldloc.3
0x6fc9d  ldloc.s  5
0x6fc9f  ldstr    aTimeformatcode// "timeformatcode"
0x6fca4  ldtoken  [mscorlib]System.Int32
0x6fca9  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fcae  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fcb3  pop
0x6fcb4  ldarg.0
0x6fcb5  ldarg.1
0x6fcb6  ldloc.3
0x6fcb7  ldloc.s  5
0x6fcb9  ldstr    aShowweeknumber// "showweeknumber"
0x6fcbe  ldtoken  [mscorlib]System.Boolean
0x6fcc3  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fcc8  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fccd  pop
0x6fcce  ldarg.0
0x6fccf  ldarg.1
0x6fcd0  ldloc.3
0x6fcd1  ldloc.s  5
0x6fcd3  ldstr    aMaxappointment// "maxappointmentdurationdays"
0x6fcd8  ldtoken  [mscorlib]System.Int32
0x6fcdd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fce2  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fce7  pop
0x6fce8  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x6fced  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x6fcf2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_EnableSchedulingEngine()
0x6fcf7  ldarg.0
0x6fcf8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_context
0x6fcfd  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x6fd02  brfalse.s loc_6FD1E
0x6fd04  ldarg.0
0x6fd05  ldarg.1
0x6fd06  ldloc.3
0x6fd07  ldloc.s  5
0x6fd09  ldstr    aSchedulingengi// "schedulingengine"
0x6fd0e  ldtoken  [mscorlib]System.Int32
0x6fd13  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6fd18  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::AddNode(class [System.Xml]System.Xml.XmlDocument importDocument, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Organization org, class [System.Xml]System.Xml.XmlElement orgNode, string attributeName, class [mscorlib]System.Type type)
0x6fd1d  pop
0x6fd1e  ldarg.0
0x6fd1f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsHandler::_orgSettingsParameters
0x6fd24  callvirt instance bool Microsoft.Crm.Tools.ImportExportPublish.OrgSettingsParameters::get_ExportEmailTrackingSettings()
0x6fd29  brfalse  loc_6FDFA
0x6fd2e  ldarg.1
0x6fd2f  ldstr    aEmail_0// "email"
0x6fd34  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x6fd39  stloc.s  6
  ... truncated ...
```
