# Microsoft.Crm.ObjectModel.ReportServiceInternal`1::SetReportLinks

- ea: `0x14ee90`
- end: `0x14f468`
- name: `Microsoft.Crm.ObjectModel.ReportServiceInternal`1::SetReportLinks`
- size: `1496`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14ee90`

## string_xrefs

- `0x14ef0c`: `ReportLink`
- `0x14ef56`: `ReportLink`
- `0x14ef78`: `ReportLink`
- `0x14ef28`: `linkedreportid`
- `0x14efa4`: `linkedreportid`
- `0x14f045`: `linkedreportid`
- `0x14f06c`: `linkedreportid`
- `0x14f219`: `linkedreportid`
- `0x14f255`: `linkedreportid`
- `0x14ef34`: `linkedreportname`
- `0x14f00c`: `linkedreportname`
- `0x14f2d8`: `linkedreportname`
- `0x14f318`: `linkedreportname`
- `0x14f3ca`: `linkedreportname`
- `0x14ee99`: `ReportService: Called SetReportLinks on on (Id={0})`
- `0x14ef1c`: `reportlinkid`
- `0x14f032`: `reportlinkid`
- `0x14ef40`: `linktypecode`
- `0x14f01f`: `linktypecode`
- `0x14f176`: `linktypecode`
- `0x14f1b3`: `linktypecode`
- `0x14f1f8`: `linktypecode`
- `0x14f34a`: `linktypecode`
- `0x14f35e`: `linktypecode`
- `0x14f3ea`: `linktypecode`

## pseudocode

```c

```

## disassembly

```asm
0x14ee90  ldarg.s  4
0x14ee92  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x14ee97  ldc.i4.s 0x11
0x14ee99  ldstr    aReportserviceC_2// "ReportService: Called SetReportLinks on"...
0x14ee9e  ldc.i4.1
0x14ee9f  newarr   [mscorlib]System.Object
0x14eea4  dup
0x14eea5  ldc.i4.0
0x14eea6  ldarg.2
0x14eea7  box      [mscorlib]System.Guid
0x14eeac  stelem.ref
0x14eead  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x14eeb2  ldc.i4.0
0x14eeb3  stloc.0
0x14eeb4  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x14eeb9  stloc.1
0x14eeba  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x14eebf  stloc.2
0x14eec0  ldarg.3
0x14eec1  brfalse.s loc_14EF06
0x14eec3  ldarg.3
0x14eec4  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::get_DrillThroughReportNames()
0x14eec9  stloc.1
0x14eeca  ldarg.3
0x14eecb  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::get_SubReportNames()
0x14eed0  stloc.2
0x14eed1  ldarg.1
0x14eed2  ldstr    aFilename_0// "filename"
0x14eed7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14eedc  castclass [mscorlib]System.String
0x14eee1  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x14eee6  stloc.s  0x11
0x14eee8  ldloc.1
0x14eee9  ldloc.s  0x11
0x14eeeb  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14eef0  brfalse.s loc_14EF06
0x14eef2  ldloc.1
0x14eef3  ldloc.s  0x11
0x14eef5  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14eefa  ldarg.3
0x14eefb  ldloc.s  0x11
0x14eefd  ldarg.s  5
0x14eeff  callvirt instance void [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::SetChildReport(string, string)
0x14ef04  ldc.i4.1
0x14ef05  stloc.0
0x14ef06  newobj   instance void class Microsoft.Crm.ObjectModel.ReportLinkServiceInternal`1<var<u1>>::.ctor()
0x14ef0b  stloc.3
0x14ef0c  ldstr    aReportlink// "ReportLink"
0x14ef11  ldarg.s  4
0x14ef13  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14ef18  stloc.s  4
0x14ef1a  ldloc.s  4
0x14ef1c  ldstr    aReportlinkid// "reportlinkid"
0x14ef21  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14ef26  ldloc.s  4
0x14ef28  ldstr    aLinkedreportid// "linkedreportid"
0x14ef2d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14ef32  ldloc.s  4
0x14ef34  ldstr    aLinkedreportna// "linkedreportname"
0x14ef39  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14ef3e  ldloc.s  4
0x14ef40  ldstr    aLinktypecode// "linktypecode"
0x14ef45  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14ef4a  ldloc.s  4
0x14ef4c  ldstr    aReportid// "reportid"
0x14ef51  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14ef56  ldstr    aReportlink// "ReportLink"
0x14ef5b  ldarg.s  4
0x14ef5d  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::.ctor(string, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14ef62  stloc.s  5
0x14ef64  ldloc.s  5
0x14ef66  ldstr    aReportid// "reportid"
0x14ef6b  ldc.i4.0
0x14ef6c  ldarg.2
0x14ef6d  box      [mscorlib]System.Guid
0x14ef72  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x14ef77  pop
0x14ef78  ldstr    aReportlink// "ReportLink"
0x14ef7d  ldarg.s  4
0x14ef7f  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x14ef84  stloc.s  6
0x14ef86  ldloc.s  6
0x14ef88  ldloc.s  4
0x14ef8a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_ColumnSet(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression)
0x14ef8f  ldloc.s  6
0x14ef91  ldloc.s  5
0x14ef93  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::set_Criteria(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression)
0x14ef98  ldloc.s  6
0x14ef9a  ldstr    aReport// "Report"
0x14ef9f  ldstr    aReportid// "reportid"
0x14efa4  ldstr    aLinkedreportid// "linkedreportid"
0x14efa9  ldc.i4.0
0x14efaa  ldc.i4.1
0x14efab  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::AddLinkEntity(string, string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.JoinOperator)
0x14efb0  stloc.s  7
0x14efb2  ldloc.s  7
0x14efb4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_ColumnSet()
0x14efb9  ldstr    aReportnameonsr// "reportnameonsrs"
0x14efbe  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumn(string)
0x14efc3  ldarg.s  4
0x14efc5  ldc.i4.1
0x14efc6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x14efcb  stloc.s  0x12
0x14efcd  ldloc.3
0x14efce  ldloc.s  6
0x14efd0  ldarg.s  4
0x14efd2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14efd7  stloc.s  8
0x14efd9  leave.s  loc_14EFE7
0x14efdb  ldloc.s  0x12
0x14efdd  brfalse.s loc_14EFE6
0x14efdf  ldloc.s  0x12
0x14efe1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14efe6  endfinally
0x14efe7  ldsfld   string [mscorlib]System.String::Empty
0x14efec  stloc.s  0xC
0x14efee  ldloc.s  8
0x14eff0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x14eff5  stloc.s  0x13
0x14eff7  br       loc_14F2A5
0x14effc  ldloc.s  0x13
0x14effe  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x14f003  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x14f008  stloc.s  0x14
0x14f00a  ldloc.s  0x14
0x14f00c  ldstr    aLinkedreportna// "linkedreportname"
0x14f011  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f016  castclass [mscorlib]System.String
0x14f01b  stloc.s  9
0x14f01d  ldloc.s  0x14
0x14f01f  ldstr    aLinktypecode// "linktypecode"
0x14f024  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f029  unbox.any [mscorlib]System.Int32
0x14f02e  stloc.s  0xA
0x14f030  ldloc.s  0x14
0x14f032  ldstr    aReportlinkid// "reportlinkid"
0x14f037  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f03c  unbox.any [mscorlib]System.Guid
0x14f041  stloc.s  0xB
0x14f043  ldloc.s  0x14
0x14f045  ldstr    aLinkedreportid// "linkedreportid"
0x14f04a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14f04f  ldc.i4.0
0x14f050  ceq
0x14f052  brfalse  loc_14F0DE
0x14f057  ldarg.1
0x14f058  ldstr    aReporttypecode// "reporttypecode"
0x14f05d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f062  unbox.any [mscorlib]System.Int32
0x14f067  ldc.i4.1
0x14f068  bne.un.s loc_14F0DE
0x14f06a  ldloc.s  0x14
0x14f06c  ldstr    aLinkedreportid// "linkedreportid"
0x14f071  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x14f076  unbox.any [mscorlib]System.Guid
0x14f07b  stloc.s  0x16
0x14f07d  ldloca.s 0x16
0x14f07f  ldstr    aB// "B"
0x14f084  call     instance string [mscorlib]System.Guid::ToString(string)
0x14f089  stloc.s  0xC
0x14f08b  ldloc.s  0x14
0x14f08d  ldloc.s  7
0x14f08f  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x14f094  ldstr    aReportnameonsr_0// ".reportnameonsrs"
0x14f099  call     string [mscorlib]System.String::Concat(string, string)
0x14f09e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x14f0a3  brtrue.s loc_14F0CE
0x14f0a5  ldloc.s  0x14
0x14f0a7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Attributes()
0x14f0ac  ldloc.s  7
0x14f0ae  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.LinkEntityExpression::get_TableAlias()
0x14f0b3  ldstr    aReportnameonsr_0// ".reportnameonsrs"
0x14f0b8  call     string [mscorlib]System.String::Concat(string, string)
0x14f0bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection::get_Item(string)
0x14f0c2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfo::get_Value()
0x14f0c7  castclass [mscorlib]System.String
0x14f0cc  br.s     loc_14F0D0
0x14f0ce  ldloc.s  0xC
0x14f0d0  stloc.s  0x15
0x14f0d2  ldarg.3
0x14f0d3  ldloc.s  9
0x14f0d5  ldloc.s  0x15
0x14f0d7  callvirt instance void [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SRSReport::SetChildReport(string, string)
0x14f0dc  ldc.i4.1
0x14f0dd  stloc.0
0x14f0de  ldloc.s  0xA
0x14f0e0  ldc.i4.1
0x14f0e1  bne.un.s loc_14F104
0x14f0e3  ldloc.1
0x14f0e4  ldloc.s  9
0x14f0e6  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f0eb  brfalse.s loc_14F104
0x14f0ed  ldloc.2
0x14f0ee  ldloc.s  9
0x14f0f0  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f0f5  brtrue.s loc_14F104
0x14f0f7  ldloc.1
0x14f0f8  ldloc.s  9
0x14f0fa  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f0ff  br       loc_14F2A5
0x14f104  ldloc.s  0xA
0x14f106  ldc.i4.2
0x14f107  bne.un.s loc_14F12A
0x14f109  ldloc.1
0x14f10a  ldloc.s  9
0x14f10c  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f111  brtrue.s loc_14F12A
0x14f113  ldloc.2
0x14f114  ldloc.s  9
0x14f116  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f11b  brfalse.s loc_14F12A
0x14f11d  ldloc.2
0x14f11e  ldloc.s  9
0x14f120  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f125  br       loc_14F2A5
0x14f12a  ldloc.s  0xA
0x14f12c  ldc.i4.3
0x14f12d  bne.un.s loc_14F158
0x14f12f  ldloc.1
0x14f130  ldloc.s  9
0x14f132  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f137  brfalse.s loc_14F158
0x14f139  ldloc.2
0x14f13a  ldloc.s  9
0x14f13c  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f141  brfalse.s loc_14F158
0x14f143  ldloc.1
0x14f144  ldloc.s  9
0x14f146  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f14b  ldloc.2
0x14f14c  ldloc.s  9
0x14f14e  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f153  br       loc_14F2A5
0x14f158  ldloc.1
0x14f159  ldloc.s  9
0x14f15b  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f160  brfalse.s loc_14F195
0x14f162  ldloc.2
0x14f163  ldloc.s  9
0x14f165  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f16a  brtrue.s loc_14F195
0x14f16c  ldloc.1
0x14f16d  ldloc.s  9
0x14f16f  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f174  ldloc.s  0x14
0x14f176  ldstr    aLinktypecode// "linktypecode"
0x14f17b  ldc.i4.1
0x14f17c  box      [mscorlib]System.Int32
0x14f181  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x14f186  ldloc.3
0x14f187  ldloc.s  0x14
0x14f189  ldarg.s  4
0x14f18b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f190  br       loc_14F2A5
0x14f195  ldloc.1
0x14f196  ldloc.s  9
0x14f198  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f19d  brtrue.s loc_14F1D2
0x14f19f  ldloc.2
0x14f1a0  ldloc.s  9
0x14f1a2  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f1a7  brfalse.s loc_14F1D2
0x14f1a9  ldloc.2
0x14f1aa  ldloc.s  9
0x14f1ac  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f1b1  ldloc.s  0x14
0x14f1b3  ldstr    aLinktypecode// "linktypecode"
0x14f1b8  ldc.i4.2
0x14f1b9  box      [mscorlib]System.Int32
0x14f1be  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x14f1c3  ldloc.3
0x14f1c4  ldloc.s  0x14
0x14f1c6  ldarg.s  4
0x14f1c8  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f1cd  br       loc_14F2A5
0x14f1d2  ldloc.1
0x14f1d3  ldloc.s  9
0x14f1d5  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f1da  brfalse.s loc_14F217
0x14f1dc  ldloc.2
0x14f1dd  ldloc.s  9
0x14f1df  callvirt instance bool [mscorlib]System.Collections.ArrayList::Contains(object)
0x14f1e4  brfalse.s loc_14F217
0x14f1e6  ldloc.1
0x14f1e7  ldloc.s  9
0x14f1e9  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f1ee  ldloc.2
0x14f1ef  ldloc.s  9
0x14f1f1  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0x14f1f6  ldloc.s  0x14
0x14f1f8  ldstr    aLinktypecode// "linktypecode"
0x14f1fd  ldc.i4.3
0x14f1fe  box      [mscorlib]System.Int32
0x14f203  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x14f208  ldloc.3
0x14f209  ldloc.s  0x14
0x14f20b  ldarg.s  4
0x14f20d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x14f212  br       loc_14F2A5
0x14f217  ldloc.s  0x14
  ... truncated ...
```
