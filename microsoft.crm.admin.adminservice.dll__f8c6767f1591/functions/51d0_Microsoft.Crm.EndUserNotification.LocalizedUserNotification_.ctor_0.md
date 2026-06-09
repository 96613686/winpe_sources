# Microsoft.Crm.EndUserNotification.LocalizedUserNotification::.ctor_0

- ea: `0x51d0`
- end: `0x530c`
- name: `Microsoft.Crm.EndUserNotification.LocalizedUserNotification::.ctor_0`
- size: `316`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x6f20`

## callees

- `0x5030`
- `0x5050`
- `0x5070`
- `0x50b0`
- `0x50f0`
- `0x5110`
- `0x5130`
- `0x5150`
- `0x5170`
- `0x5190`
- `0x51a0`
- `0x51d0`

## string_xrefs

- `0x52bd`: `CreatedOn`
- `0x52cb`: `CreatedOn`
- `0x52e1`: `TemplateName`

## pseudocode

```c

```

## disassembly

```asm
0x51d0  ldarg.0
0x51d1  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::.ctor()
0x51d6  ldarg.1
0x51d7  ldstr    aBag// "bag"
0x51dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x51e1  ldarg.0
0x51e2  ldarg.1
0x51e3  ldstr    aId// "Id"
0x51e8  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x51ed  unbox.any [mscorlib]System.Guid
0x51f2  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_Id(valuetype [mscorlib]System.Guid value)
0x51f7  ldarg.0
0x51f8  ldarg.1
0x51f9  ldstr    aStatuscode// "StatusCode"
0x51fe  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5203  unbox.any [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode
0x5208  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_StatusCode(valuetype [Microsoft.Crm.Constants]Microsoft.Crm.EndUserNotification.EndUserNotificationStatusCode value)
0x520d  ldarg.1
0x520e  ldstr    aDescription// "Description"
0x5213  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5218  brfalse.s loc_5230
0x521a  ldarg.0
0x521b  ldarg.1
0x521c  ldstr    aDescription// "Description"
0x5221  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5226  castclass [mscorlib]System.String
0x522b  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_Description(string value)
0x5230  ldarg.1
0x5231  ldstr    aScalegroupid_0// "ScaleGroupId"
0x5236  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x523b  brfalse.s loc_5253
0x523d  ldarg.0
0x523e  ldarg.1
0x523f  ldstr    aScalegroupid_0// "ScaleGroupId"
0x5244  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5249  unbox.any [mscorlib]System.Guid
0x524e  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x5253  ldarg.1
0x5254  ldstr    aOrganizationid_0// "OrganizationId"
0x5259  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x525e  brfalse.s loc_5276
0x5260  ldarg.0
0x5261  ldarg.1
0x5262  ldstr    aOrganizationid_0// "OrganizationId"
0x5267  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x526c  unbox.any [mscorlib]System.Guid
0x5271  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x5276  ldarg.1
0x5277  ldstr    aStartson// "StartsOn"
0x527c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5281  brfalse.s loc_5299
0x5283  ldarg.0
0x5284  ldarg.1
0x5285  ldstr    aStartson// "StartsOn"
0x528a  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x528f  unbox.any [mscorlib]System.DateTime
0x5294  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_StartsOn(valuetype [mscorlib]System.DateTime value)
0x5299  ldarg.1
0x529a  ldstr    aEndson// "EndsOn"
0x529f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x52a4  brfalse.s loc_52BC
0x52a6  ldarg.0
0x52a7  ldarg.1
0x52a8  ldstr    aEndson// "EndsOn"
0x52ad  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x52b2  unbox.any [mscorlib]System.DateTime
0x52b7  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_EndsOn(valuetype [mscorlib]System.DateTime value)
0x52bc  ldarg.1
0x52bd  ldstr    aCreatedon// "CreatedOn"
0x52c2  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x52c7  brfalse.s loc_52DF
0x52c9  ldarg.0
0x52ca  ldarg.1
0x52cb  ldstr    aCreatedon// "CreatedOn"
0x52d0  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x52d5  unbox.any [mscorlib]System.DateTime
0x52da  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_CreatedOn(valuetype [mscorlib]System.DateTime value)
0x52df  ldarg.0
0x52e0  ldarg.1
0x52e1  ldstr    aTemplatename// "TemplateName"
0x52e6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x52eb  castclass [mscorlib]System.String
0x52f0  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_TemplateName(string value)
0x52f5  ldarg.0
0x52f6  ldarg.1
0x52f7  ldstr    aVersion// "Version"
0x52fc  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x5301  unbox.any [mscorlib]System.Int32
0x5306  call     instance void Microsoft.Crm.EndUserNotification.LocalizedUserNotification::set_Version(int32 value)
0x530b  ret
```
