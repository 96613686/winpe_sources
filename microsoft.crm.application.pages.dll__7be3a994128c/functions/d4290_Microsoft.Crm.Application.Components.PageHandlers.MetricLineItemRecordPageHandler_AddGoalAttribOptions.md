# Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::AddGoalAttribOptions

- ea: `0xd4290`
- end: `0xd44f2`
- name: `Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::AddGoalAttribOptions`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd3e40`

## callees

- `0xd2130`
- `0xd2160`
- `0xd4260`
- `0xd4290`

## string_xrefs

- `0xd42cb`: `_CreateFromId`
- `0xd42e2`: `_CreateFromId`
- `0xd431d`: `isamount`
- `0xd433a`: `isamount`
- `0xd4325`: `amountdatatype`
- `0xd4371`: `amountdatatype`

## pseudocode

```c

```

## disassembly

```asm
0xd4290  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd4295  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd429a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd429f  stloc.0
0xd42a0  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0xd42a5  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0xd42aa  stloc.1
0xd42ab  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd42b0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd42b5  ldc.i4   0x2580
0xd42ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xd42bf  stloc.2
0xd42c0  ldarg.0
0xd42c1  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xd42c6  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd42cb  ldstr    aCreatefromid// "_CreateFromId"
0xd42d0  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd42d5  brfalse.s loc_D42EF
0xd42d7  ldarg.0
0xd42d8  call     instance class [System.Web]System.Web.HttpRequest Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_Request()
0xd42dd  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xd42e2  ldstr    aCreatefromid// "_CreateFromId"
0xd42e7  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xd42ec  stloc.3
0xd42ed  br.s     loc_D430A
0xd42ef  ldarg.0
0xd42f0  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd42f5  ldstr    aMetricid// "metricid"
0xd42fa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd42ff  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd4304  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd4309  stloc.3
0xd430a  ldstr    aMetric// "metric"
0xd430f  ldloc.3
0xd4310  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd4315  ldc.i4.2
0xd4316  newarr   [mscorlib]System.String
0xd431b  dup
0xd431c  ldc.i4.0
0xd431d  ldstr    aIsamount// "isamount"
0xd4322  stelem.ref
0xd4323  dup
0xd4324  ldc.i4.1
0xd4325  ldstr    aAmountdatatype// "amountdatatype"
0xd432a  stelem.ref
0xd432b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd4330  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd4335  stloc.s  4
0xd4337  ldarg.0
0xd4338  ldloc.s  4
0xd433a  ldstr    aIsamount// "isamount"
0xd433f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd4344  unbox.any [mscorlib]System.Boolean
0xd4349  stfld    bool Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::metrictype
0xd434e  ldarg.0
0xd434f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd4354  ldstr    aMetrictype_0// "METRICTYPE"
0xd4359  ldarg.0
0xd435a  ldfld    bool Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::metrictype
0xd435f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, bool)
0xd4364  ldc.i4.0
0xd4365  stloc.s  5
0xd4367  ldarg.0
0xd4368  ldfld    bool Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::metrictype
0xd436d  brfalse.s loc_D4397
0xd436f  ldloc.s  4
0xd4371  ldstr    aAmountdatatype// "amountdatatype"
0xd4376  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd437b  unbox.any [mscorlib]System.Int32
0xd4380  stloc.s  5
0xd4382  ldarg.0
0xd4383  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd4388  ldstr    aGoaltype// "GOALTYPE"
0xd438d  ldloc.s  5
0xd438f  conv.i8
0xd4390  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd4395  br.s     loc_D43A9
0xd4397  ldarg.0
0xd4398  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0xd439d  ldstr    aGoaltype// "GOALTYPE"
0xd43a2  ldc.i4.m1
0xd43a3  conv.i8
0xd43a4  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0xd43a9  ldc.i4.3
0xd43aa  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0xd43af  stloc.s  6
0xd43b1  ldarg.0
0xd43b2  ldfld    bool Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::metrictype
0xd43b7  brtrue.s loc_D43C3
0xd43b9  ldarg.0
0xd43ba  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::IntTypePicklist
0xd43bf  stloc.s  6
0xd43c1  br.s     loc_D43D2
0xd43c3  ldarg.0
0xd43c4  ldloc.s  5
0xd43c6  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<string> Microsoft.Crm.Application.Components.PageHandlers.MetricLineItemRecordPageHandler::GetPickList(int32 dataType)
0xd43cb  castclass class [mscorlib]System.Collections.Generic.List`1<string>
0xd43d0  stloc.s  6
0xd43d2  ldloc.s  6
0xd43d4  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor(class [mscorlib]System.Collections.ICollection)
0xd43d9  stloc.s  7
0xd43db  ldstr    aRollupfield// "rollupfield"
0xd43e0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd43e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd43ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xd43ef  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xd43f4  stloc.s  8
0xd43f6  ldloc.s  8
0xd43f8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0xd43fd  ldstr    aMetricid// "metricid"
0xd4402  ldc.i4.0
0xd4403  ldc.i4.1
0xd4404  newarr   [mscorlib]System.Object
0xd4409  dup
0xd440a  ldc.i4.0
0xd440b  ldloc.3
0xd440c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd4411  box      [mscorlib]System.Guid
0xd4416  stelem.ref
0xd4417  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0xd441c  ldloc.s  8
0xd441e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0xd4423  ldstr    aGoalattribute// "goalattribute"
0xd4428  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0xd442d  ldloc.s  8
0xd442f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd4434  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd4439  stloc.s  9
0xd443b  ldloc.s  9
0xd443d  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd4442  ldc.i4.0
0xd4443  ble.s    loc_D449E
0xd4445  ldc.i4.0
0xd4446  stloc.s  0xA
0xd4448  br.s     loc_D4493
0xd444a  ldloc.s  9
0xd444c  ldloc.s  0xA
0xd444e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd4453  ldstr    aGoalattribute// "goalattribute"
0xd4458  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd445d  castclass [mscorlib]System.String
0xd4462  stloc.s  0xB
0xd4464  ldloc.s  9
0xd4466  ldloc.s  0xA
0xd4468  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd446d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd4472  ldarg.0
0xd4473  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0xd4478  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0xd447d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd4482  brtrue.s loc_D448D
0xd4484  ldloc.s  7
0xd4486  ldloc.s  0xB
0xd4488  callvirt instance void [mscorlib]System.Collections.ArrayList::Remove(object)
0xd448d  ldloc.s  0xA
0xd448f  ldc.i4.1
0xd4490  add
0xd4491  stloc.s  0xA
0xd4493  ldloc.s  0xA
0xd4495  ldloc.s  9
0xd4497  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd449c  blt.s    loc_D444A
0xd449e  ldc.i4.0
0xd449f  stloc.s  0xC
0xd44a1  br.s     loc_D44E6
0xd44a3  ldloc.2
0xd44a4  ldloc.s  7
0xd44a6  ldloc.s  0xC
0xd44a8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd44ad  callvirt instance string [mscorlib]System.Object::ToString()
0xd44b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xd44b7  stloc.s  0xD
0xd44b9  ldarg.1
0xd44ba  ldloc.s  0xD
0xd44bc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_DisplayNames()
0xd44c1  ldloc.1
0xd44c2  ldloc.0
0xd44c3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::GetLabel(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd44c8  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Label::get_Description()
0xd44cd  ldloc.s  7
0xd44cf  ldloc.s  0xC
0xd44d1  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0xd44d6  callvirt instance string [mscorlib]System.Object::ToString()
0xd44db  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PicklistControl::AddItem(string, string)
0xd44e0  ldloc.s  0xC
0xd44e2  ldc.i4.1
0xd44e3  add
0xd44e4  stloc.s  0xC
0xd44e6  ldloc.s  0xC
0xd44e8  ldloc.s  7
0xd44ea  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xd44ef  blt.s    loc_D44A3
0xd44f1  ret
```
