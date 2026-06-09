# Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::RetrieveMultiple

- ea: `0x1c090`
- end: `0x1c411`
- name: `Microsoft.Crm.Admin.AdminService.CrmMonitoringResultsService::RetrieveMultiple`
- size: `897`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x1c420`

## callees

- `0x1c090`
- `0x1c5b0`
- `0x1c7d0`
- `0x1c7f0`
- `0x1c810`
- `0x1c830`
- `0x1c850`
- `0x1c870`
- `0x1c890`

## string_xrefs

- `0x1c365`: `D:\a\1\s\src\CrmLive\Admin\MonitoringResults\CrmMonitoringResultsService.cs`
- `0x1c384`: `D:\a\1\s\src\CrmLive\Admin\MonitoringResults\CrmMonitoringResultsService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1c090  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.MonitoringResultData>::.ctor()
0x1c095  stloc.0
0x1c096  ldnull
0x1c097  stloc.1
0x1c098  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1c09d  stloc.2
0x1c09e  ldnull
0x1c09f  stloc.3
0x1c0a0  ldarg.1
0x1c0a1  brfalse  loc_1C33E
0x1c0a6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1c0ab  stloc.1
0x1c0ac  ldarg.1
0x1c0ad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Id()
0x1c0b2  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c0b7  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c0bc  brfalse.s loc_1C0D4
0x1c0be  ldloc.1
0x1c0bf  ldstr    aId// "Id"
0x1c0c4  ldarg.1
0x1c0c5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Id()
0x1c0ca  box      [mscorlib]System.Guid
0x1c0cf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c0d4  ldarg.1
0x1c0d5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Monitoring]Microsoft.Crm.Monitoring.TestStatus> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Status()
0x1c0da  stloc.s  4
0x1c0dc  ldloca.s 4
0x1c0de  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Monitoring]Microsoft.Crm.Monitoring.TestStatus>::get_HasValue()
0x1c0e3  brfalse.s loc_1C0FB
0x1c0e5  ldloc.1
0x1c0e6  ldstr    aStatus_0// "Status"
0x1c0eb  ldarg.1
0x1c0ec  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Monitoring]Microsoft.Crm.Monitoring.TestStatus> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Status()
0x1c0f1  box      valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Monitoring]Microsoft.Crm.Monitoring.TestStatus>
0x1c0f6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c0fb  ldarg.1
0x1c0fc  callvirt instance string[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Servers()
0x1c101  brfalse  loc_1C1A0
0x1c106  ldarg.1
0x1c107  callvirt instance string[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Servers()
0x1c10c  ldlen
0x1c10d  brfalse  loc_1C1A0
0x1c112  ldarg.1
0x1c113  callvirt instance string[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Servers()
0x1c118  ldlen
0x1c119  conv.i4
0x1c11a  ldc.i4.1
0x1c11b  bne.un.s loc_1C132
0x1c11d  ldloc.1
0x1c11e  ldstr    aServer_1// "Server"
0x1c123  ldarg.1
0x1c124  callvirt instance string[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Servers()
0x1c129  ldc.i4.0
0x1c12a  ldelem.ref
0x1c12b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c130  br.s     loc_1C1A0
0x1c132  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::.ctor()
0x1c137  stloc.s  5
0x1c139  ldarg.1
0x1c13a  callvirt instance string[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Servers()
0x1c13f  stloc.s  6
0x1c141  ldc.i4.0
0x1c142  stloc.s  7
0x1c144  br.s     loc_1C18B
0x1c146  ldloc.s  6
0x1c148  ldloc.s  7
0x1c14a  ldelem.ref
0x1c14b  stloc.s  8
0x1c14d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::.ctor()
0x1c152  stloc.s  9
0x1c154  ldloc.s  9
0x1c156  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c15b  ldc.i4.0
0x1c15c  ldloc.s  8
0x1c15e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c163  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c168  ldloc.s  9
0x1c16a  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c16f  ldc.i4.0
0x1c170  ldloc.s  8
0x1c172  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c177  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c17c  ldloc.s  5
0x1c17e  ldloc.s  9
0x1c180  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::Add(var<u1>)
0x1c185  ldloc.s  7
0x1c187  ldc.i4.1
0x1c188  add
0x1c189  stloc.s  7
0x1c18b  ldloc.s  7
0x1c18d  ldloc.s  6
0x1c18f  ldlen
0x1c190  conv.i4
0x1c191  blt.s    loc_1C146
0x1c193  ldloc.1
0x1c194  ldstr    aServer_1// "Server"
0x1c199  ldloc.s  5
0x1c19b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c1a0  ldarg.1
0x1c1a1  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Roles()
0x1c1a6  brfalse  loc_1C254
0x1c1ab  ldarg.1
0x1c1ac  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Roles()
0x1c1b1  ldlen
0x1c1b2  brfalse  loc_1C254
0x1c1b7  ldarg.1
0x1c1b8  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Roles()
0x1c1bd  ldlen
0x1c1be  conv.i4
0x1c1bf  ldc.i4.1
0x1c1c0  bne.un.s loc_1C1DC
0x1c1c2  ldloc.1
0x1c1c3  ldstr    aRole// "Role"
0x1c1c8  ldarg.1
0x1c1c9  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Roles()
0x1c1ce  ldc.i4.0
0x1c1cf  ldelem.i4
0x1c1d0  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x1c1d5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c1da  br.s     loc_1C254
0x1c1dc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::.ctor()
0x1c1e1  stloc.s  0xA
0x1c1e3  ldarg.1
0x1c1e4  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles[] Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_Roles()
0x1c1e9  stloc.s  0xB
0x1c1eb  ldc.i4.0
0x1c1ec  stloc.s  7
0x1c1ee  br.s     loc_1C23F
0x1c1f0  ldloc.s  0xB
0x1c1f2  ldloc.s  7
0x1c1f4  ldelem.i4
0x1c1f5  stloc.s  0xC
0x1c1f7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::.ctor()
0x1c1fc  stloc.s  0xD
0x1c1fe  ldloc.s  0xD
0x1c200  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c205  ldc.i4.0
0x1c206  ldloc.s  0xC
0x1c208  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x1c20d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c212  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c217  ldloc.s  0xD
0x1c219  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c21e  ldc.i4.0
0x1c21f  ldloc.s  0xC
0x1c221  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x1c226  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c22b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c230  ldloc.s  0xA
0x1c232  ldloc.s  0xD
0x1c234  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection>::Add(var<u1>)
0x1c239  ldloc.s  7
0x1c23b  ldc.i4.1
0x1c23c  add
0x1c23d  stloc.s  7
0x1c23f  ldloc.s  7
0x1c241  ldloc.s  0xB
0x1c243  ldlen
0x1c244  conv.i4
0x1c245  blt.s    loc_1C1F0
0x1c247  ldloc.1
0x1c248  ldstr    aRole// "Role"
0x1c24d  ldloc.s  0xA
0x1c24f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c254  ldarg.1
0x1c255  callvirt instance string Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_TestName()
0x1c25a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c25f  brtrue.s loc_1C272
0x1c261  ldloc.1
0x1c262  ldstr    aTestname// "TestName"
0x1c267  ldarg.1
0x1c268  callvirt instance string Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_TestName()
0x1c26d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c272  ldarg.1
0x1c273  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrBefore()
0x1c278  stloc.s  0xE
0x1c27a  ldloca.s 0xE
0x1c27c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1c281  brfalse.s loc_1C2E4
0x1c283  ldarg.1
0x1c284  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrAfter()
0x1c289  stloc.s  0xE
0x1c28b  ldloca.s 0xE
0x1c28d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1c292  brfalse.s loc_1C2E4
0x1c294  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::.ctor()
0x1c299  stloc.s  0xF
0x1c29b  ldloc.s  0xF
0x1c29d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c2a2  ldc.i4.4
0x1c2a3  ldarg.1
0x1c2a4  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrBefore()
0x1c2a9  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1c2ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c2b3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c2b8  ldloc.s  0xF
0x1c2ba  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison> [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparisonCollection::get_PropertyComparisonList()
0x1c2bf  ldc.i4.2
0x1c2c0  ldarg.1
0x1c2c1  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrAfter()
0x1c2c6  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1c2cb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c2d0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison>::Add(var<u1>)
0x1c2d5  ldloc.1
0x1c2d6  ldstr    aEndtime// "EndTime"
0x1c2db  ldloc.s  0xF
0x1c2dd  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c2e2  br.s     loc_1C33E
0x1c2e4  ldarg.1
0x1c2e5  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrBefore()
0x1c2ea  stloc.s  0xE
0x1c2ec  ldloca.s 0xE
0x1c2ee  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1c2f3  brfalse.s loc_1C311
0x1c2f5  ldloc.1
0x1c2f6  ldstr    aEndtime// "EndTime"
0x1c2fb  ldc.i4.4
0x1c2fc  ldarg.1
0x1c2fd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrBefore()
0x1c302  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1c307  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c30c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c311  ldarg.1
0x1c312  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrAfter()
0x1c317  stloc.s  0xE
0x1c319  ldloca.s 0xE
0x1c31b  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x1c320  brfalse.s loc_1C33E
0x1c322  ldloc.1
0x1c323  ldstr    aEndtime// "EndTime"
0x1c328  ldc.i4.2
0x1c329  ldarg.1
0x1c32a  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Admin.AdminService.MonitoringResultsFilter::get_EndedOnOrAfter()
0x1c32f  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1c334  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0x1c339  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1c33e  ldloc.1
0x1c33f  brfalse.s loc_1C372
0x1c341  ldloc.1
0x1c342  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Count()
0x1c347  ldc.i4.0
0x1c348  ble.s    loc_1C372
0x1c34a  ldloc.2
0x1c34b  ldstr    aMonitoringresu// "MonitoringResults"
0x1c350  ldnull
0x1c351  ldc.i4.1
0x1c352  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1c357  dup
0x1c358  ldc.i4.0
0x1c359  ldloc.1
0x1c35a  stelem.ref
0x1c35b  ldc.i4   0xE2
0x1c360  ldstr    aRetrievemultip// "RetrieveMultiple"
0x1c365  ldstr    aDA1SSrcCrmlive_38// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Monit"...
0x1c36a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1c36f  stloc.3
0x1c370  br.s     loc_1C38F
0x1c372  ldloc.2
0x1c373  ldstr    aMonitoringresu// "MonitoringResults"
0x1c378  ldnull
0x1c379  ldnull
0x1c37a  ldc.i4   0xE6
0x1c37f  ldstr    aRetrievemultip// "RetrieveMultiple"
0x1c384  ldstr    aDA1SSrcCrmlive_38// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Monit"...
0x1c389  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1c38e  stloc.3
0x1c38f  ldloc.3
0x1c390  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x1c395  brtrue.s loc_1C3D5
0x1c397  ldloc.3
0x1c398  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1c39d  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1c3a2  stloc.s  0x10
0x1c3a4  br.s     loc_1C3BC
0x1c3a6  ldloca.s 0x10
0x1c3a8  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1c3ad  newobj   instance void Microsoft.Crm.Admin.AdminService.MonitoringResultData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x1c3b2  stloc.s  0x11
0x1c3b4  ldloc.0
0x1c3b5  ldloc.s  0x11
0x1c3b7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.MonitoringResultData>::Add(var<u1>)
0x1c3bc  ldloca.s 0x10
0x1c3be  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x1c3c3  brtrue.s loc_1C3A6
0x1c3c5  leave.s  loc_1C3D5
0x1c3c7  ldloca.s 0x10
0x1c3c9  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x1c3cf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3d4  endfinally
0x1c3d5  ldloc.0
0x1c3d6  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Admin.AdminService.MonitoringResultData>::ToArray()
0x1c3db  stloc.s  0x12
0x1c3dd  leave.s  loc_1C40E
0x1c3df  ldloc.2
0x1c3e0  brfalse.s loc_1C3E8
0x1c3e2  ldloc.2
0x1c3e3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c3e8  endfinally
0x1c3e9  stloc.s  0x13
0x1c3eb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
  ... truncated ...
```
