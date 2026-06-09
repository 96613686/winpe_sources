# Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::LoadData

- ea: `0x7d7e0`
- end: `0x7d977`
- name: `Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::LoadData`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config, broker_com_uri`

## callees

- `0xbd0`
- `0xc20`
- `0xc30`
- `0x2fb90`
- `0x2fbc0`
- `0x47920`
- `0x579e0`
- `0x59960`
- `0x7b830`
- `0x7ba10`
- `0x7bda0`
- `0x7bdc0`
- `0x7d550`
- `0x7d5e0`
- `0x7d620`
- `0x7d640`
- `0x7d660`
- `0x7d710`
- `0x7d780`
- `0x7d7b0`
- `0x7d7c0`
- `0x7d7d0`
- `0x7d7e0`
- `0x7d9e0`
- `0x7dc50`
- `0x85780`

## string_xrefs

- `0x7d885`: `VisualizationDataProvider.LoadData(): Executing Aggregate Query. OuterXml : {0}. InnerXml : {1}`
- `0x7d913`: `Generated Result XML for caching: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7d7e0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7d7e5  stloc.0
0x7d7e6  ldarg.0
0x7d7e7  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_WebResourceId()
0x7d7ec  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d7f1  brtrue.s loc_7D804
0x7d7f3  ldc.i4   0x8004E020
0x7d7f8  ldc.i4.0
0x7d7f9  newarr   [mscorlib]System.Object
0x7d7fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x7d803  throw
0x7d804  ldarg.0
0x7d805  callvirt instance void Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::SetupAggregationQueries()
0x7d80a  ldarg.0
0x7d80b  call     instance class Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_VisualizationDataDescription()
0x7d810  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_PrimaryEntityMetadata()
0x7d815  stloc.1
0x7d816  ldloc.1
0x7d817  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsEnabledForCharts()
0x7d81c  brtrue.s loc_7D83D
0x7d81e  ldc.i4   0x8004E00C
0x7d823  ldc.i4.1
0x7d824  newarr   [mscorlib]System.Object
0x7d829  dup
0x7d82a  ldc.i4.0
0x7d82b  ldloc.1
0x7d82c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x7d831  box      [mscorlib]System.Int32
0x7d836  stelem.ref
0x7d837  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x7d83c  throw
0x7d83d  ldarg.0
0x7d83e  call     instance void Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::AddColumnsToDataTable()
0x7d843  ldarg.0
0x7d844  call     instance class Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_VisualizationDataDescription()
0x7d849  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory> Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_CategoryCollection()
0x7d84e  ldc.i4.0
0x7d84f  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory>::get_Item(!!T0)
0x7d854  callvirt instance bool Microsoft.Crm.Application.Platform.Visualization.VisualizationCategory::get_ExtendedGroupByExists()
0x7d859  brfalse.s loc_7D862
0x7d85b  ldarg.0
0x7d85c  ldc.i4.0
0x7d85d  call     instance void Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::set_CanUseCachedData(bool value)
0x7d862  ldnull
0x7d863  stloc.2
0x7d864  ldarg.0
0x7d865  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_ResultXml()
0x7d86a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7d86f  brtrue.s loc_7D885
0x7d871  ldarg.0
0x7d872  call     instance bool Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_UseCachedData()
0x7d877  brfalse.s loc_7D885
0x7d879  ldarg.0
0x7d87a  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_ResultXml()
0x7d87f  stloc.2
0x7d880  br       loc_7D92F
0x7d885  ldstr    aVisualizationd// "VisualizationDataProvider.LoadData(): E"...
0x7d88a  ldc.i4.2
0x7d88b  newarr   [mscorlib]System.Object
0x7d890  dup
0x7d891  ldc.i4.0
0x7d892  ldarg.0
0x7d893  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_AggregationFetchXml()
0x7d898  stelem.ref
0x7d899  dup
0x7d89a  ldc.i4.1
0x7d89b  ldarg.0
0x7d89c  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_FilterFetchXml()
0x7d8a1  stelem.ref
0x7d8a2  call     void Microsoft.Crm.Util::TraceInfo(string message, object[] args)
0x7d8a7  ldarg.0
0x7d8a8  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_AggregationFetchXml()
0x7d8ad  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x7d8b2  newobj   instance void [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.QueryByEntityNameDictionary::.ctor()
0x7d8b7  stloc.s  4
0x7d8b9  ldloc.s  4
0x7d8bb  ldstr    asc_A9652// ""
0x7d8c0  ldarg.0
0x7d8c1  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_FilterFetchXml()
0x7d8c6  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression::.ctor(string)
0x7d8cb  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase>::set_Item(var<u1>, !!T0)
0x7d8d0  ldloc.s  4
0x7d8d2  ldc.i4.2
0x7d8d3  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d8d8  call     class Microsoft.Crm.Application.Platform.ApplicationEntityCollection Microsoft.Crm.Application.Platform.DataSource::RetrieveEntitiesForAggregateQuery(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FetchExpression outerQuery, class [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Messages.QueryByEntityNameDictionary subQueries, int32 applicationFeature, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x7d8dd  stloc.s  5
0x7d8df  ldarg.0
0x7d8e0  call     instance class Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_VisualizationDataDescription()
0x7d8e5  callvirt instance bool Microsoft.Crm.Application.Platform.Visualization.VisualizationDataDescription::get_HasOrderOnGroupBy()
0x7d8ea  brfalse.s loc_7D8F4
0x7d8ec  ldarg.0
0x7d8ed  ldloc.s  5
0x7d8ef  call     instance void Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::SortForPicklistGroupBy(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection result)
0x7d8f4  ldstr    aVisualizationd_0// "VisualizationDataProvider.LoadData(): A"...
0x7d8f9  call     void Microsoft.Crm.Util::TraceVerbose(string message)
0x7d8fe  ldarg.0
0x7d8ff  call     instance bool Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_CanUseCachedData()
0x7d904  brfalse.s loc_7D92C
0x7d906  ldarg.0
0x7d907  ldloc.s  5
0x7d909  call     string Microsoft.Crm.Application.Platform.ApplicationEntityCollection::Serialize(class Microsoft.Crm.Application.Platform.ApplicationEntityCollection entities)
0x7d90e  call     instance void Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::set_ResultXml(string value)
0x7d913  ldstr    aGeneratedResul// "Generated Result XML for caching: {0}"
0x7d918  ldc.i4.1
0x7d919  newarr   [mscorlib]System.Object
0x7d91e  dup
0x7d91f  ldc.i4.0
0x7d920  ldarg.0
0x7d921  call     instance string Microsoft.Crm.Application.Platform.Visualization.VisualizationDataProviderBase::get_ResultXml()
0x7d926  stelem.ref
0x7d927  call     void Microsoft.Crm.Util::TraceVerbose(string message, object[] args)
0x7d92c  ldloc.s  5
0x7d92e  stloc.2
0x7d92f  ldarg.0
0x7d930  ldloc.2
0x7d931  ldc.i4.1
0x7d932  callvirt instance void Microsoft.Crm.Application.Platform.Grid.GridDataProviderBase::ProcessData(object data, valuetype Microsoft.Crm.Application.Platform.Grid.DataProcessorType type)
0x7d937  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x7d93c  stloc.s  6
0x7d93e  ldloca.s 6
0x7d940  ldloc.0
0x7d941  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::Subtract(valuetype [mscorlib]System.DateTime)
0x7d946  stloc.3
0x7d947  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7d94c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x7d951  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x7d956  ldstr    aTimeTakenByCha// "Time taken by Chart Data Provider to lo"...
0x7d95b  ldc.i4.1
0x7d95c  newarr   [mscorlib]System.Object
0x7d961  dup
0x7d962  ldc.i4.0
0x7d963  ldloca.s 3
0x7d965  constrained. [mscorlib]System.TimeSpan
0x7d96b  callvirt instance string [mscorlib]System.Object::ToString()
0x7d970  stelem.ref
0x7d971  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7d976  ret
```
