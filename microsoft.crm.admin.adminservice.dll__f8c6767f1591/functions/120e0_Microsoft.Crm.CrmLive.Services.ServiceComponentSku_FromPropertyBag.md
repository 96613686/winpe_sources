# Microsoft.Crm.CrmLive.Services.ServiceComponentSku::FromPropertyBag

- ea: `0x120e0`
- end: `0x12229`
- name: `Microsoft.Crm.CrmLive.Services.ServiceComponentSku::FromPropertyBag`
- size: `329`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x12310`
- `0x12460`
- `0x124a0`
- `0x126c0`

## callees

- `0x12020`
- `0x12050`
- `0x12070`
- `0x12090`
- `0x120b0`
- `0x120d0`
- `0x120e0`

## string_xrefs

- `0x120ef`: `ServiceComponentId`
- `0x12108`: `ServiceComponentId`
- `0x12187`: `ServiceComponentId`

## pseudocode

```c

```

## disassembly

```asm
0x120e0  ldarg.0
0x120e1  ldnull
0x120e2  cgt.un
0x120e4  ldstr    aPropbagIsNull// "propBag is null."
0x120e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x120ee  ldarg.0
0x120ef  ldstr    aServicecompone// "ServiceComponentId"
0x120f4  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x120f9  brtrue.s loc_12114
0x120fb  ldc.i4   0x8004B028
0x12100  ldc.i4.1
0x12101  newarr   [mscorlib]System.Object
0x12106  dup
0x12107  ldc.i4.0
0x12108  ldstr    aServicecompone// "ServiceComponentId"
0x1210d  stelem.ref
0x1210e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0x12113  throw
0x12114  ldarg.0
0x12115  ldstr    aName// "Name"
0x1211a  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x1211f  brtrue.s loc_1213A
0x12121  ldc.i4   0x8004B028
0x12126  ldc.i4.1
0x12127  newarr   [mscorlib]System.Object
0x1212c  dup
0x1212d  ldc.i4.0
0x1212e  ldstr    aName// "Name"
0x12133  stelem.ref
0x12134  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0x12139  throw
0x1213a  ldarg.0
0x1213b  ldstr    aRestricted// "Restricted"
0x12140  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x12145  brtrue.s loc_12160
0x12147  ldc.i4   0x8004B028
0x1214c  ldc.i4.1
0x1214d  newarr   [mscorlib]System.Object
0x12152  dup
0x12153  ldc.i4.0
0x12154  ldstr    aRestricted// "Restricted"
0x12159  stelem.ref
0x1215a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0x1215f  throw
0x12160  ldarg.0
0x12161  ldstr    aBillingmethod// "BillingMethod"
0x12166  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x1216b  brtrue.s loc_12186
0x1216d  ldc.i4   0x8004B028
0x12172  ldc.i4.1
0x12173  newarr   [mscorlib]System.Object
0x12178  dup
0x12179  ldc.i4.0
0x1217a  ldstr    aBillingmethod// "BillingMethod"
0x1217f  stelem.ref
0x12180  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmLiveException::.ctor(int32, object[])
0x12185  throw
0x12186  ldarg.0
0x12187  ldstr    aServicecompone// "ServiceComponentId"
0x1218c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x12191  castclass [mscorlib]System.String
0x12196  stloc.0
0x12197  ldarg.0
0x12198  ldstr    aName// "Name"
0x1219d  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121a2  castclass [mscorlib]System.String
0x121a7  stloc.1
0x121a8  ldarg.0
0x121a9  ldstr    aRestricted// "Restricted"
0x121ae  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121b3  unbox.any [mscorlib]System.Boolean
0x121b8  stloc.2
0x121b9  ldc.i4.4
0x121ba  stloc.3
0x121bb  ldarg.0
0x121bc  ldstr    aBillingmethod// "BillingMethod"
0x121c1  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121c6  brfalse.s loc_121D9
0x121c8  ldarg.0
0x121c9  ldstr    aBillingmethod// "BillingMethod"
0x121ce  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121d3  unbox.any Microsoft.Crm.CrmLive.Services.BillingMethod
0x121d8  stloc.3
0x121d9  ldsfld   string [mscorlib]System.String::Empty
0x121de  stloc.s  4
0x121e0  ldarg.0
0x121e1  ldstr    aCapability// "Capability"
0x121e6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121eb  brfalse.s loc_121FF
0x121ed  ldarg.0
0x121ee  ldstr    aCapability// "Capability"
0x121f3  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x121f8  castclass [mscorlib]System.String
0x121fd  stloc.s  4
0x121ff  newobj   instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::.ctor()
0x12204  dup
0x12205  ldloc.0
0x12206  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::set_ServiceComponentId(string value)
0x1220b  dup
0x1220c  ldloc.1
0x1220d  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::set_Description(string value)
0x12212  dup
0x12213  ldloc.2
0x12214  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::set_Restricted(bool value)
0x12219  dup
0x1221a  ldloc.3
0x1221b  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::set_BillingMethod(valuetype Microsoft.Crm.CrmLive.Services.BillingMethod value)
0x12220  dup
0x12221  ldloc.s  4
0x12223  callvirt instance void Microsoft.Crm.CrmLive.Services.ServiceComponentSku::set_OsdpCapability(string value)
0x12228  ret
```
