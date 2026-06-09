# Microsoft.Crm.Web.WebRequestTelemetryEvents::ReportWebRequestStatistics

- ea: `0x4320`
- end: `0x4832`
- name: `Microsoft.Crm.Web.WebRequestTelemetryEvents::ReportWebRequestStatistics`
- size: `1298`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x4320`
- `0x4840`

## string_xrefs

- `0x4433`: `SqlConnectionOpens`

## pseudocode

```c

```

## disassembly

```asm
0x4320  call     class [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentContext()
0x4325  stloc.0
0x4326  ldloc.0
0x4327  brtrue.s loc_432A
0x4329  ret
0x432a  ldnull
0x432b  stloc.1
0x432c  ldsfld   string [mscorlib]System.String::Empty
0x4331  stloc.2
0x4332  ldc.i4.0
0x4333  stloc.3
0x4334  ldloca.s 4
0x4336  initobj  valuetype [mscorlib]System.Nullable`1<bool>
0x433c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentActivityProperties()
0x4341  brfalse.s loc_43C1
0x4343  ldnull
0x4344  stloc.s  0x21
0x4346  ldnull
0x4347  stloc.s  0x22
0x4349  ldnull
0x434a  stloc.s  0x23
0x434c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentActivityProperties()
0x4351  ldstr    aRequest// "Request"
0x4356  ldloca.s 1
0x4358  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x435d  pop
0x435e  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentActivityProperties()
0x4363  ldstr    aOperationname// "OperationName"
0x4368  ldloca.s 0x21
0x436a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x436f  brfalse.s loc_437D
0x4371  ldloc.s  0x21
0x4373  brfalse.s loc_437D
0x4375  ldloc.s  0x21
0x4377  castclass [mscorlib]System.String
0x437c  stloc.2
0x437d  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentActivityProperties()
0x4382  ldstr    aEntitytypecode// "EntityTypeCode"
0x4387  ldloca.s 0x22
0x4389  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x438e  brfalse.s loc_439C
0x4390  ldloc.s  0x22
0x4392  brfalse.s loc_439C
0x4394  ldloc.s  0x22
0x4396  unbox.any [mscorlib]System.Int32
0x439b  stloc.3
0x439c  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentActivityProperties()
0x43a1  ldstr    aEntityisnew// "EntityIsNew"
0x43a6  ldloca.s 0x23
0x43a8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x43ad  brfalse.s loc_43C1
0x43af  ldloc.s  0x23
0x43b1  brfalse.s loc_43C1
0x43b3  ldloca.s 4
0x43b5  ldloc.s  0x23
0x43b7  unbox.any [mscorlib]System.Boolean
0x43bc  call     instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x43c1  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x43c6  stloc.s  5
0x43c8  ldc.i4.0
0x43c9  stloc.s  6
0x43cb  ldc.i4.0
0x43cc  stloc.s  7
0x43ce  ldc.i4.0
0x43cf  stloc.s  8
0x43d1  ldc.i4.0
0x43d2  stloc.s  9
0x43d4  ldc.i4.0
0x43d5  stloc.s  0xA
0x43d7  ldc.i4.0
0x43d8  stloc.s  0xB
0x43da  ldc.i4.0
0x43db  stloc.s  0xC
0x43dd  ldc.i4.0
0x43de  stloc.s  0xD
0x43e0  ldc.i4.0
0x43e1  stloc.s  0xE
0x43e3  ldc.i4.0
0x43e4  stloc.s  0xF
0x43e6  ldc.i4.0
0x43e7  stloc.s  0x10
0x43e9  ldc.i4.0
0x43ea  stloc.s  0x11
0x43ec  ldc.i4.0
0x43ed  stloc.s  0x12
0x43ef  ldc.i4.0
0x43f0  stloc.s  0x13
0x43f2  ldc.i4.0
0x43f3  stloc.s  0x14
0x43f5  ldc.i4.0
0x43f6  stloc.s  0x15
0x43f8  ldloc.0
0x43f9  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x43fe  brfalse  loc_4553
0x4403  ldloc.0
0x4404  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x4409  ldstr    aSqlexecutions// "SqlExecutions"
0x440e  ldloca.s 0x24
0x4410  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x4415  pop
0x4416  ldloc.s  0x24
0x4418  brfalse.s loc_442D
0x441a  ldloc.s  0x24
0x441c  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x4421  stloc.s  6
0x4423  ldloc.s  0x24
0x4425  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x442a  conv.i4
0x442b  stloc.s  7
0x442d  ldloc.0
0x442e  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x4433  ldstr    aSqlconnectiono// "SqlConnectionOpens"
0x4438  ldloca.s 0x25
0x443a  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x443f  pop
0x4440  ldloc.s  0x25
0x4442  brfalse.s loc_4457
0x4444  ldloc.s  0x25
0x4446  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x444b  stloc.s  8
0x444d  ldloc.s  0x25
0x444f  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x4454  conv.i4
0x4455  stloc.s  9
0x4457  ldloc.0
0x4458  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x445d  ldsfld   string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.Extensibility.SdkMetricNames::SdkTotals
0x4462  ldloca.s 0x26
0x4464  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x4469  pop
0x446a  ldloc.s  0x26
0x446c  brfalse.s loc_4481
0x446e  ldloc.s  0x26
0x4470  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x4475  stloc.s  0xA
0x4477  ldloc.s  0x26
0x4479  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x447e  conv.i4
0x447f  stloc.s  0xB
0x4481  ldloc.0
0x4482  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x4487  ldsfld   string [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.ObjectModel.DatabaseServiceMetricNames::DatabaseService
0x448c  ldloca.s 0x27
0x448e  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x4493  pop
0x4494  ldloc.s  0x27
0x4496  brfalse.s loc_44AB
0x4498  ldloc.s  0x27
0x449a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x449f  stloc.s  0xC
0x44a1  ldloc.s  0x27
0x44a3  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x44a8  conv.i4
0x44a9  stloc.s  0xD
0x44ab  ldloc.0
0x44ac  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x44b1  ldsfld   string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheMetricNames::LoadCacheData
0x44b6  ldloca.s 0x28
0x44b8  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x44bd  pop
0x44be  ldloc.s  0x28
0x44c0  brfalse.s loc_44D5
0x44c2  ldloc.s  0x28
0x44c4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x44c9  stloc.s  0xE
0x44cb  ldloc.s  0x28
0x44cd  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x44d2  conv.i4
0x44d3  stloc.s  0xF
0x44d5  ldloc.0
0x44d6  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x44db  ldstr    aMediumslowquer// "MediumSlowQueryCount"
0x44e0  ldloca.s 0x29
0x44e2  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x44e7  pop
0x44e8  ldloc.s  0x29
0x44ea  brfalse.s loc_44FF
0x44ec  ldloc.s  0x29
0x44ee  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x44f3  stloc.s  0x12
0x44f5  ldloc.s  0x29
0x44f7  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x44fc  conv.i4
0x44fd  stloc.s  0x13
0x44ff  ldloc.0
0x4500  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x4505  ldstr    aLongrunningque// "LongRunningQueryCount"
0x450a  ldloca.s 0x2A
0x450c  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x4511  pop
0x4512  ldloc.s  0x2A
0x4514  brfalse.s loc_4529
0x4516  ldloc.s  0x2A
0x4518  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x451d  stloc.s  0x10
0x451f  ldloc.s  0x2A
0x4521  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x4526  conv.i4
0x4527  stloc.s  0x11
0x4529  ldloc.0
0x452a  callvirt instance class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric> [Microsoft.Crm.Core]Microsoft.Crm.MetricsReportingContext::get_CounterMetrics()
0x452f  ldstr    aSqlfailedqueri// "SqlFailedQueries"
0x4534  ldloca.s 0x2B
0x4536  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, class [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric>::TryGetValue(var<u1>, !!T0)
0x453b  pop
0x453c  ldloc.s  0x2B
0x453e  brfalse.s loc_4553
0x4540  ldloc.s  0x2B
0x4542  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_Count()
0x4547  stloc.s  0x14
0x4549  ldloc.s  0x2B
0x454b  callvirt instance float64 [Microsoft.Crm.Core]Microsoft.Crm.Core.Diagnostics.Metrics.CounterMetric::get_TotalMilliseconds()
0x4550  conv.i4
0x4551  stloc.s  0x15
0x4553  ldsfld   string [mscorlib]System.String::Empty
0x4558  stloc.s  0x16
0x455a  ldsfld   string [mscorlib]System.String::Empty
0x455f  stloc.s  0x17
0x4561  ldsfld   string [mscorlib]System.String::Empty
0x4566  stloc.s  0x18
0x4568  ldsfld   string [mscorlib]System.String::Empty
0x456d  stloc.s  0x19
0x456f  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4574  stloc.s  0x1A
0x4576  ldloc.s  0x1A
0x4578  brfalse  loc_4636
0x457d  ldloc.s  0x1A
0x457f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4584  brfalse  loc_4636
0x4589  ldloc.3
0x458a  brtrue.s loc_45BB
0x458c  ldloc.s  0x1A
0x458e  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4593  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x4598  brfalse.s loc_45BB
0x459a  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x459f  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x45a4  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x45a9  ldstr    aEtc// "etc"
0x45ae  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45b3  ldloca.s 3
0x45b5  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x45ba  pop
0x45bb  ldloc.s  0x1A
0x45bd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x45c2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x45c7  ldstr    aFormloadid// "FormLoadId"
0x45cc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45d1  brfalse.s loc_45EB
0x45d3  ldloc.s  0x1A
0x45d5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x45da  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x45df  ldstr    aFormloadid// "FormLoadId"
0x45e4  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x45e9  stloc.s  0x16
0x45eb  ldloc.s  0x1A
0x45ed  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x45f2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x45f7  ldstr    aLoginrequestco// "LoginRequestCorrelationId"
0x45fc  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4601  brfalse.s loc_461B
0x4603  ldloc.s  0x1A
0x4605  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x460a  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_Headers()
0x460f  ldstr    aLoginrequestco// "LoginRequestCorrelationId"
0x4614  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4619  stloc.s  0x18
0x461b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4620  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4625  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x462a  ldstr    aPagetype// "pagetype"
0x462f  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x4634  stloc.s  0x19
0x4636  ldloc.3
0x4637  ldc.i4.0
0x4638  ble.s    loc_4673
0x463a  ldarg.1
0x463b  brfalse.s loc_4673
0x463d  ldarg.1
0x463e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::TryGetOrganizationId()
0x4643  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4648  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x464d  brfalse.s loc_4673
0x464f  ldarg.1
0x4650  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4655  ldloc.3
0x4656  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(int32)
0x465b  stloc.s  0x2C
0x465d  ldloc.s  0x2C
0x465f  brfalse.s loc_4673
0x4661  ldloc.s  0x2C
0x4663  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCustomEntity()
0x4668  brtrue.s loc_4673
0x466a  ldloc.s  0x2C
0x466c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x4671  stloc.s  0x17
0x4673  ldloc.s  0x1A
0x4675  brtrue.s loc_467A
0x4677  ldnull
0x4678  br.s     loc_468D
  ... truncated ...
```
