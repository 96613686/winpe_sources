# Microsoft.Crm.ObjectModel.ReportServiceInternal`1::SetReportParent

- ea: `0x14f470`
- end: `0x14fd7d`
- name: `Microsoft.Crm.ObjectModel.ReportServiceInternal`1::SetReportParent`
- size: `2317`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14f470`

## string_xrefs

- `0x14f4fc`: `ReportLink`
- `0x14f522`: `ReportLink`
- `0x14f875`: `ReportLink`
- `0x14f89b`: `ReportLink`
- `0x14faaf`: `ReportLink`
- `0x14fac9`: `ReportLink`
- `0x14fb2e`: `ReportLink`
- `0x14f532`: `linkedreportid`
- `0x14f8ab`: `linkedreportid`
- `0x14f938`: `linkedreportid`
- `0x14fbf2`: `linkedreportid`
- `0x14f891`: `linkedreportname`
- `0x14f9b2`: `linkedreportname`
- `0x14fad9`: `linkedreportname`
- `0x14fb3e`: `linkedreportname`
- `0x14f50c`: `reportlinkid`
- `0x14f885`: `reportlinkid`
- `0x14fabf`: `reportlinkid`
- `0x14f487`: `ReportService: Called SetReportParent on (Id={0})`
- `0x14f57a`: `Report {0}: More than one report link found in ReportLink table. Each report can have only one parent.`
- `0x14f908`: `Report {0}: More than one report link found in ReportLink table. Each report can have only one parent.`
- `0x14fbc1`: `Report {0}: More than one report link found in ReportLink table. Each report can have only one parent.`
- `0x14fa10`: `ReportService.SetReportParent: Uploading parent report (reportid={0})`
- `0x14fcf3`: `ReportService.SetReportParent: Uploading parent report (reportid={0})`
- `0x14fb96`: `Report {0}: Unable to find ReportLink between report and parent.`

## pseudocode

```c

```

## disassembly

```asm
0x14f470  ldarg.1
0x14f471  ldstr    aParentreportid// "parentreportid"
0x14f476  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f47b  brtrue.s loc_14F47E
0x14f47d  ret
0x14f47e  ldarg.s  4
0x14f480  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x14f485  ldc.i4.s 0x11
0x14f487  ldstr    aReportserviceC_3// "ReportService: Called SetReportParent o"...
0x14f48c  ldc.i4.1
0x14f48d  newarr   [mscorlib]System.Object
0x14f492  dup
0x14f493  ldc.i4.0
0x14f494  ldarg.2
0x14f495  box      [mscorlib]System.Guid
0x14f49a  stelem.ref
0x14f49b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14f4a0  ldarg.1
0x14f4a1  ldstr    aReportnameonsr// "reportnameonsrs"
0x14f4a6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14f4ab  brtrue.s loc_14F4BF
0x14f4ad  ldarg.1
0x14f4ae  ldstr    aReportnameonsr// "reportnameonsrs"
0x14f4b3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f4b8  castclass [mscorlib]System.String
0x14f4bd  br.s     loc_14F4CB
0x14f4bf  ldarga.s 2
0x14f4c1  ldstr    aB// "B"
0x14f4c6  call     instance string [mscorlib]System.Guid::ToString(string)
0x14f4cb  stloc.0
0x14f4cc  ldarg.1
0x14f4cd  ldstr    aName// "name"
0x14f4d2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f4d7  castclass [mscorlib]System.String
0x14f4dc  stloc.1
0x14f4dd  ldarg.1
0x14f4de  ldstr    aFilename_0// "filename"
0x14f4e3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f4e8  castclass [mscorlib]System.String
0x14f4ed  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x14f4f2  stloc.2
0x14f4f3  ldc.i4.1
0x14f4f4  stloc.3
0x14f4f5  newobj   instance void class Microsoft.Crm.ObjectModel.ReportLinkServiceInternal`1<var<u1>>::.ctor()
0x14f4fa  stloc.s  4
0x14f4fc  ldstr    aReportlink// "ReportLink"
0x14f501  ldarg.s  4
0x14f503  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f508  stloc.s  5
0x14f50a  ldloc.s  5
0x14f50c  ldstr    aReportlinkid// "reportlinkid"
0x14f511  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f516  ldloc.s  5
0x14f518  ldstr    aReportid// "reportid"
0x14f51d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f522  ldstr    aReportlink// "ReportLink"
0x14f527  ldarg.s  4
0x14f529  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f52e  stloc.s  6
0x14f530  ldloc.s  6
0x14f532  ldstr    aLinkedreportid// "linkedreportid"
0x14f537  ldc.i4.0
0x14f538  ldarg.2
0x14f539  box      [mscorlib]System.Guid
0x14f53e  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14f543  pop
0x14f544  ldarg.s  4
0x14f546  ldc.i4.1
0x14f547  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14f54c  stloc.s  9
0x14f54e  ldloc.s  4
0x14f550  ldloc.s  6
0x14f552  ldloc.s  5
0x14f554  ldarg.s  4
0x14f556  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f55b  stloc.s  7
0x14f55d  leave.s  loc_14F56B
0x14f55f  ldloc.s  9
0x14f561  brfalse.s loc_14F56A
0x14f563  ldloc.s  9
0x14f565  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f56a  endfinally
0x14f56b  ldloc.s  7
0x14f56d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14f572  ldc.i4.1
0x14f573  ble.s    loc_14F5A4
0x14f575  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14f57a  ldstr    aReport0MoreTha// "Report {0}: More than one report link f"...
0x14f57f  ldc.i4.1
0x14f580  newarr   [mscorlib]System.Object
0x14f585  dup
0x14f586  ldc.i4.0
0x14f587  ldarga.s 2
0x14f589  ldstr    aB// "B"
0x14f58e  call     instance string [mscorlib]System.Guid::ToString(string)
0x14f593  stelem.ref
0x14f594  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14f599  ldc.i4   0x80040485
0x14f59e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14f5a3  throw
0x14f5a4  ldloc.s  7
0x14f5a6  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14f5ab  brtrue.s loc_14F5C0
0x14f5ad  ldarg.1
0x14f5ae  ldstr    aParentreportid// "parentreportid"
0x14f5b3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f5b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14f5bd  bne.un.s loc_14F5C0
0x14f5bf  ret
0x14f5c0  ldnull
0x14f5c1  stloc.s  8
0x14f5c3  ldloc.s  7
0x14f5c5  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14f5ca  ldc.i4.1
0x14f5cb  bne.un   loc_14F788
0x14f5d0  ldloc.s  7
0x14f5d2  ldc.i4.0
0x14f5d3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x14f5d8  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ReportLink
0x14f5dd  stloc.s  8
0x14f5df  ldarg.1
0x14f5e0  ldstr    aParentreportid// "parentreportid"
0x14f5e5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f5ea  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x14f5ef  beq      loc_14F788
0x14f5f4  ldarg.1
0x14f5f5  ldstr    aParentreportid// "parentreportid"
0x14f5fa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f5ff  unbox.any [mscorlib]System.Guid
0x14f604  stloc.s  0xA
0x14f606  ldloc.s  8
0x14f608  ldstr    aReportid// "reportid"
0x14f60d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f612  unbox.any [mscorlib]System.Guid
0x14f617  stloc.s  0xB
0x14f619  ldloc.s  0xA
0x14f61b  ldloc.s  0xB
0x14f61d  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x14f622  brfalse  loc_14F788
0x14f627  ldarg.1
0x14f628  ldstr    aReportnameonsr// "reportnameonsrs"
0x14f62d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14f632  brtrue   loc_14F787
0x14f637  ldarg.3
0x14f638  ldarga.s 2
0x14f63a  ldstr    aB// "B"
0x14f63f  call     instance string [mscorlib]System.Guid::ToString(string)
0x14f644  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::IsChildReportReferenced(string)
0x14f649  brfalse  loc_14F787
0x14f64e  ldarg.3
0x14f64f  ldarga.s 2
0x14f651  ldstr    aB// "B"
0x14f656  call     instance string [mscorlib]System.Guid::ToString(string)
0x14f65b  ldloc.0
0x14f65c  callvirt instance void [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::SetChildReport(string, string)
0x14f661  ldloc.s  0xA
0x14f663  ldarg.0
0x14f664  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x14f669  ldarg.s  4
0x14f66b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14f670  stloc.s  0xC
0x14f672  ldarg.0
0x14f673  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x14f678  ldarg.s  4
0x14f67a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14f67f  stloc.s  0xD
0x14f681  ldloc.s  0xD
0x14f683  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f688  ldstr    aName// "name"
0x14f68d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f692  ldloc.s  0xD
0x14f694  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f699  ldstr    aDescription// "description"
0x14f69e  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f6a3  ldloc.s  0xD
0x14f6a5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f6aa  ldstr    aReporttypecode// "reporttypecode"
0x14f6af  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f6b4  ldloc.s  0xD
0x14f6b6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f6bb  ldstr    aSignatureid// "signatureid"
0x14f6c0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f6c5  ldloc.s  0xD
0x14f6c7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f6cc  ldstr    aReportnameonsr// "reportnameonsrs"
0x14f6d1  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f6d6  ldarg.s  4
0x14f6d8  ldc.i4.1
0x14f6d9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14f6de  stloc.s  9
0x14f6e0  ldarg.0
0x14f6e1  ldloc.s  0xC
0x14f6e3  ldloc.s  0xD
0x14f6e5  ldarg.s  4
0x14f6e7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f6ec  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Report
0x14f6f1  stloc.s  0xE
0x14f6f3  leave.s  loc_14F701
0x14f6f5  ldloc.s  9
0x14f6f7  brfalse.s loc_14F700
0x14f6f9  ldloc.s  9
0x14f6fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f700  endfinally
0x14f701  ldloc.s  0xE
0x14f703  ldstr    aBodytext// "bodytext"
0x14f708  ldarg.3
0x14f709  callvirt instance string [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::get_ReportBody()
0x14f70e  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x14f713  ldarg.0
0x14f714  ldloc.s  0xE
0x14f716  ldarg.s  4
0x14f718  call     instance void class Microsoft.Crm.ObjectModel.ReportServiceInternal`1<var<u1>>::ValidateAndSetFileSize(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f71d  ldarg.s  4
0x14f71f  ldc.i4.1
0x14f720  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14f725  stloc.s  9
0x14f727  ldarg.0
0x14f728  ldloc.s  0xE
0x14f72a  ldarg.s  4
0x14f72c  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f731  leave.s  loc_14F73F
0x14f733  ldloc.s  9
0x14f735  brfalse.s loc_14F73E
0x14f737  ldloc.s  9
0x14f739  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14f73e  endfinally
0x14f73f  ldloc.s  0xE
0x14f741  ldstr    aSignatureid// "signatureid"
0x14f746  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14f74b  stloc.s  0xF
0x14f74d  ldarg.0
0x14f74e  ldloc.s  0xA
0x14f750  ldarg.0
0x14f751  ldloc.s  0xE
0x14f753  ldloc.s  0xA
0x14f755  call     instance string class Microsoft.Crm.ObjectModel.ReportServiceInternal`1<var<u1>>::GetReportItemName(class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.Report, valuetype [mscorlib]System.Guid)
0x14f75a  ldloc.s  0xE
0x14f75c  ldstr    aName// "name"
0x14f761  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f766  castclass [mscorlib]System.String
0x14f76b  ldloc.s  0xE
0x14f76d  ldstr    aDescription// "description"
0x14f772  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f777  castclass [mscorlib]System.String
0x14f77c  ldarg.3
0x14f77d  ldarg.s  4
0x14f77f  ldloc.s  0xF
0x14f781  ldc.i4.1
0x14f782  call     instance void class Microsoft.Crm.ObjectModel.ReportServiceInternal`1<var<u1>>::UploadSRSReport(valuetype [mscorlib]System.Guid, string, string, string, class [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool, bool)
0x14f787  ret
0x14f788  ldloc.s  8
0x14f78a  brfalse  loc_14FA85
0x14f78f  ldloc.s  8
0x14f791  ldstr    aReportid// "reportid"
0x14f796  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f79b  unbox.any [mscorlib]System.Guid
0x14f7a0  stloc.s  0x10
0x14f7a2  ldloc.s  0x10
0x14f7a4  ldarg.1
0x14f7a5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x14f7aa  ldarg.s  4
0x14f7ac  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14f7b1  stloc.s  0x11
0x14f7b3  ldarg.0
0x14f7b4  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x14f7b9  ldarg.s  4
0x14f7bb  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14f7c0  stloc.s  0x12
0x14f7c2  ldloc.s  0x12
0x14f7c4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f7c9  ldstr    aName// "name"
0x14f7ce  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f7d3  ldloc.s  0x12
0x14f7d5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f7da  ldstr    aDescription// "description"
0x14f7df  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f7e4  ldloc.s  0x12
0x14f7e6  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f7eb  ldstr    aBodytext// "bodytext"
0x14f7f0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f7f5  ldloc.s  0x12
0x14f7f7  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f7fc  ldstr    aDefaultfilter// "defaultfilter"
0x14f801  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f806  ldloc.s  0x12
0x14f808  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f80d  ldstr    aReporttypecode// "reporttypecode"
0x14f812  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f817  ldloc.s  0x12
0x14f819  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f81e  ldstr    aSignatureid// "signatureid"
0x14f823  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f828  ldloc.s  0x12
0x14f82a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f82f  ldstr    aReportnameonsr// "reportnameonsrs"
0x14f834  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14f839  ldloc.s  0x12
0x14f83b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14f840  ldstr    aReportid// "reportid"
0x14f845  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
  ... truncated ...
```
