# Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::LoadData

- ea: `0x59310`
- end: `0x595a7`
- name: `Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::LoadData`
- size: `663`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x59310`
- `0x595b0`
- `0x595c0`
- `0x59680`
- `0x59800`
- `0x59890`

## string_xrefs

- `0x594a5`: `scheduledstart`
- `0x594b6`: `scheduledend`
- `0x5941a`: `CRMServiceAppointment.RetrieveByUserByParty`

## pseudocode

```c

```

## disassembly

```asm
0x59310  ldarg.0
0x59311  ldarg.0
0x59312  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x59317  ldstr    aStartdate// "StartDate"
0x5931c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59321  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59326  call     valuetype [mscorlib]System.DateTime [mscorlib]System.Convert::ToDateTime(string, class [mscorlib]System.IFormatProvider)
0x5932b  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_startDate
0x59330  ldarg.0
0x59331  ldarg.0
0x59332  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x59337  ldstr    aEnddate// "EndDate"
0x5933c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59341  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x59346  call     valuetype [mscorlib]System.DateTime [mscorlib]System.Convert::ToDateTime(string, class [mscorlib]System.IFormatProvider)
0x5934b  stloc.0
0x5934c  ldloca.s 0
0x5934e  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Date()
0x59353  stloc.0
0x59354  ldloca.s 0
0x59356  ldc.r8   1.0
0x5935f  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddDays(float64)
0x59364  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_endDate
0x59369  ldarg.0
0x5936a  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5936f  ldstr    aViewid_1// "viewid"
0x59374  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59379  ldnull
0x5937a  cgt.un
0x5937c  ldstr    aViewIdIsNotSet// "View ID is not set in the Grid Paramete"...
0x59381  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x59386  ldarg.0
0x59387  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x5938c  ldstr    aViewtype_1// "viewtype"
0x59391  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x59396  ldnull
0x59397  cgt.un
0x59399  ldstr    aViewtypeIsNotS// "ViewType is not set in the Grid Paramet"...
0x5939e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x593a3  ldarg.0
0x593a4  ldarg.0
0x593a5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_CurrentView()
0x593aa  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_view
0x593af  ldarg.0
0x593b0  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_view
0x593b5  ldc.i4.0
0x593b6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::set_PreviewEnabled(bool)
0x593bb  ldarg.0
0x593bc  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x593c1  ldstr    aAppbookviewtyp// "AppBookViewType"
0x593c6  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x593cb  stloc.1
0x593cc  ldloc.1
0x593cd  ldstr    aApptbook// "apptbook"
0x593d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x593d7  brtrue.s loc_593FA
0x593d9  ldloc.1
0x593da  ldstr    aSchedules// "schedules"
0x593df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x593e4  brtrue   loc_59589
0x593e9  ldloc.1
0x593ea  ldstr    aAppforsched// "appforsched"
0x593ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x593f4  brtrue   loc_59590
0x593f9  ret
0x593fa  ldarg.0
0x593fb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_view
0x59400  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_QueryApi()
0x59405  callvirt instance int32 [mscorlib]System.String::get_Length()
0x5940a  ldc.i4.0
0x5940b  ble.s    loc_5943D
0x5940d  ldarg.0
0x5940e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_view
0x59413  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View::get_QueryApi()
0x59418  stloc.1
0x59419  ldloc.1
0x5941a  ldstr    aCrmserviceappo// "CRMServiceAppointment.RetrieveByUserByP"...
0x5941f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59424  brtrue.s loc_59436
0x59426  ldloc.1
0x59427  ldstr    aCrmappointment// "CRMAppointment.RetrieveByUserByParty"
0x5942c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x59431  brfalse  loc_595A6
0x59436  ldarg.0
0x59437  call     instance void Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::CreateTableViewMyActivities()
0x5943c  ret
0x5943d  ldarg.0
0x5943e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_CurrentView()
0x59443  stloc.2
0x59444  ldloc.2
0x59445  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5944a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5944f  stloc.3
0x59450  ldarg.0
0x59451  ldloc.3
0x59452  ldloc.2
0x59453  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderQueryBuilder::SetupQueryBuilder(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder, class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.View)
0x59458  brfalse  loc_595A6
0x5945d  ldloc.3
0x5945e  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x59463  ldarg.0
0x59464  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x59469  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::AddParameters(class [System]System.Collections.Specialized.NameValueCollection)
0x5946e  ldloc.3
0x5946f  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.QueryBuilder::get_Query()
0x59474  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.ApplicationQuery::get_QueryXml()
0x59479  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x5947e  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::FetchXmlToQueryExpression(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59483  stloc.s  4
0x59485  ldloc.s  4
0x59487  ldc.i4.0
0x59488  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_NoLock(bool)
0x5948d  ldloc.s  4
0x5948f  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x59494  ldstr    aStatuscode// "statuscode"
0x59499  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x5949e  ldloc.s  4
0x594a0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x594a5  ldstr    aScheduledstart// "scheduledstart"
0x594aa  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x594af  ldloc.s  4
0x594b1  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x594b6  ldstr    aScheduledend// "scheduledend"
0x594bb  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x594c0  ldloc.s  4
0x594c2  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_EntityName()
0x594c7  ldstr    aActivitypointe// "activitypointer"
0x594cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x594d1  brfalse  loc_59557
0x594d6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x594db  stloc.s  5
0x594dd  ldloc.s  5
0x594df  ldc.i4.1
0x594e0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x594e5  ldstr    aActivitytypeco// "activitytypecode"
0x594ea  ldc.i4.0
0x594eb  ldc.i4.1
0x594ec  newarr   [mscorlib]System.Object
0x594f1  dup
0x594f2  ldc.i4.0
0x594f3  ldc.i4   0x1076
0x594f8  box      [mscorlib]System.Int32
0x594fd  stelem.ref
0x594fe  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59503  stloc.s  6
0x59505  ldstr    aActivitytypeco// "activitytypecode"
0x5950a  ldc.i4.0
0x5950b  ldc.i4.1
0x5950c  newarr   [mscorlib]System.Object
0x59511  dup
0x59512  ldc.i4.0
0x59513  ldc.i4   0x1069
0x59518  box      [mscorlib]System.Int32
0x5951d  stelem.ref
0x5951e  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x59523  stloc.s  7
0x59525  ldloc.s  5
0x59527  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5952c  ldloc.s  6
0x5952e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x59533  pop
0x59534  ldloc.s  5
0x59536  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Conditions()
0x5953b  ldloc.s  7
0x5953d  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x59542  pop
0x59543  ldloc.s  4
0x59545  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x5954a  callvirt instance class [mscorlib]System.Collections.ArrayList [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::get_Filters()
0x5954f  ldloc.s  5
0x59551  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x59556  pop
0x59557  ldarg.0
0x59558  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_startDate
0x5955d  ldarg.0
0x5955e  ldfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_endDate
0x59563  ldloc.s  4
0x59565  call     void Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::SetActivitiesDateRangeFilter(valuetype [mscorlib]System.DateTime startTime, valuetype [mscorlib]System.DateTime endTime, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression query)
0x5956a  ldarg.0
0x5956b  ldloc.s  4
0x5956d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x59572  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x59577  stfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_dataList
0x5957c  ldarg.0
0x5957d  ldarg.0
0x5957e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::_dataList
0x59583  call     instance void Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::AppointmentProcessData(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection entityCollection)
0x59588  ret
0x59589  ldarg.0
0x5958a  call     instance void Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::LoadScheduleData()
0x5958f  ret
0x59590  ldarg.0
0x59591  ldarg.0
0x59592  call     instance class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::get_Parameters()
0x59597  ldstr    aEntityid// "EntityId"
0x5959c  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x595a1  call     instance void Microsoft.Crm.Application.Controls.AppointmentBookGridDataProvider::CreateTableViewResourcesForAppointment(string activityId)
0x595a6  ret
```
