# Microsoft.Crm.ObjectModel.ReportServiceInternal`1::ValidateAndGetParentReport

- ea: `0x14e410`
- end: `0x14e7a4`
- name: `Microsoft.Crm.ObjectModel.ReportServiceInternal`1::ValidateAndGetParentReport`
- size: `916`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14e410`

## string_xrefs

- `0x14e4c6`: `ReportLink`
- `0x14e4d4`: `ReportLink`
- `0x14e4a8`: `Parent report is specified for a non-Reporting Services report. Only SQL Reporting Services reports can have parent reports.`
- `0x14e706`: `Parent report is specified for a non-Reporting Services report. Only SQL Reporting Services reports can have parent reports.`
- `0x14e4f8`: `linkedreportid`
- `0x14e51c`: `linkedreportid`
- `0x14e531`: `linkedreportname`
- `0x14e794`: `Parent report is specified for a report that does not reference the current one. Only SQL Reporting Services reports can be parent reports.`

## pseudocode

```c

```

## disassembly

```asm
0x14e410  ldarg.1
0x14e411  ldstr    aParentreportid// "parentreportid"
0x14e416  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14e41b  brfalse.s loc_14E41F
0x14e41d  ldnull
0x14e41e  ret
0x14e41f  ldarg.1
0x14e420  ldstr    aParentreportid// "parentreportid"
0x14e425  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e42a  unbox.any [mscorlib]System.Guid
0x14e42f  stloc.0
0x14e430  ldarg.1
0x14e431  ldstr    aFilename_0// "filename"
0x14e436  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e43b  castclass [mscorlib]System.String
0x14e440  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x14e445  stloc.1
0x14e446  ldarg.1
0x14e447  ldstr    aName// "name"
0x14e44c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14e451  brtrue.s loc_14E465
0x14e453  ldarg.1
0x14e454  ldstr    aName// "name"
0x14e459  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e45e  castclass [mscorlib]System.String
0x14e463  br.s     loc_14E475
0x14e465  ldarg.2
0x14e466  ldstr    aName// "name"
0x14e46b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e470  castclass [mscorlib]System.String
0x14e475  stloc.2
0x14e476  ldloc.2
0x14e477  ldnull
0x14e478  cgt.un
0x14e47a  ldstr    aReportNameMust// "Report name must be specified in new en"...
0x14e47f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x14e484  ldarg.1
0x14e485  ldstr    aReporttypecode// "reporttypecode"
0x14e48a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e48f  stloc.3
0x14e490  ldloc.3
0x14e491  brtrue.s loc_14E49F
0x14e493  ldarg.2
0x14e494  ldstr    aReporttypecode// "reporttypecode"
0x14e499  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e49e  stloc.3
0x14e49f  ldloc.3
0x14e4a0  unbox.any [mscorlib]System.Int32
0x14e4a5  ldc.i4.1
0x14e4a6  beq.s    loc_14E4B8
0x14e4a8  ldstr    aParentReportIs// "Parent report is specified for a non-Re"...
0x14e4ad  ldc.i4   0x80040487
0x14e4b2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e4b7  throw
0x14e4b8  newobj   instance void class Microsoft.Crm.ObjectModel.ReportLinkServiceInternal`1<var<u1>>::.ctor()
0x14e4bd  stloc.s  4
0x14e4bf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14e4c4  stloc.s  5
0x14e4c6  ldstr    aReportlink// "ReportLink"
0x14e4cb  ldarg.s  4
0x14e4cd  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e4d2  stloc.s  6
0x14e4d4  ldstr    aReportlink// "ReportLink"
0x14e4d9  ldarg.s  4
0x14e4db  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e4e0  stloc.s  7
0x14e4e2  ldloc.s  7
0x14e4e4  ldstr    aReportid// "reportid"
0x14e4e9  ldc.i4.0
0x14e4ea  ldloc.0
0x14e4eb  box      [mscorlib]System.Guid
0x14e4f0  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14e4f5  pop
0x14e4f6  ldloc.s  7
0x14e4f8  ldstr    aLinkedreportid// "linkedreportid"
0x14e4fd  ldc.i4.s 0xD
0x14e4ff  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator)
0x14e504  pop
0x14e505  ldarg.3
0x14e506  brfalse.s loc_14E52F
0x14e508  ldarg.1
0x14e509  ldstr    aReportid// "reportid"
0x14e50e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e513  unbox.any [mscorlib]System.Guid
0x14e518  stloc.s  5
0x14e51a  ldloc.s  7
0x14e51c  ldstr    aLinkedreportid// "linkedreportid"
0x14e521  ldc.i4.1
0x14e522  ldloc.s  5
0x14e524  box      [mscorlib]System.Guid
0x14e529  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14e52e  pop
0x14e52f  ldloc.s  7
0x14e531  ldstr    aLinkedreportna// "linkedreportname"
0x14e536  ldc.i4.0
0x14e537  ldloc.1
0x14e538  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14e53d  pop
0x14e53e  ldarg.s  4
0x14e540  ldc.i4.1
0x14e541  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14e546  stloc.s  0xD
0x14e548  ldloc.s  4
0x14e54a  ldloc.s  7
0x14e54c  ldloc.s  6
0x14e54e  ldarg.s  4
0x14e550  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e555  stloc.s  8
0x14e557  leave.s  loc_14E565
0x14e559  ldloc.s  0xD
0x14e55b  brfalse.s loc_14E564
0x14e55d  ldloc.s  0xD
0x14e55f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14e564  endfinally
0x14e565  ldloc.s  8
0x14e567  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x14e56c  ldc.i4.0
0x14e56d  ble.s    loc_14E580
0x14e56f  ldc.i4   0x80040496
0x14e574  ldc.i4.0
0x14e575  newarr   [mscorlib]System.Object
0x14e57a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x14e57f  throw
0x14e580  ldarg.3
0x14e581  brfalse  loc_14E67A
0x14e586  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14e58b  ldstr    aExecPDetectrep// "exec p_DetectReportLoop '{0}','{1}'"
0x14e590  ldc.i4.2
0x14e591  newarr   [mscorlib]System.Object
0x14e596  dup
0x14e597  ldc.i4.0
0x14e598  ldloca.s 0
0x14e59a  ldstr    aB// "B"
0x14e59f  call     instance string [mscorlib]System.Guid::ToString(string)
0x14e5a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14e5a9  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x14e5ae  stelem.ref
0x14e5af  dup
0x14e5b0  ldc.i4.1
0x14e5b1  ldloca.s 5
0x14e5b3  ldstr    aB// "B"
0x14e5b8  call     instance string [mscorlib]System.Guid::ToString(string)
0x14e5bd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14e5c2  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x14e5c7  stelem.ref
0x14e5c8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x14e5cd  ldarg.s  4
0x14e5cf  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteScalar(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e5d4  castclass [mscorlib]System.String
0x14e5d9  stloc.s  0xE
0x14e5db  ldloc.s  0xE
0x14e5dd  ldstr    a0_2// "0"
0x14e5e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e5e7  brtrue   loc_14E67A
0x14e5ec  ldloc.s  0xE
0x14e5ee  ldstr    a1// "1"
0x14e5f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e5f8  brtrue.s loc_14E626
0x14e5fa  ldloc.s  0xE
0x14e5fc  ldstr    a2// "2"
0x14e601  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e606  brtrue.s loc_14E63B
0x14e608  ldloc.s  0xE
0x14e60a  ldstr    a3// "3"
0x14e60f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e614  brtrue.s loc_14E650
0x14e616  ldloc.s  0xE
0x14e618  ldstr    a4// "4"
0x14e61d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x14e622  brtrue.s loc_14E650
0x14e624  br.s     loc_14E665
0x14e626  ldc.i4   0x80040497
0x14e62b  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x14e630  ldc.i4   0x80040497
0x14e635  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e63a  throw
0x14e63b  ldc.i4   0x80040498
0x14e640  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x14e645  ldc.i4   0x80040498
0x14e64a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e64f  throw
0x14e650  ldc.i4   0x80040499
0x14e655  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x14e65a  ldc.i4   0x80040499
0x14e65f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e664  throw
0x14e665  ldc.i4   0x80042300
0x14e66a  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x14e66f  ldc.i4   0x80042300
0x14e674  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e679  throw
0x14e67a  ldloc.0
0x14e67b  ldarg.0
0x14e67c  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x14e681  ldarg.s  4
0x14e683  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x14e688  stloc.s  9
0x14e68a  ldarg.0
0x14e68b  call     instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_PlatformName()
0x14e690  ldarg.s  4
0x14e692  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14e697  stloc.s  0xA
0x14e699  ldloc.s  0xA
0x14e69b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14e6a0  ldstr    aBodytext// "bodytext"
0x14e6a5  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14e6aa  ldloc.s  0xA
0x14e6ac  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14e6b1  ldstr    aReporttypecode// "reporttypecode"
0x14e6b6  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14e6bb  ldloc.s  0xA
0x14e6bd  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x14e6c2  ldstr    aDefaultfilter// "defaultfilter"
0x14e6c7  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14e6cc  ldarg.s  4
0x14e6ce  ldc.i4.1
0x14e6cf  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14e6d4  stloc.s  0xD
0x14e6d6  ldarg.0
0x14e6d7  ldloc.s  9
0x14e6d9  ldloc.s  0xA
0x14e6db  ldarg.s  4
0x14e6dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e6e2  stloc.s  0xB
0x14e6e4  leave.s  loc_14E6F2
0x14e6e6  ldloc.s  0xD
0x14e6e8  brfalse.s loc_14E6F1
0x14e6ea  ldloc.s  0xD
0x14e6ec  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14e6f1  endfinally
0x14e6f2  ldloc.s  0xB
0x14e6f4  ldstr    aReporttypecode// "reporttypecode"
0x14e6f9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e6fe  unbox.any [mscorlib]System.Int32
0x14e703  ldc.i4.1
0x14e704  beq.s    loc_14E716
0x14e706  ldstr    aParentReportIs// "Parent report is specified for a non-Re"...
0x14e70b  ldc.i4   0x80040487
0x14e710  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e715  throw
0x14e716  ldloc.s  0xB
0x14e718  ldstr    aBodytext// "bodytext"
0x14e71d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e722  castclass [mscorlib]System.String
0x14e727  ldloc.s  0xB
0x14e729  ldstr    aDefaultfilter// "defaultfilter"
0x14e72e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e733  castclass [mscorlib]System.String
0x14e738  ldc.i4.0
0x14e739  ldarg.s  4
0x14e73b  newobj   instance void [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::.ctor(string, string, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14e740  stloc.s  0xC
0x14e742  ldloc.s  0xC
0x14e744  ldloc.1
0x14e745  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::IsChildReportReferenced(string)
0x14e74a  brtrue.s loc_14E791
0x14e74c  ldloc.s  0xC
0x14e74e  ldloca.s 5
0x14e750  ldstr    aB// "B"
0x14e755  call     instance string [mscorlib]System.Guid::ToString(string)
0x14e75a  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::IsChildReportReferenced(string)
0x14e75f  brtrue.s loc_14E791
0x14e761  ldloc.s  0xC
0x14e763  ldloc.2
0x14e764  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::IsChildReportReferenced(string)
0x14e769  brtrue.s loc_14E791
0x14e76b  ldarg.1
0x14e76c  ldstr    aReportnameonsr// "reportnameonsrs"
0x14e771  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14e776  brtrue.s loc_14E794
0x14e778  ldloc.s  0xC
0x14e77a  ldarg.1
0x14e77b  ldstr    aReportnameonsr// "reportnameonsrs"
0x14e780  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14e785  castclass [mscorlib]System.String
0x14e78a  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::IsChildReportReferenced(string)
0x14e78f  brfalse.s loc_14E794
0x14e791  ldloc.s  0xC
0x14e793  ret
0x14e794  ldstr    aParentReportIs_0// "Parent report is specified for a report"...
0x14e799  ldc.i4   0x80040486
0x14e79e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x14e7a3  throw
```
