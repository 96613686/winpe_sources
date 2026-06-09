# Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RemoveDeployment

- ea: `0x1f900`
- end: `0x1fa68`
- name: `Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::RemoveDeployment`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ee60`

## callees

- `0x1f900`

## string_xrefs

- `0x1f97e`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1fa01`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1fa21`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`
- `0x1f979`: `RemoveDeployment`
- `0x1f9fc`: `RemoveDeployment`
- `0x1fa1c`: `RemoveDeployment`

## pseudocode

```c

```

## disassembly

```asm
0x1f900  ldarg.0
0x1f901  ldstr    aScalegroupIden// "ScaleGroup identifier"
0x1f906  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1f90b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1f910  ldc.i4.s 0x14
0x1f912  ldstr    aRemovingDeploy// "Removing Deployment for  ScaleGroup wit"...
0x1f917  ldc.i4.1
0x1f918  newarr   [mscorlib]System.Object
0x1f91d  dup
0x1f91e  ldc.i4.0
0x1f91f  ldarg.0
0x1f920  box      [mscorlib]System.Guid
0x1f925  stelem.ref
0x1f926  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f92b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1f930  stloc.0
0x1f931  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1f936  stloc.1
0x1f937  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1f93c  stloc.1
0x1f93d  ldloc.1
0x1f93e  ldstr    aScalegroupid_0// "ScaleGroupId"
0x1f943  ldarg.0
0x1f944  box      [mscorlib]System.Guid
0x1f949  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1f94e  ldloc.0
0x1f94f  ldstr    aScalegroupdepl// "ScaleGroupDeployment"
0x1f954  ldc.i4.2
0x1f955  newarr   [mscorlib]System.String
0x1f95a  dup
0x1f95b  ldc.i4.0
0x1f95c  ldstr    aId// "Id"
0x1f961  stelem.ref
0x1f962  dup
0x1f963  ldc.i4.1
0x1f964  ldstr    aDeploymentid// "DeploymentId"
0x1f969  stelem.ref
0x1f96a  ldc.i4.1
0x1f96b  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1f970  dup
0x1f971  ldc.i4.0
0x1f972  ldloc.1
0x1f973  stelem.ref
0x1f974  ldc.i4   0x2F2
0x1f979  ldstr    aRemovedeployme// "RemoveDeployment"
0x1f97e  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1f983  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1f988  stloc.2
0x1f989  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f98e  stloc.3
0x1f98f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1f994  stloc.s  4
0x1f996  ldloc.2
0x1f997  brfalse.s loc_1F9EA
0x1f999  ldloc.2
0x1f99a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x1f99f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x1f9a4  stloc.s  5
0x1f9a6  br.s     loc_1F9D1
0x1f9a8  ldloca.s 5
0x1f9aa  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1f9af  dup
0x1f9b0  ldstr    aId// "Id"
0x1f9b5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1f9ba  unbox.any [mscorlib]System.Guid
0x1f9bf  stloc.s  4
0x1f9c1  ldstr    aDeploymentid// "DeploymentId"
0x1f9c6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1f9cb  unbox.any [mscorlib]System.Guid
0x1f9d0  stloc.3
0x1f9d1  ldloca.s 5
0x1f9d3  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x1f9d8  brtrue.s loc_1F9A8
0x1f9da  leave.s  loc_1F9EA
0x1f9dc  ldloca.s 5
0x1f9de  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x1f9e4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f9e9  endfinally
0x1f9ea  ldloc.0
0x1f9eb  ldstr    aScalegroupdepl// "ScaleGroupDeployment"
0x1f9f0  ldloc.s  4
0x1f9f2  box      [mscorlib]System.Guid
0x1f9f7  ldc.i4   0x304
0x1f9fc  ldstr    aRemovedeployme// "RemoveDeployment"
0x1fa01  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1fa06  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1fa0b  ldloc.0
0x1fa0c  ldstr    aDeployment// "Deployment"
0x1fa11  ldloc.3
0x1fa12  box      [mscorlib]System.Guid
0x1fa17  ldc.i4   0x306
0x1fa1c  ldstr    aRemovedeployme// "RemoveDeployment"
0x1fa21  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1fa26  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1fa2b  leave.s  loc_1FA37
0x1fa2d  ldloc.0
0x1fa2e  brfalse.s loc_1FA36
0x1fa30  ldloc.0
0x1fa31  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1fa36  endfinally
0x1fa37  leave.s  loc_1FA67
0x1fa39  stloc.s  6
0x1fa3b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1fa40  ldc.i4.s 0x14
0x1fa42  ldstr    aExceptionInRem// "Exception in removing Deployment with S"...
0x1fa47  ldc.i4.2
0x1fa48  newarr   [mscorlib]System.Object
0x1fa4d  dup
0x1fa4e  ldc.i4.0
0x1fa4f  ldarg.0
0x1fa50  box      [mscorlib]System.Guid
0x1fa55  stelem.ref
0x1fa56  dup
0x1fa57  ldc.i4.1
0x1fa58  ldloc.s  6
0x1fa5a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1fa5f  stelem.ref
0x1fa60  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1fa65  rethrow
0x1fa67  ret
```
