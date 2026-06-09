# Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::ImportItem

- ea: `0x31c10`
- end: `0x31f4b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::ImportItem`
- size: `827`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x31c10`
- `0x31f50`
- `0x320b0`
- `0x35250`
- `0x352c0`
- `0x4cb60`
- `0x50580`
- `0x63db0`
- `0x63df0`

## string_xrefs

- `0x31cda`: `componentstate`
- `0x31dee`: `componentstate`
- `0x31c4b`: `CustomControlDefaultConfig`
- `0x31c9b`: `CustomControlDefaultConfig`
- `0x31cc6`: `CustomControlDefaultConfig`
- `0x31c79`: `CustomControlDefaultConfigId`
- `0x31e22`: `CustomControlDefaultConfigId`
- `0x31c37`: `CustomControlDefaultConfigs`

## pseudocode

```c

```

## disassembly

```asm
0x31c10  ldarg.0
0x31c11  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::importDocument
0x31c16  ldarg.0
0x31c17  call     instance string Microsoft.Crm.Tools.ImportExportPublish.ImportHandler::get_EntityName()
0x31c1c  ldarg.0
0x31c1d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::importHelper
0x31c22  ldarg.0
0x31c23  ldflda   int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31c28  call     class [System.Xml]System.Xml.XmlNode Microsoft.Crm.Tools.ImportExportPublish.ImportExportUtils::GetEntityNodeAndAdjustObjectTypeCode(class [System.Xml]System.Xml.XmlDocument importDocument, string entityName, class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper importHelper, int32& objectTypeCode)
0x31c2d  stloc.0
0x31c2e  ldloc.0
0x31c2f  brtrue.s loc_31C36
0x31c31  leave    loc_31F4A
0x31c36  ldloc.0
0x31c37  ldstr    aCustomcontrold_2// "CustomControlDefaultConfigs"
0x31c3c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x31c41  stloc.1
0x31c42  ldloc.1
0x31c43  brtrue.s loc_31C4A
0x31c45  leave    loc_31F4A
0x31c4a  ldloc.1
0x31c4b  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x31c50  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x31c55  stloc.2
0x31c56  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService::.ctor()
0x31c5b  stloc.3
0x31c5c  ldloc.2
0x31c5d  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x31c62  stloc.s  4
0x31c64  br       loc_31EBD
0x31c69  ldloc.s  4
0x31c6b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x31c70  castclass [System.Xml]System.Xml.XmlNode
0x31c75  stloc.s  5
0x31c77  ldloc.s  5
0x31c79  ldstr    aCustomcontrold_0// "CustomControlDefaultConfigId"
0x31c7e  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31c83  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x31c88  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x31c8d  pop
0x31c8e  ldloc.s  5
0x31c90  ldarg.0
0x31c91  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::context
0x31c96  call     void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.FormSolutionUtility::PostProcessCustomControls(class [System.Xml]System.Xml.XmlNode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31c9b  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x31ca0  ldarg.0
0x31ca1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::context
0x31ca6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31cab  stloc.s  6
0x31cad  ldloc.s  6
0x31caf  ldstr    aPrimaryentityt// "primaryentitytypecode"
0x31cb4  ldc.i4.0
0x31cb5  ldarg.0
0x31cb6  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31cbb  box      [mscorlib]System.Int32
0x31cc0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x31cc5  pop
0x31cc6  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x31ccb  ldarg.0
0x31ccc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::context
0x31cd1  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31cd6  stloc.s  7
0x31cd8  ldloc.s  7
0x31cda  ldstr    aComponentstate_0// "componentstate"
0x31cdf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x31ce4  ldloc.s  7
0x31ce6  ldstr    aSolutionid// "solutionid"
0x31ceb  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x31cf0  ldloc.s  6
0x31cf2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x31cf7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x31cfc  ldarg.0
0x31cfd  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::context
0x31d02  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x31d07  stloc.s  8
0x31d09  ldloc.s  8
0x31d0b  ldloc.s  6
0x31d0d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x31d12  ldloc.s  8
0x31d14  ldloc.s  7
0x31d16  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x31d1b  ldloc.3
0x31d1c  ldloc.s  8
0x31d1e  ldc.i4.4
0x31d1f  ldarg.0
0x31d20  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::context
0x31d25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x31d2a  stloc.s  9
0x31d2c  ldloc.s  9
0x31d2e  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x31d33  brtrue.s loc_31D72
0x31d35  ldarg.0
0x31d36  ldloc.3
0x31d37  ldloc.s  5
0x31d39  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::CreateCustomControlDefaultConfig(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService customControlDefaultConfigService, class [System.Xml]System.Xml.XmlNode customControlDefaultConfigNode)
0x31d3e  ldarg.0
0x31d3f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::tracer
0x31d44  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31d49  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportSuccessMessage
0x31d4e  ldc.i4.1
0x31d4f  newarr   [mscorlib]System.Object
0x31d54  dup
0x31d55  ldc.i4.0
0x31d56  ldarg.0
0x31d57  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31d5c  box      [mscorlib]System.Int32
0x31d61  stelem.ref
0x31d62  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31d67  ldc.i4.1
0x31d68  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x31d6d  br       loc_31EBD
0x31d72  ldarg.0
0x31d73  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::createEntity
0x31d78  brfalse.s loc_31DC8
0x31d7a  ldarg.0
0x31d7b  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31d80  brfalse.s loc_31DC8
0x31d82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31d87  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportErrorMessage2
0x31d8c  ldc.i4.1
0x31d8d  newarr   [mscorlib]System.Object
0x31d92  dup
0x31d93  ldc.i4.0
0x31d94  ldarg.0
0x31d95  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31d9a  box      [mscorlib]System.Int32
0x31d9f  stelem.ref
0x31da0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31da5  stloc.s  0xA
0x31da7  ldloc.s  0xA
0x31da9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x31dae  stloc.s  0xB
0x31db0  ldarg.0
0x31db1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::tracer
0x31db6  ldloc.s  0xA
0x31db8  ldloc.s  0xB
0x31dba  ldc.i4.1
0x31dbb  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x31dc0  ldloc.s  0xA
0x31dc2  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigExistingException::.ctor(string message)
0x31dc7  throw
0x31dc8  ldloc.s  9
0x31dca  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x31dcf  stloc.s  0xC
0x31dd1  br       loc_31E5A
0x31dd6  ldloc.s  0xC
0x31dd8  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x31ddd  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CustomControlDefaultConfig
0x31de2  stloc.s  0xD
0x31de4  ldarg.0
0x31de5  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::createEntity
0x31dea  brfalse.s loc_31E5A
0x31dec  ldloc.s  0xD
0x31dee  ldstr    aComponentstate_0// "componentstate"
0x31df3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x31df8  unbox.any [mscorlib]System.Int32
0x31dfd  ldc.i4.3
0x31dfe  bne.un.s loc_31E5A
0x31e00  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31e05  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportErrorMessage3
0x31e0a  ldc.i4.2
0x31e0b  newarr   [mscorlib]System.Object
0x31e10  dup
0x31e11  ldc.i4.0
0x31e12  ldarg.0
0x31e13  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31e18  box      [mscorlib]System.Int32
0x31e1d  stelem.ref
0x31e1e  dup
0x31e1f  ldc.i4.1
0x31e20  ldloc.s  5
0x31e22  ldstr    aCustomcontrold_0// "CustomControlDefaultConfigId"
0x31e27  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x31e2c  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerXml()
0x31e31  stelem.ref
0x31e32  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31e37  stloc.s  0xE
0x31e39  ldloc.s  0xE
0x31e3b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x31e40  stloc.s  0xF
0x31e42  ldarg.0
0x31e43  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::tracer
0x31e48  ldloc.s  0xE
0x31e4a  ldloc.s  0xF
0x31e4c  ldc.i4.1
0x31e4d  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x31e52  ldloc.s  0xE
0x31e54  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.CustomControlDefaultConfigDeletedException::.ctor(string message)
0x31e59  throw
0x31e5a  ldloc.s  0xC
0x31e5c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31e61  brtrue   loc_31DD6
0x31e66  leave.s  loc_31E7D
0x31e68  ldloc.s  0xC
0x31e6a  isinst   [mscorlib]System.IDisposable
0x31e6f  stloc.s  0x10
0x31e71  ldloc.s  0x10
0x31e73  brfalse.s loc_31E7C
0x31e75  ldloc.s  0x10
0x31e77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31e7c  endfinally
0x31e7d  ldarg.0
0x31e7e  ldloc.s  9
0x31e80  ldc.i4.0
0x31e81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x31e86  ldloc.3
0x31e87  ldloc.s  5
0x31e89  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::UpdateCustomControlDefaultConfig(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity existingCustomControlDefaultConfig, class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.CustomControlDefaultConfigService customControlDefaultConfigService, class [System.Xml]System.Xml.XmlNode customControlDefaultConfigNode)
0x31e8e  ldarg.0
0x31e8f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::tracer
0x31e94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31e99  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportSuccessMessage
0x31e9e  ldc.i4.1
0x31e9f  newarr   [mscorlib]System.Object
0x31ea4  dup
0x31ea5  ldc.i4.0
0x31ea6  ldarg.0
0x31ea7  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31eac  box      [mscorlib]System.Int32
0x31eb1  stelem.ref
0x31eb2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31eb7  ldc.i4.1
0x31eb8  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddSuccess(string successMessage, int32 count)
0x31ebd  ldloc.s  4
0x31ebf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x31ec4  brtrue   loc_31C69
0x31ec9  leave.s  loc_31EE0
0x31ecb  ldloc.s  4
0x31ecd  isinst   [mscorlib]System.IDisposable
0x31ed2  stloc.s  0x10
0x31ed4  ldloc.s  0x10
0x31ed6  brfalse.s loc_31EDF
0x31ed8  ldloc.s  0x10
0x31eda  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31edf  endfinally
0x31ee0  leave.s  loc_31EEC
0x31ee2  ldloc.2
0x31ee3  brfalse.s loc_31EEB
0x31ee5  ldloc.2
0x31ee6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x31eeb  endfinally
0x31eec  leave.s  loc_31F4A
0x31eee  stloc.s  0x11
0x31ef0  ldarg.0
0x31ef1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportTracer Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::tracer
0x31ef6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31efb  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportErrorMessage4
0x31f00  ldc.i4.1
0x31f01  newarr   [mscorlib]System.Object
0x31f06  dup
0x31f07  ldc.i4.0
0x31f08  ldarg.0
0x31f09  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31f0e  box      [mscorlib]System.Int32
0x31f13  stelem.ref
0x31f14  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31f19  ldloc.s  0x11
0x31f1b  ldc.i4.1
0x31f1c  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ImportTracer::AddError(string errorMessage, class [mscorlib]System.Exception errorException, int32 severity)
0x31f21  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x31f26  ldsfld   string Microsoft.Crm.Tools.ImportExportPublish.ImportExportStrings::CustomControlDefaultConfigImportErrorMessage4
0x31f2b  ldc.i4.1
0x31f2c  newarr   [mscorlib]System.Object
0x31f31  dup
0x31f32  ldc.i4.0
0x31f33  ldarg.0
0x31f34  ldfld    int32 Microsoft.Crm.Tools.ImportExportPublish.ImportCustomControlDefaultConfigsHandler::objectTypeCode
0x31f39  box      [mscorlib]System.Int32
0x31f3e  stelem.ref
0x31f3f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x31f44  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x31f49  throw
0x31f4a  ret
```
