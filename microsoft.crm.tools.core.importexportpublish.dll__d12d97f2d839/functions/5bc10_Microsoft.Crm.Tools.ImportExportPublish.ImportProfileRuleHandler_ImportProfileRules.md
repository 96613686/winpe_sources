# Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::ImportProfileRules

- ea: `0x5bc10`
- end: `0x5be2e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::ImportProfileRules`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x5bb80`

## callees

- `0x36160`
- `0x5bc10`
- `0x5be30`
- `0x5c000`
- `0x5c1c0`
- `0x63db0`
- `0x63df0`
- `0x686f0`
- `0x68720`
- `0x72e50`

## string_xrefs

- `0x5bc34`: `ChannelAccessProfileRuleId`
- `0x5bc77`: `ChannelAccessProfileRuleId`
- `0x5bcab`: `channelaccessprofileruleid`
- `0x5bd60`: `ChannelAccessProfileRuleItems`
- `0x5bd72`: `ChannelAccessProfileRuleItem`

## pseudocode

```c

```

## disassembly

```asm
0x5bc10  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bc15  stloc.0
0x5bc16  ldarg.1
0x5bc17  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x5bc1c  stloc.1
0x5bc1d  br       loc_5BDB7
0x5bc22  ldloc.1
0x5bc23  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x5bc28  castclass [System.Xml]System.Xml.XmlNode
0x5bc2d  stloc.2
0x5bc2e  ldloc.2
0x5bc2f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5bc34  ldstr    aChannelaccessp_2// "ChannelAccessProfileRuleId"
0x5bc39  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5bc3e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5bc43  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x5bc48  stloc.0
0x5bc49  ldc.i4   0xA9
0x5bc4e  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x5bc53  ldarg.0
0x5bc54  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x5bc59  ldsfld   string [mscorlib]System.String::Empty
0x5bc5e  ldloc.0
0x5bc5f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5bc64  ldarg.0
0x5bc65  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::context
0x5bc6a  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5bc6f  ldloca.s 3
0x5bc71  ldloc.2
0x5bc72  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5bc77  ldstr    aChannelaccessp_2// "ChannelAccessProfileRuleId"
0x5bc7c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5bc81  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5bc86  call     instance void [mscorlib]System.Guid::.ctor(string)
0x5bc8b  ldloc.2
0x5bc8c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5bc91  ldstr    aName_1// "Name"
0x5bc96  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x5bc9b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x5bca0  stloc.s  4
0x5bca2  ldloc.3
0x5bca3  ldc.i4.2
0x5bca4  newarr   [mscorlib]System.String
0x5bca9  dup
0x5bcaa  ldc.i4.0
0x5bcab  ldstr    aChannelaccessp_3// "channelaccessprofileruleid"
0x5bcb0  stelem.ref
0x5bcb1  dup
0x5bcb2  ldc.i4.1
0x5bcb3  ldstr    aWorkflowid_0// "workflowid"
0x5bcb8  stelem.ref
0x5bcb9  ldarg.0
0x5bcba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::context
0x5bcbf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ProfileRuleImportExportHelper::RetrieveProfileRule(valuetype [mscorlib]System.Guid profileRuleId, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x5bcc4  stloc.s  5
0x5bcc6  ldloc.s  5
0x5bcc8  brfalse.s loc_5BCD3
0x5bcca  ldloc.s  5
0x5bccc  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5bcd1  brtrue.s loc_5BD0C
0x5bcd3  ldarg.0
0x5bcd4  ldloc.2
0x5bcd5  ldnull
0x5bcd6  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::CreateOrUpdateProfileRule(class [System.Xml]System.Xml.XmlNode profileRuleNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingProfileRule)
0x5bcdb  ldarg.0
0x5bcdc  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::tracer
0x5bce1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5bce6  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ReportImportSuccessMessage
0x5bceb  ldc.i4.2
0x5bcec  newarr   [mscorlib]System.Object
0x5bcf1  dup
0x5bcf2  ldc.i4.0
0x5bcf3  ldloc.s  4
0x5bcf5  stelem.ref
0x5bcf6  dup
0x5bcf7  ldc.i4.1
0x5bcf8  ldloc.3
0x5bcf9  box      [mscorlib]System.Guid
0x5bcfe  stelem.ref
0x5bcff  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5bd04  ldc.i4.1
0x5bd05  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x5bd0a  br.s     loc_5BD4A
0x5bd0c  ldarg.0
0x5bd0d  ldloc.2
0x5bd0e  ldloc.s  5
0x5bd10  ldc.i4.0
0x5bd11  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x5bd16  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::CreateOrUpdateProfileRule(class [System.Xml]System.Xml.XmlNode profileRuleNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingProfileRule)
0x5bd1b  ldarg.0
0x5bd1c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::tracer
0x5bd21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5bd26  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ReportImportSuccessMessage
0x5bd2b  ldc.i4.2
0x5bd2c  newarr   [mscorlib]System.Object
0x5bd31  dup
0x5bd32  ldc.i4.0
0x5bd33  ldloc.s  4
0x5bd35  stelem.ref
0x5bd36  dup
0x5bd37  ldc.i4.1
0x5bd38  ldloc.3
0x5bd39  box      [mscorlib]System.Guid
0x5bd3e  stelem.ref
0x5bd3f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5bd44  ldc.i4.1
0x5bd45  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x5bd4a  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x5bd4f  dup
0x5bd50  ldloc.2
0x5bd51  callvirt instance string [System.Xml]System.Xml.XmlNode::get_OuterXml()
0x5bd56  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x5bd5b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x5bd60  ldstr    aChannelaccessp_17// "ChannelAccessProfileRuleItems"
0x5bd65  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x5bd6a  stloc.s  6
0x5bd6c  ldloc.s  6
0x5bd6e  brfalse.s loc_5BD9D
0x5bd70  ldloc.s  6
0x5bd72  ldstr    aChannelaccessp_18// "ChannelAccessProfileRuleItem"
0x5bd77  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x5bd7c  stloc.s  7
0x5bd7e  ldarg.1
0x5bd7f  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x5bd84  ldc.i4.0
0x5bd85  ble.s    loc_5BD8F
0x5bd87  ldarg.0
0x5bd88  ldloc.s  7
0x5bd8a  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::ImportProfileRuleItems(class [System.Xml]System.Xml.XmlNodeList profileRuleItems)
0x5bd8f  leave.s  loc_5BD9D
0x5bd91  ldloc.s  7
0x5bd93  brfalse.s loc_5BD9C
0x5bd95  ldloc.s  7
0x5bd97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bd9c  endfinally
0x5bd9d  ldarg.0
0x5bd9e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x5bda3  ldarg.0
0x5bda4  ldloc.0
0x5bda5  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::GetParameterXPath(valuetype [mscorlib]System.Guid id)
0x5bdaa  ldstr    aSuccess// "success"
0x5bdaf  ldnull
0x5bdb0  ldc.i4.1
0x5bdb1  ldc.i4.0
0x5bdb2  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x5bdb7  ldloc.1
0x5bdb8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5bdbd  brtrue   loc_5BC22
0x5bdc2  leave.s  loc_5BDD8
0x5bdc4  ldloc.1
0x5bdc5  isinst   [mscorlib]System.IDisposable
0x5bdca  stloc.s  8
0x5bdcc  ldloc.s  8
0x5bdce  brfalse.s loc_5BDD7
0x5bdd0  ldloc.s  8
0x5bdd2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5bdd7  endfinally
0x5bdd8  leave.s  loc_5BE2D
0x5bdda  stloc.s  9
0x5bddc  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ProfileRuleImportErrorMessage
0x5bde1  stloc.s  0xA
0x5bde3  ldarg.0
0x5bde4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::tracer
0x5bde9  ldloc.s  0xA
0x5bdeb  ldloc.s  9
0x5bded  ldc.i4.3
0x5bdee  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x5bdf3  ldloc.s  9
0x5bdf5  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException
0x5bdfa  ldnull
0x5bdfb  cgt.un
0x5bdfd  ldc.i4.0
0x5bdfe  ceq
0x5be00  stloc.s  0xB
0x5be02  ldarg.0
0x5be03  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x5be08  ldarg.0
0x5be09  ldloc.0
0x5be0a  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRuleHandler::GetParameterXPath(valuetype [mscorlib]System.Guid id)
0x5be0f  ldstr    aFailure// "failure"
0x5be14  ldloc.s  9
0x5be16  ldc.i4.0
0x5be17  ldc.i4.1
0x5be18  ldloc.s  0xB
0x5be1a  ldc.i4.0
0x5be1b  ceq
0x5be1d  ldc.i4.0
0x5be1e  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, bool replaceExistingResult, bool ignoreInnerException, [opt] int32 crmErrorCode)
0x5be23  ldloc.s  0xA
0x5be25  ldloc.s  9
0x5be27  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportProfileRulesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x5be2c  throw
0x5be2d  ret
```
