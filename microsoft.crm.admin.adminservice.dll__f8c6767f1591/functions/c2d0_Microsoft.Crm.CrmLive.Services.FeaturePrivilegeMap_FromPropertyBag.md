# Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::FromPropertyBag

- ea: `0xc2d0`
- end: `0xc398`
- name: `Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::FromPropertyBag`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0xc420`
- `0xc470`

## callees

- `0xc1f0`
- `0xc230`
- `0xc250`
- `0xc270`
- `0xc2d0`

## string_xrefs

- `0xc32b`: `PrivilegeId`
- `0xc344`: `PrivilegeId`
- `0xc383`: `PrivilegeId`

## pseudocode

```c

```

## disassembly

```asm
0xc2d0  ldarg.0
0xc2d1  ldnull
0xc2d2  cgt.un
0xc2d4  ldstr    aPropbagIsNull// "propBag is null."
0xc2d9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xc2de  ldarg.0
0xc2df  ldstr    aId// "Id"
0xc2e4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xc2e9  brtrue.s loc_C304
0xc2eb  ldc.i4   0x8004B028
0xc2f0  ldc.i4.1
0xc2f1  newarr   [mscorlib]System.Object
0xc2f6  dup
0xc2f7  ldc.i4.0
0xc2f8  ldstr    aId// "Id"
0xc2fd  stelem.ref
0xc2fe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xc303  throw
0xc304  ldarg.0
0xc305  ldstr    aFeatureid// "FeatureId"
0xc30a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xc30f  brtrue.s loc_C32A
0xc311  ldc.i4   0x8004B028
0xc316  ldc.i4.1
0xc317  newarr   [mscorlib]System.Object
0xc31c  dup
0xc31d  ldc.i4.0
0xc31e  ldstr    aFeatureid// "FeatureId"
0xc323  stelem.ref
0xc324  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xc329  throw
0xc32a  ldarg.0
0xc32b  ldstr    aPrivilegeid// "PrivilegeId"
0xc330  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0xc335  brtrue.s loc_C350
0xc337  ldc.i4   0x8004B028
0xc33c  ldc.i4.1
0xc33d  newarr   [mscorlib]System.Object
0xc342  dup
0xc343  ldc.i4.0
0xc344  ldstr    aPrivilegeid// "PrivilegeId"
0xc349  stelem.ref
0xc34a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0xc34f  throw
0xc350  newobj   instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::.ctor()
0xc355  dup
0xc356  ldarg.0
0xc357  ldstr    aId// "Id"
0xc35c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xc361  unbox.any [mscorlib]System.Guid
0xc366  callvirt instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::set_Id(valuetype [mscorlib]System.Guid value)
0xc36b  dup
0xc36c  ldarg.0
0xc36d  ldstr    aFeatureid// "FeatureId"
0xc372  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xc377  unbox.any [mscorlib]System.Guid
0xc37c  callvirt instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::set_FeatureId(valuetype [mscorlib]System.Guid value)
0xc381  dup
0xc382  ldarg.0
0xc383  ldstr    aPrivilegeid// "PrivilegeId"
0xc388  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0xc38d  unbox.any [mscorlib]System.Guid
0xc392  callvirt instance void Microsoft.Crm.CrmLive.Services.FeaturePrivilegeMap::set_PrivilegeId(valuetype [mscorlib]System.Guid value)
0xc397  ret
```
