# Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::UpdateLinks

- ea: `0x57d40`
- end: `0x5822d`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::UpdateLinks`
- size: `1261`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x57a50`

## callees

- `0x511e0`
- `0x57d40`
- `0x58230`
- `0x58300`
- `0x583d0`

## string_xrefs

- `0x57d5c`: `ReportLink`
- `0x57e42`: `ReportLink`
- `0x58025`: `ReportLink`
- `0x57d6b`: `linkedreportname`
- `0x57e73`: `linkedreportname`
- `0x57f19`: `linkedreportname`
- `0x58092`: `linkedreportname`
- `0x58177`: `linkedreportname`
- `0x57e63`: `reportlinkid`
- `0x58016`: `reportlinkid`
- `0x57e6b`: `linkedreportid`
- `0x57fce`: `linkedreportid`
- `0x57ff4`: `linkedreportid`
- `0x580f8`: `linkedreportid`
- `0x581b5`: `linkedreportid`
- `0x57e7b`: `linktypecode`
- `0x57f54`: `linktypecode`
- `0x57f7f`: `linktypecode`
- `0x57faa`: `linktypecode`
- `0x580c7`: `linktypecode`
- `0x580db`: `linktypecode`
- `0x58198`: `linktypecode`

## pseudocode

```c

```

## disassembly

```asm
0x57d40  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportService::.ctor()
0x57d45  stloc.0
0x57d46  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.ReportLinkService::.ctor()
0x57d4b  stloc.1
0x57d4c  ldarg.0
0x57d4d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ImportHelper Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::_importHelper
0x57d52  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::get_MetadataCache()
0x57d57  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_EntitiesByName()
0x57d5c  ldstr    aReportlink// "ReportLink"
0x57d61  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x57d66  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x57d6b  ldstr    aLinkedreportna// "linkedreportname"
0x57d70  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0x57d75  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0x57d7a  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0x57d7f  stloc.2
0x57d80  ldarg.0
0x57d81  ldarg.1
0x57d82  call     instance class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::RetrieveAffectedReportsInSolutionImport(class [System.Xml]System.Xml.XmlNode reports)
0x57d87  stloc.3
0x57d88  ldloc.3
0x57d89  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x57d8e  brtrue.s loc_57D91
0x57d90  ret
0x57d91  ldstr    aReport// "Report"
0x57d96  ldarg.0
0x57d97  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57d9c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x57da1  stloc.s  4
0x57da3  ldloc.s  4
0x57da5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x57daa  ldc.i4.4
0x57dab  newarr   [mscorlib]System.String
0x57db0  dup
0x57db1  ldc.i4.0
0x57db2  ldstr    aReporttypecode// "reporttypecode"
0x57db7  stelem.ref
0x57db8  dup
0x57db9  ldc.i4.1
0x57dba  ldstr    aOriginalbodyte// "originalbodytext"
0x57dbf  stelem.ref
0x57dc0  dup
0x57dc1  ldc.i4.2
0x57dc2  ldstr    aParentreportid// "parentreportid"
0x57dc7  stelem.ref
0x57dc8  dup
0x57dc9  ldc.i4.3
0x57dca  ldstr    aFilename_0// "filename"
0x57dcf  stelem.ref
0x57dd0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x57dd5  ldloc.s  4
0x57dd7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57ddc  ldstr    aReportid// "reportid"
0x57de1  ldc.i4.8
0x57de2  ldloc.3
0x57de3  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::ToArray()
0x57de8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x57ded  pop
0x57dee  ldloc.s  4
0x57df0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57df5  ldstr    aReporttypecode// "reporttypecode"
0x57dfa  ldc.i4.0
0x57dfb  ldc.i4.1
0x57dfc  box      [mscorlib]System.Int32
0x57e01  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x57e06  pop
0x57e07  ldloc.0
0x57e08  ldloc.s  4
0x57e0a  ldarg.0
0x57e0b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57e10  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57e15  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x57e1a  stloc.s  5
0x57e1c  br       loc_58209
0x57e21  ldloc.s  5
0x57e23  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57e28  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x57e2d  stloc.s  6
0x57e2f  ldloc.s  6
0x57e31  ldstr    aReportid// "reportid"
0x57e36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57e3b  unbox.any [mscorlib]System.Guid
0x57e40  stloc.s  7
0x57e42  ldstr    aReportlink// "ReportLink"
0x57e47  ldarg.0
0x57e48  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57e4d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x57e52  stloc.s  8
0x57e54  ldloc.s  8
0x57e56  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x57e5b  ldc.i4.5
0x57e5c  newarr   [mscorlib]System.String
0x57e61  dup
0x57e62  ldc.i4.0
0x57e63  ldstr    aReportlinkid// "reportlinkid"
0x57e68  stelem.ref
0x57e69  dup
0x57e6a  ldc.i4.1
0x57e6b  ldstr    aLinkedreportid// "linkedreportid"
0x57e70  stelem.ref
0x57e71  dup
0x57e72  ldc.i4.2
0x57e73  ldstr    aLinkedreportna// "linkedreportname"
0x57e78  stelem.ref
0x57e79  dup
0x57e7a  ldc.i4.3
0x57e7b  ldstr    aLinktypecode// "linktypecode"
0x57e80  stelem.ref
0x57e81  dup
0x57e82  ldc.i4.4
0x57e83  ldstr    aReportid// "reportid"
0x57e88  stelem.ref
0x57e89  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x57e8e  ldloc.s  8
0x57e90  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x57e95  ldstr    aReportid// "reportid"
0x57e9a  ldc.i4.0
0x57e9b  ldloc.s  7
0x57e9d  box      [mscorlib]System.Guid
0x57ea2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x57ea7  pop
0x57ea8  ldarg.0
0x57ea9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57eae  ldc.i4.1
0x57eaf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x57eb4  stloc.s  0xD
0x57eb6  ldloc.1
0x57eb7  ldloc.s  8
0x57eb9  ldarg.0
0x57eba  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x57ebf  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x57ec4  stloc.s  9
0x57ec6  leave.s  loc_57ED4
0x57ec8  ldloc.s  0xD
0x57eca  brfalse.s loc_57ED3
0x57ecc  ldloc.s  0xD
0x57ece  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x57ed3  endfinally
0x57ed4  ldarg.0
0x57ed5  ldloc.s  7
0x57ed7  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::RetrieveChildReporrts(valuetype [mscorlib]System.Guid reportId)
0x57edc  stloc.s  0xA
0x57ede  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x57ee3  stloc.s  0xB
0x57ee5  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x57eea  stloc.s  0xC
0x57eec  ldarg.0
0x57eed  ldloc.s  6
0x57eef  ldloca.s 0xB
0x57ef1  ldloca.s 0xC
0x57ef3  call     instance void Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::GetSrsChildReports(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity report, class [mscorlib]System.Collections.ArrayList& subReports, class [mscorlib]System.Collections.ArrayList& drillThroughReports)
0x57ef8  ldloc.s  9
0x57efa  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x57eff  stloc.s  0xE
0x57f01  br       loc_58040
0x57f06  ldloc.s  0xE
0x57f08  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x57f0d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x57f12  stloc.s  0xF
0x57f14  ldc.i4.0
0x57f15  stloc.s  0x10
0x57f17  ldloc.s  0xF
0x57f19  ldstr    aLinkedreportna// "linkedreportname"
0x57f1e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x57f23  castclass [mscorlib]System.String
0x57f28  stloc.s  0x11
0x57f2a  ldloc.s  0xC
0x57f2c  ldloc.s  0x11
0x57f2e  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x57f33  brfalse.s loc_57F69
0x57f35  ldloc.s  0xB
0x57f37  ldloc.s  0x11
0x57f39  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x57f3e  brfalse.s loc_57F69
0x57f40  ldloc.s  0xC
0x57f42  ldloc.s  0x11
0x57f44  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x57f49  ldloc.s  0xB
0x57f4b  ldloc.s  0x11
0x57f4d  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x57f52  ldloc.s  0xF
0x57f54  ldstr    aLinktypecode// "linktypecode"
0x57f59  ldc.i4.3
0x57f5a  box      [mscorlib]System.Int32
0x57f5f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57f64  ldc.i4.1
0x57f65  stloc.s  0x10
0x57f67  br.s     loc_57FBD
0x57f69  ldloc.s  0xC
0x57f6b  ldloc.s  0x11
0x57f6d  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x57f72  brfalse.s loc_57F94
0x57f74  ldloc.s  0xC
0x57f76  ldloc.s  0x11
0x57f78  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x57f7d  ldloc.s  0xF
0x57f7f  ldstr    aLinktypecode// "linktypecode"
0x57f84  ldc.i4.1
0x57f85  box      [mscorlib]System.Int32
0x57f8a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57f8f  ldc.i4.1
0x57f90  stloc.s  0x10
0x57f92  br.s     loc_57FBD
0x57f94  ldloc.s  0xB
0x57f96  ldloc.s  0x11
0x57f98  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x57f9d  brfalse.s loc_57FBD
0x57f9f  ldloc.s  0xB
0x57fa1  ldloc.s  0x11
0x57fa3  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x57fa8  ldloc.s  0xF
0x57faa  ldstr    aLinktypecode// "linktypecode"
0x57faf  ldc.i4.2
0x57fb0  box      [mscorlib]System.Int32
0x57fb5  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57fba  ldc.i4.1
0x57fbb  stloc.s  0x10
0x57fbd  ldloc.s  0x10
0x57fbf  brfalse.s loc_58013
0x57fc1  ldloc.s  0xA
0x57fc3  ldloc.s  0x11
0x57fc5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0x57fca  brfalse.s loc_57FF2
0x57fcc  ldloc.s  0xF
0x57fce  ldstr    aLinkedreportid// "linkedreportid"
0x57fd3  ldloc.s  0xA
0x57fd5  ldloc.s  0x11
0x57fd7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::get_Item(void)
0x57fdc  box      [mscorlib]System.Guid
0x57fe1  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x57fe6  ldloc.s  0xA
0x57fe8  ldloc.s  0x11
0x57fea  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::Remove(var<u1>)
0x57fef  pop
0x57ff0  br.s     loc_58003
0x57ff2  ldloc.s  0xF
0x57ff4  ldstr    aLinkedreportid// "linkedreportid"
0x57ff9  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x57ffe  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x58003  ldloc.1
0x58004  ldloc.s  0xF
0x58006  ldarg.0
0x58007  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x5800c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x58011  br.s     loc_58040
0x58013  ldloc.1
0x58014  ldloc.s  0xF
0x58016  ldstr    aReportlinkid// "reportlinkid"
0x5801b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x58020  unbox.any [mscorlib]System.Guid
0x58025  ldstr    aReportlink// "ReportLink"
0x5802a  ldarg.0
0x5802b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x58030  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x58035  ldarg.0
0x58036  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x5803b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Delete(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x58040  ldloc.s  0xE
0x58042  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x58047  brtrue   loc_57F06
0x5804c  leave.s  loc_58063
0x5804e  ldloc.s  0xE
0x58050  isinst   [mscorlib]System.IDisposable
0x58055  stloc.s  0x12
0x58057  ldloc.s  0x12
0x58059  brfalse.s loc_58062
0x5805b  ldloc.s  0x12
0x5805d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x58062  endfinally
0x58063  ldloc.s  0xC
0x58065  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x5806a  stloc.s  0xE
0x5806c  br       loc_58129
0x58071  ldloc.s  0xE
0x58073  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x58078  stloc.s  0x13
0x5807a  ldloc.s  0x13
0x5807c  castclass [mscorlib]System.String
0x58081  stloc.s  0x14
0x58083  ldarg.0
0x58084  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ImportReportsHandler::context
0x58089  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ReportLink::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5808e  stloc.s  0x15
0x58090  ldloc.s  0x15
0x58092  ldstr    aLinkedreportna// "linkedreportname"
0x58097  ldloc.s  0x14
0x58099  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5809e  ldloc.s  0x15
0x580a0  ldstr    aReportid// "reportid"
0x580a5  ldloc.s  7
0x580a7  box      [mscorlib]System.Guid
0x580ac  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x580b1  ldloc.s  0xB
0x580b3  ldloc.s  0x13
0x580b5  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x580ba  brfalse.s loc_580D9
0x580bc  ldloc.s  0xB
0x580be  ldloc.s  0x13
0x580c0  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x580c5  ldloc.s  0x15
  ... truncated ...
```
