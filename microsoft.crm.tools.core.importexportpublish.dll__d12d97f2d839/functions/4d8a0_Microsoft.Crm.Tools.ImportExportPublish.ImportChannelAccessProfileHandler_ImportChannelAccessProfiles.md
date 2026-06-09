# Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportChannelAccessProfiles

- ea: `0x4d8a0`
- end: `0x4da6d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportChannelAccessProfiles`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x4d780`

## callees

- `0x2c410`
- `0x361d0`
- `0x4d8a0`
- `0x4da70`
- `0x4dc10`
- `0x4dcf0`
- `0x63db0`
- `0x63df0`
- `0x686f0`
- `0x68720`

## string_xrefs

- `0x4d8c4`: `ChannelAccessProfileId`
- `0x4d907`: `ChannelAccessProfileId`
- `0x4d93b`: `channelaccessprofileid`

## pseudocode

```c

```

## disassembly

```asm
0x4d8a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4d8a5  stloc.0
0x4d8a6  ldarg.1
0x4d8a7  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x4d8ac  stloc.1
0x4d8ad  br       loc_4D9F6
0x4d8b2  ldloc.1
0x4d8b3  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x4d8b8  castclass [System.Xml]System.Xml.XmlNode
0x4d8bd  stloc.2
0x4d8be  ldloc.2
0x4d8bf  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4d8c4  ldstr    aChannelaccessp_0// "ChannelAccessProfileId"
0x4d8c9  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4d8ce  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4d8d3  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4d8d8  stloc.0
0x4d8d9  ldc.i4   0xAC
0x4d8de  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ImportExportDependencyHelperFactory::RetrieveHelper(int32)
0x4d8e3  ldarg.0
0x4d8e4  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x4d8e9  ldsfld   string [mscorlib]System.String::Empty
0x4d8ee  ldloc.0
0x4d8ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4d8f4  ldarg.0
0x4d8f5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::context
0x4d8fa  callvirt instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IImportExportDependencyHelper::CheckForRootComponent(class [System.Xml]System.Xml.XmlDocument, string, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4d8ff  ldloca.s 3
0x4d901  ldloc.2
0x4d902  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4d907  ldstr    aChannelaccessp_0// "ChannelAccessProfileId"
0x4d90c  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4d911  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4d916  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4d91b  ldloc.2
0x4d91c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x4d921  ldstr    aName_1// "Name"
0x4d926  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x4d92b  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x4d930  stloc.s  4
0x4d932  ldloc.3
0x4d933  ldc.i4.1
0x4d934  newarr   [mscorlib]System.String
0x4d939  dup
0x4d93a  ldc.i4.0
0x4d93b  ldstr    aChannelaccessp_1// "channelaccessprofileid"
0x4d940  stelem.ref
0x4d941  ldarg.0
0x4d942  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::context
0x4d947  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Tools.ImportExportPublish.ChannelAccessProfileImportExportHelper::RetrieveChannelAccessProfile(valuetype [mscorlib]System.Guid channelAccessProfileId, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4d94c  stloc.s  5
0x4d94e  ldloc.s  5
0x4d950  brfalse.s loc_4D95B
0x4d952  ldloc.s  5
0x4d954  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x4d959  brtrue.s loc_4D994
0x4d95b  ldarg.0
0x4d95c  ldloc.2
0x4d95d  ldnull
0x4d95e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::CreateOrUpdateChannelAccessProfile(class [System.Xml]System.Xml.XmlNode channelAccessProfileNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingChannelAccessProfile)
0x4d963  ldarg.0
0x4d964  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::tracer
0x4d969  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d96e  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ReportImportSuccessMessage
0x4d973  ldc.i4.2
0x4d974  newarr   [mscorlib]System.Object
0x4d979  dup
0x4d97a  ldc.i4.0
0x4d97b  ldloc.s  4
0x4d97d  stelem.ref
0x4d97e  dup
0x4d97f  ldc.i4.1
0x4d980  ldloc.3
0x4d981  box      [mscorlib]System.Guid
0x4d986  stelem.ref
0x4d987  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d98c  ldc.i4.1
0x4d98d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x4d992  br.s     loc_4D9D2
0x4d994  ldarg.0
0x4d995  ldloc.2
0x4d996  ldloc.s  5
0x4d998  ldc.i4.0
0x4d999  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x4d99e  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::CreateOrUpdateChannelAccessProfile(class [System.Xml]System.Xml.XmlNode channelAccessProfileNode, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingChannelAccessProfile)
0x4d9a3  ldarg.0
0x4d9a4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::tracer
0x4d9a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4d9ae  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ReportImportSuccessMessage
0x4d9b3  ldc.i4.2
0x4d9b4  newarr   [mscorlib]System.Object
0x4d9b9  dup
0x4d9ba  ldc.i4.0
0x4d9bb  ldloc.s  4
0x4d9bd  stelem.ref
0x4d9be  dup
0x4d9bf  ldc.i4.1
0x4d9c0  ldloc.3
0x4d9c1  box      [mscorlib]System.Guid
0x4d9c6  stelem.ref
0x4d9c7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4d9cc  ldc.i4.1
0x4d9cd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x4d9d2  ldarg.0
0x4d9d3  ldloc.3
0x4d9d4  ldloc.s  4
0x4d9d6  ldloc.2
0x4d9d7  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::ImportProfileEntityAccessLevel(valuetype [mscorlib]System.Guid channelAccessProfileId, string name, class [System.Xml]System.Xml.XmlNode channelAccessProfileNode)
0x4d9dc  ldarg.0
0x4d9dd  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x4d9e2  ldarg.0
0x4d9e3  ldloc.0
0x4d9e4  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::GetParameterXPath(valuetype [mscorlib]System.Guid id)
0x4d9e9  ldstr    aSuccess// "success"
0x4d9ee  ldnull
0x4d9ef  ldc.i4.1
0x4d9f0  ldc.i4.0
0x4d9f1  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, [opt] int32 errorCode)
0x4d9f6  ldloc.1
0x4d9f7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4d9fc  brtrue   loc_4D8B2
0x4da01  leave.s  loc_4DA17
0x4da03  ldloc.1
0x4da04  isinst   [mscorlib]System.IDisposable
0x4da09  stloc.s  6
0x4da0b  ldloc.s  6
0x4da0d  brfalse.s loc_4DA16
0x4da0f  ldloc.s  6
0x4da11  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4da16  endfinally
0x4da17  leave.s  loc_4DA6C
0x4da19  stloc.s  7
0x4da1b  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::ChannelAccessProfileImportErrorMessage
0x4da20  stloc.s  8
0x4da22  ldarg.0
0x4da23  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::tracer
0x4da28  ldloc.s  8
0x4da2a  ldloc.s  7
0x4da2c  ldc.i4.3
0x4da2d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x4da32  ldloc.s  7
0x4da34  isinst   [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException
0x4da39  ldnull
0x4da3a  cgt.un
0x4da3c  ldc.i4.0
0x4da3d  ceq
0x4da3f  stloc.s  9
0x4da41  ldarg.0
0x4da42  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportXml Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::_parent
0x4da47  ldarg.0
0x4da48  ldloc.0
0x4da49  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfileHandler::GetParameterXPath(valuetype [mscorlib]System.Guid id)
0x4da4e  ldstr    aFailure// "failure"
0x4da53  ldloc.s  7
0x4da55  ldc.i4.0
0x4da56  ldc.i4.1
0x4da57  ldloc.s  9
0x4da59  ldc.i4.0
0x4da5a  ceq
0x4da5c  ldc.i4.0
0x4da5d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportXml::UpdateProgress(string path, string result, class [mscorlib]System.Exception ex, bool isProcessed, bool replaceExistingResult, bool ignoreInnerException, [opt] int32 crmErrorCode)
0x4da62  ldloc.s  8
0x4da64  ldloc.s  7
0x4da66  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ImportChannelAccessProfilesException::.ctor(string message, class [mscorlib]System.Exception innerException)
0x4da6b  throw
0x4da6c  ret
```
