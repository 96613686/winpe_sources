# Microsoft.Crm.Admin.AdminService.UserLicense::FromPropertyBag

- ea: `0x247d0`
- end: `0x2498d`
- name: `Microsoft.Crm.Admin.AdminService.UserLicense::FromPropertyBag`
- size: `445`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x24ae0`
- `0x24b60`

## callees

- `0x24700`
- `0x24720`
- `0x24740`
- `0x24760`
- `0x24770`
- `0x24780`
- `0x247a0`
- `0x247c0`
- `0x247d0`
- `0x24a10`

## string_xrefs

- `0x2493f`: `ServicePlanIds`
- `0x2494c`: `ServicePlanIds`

## pseudocode

```c

```

## disassembly

```asm
0x247d0  newobj   instance void Microsoft.Crm.Admin.AdminService.UserLicense::.ctor()
0x247d5  stloc.0
0x247d6  ldarg.0
0x247d7  ldstr    aPropbag// "propBag"
0x247dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x247e1  ldarg.0
0x247e2  ldstr    aId// "Id"
0x247e7  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x247ec  brtrue.s loc_24807
0x247ee  ldc.i4   0x8004B028
0x247f3  ldc.i4.1
0x247f4  newarr   [mscorlib]System.Object
0x247f9  dup
0x247fa  ldc.i4.0
0x247fb  ldstr    aId// "Id"
0x24800  stelem.ref
0x24801  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x24806  throw
0x24807  ldarg.0
0x24808  ldstr    aCapability// "Capability"
0x2480d  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x24812  brtrue.s loc_2482D
0x24814  ldc.i4   0x8004B028
0x24819  ldc.i4.1
0x2481a  newarr   [mscorlib]System.Object
0x2481f  dup
0x24820  ldc.i4.0
0x24821  ldstr    aCapability// "Capability"
0x24826  stelem.ref
0x24827  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2482c  throw
0x2482d  ldarg.0
0x2482e  ldstr    aFriendlyname// "FriendlyName"
0x24833  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x24838  brtrue.s loc_24853
0x2483a  ldc.i4   0x8004B028
0x2483f  ldc.i4.1
0x24840  newarr   [mscorlib]System.Object
0x24845  dup
0x24846  ldc.i4.0
0x24847  ldstr    aFriendlyname// "FriendlyName"
0x2484c  stelem.ref
0x2484d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x24852  throw
0x24853  ldarg.0
0x24854  ldstr    aOrguserlicense// "OrgUserLicenseType"
0x24859  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x2485e  brtrue.s loc_24879
0x24860  ldc.i4   0x8004B028
0x24865  ldc.i4.1
0x24866  newarr   [mscorlib]System.Object
0x2486b  dup
0x2486c  ldc.i4.0
0x2486d  ldstr    aOrguserlicense// "OrgUserLicenseType"
0x24872  stelem.ref
0x24873  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x24878  throw
0x24879  ldarg.0
0x2487a  ldstr    aOrgcaltype// "OrgCalType"
0x2487f  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x24884  brtrue.s loc_2489F
0x24886  ldc.i4   0x8004B028
0x2488b  ldc.i4.1
0x2488c  newarr   [mscorlib]System.Object
0x24891  dup
0x24892  ldc.i4.0
0x24893  ldstr    aOrgcaltype// "OrgCalType"
0x24898  stelem.ref
0x24899  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x2489e  throw
0x2489f  ldloc.0
0x248a0  ldarg.0
0x248a1  ldstr    aId// "Id"
0x248a6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x248ab  unbox.any [mscorlib]System.Guid
0x248b0  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_Id(valuetype [mscorlib]System.Guid value)
0x248b5  ldloc.0
0x248b6  ldarg.0
0x248b7  ldstr    aCapability// "Capability"
0x248bc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x248c1  castclass [mscorlib]System.String
0x248c6  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_Capability(string value)
0x248cb  ldloc.0
0x248cc  ldarg.0
0x248cd  ldstr    aFriendlyname// "FriendlyName"
0x248d2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x248d7  castclass [mscorlib]System.String
0x248dc  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_FriendlyName(string value)
0x248e1  ldloc.0
0x248e2  ldarg.0
0x248e3  ldstr    aOrguserlicense// "OrgUserLicenseType"
0x248e8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x248ed  unbox.any [mscorlib]System.Int32
0x248f2  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_OrgUserLicenseType(int32 value)
0x248f7  ldloc.0
0x248f8  ldarg.0
0x248f9  ldstr    aOrgcaltype// "OrgCalType"
0x248fe  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24903  unbox.any [mscorlib]System.Int32
0x24908  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_OrgCalType(int32 value)
0x2490d  ldarg.0
0x2490e  ldstr    aEffectiveorgca// "EffectiveOrgCalType"
0x24913  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x24918  brtrue.s loc_24928
0x2491a  ldloc.0
0x2491b  ldloc.0
0x2491c  callvirt instance int32 Microsoft.Crm.Admin.AdminService.UserLicense::get_OrgCalType()
0x24921  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_EffectiveOrgCalType(int32 value)
0x24926  br.s     loc_2493E
0x24928  ldloc.0
0x24929  ldarg.0
0x2492a  ldstr    aEffectiveorgca// "EffectiveOrgCalType"
0x2492f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24934  unbox.any [mscorlib]System.Int32
0x24939  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_EffectiveOrgCalType(int32 value)
0x2493e  ldarg.0
0x2493f  ldstr    aServiceplanids// "ServicePlanIds"
0x24944  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x24949  brfalse.s loc_2498B
0x2494b  ldarg.0
0x2494c  ldstr    aServiceplanids// "ServicePlanIds"
0x24951  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x24956  castclass [mscorlib]System.String
0x2495b  stloc.1
0x2495c  ldloc.0
0x2495d  ldloc.1
0x2495e  brtrue.s loc_24963
0x24960  ldnull
0x24961  br.s     loc_24986
0x24963  ldloc.1
0x24964  ldc.i4.1
0x24965  newarr   [mscorlib]System.Char
0x2496a  dup
0x2496b  ldc.i4.0
0x2496c  ldc.i4.s 0x2C
0x2496e  stelem.i2
0x2496f  ldc.i4.1
0x24970  call     instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x24975  ldnull
0x24976  ldftn    valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x2497c  newobj   instance void class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x24981  call     T0x2B000096
0x24986  callvirt instance void Microsoft.Crm.Admin.AdminService.UserLicense::set_ServicePlanIds(class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> value)
0x2498b  ldloc.0
0x2498c  ret
```
