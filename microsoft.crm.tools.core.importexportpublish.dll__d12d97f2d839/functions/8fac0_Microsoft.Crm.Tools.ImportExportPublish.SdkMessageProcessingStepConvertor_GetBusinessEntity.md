# Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::GetBusinessEntity

- ea: `0x8fac0`
- end: `0x8fe83`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::GetBusinessEntity`
- size: `963`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x8fac0`
- `0x8fe90`
- `0x90060`
- `0x90190`

## string_xrefs

- `0x8fcf8`: `PluginTypeId`
- `0x8fb49`: `asyncautodelete`
- `0x8fb3a`: `AsyncAutoDelete`
- `0x8fb69`: `Configuration`
- `0x8fb78`: `configuration`
- `0x8fbe8`: `ImpersonatingUserIdName`
- `0x8fbf7`: `impersonatinguseridname`
- `0x8fd55`: `PluginTypeName`

## pseudocode

```c

```

## disassembly

```asm
0x8fac0  ldarg.1
0x8fac1  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SdkMessageProcessingStep::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8fac6  stloc.0
0x8fac7  ldloca.s 1
0x8fac9  ldarg.2
0x8faca  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8facf  ldstr    aSdkmessageproc_4// "SdkMessageProcessingStepId"
0x8fad4  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8fad9  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x8fade  call     instance void [mscorlib]System.Guid::.ctor(string)
0x8fae3  ldloc.0
0x8fae4  ldstr    aSdkmessageproc_0// "sdkmessageprocessingstepid"
0x8fae9  ldloc.1
0x8faea  box      [mscorlib]System.Guid
0x8faef  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8faf4  ldarg.2
0x8faf5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x8fafa  ldstr    aName_1// "Name"
0x8faff  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x8fb04  stloc.2
0x8fb05  ldloc.2
0x8fb06  brfalse.s loc_8FB19
0x8fb08  ldloc.0
0x8fb09  ldstr    aName// "name"
0x8fb0e  ldloc.2
0x8fb0f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fb14  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fb19  ldarg.2
0x8fb1a  ldstr    aDescription_0// "Description"
0x8fb1f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fb24  stloc.3
0x8fb25  ldloc.3
0x8fb26  brfalse.s loc_8FB39
0x8fb28  ldloc.0
0x8fb29  ldstr    aDescription// "description"
0x8fb2e  ldloc.3
0x8fb2f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fb34  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fb39  ldarg.2
0x8fb3a  ldstr    aAsyncautodelet_1// "AsyncAutoDelete"
0x8fb3f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fb44  stloc.3
0x8fb45  ldloc.3
0x8fb46  brfalse.s loc_8FB68
0x8fb48  ldloc.0
0x8fb49  ldstr    aAsyncautodelet_0// "asyncautodelete"
0x8fb4e  ldloc.3
0x8fb4f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fb54  ldstr    a1// "1"
0x8fb59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8fb5e  box      [mscorlib]System.Boolean
0x8fb63  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fb68  ldarg.2
0x8fb69  ldstr    aConfiguration// "Configuration"
0x8fb6e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fb73  stloc.3
0x8fb74  ldloc.3
0x8fb75  brfalse.s loc_8FB88
0x8fb77  ldloc.0
0x8fb78  ldstr    aConfiguration_0// "configuration"
0x8fb7d  ldloc.3
0x8fb7e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fb83  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fb88  ldarg.2
0x8fb89  ldstr    aEventexpander_0// "EventExpander"
0x8fb8e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fb93  stloc.3
0x8fb94  ldloc.3
0x8fb95  brfalse.s loc_8FBA8
0x8fb97  ldloc.0
0x8fb98  ldstr    aEventexpander// "eventexpander"
0x8fb9d  ldloc.3
0x8fb9e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fba3  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fba8  ldarg.2
0x8fba9  ldstr    aFilteringattri// "FilteringAttributes"
0x8fbae  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fbb3  stloc.3
0x8fbb4  ldloc.3
0x8fbb5  brfalse.s loc_8FBE7
0x8fbb7  ldloc.3
0x8fbb8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fbbd  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8fbc2  brtrue.s loc_8FBD6
0x8fbc4  ldloc.0
0x8fbc5  ldstr    aFilteringattri_0// "filteringattributes"
0x8fbca  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x8fbcf  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fbd4  br.s     loc_8FBE7
0x8fbd6  ldloc.0
0x8fbd7  ldstr    aFilteringattri_0// "filteringattributes"
0x8fbdc  ldloc.3
0x8fbdd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fbe2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fbe7  ldarg.2
0x8fbe8  ldstr    aImpersonatingu// "ImpersonatingUserIdName"
0x8fbed  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fbf2  stloc.3
0x8fbf3  ldloc.3
0x8fbf4  brfalse.s loc_8FC07
0x8fbf6  ldloc.0
0x8fbf7  ldstr    aImpersonatingu_0// "impersonatinguseridname"
0x8fbfc  ldloc.3
0x8fbfd  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fc02  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fc07  ldarg.2
0x8fc08  ldstr    aInvocationsour// "InvocationSource"
0x8fc0d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fc12  stloc.3
0x8fc13  ldloc.3
0x8fc14  brfalse.s loc_8FC36
0x8fc16  ldloc.0
0x8fc17  ldstr    aInvocationsour_0// "invocationsource"
0x8fc1c  ldloc.3
0x8fc1d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fc22  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fc27  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fc2c  box      [mscorlib]System.Int32
0x8fc31  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fc36  ldarg.2
0x8fc37  ldstr    aMode// "Mode"
0x8fc3c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fc41  stloc.3
0x8fc42  ldloc.3
0x8fc43  brfalse.s loc_8FC65
0x8fc45  ldloc.0
0x8fc46  ldstr    aMode_0// "mode"
0x8fc4b  ldloc.3
0x8fc4c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fc51  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fc56  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fc5b  box      [mscorlib]System.Int32
0x8fc60  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fc65  ldarg.2
0x8fc66  ldstr    aRank// "Rank"
0x8fc6b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fc70  stloc.3
0x8fc71  ldloc.3
0x8fc72  brfalse.s loc_8FC94
0x8fc74  ldloc.0
0x8fc75  ldstr    aRank_0// "rank"
0x8fc7a  ldloc.3
0x8fc7b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fc80  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fc85  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fc8a  box      [mscorlib]System.Int32
0x8fc8f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fc94  ldarg.2
0x8fc95  ldstr    aSdkmessageid_0// "SdkMessageId"
0x8fc9a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fc9f  stloc.3
0x8fca0  ldloc.0
0x8fca1  ldstr    aSdkmessageid// "sdkmessageid"
0x8fca6  ldloc.3
0x8fca7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fcac  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8fcb1  box      [mscorlib]System.Guid
0x8fcb6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fcbb  ldarg.2
0x8fcbc  ldstr    aEventhandlerty// "EventHandlerTypeCode"
0x8fcc1  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fcc6  stloc.3
0x8fcc7  ldloc.3
0x8fcc8  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fccd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fcd2  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fcd7  stloc.s  4
0x8fcd9  ldloc.0
0x8fcda  ldstr    aEventhandlerty_0// "eventhandlertypecode"
0x8fcdf  ldloc.s  4
0x8fce1  box      [mscorlib]System.Int32
0x8fce6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fceb  ldloc.s  4
0x8fced  ldc.i4   0x11FA
0x8fcf2  bne.un   loc_8FD7F
0x8fcf7  ldarg.2
0x8fcf8  ldstr    aPlugintypeid// "PluginTypeId"
0x8fcfd  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fd02  stloc.3
0x8fd03  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd08  stloc.s  5
0x8fd0a  ldloc.3
0x8fd0b  brfalse.s loc_8FD27
0x8fd0d  ldloc.3
0x8fd0e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fd13  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8fd18  brtrue.s loc_8FD27
0x8fd1a  ldloca.s 5
0x8fd1c  ldloc.3
0x8fd1d  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fd22  call     instance void [mscorlib]System.Guid::.ctor(string)
0x8fd27  ldloc.s  5
0x8fd29  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd2e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8fd33  brfalse.s loc_8FD54
0x8fd35  ldarg.0
0x8fd36  ldloc.s  5
0x8fd38  ldarg.1
0x8fd39  call     instance bool Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::ValidatePluginTypeId(valuetype [mscorlib]System.Guid pluginTypeId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fd3e  brfalse.s loc_8FD54
0x8fd40  ldloc.0
0x8fd41  ldstr    aEventhandler_0// "eventhandler"
0x8fd46  ldloc.s  5
0x8fd48  box      [mscorlib]System.Guid
0x8fd4d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fd52  br.s     loc_8FDA6
0x8fd54  ldarg.2
0x8fd55  ldstr    aPlugintypename// "PluginTypeName"
0x8fd5a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fd5f  stloc.3
0x8fd60  ldloc.0
0x8fd61  ldstr    aEventhandler_0// "eventhandler"
0x8fd66  ldarg.0
0x8fd67  ldarg.1
0x8fd68  ldloc.3
0x8fd69  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fd6e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.SdkMessageProcessingStepConvertor::FindPluginTypeId(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string assemblyQualifiedName)
0x8fd73  box      [mscorlib]System.Guid
0x8fd78  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fd7d  br.s     loc_8FDA6
0x8fd7f  ldarg.2
0x8fd80  ldstr    aEventhandler// "EventHandler"
0x8fd85  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fd8a  stloc.3
0x8fd8b  ldloc.0
0x8fd8c  ldstr    aEventhandler_0// "eventhandler"
0x8fd91  ldloc.3
0x8fd92  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fd97  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x8fd9c  box      [mscorlib]System.Guid
0x8fda1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fda6  ldarg.2
0x8fda7  ldstr    aStage// "Stage"
0x8fdac  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fdb1  stloc.3
0x8fdb2  ldloc.3
0x8fdb3  brfalse.s loc_8FDD5
0x8fdb5  ldloc.0
0x8fdb6  ldstr    aStage_0// "stage"
0x8fdbb  ldloc.3
0x8fdbc  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fdc1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fdc6  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fdcb  box      [mscorlib]System.Int32
0x8fdd0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fdd5  ldarg.2
0x8fdd6  ldstr    aIscustomizable_0// "IsCustomizable"
0x8fddb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fde0  stloc.3
0x8fde1  ldloc.3
0x8fde2  brfalse.s loc_8FDFF
0x8fde4  ldloc.0
0x8fde5  ldstr    aIscustomizable// "iscustomizable"
0x8fdea  ldloc.3
0x8fdeb  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fdf0  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x8fdf5  box      [mscorlib]System.Boolean
0x8fdfa  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fdff  ldarg.2
0x8fe00  ldstr    aIshidden// "IsHidden"
0x8fe05  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fe0a  stloc.3
0x8fe0b  ldloc.3
0x8fe0c  brfalse.s loc_8FE29
0x8fe0e  ldloc.0
0x8fe0f  ldstr    aIshidden_0// "ishidden"
0x8fe14  ldloc.3
0x8fe15  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fe1a  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0x8fe1f  box      [mscorlib]System.Boolean
0x8fe24  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fe29  ldarg.2
0x8fe2a  ldstr    aSupporteddeplo// "SupportedDeployment"
0x8fe2f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fe34  stloc.3
0x8fe35  ldloc.3
0x8fe36  brfalse.s loc_8FE58
0x8fe38  ldloc.0
0x8fe39  ldstr    aSupporteddeplo_0// "supporteddeployment"
0x8fe3e  ldloc.3
0x8fe3f  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fe44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8fe49  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x8fe4e  box      [mscorlib]System.Int32
0x8fe53  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fe58  ldarg.2
0x8fe59  ldstr    aIntroducedvers_0// "IntroducedVersion"
0x8fe5e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x8fe63  stloc.3
0x8fe64  ldloc.3
0x8fe65  brfalse.s loc_8FE78
0x8fe67  ldloc.0
0x8fe68  ldstr    aIntroducedvers// "introducedversion"
0x8fe6d  ldloc.3
0x8fe6e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x8fe73  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x8fe78  ldarg.0
0x8fe79  ldloc.0
0x8fe7a  ldarg.2
0x8fe7b  ldarg.1
  ... truncated ...
```
