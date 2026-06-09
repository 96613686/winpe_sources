# Microsoft.Crm.CrmLive.Provisioning.FixOrganizationDataExecutor::Execute

- ea: `0x14820`
- end: `0x149ed`
- name: `Microsoft.Crm.CrmLive.Provisioning.FixOrganizationDataExecutor::Execute`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14820`
- `0x149f0`

## string_xrefs

- `0x148c9`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\FixOrganizationDataExecutor.cs`
- `0x1499e`: `TOTAL ORGS UPDATE SUCCESS : `
- `0x149b6`: `TOTAL ORGS UPDATE FAILED : `

## pseudocode

```c

```

## disassembly

```asm
0x14820  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x14825  stloc.0
0x14826  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1482b  stloc.1
0x1482c  ldarg.1
0x1482d  callvirt instance class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.QueueItem [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Provisioning.QueueItemTask::get_QueueItem()
0x14832  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::get_ItemData()
0x14837  ldloca.s 0
0x14839  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x1483e  brfalse.s loc_1484C
0x14840  ldloc.1
0x14841  ldloc.0
0x14842  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x14847  br       loc_1491D
0x1484c  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x14851  stloc.s  6
0x14853  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x14858  stloc.s  7
0x1485a  ldloc.s  7
0x1485c  ldstr    aScalegroupid// "ScaleGroupId"
0x14861  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x14866  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x1486b  box      [mscorlib]System.Guid
0x14870  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14875  ldloc.s  7
0x14877  ldstr    aDatacenterid_0// "DatacenterId"
0x1487c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x14881  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x14886  box      [mscorlib]System.Guid
0x1488b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x14890  ldloc.s  7
0x14892  ldstr    aState// "State"
0x14897  ldc.i4.1
0x14898  box      [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x1489d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x148a2  ldloc.s  6
0x148a4  ldstr    aOrganization// "Organization"
0x148a9  ldc.i4.1
0x148aa  newarr   [mscorlib]System.String
0x148af  dup
0x148b0  ldc.i4.0
0x148b1  ldstr    aId// "Id"
0x148b6  stelem.ref
0x148b7  ldc.i4.1
0x148b8  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x148bd  dup
0x148be  ldc.i4.0
0x148bf  ldloc.s  7
0x148c1  stelem.ref
0x148c2  ldc.i4.s 0x25
0x148c4  ldstr    aExecute// "Execute"
0x148c9  ldstr    aDDbsShDccm2110_28// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x148ce  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x148d3  stloc.s  8
0x148d5  ldloc.s  8
0x148d7  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x148dc  brtrue.s loc_1490F
0x148de  ldloc.1
0x148df  ldloc.s  8
0x148e1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x148e6  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__0_0
0x148eb  dup
0x148ec  brtrue.s loc_14905
0x148ee  pop
0x148ef  ldsfld   class <>c <>c::<>9
0x148f4  ldftn    instance valuetype [mscorlib]System.Guid <>c::<Execute>b__0_0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propBag)
0x148fa  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x148ff  dup
0x14900  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, valuetype [mscorlib]System.Guid> <>c::<>9__0_0
0x14905  call     T0x2B00004C
0x1490a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x1490f  leave.s  loc_1491D
0x14911  ldloc.s  6
0x14913  brfalse.s loc_1491C
0x14915  ldloc.s  6
0x14917  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1491c  endfinally
0x1491d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x14922  stloc.2
0x14923  ldc.i4.0
0x14924  stloc.3
0x14925  ldc.i4.0
0x14926  stloc.s  4
0x14928  ldc.i4.0
0x14929  stloc.s  5
0x1492b  ldloc.1
0x1492c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x14931  stloc.s  9
0x14933  br.s     loc_1496D
0x14935  ldloca.s 9
0x14937  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x1493c  ldloc.2
0x1493d  call     valuetype ProcessOrgResult Microsoft.Crm.CrmLive.Provisioning.FixOrganizationDataExecutor::ProcessOrg(valuetype [mscorlib]System.Guid orgId, class [mscorlib]System.Text.StringBuilder log)
0x14942  stloc.s  0xA
0x14944  ldloc.s  0xA
0x14946  switch   loc_14959, loc_1495F, loc_14967
0x14957  br.s     loc_1496D
0x14959  ldloc.3
0x1495a  ldc.i4.1
0x1495b  add
0x1495c  stloc.3
0x1495d  br.s     loc_1496D
0x1495f  ldloc.s  4
0x14961  ldc.i4.1
0x14962  add
0x14963  stloc.s  4
0x14965  br.s     loc_1496D
0x14967  ldloc.s  5
0x14969  ldc.i4.1
0x1496a  add
0x1496b  stloc.s  5
0x1496d  ldloca.s 9
0x1496f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x14974  brtrue.s loc_14935
0x14976  leave.s  loc_14986
0x14978  ldloca.s 9
0x1497a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x14980  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14985  endfinally
0x14986  ldloc.2
0x14987  ldstr    aTotalOrgsNoAct// "TOTAL ORGS NO ACTION TAKEN : "
0x1498c  ldloc.3
0x1498d  box      [mscorlib]System.Int32
0x14992  call     string [mscorlib]System.String::Concat(object, object)
0x14997  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1499c  pop
0x1499d  ldloc.2
0x1499e  ldstr    aTotalOrgsUpdat// "TOTAL ORGS UPDATE SUCCESS : "
0x149a3  ldloc.s  4
0x149a5  box      [mscorlib]System.Int32
0x149aa  call     string [mscorlib]System.String::Concat(object, object)
0x149af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149b4  pop
0x149b5  ldloc.2
0x149b6  ldstr    aTotalOrgsUpdat_0// "TOTAL ORGS UPDATE FAILED : "
0x149bb  ldloc.s  5
0x149bd  box      [mscorlib]System.Int32
0x149c2  call     string [mscorlib]System.String::Concat(object, object)
0x149c7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x149cc  pop
0x149cd  ldloc.s  5
0x149cf  ldc.i4.0
0x149d0  ble.s    loc_149E0
0x149d2  ldc.i4.s 0xB
0x149d4  ldloc.2
0x149d5  callvirt instance string [mscorlib]System.Object::ToString()
0x149da  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x149df  ret
0x149e0  ldc.i4.4
0x149e1  ldloc.2
0x149e2  callvirt instance string [mscorlib]System.Object::ToString()
0x149e7  newobj   instance void [Microsoft.Crm.ProvisioningEngine]Microsoft.Crm.CrmLive.Scheduling.TaskResult::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.TaskStatus, string)
0x149ec  ret
```
