# Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::.ctor

- ea: `0x12ea0`
- end: `0x12f8d`
- name: `Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::.ctor`
- size: `237`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x10b30`
- `0x10f30`

## callees

- `0x12d70`
- `0x12d90`
- `0x12db0`
- `0x12dd0`
- `0x12df0`
- `0x12e10`
- `0x12e30`
- `0x12e50`
- `0x12e70`
- `0x12e80`
- `0x12e90`
- `0x12ea0`

## string_xrefs

- `0x12edd`: `scheduledstart`
- `0x12eea`: `scheduledstart`
- `0x12eff`: `scheduledstart`
- `0x12ec7`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x12ea0  ldarg.0
0x12ea1  call     instance void [mscorlib]System.Object::.ctor()
0x12ea6  ldarg.0
0x12ea7  ldarg.1
0x12ea8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x12ead  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_ActivityId(valuetype [mscorlib]System.Guid value)
0x12eb2  ldarg.0
0x12eb3  ldarg.1
0x12eb4  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_LogicalName()
0x12eb9  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_LogicalName(string value)
0x12ebe  ldarg.0
0x12ebf  ldarg.2
0x12ec0  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_TypeCode(int32 value)
0x12ec5  ldarg.0
0x12ec6  ldarg.1
0x12ec7  ldstr    aScheduledend// "scheduledend"
0x12ecc  callvirt T0x2B00001A
0x12ed1  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_ScheduledEnd(valuetype [mscorlib]System.DateTime value)
0x12ed6  ldarg.0
0x12ed7  ldarg.1
0x12ed8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x12edd  ldstr    aScheduledstart// "scheduledstart"
0x12ee2  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x12ee7  brfalse.s loc_12EF6
0x12ee9  ldarg.1
0x12eea  ldstr    aScheduledstart// "scheduledstart"
0x12eef  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x12ef4  brtrue.s loc_12EFE
0x12ef6  ldarg.0
0x12ef7  call     instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::get_ScheduledEnd()
0x12efc  br.s     loc_12F0E
0x12efe  ldarg.1
0x12eff  ldstr    aScheduledstart// "scheduledstart"
0x12f04  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x12f09  unbox.any [mscorlib]System.DateTime
0x12f0e  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_ScheduledStart(valuetype [mscorlib]System.DateTime value)
0x12f13  ldarg.0
0x12f14  ldarg.1
0x12f15  ldstr    aSubject// "subject"
0x12f1a  callvirt T0x2B000011
0x12f1f  dup
0x12f20  brtrue.s loc_12F28
0x12f22  pop
0x12f23  ldsfld   string [mscorlib]System.String::Empty
0x12f28  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_Subject(string value)
0x12f2d  ldarg.0
0x12f2e  ldarg.1
0x12f2f  ldstr    aDescription// "description"
0x12f34  callvirt T0x2B000011
0x12f39  dup
0x12f3a  brtrue.s loc_12F42
0x12f3c  pop
0x12f3d  ldsfld   string [mscorlib]System.String::Empty
0x12f42  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_Description(string value)
0x12f47  ldarg.0
0x12f48  ldarg.1
0x12f49  ldstr    aRegardingobjec// "regardingobjectid"
0x12f4e  callvirt T0x2B000013
0x12f53  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_RegardingObjId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x12f58  ldarg.0
0x12f59  ldarg.1
0x12f5a  ldstr    aLocation// "location"
0x12f5f  callvirt T0x2B000011
0x12f64  dup
0x12f65  brtrue.s loc_12F6D
0x12f67  pop
0x12f68  ldsfld   string [mscorlib]System.String::Empty
0x12f6d  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_Location(string value)
0x12f72  ldarg.0
0x12f73  ldarg.1
0x12f74  ldstr    aPhonenumber// "phonenumber"
0x12f79  callvirt T0x2B000011
0x12f7e  dup
0x12f7f  brtrue.s loc_12F87
0x12f81  pop
0x12f82  ldsfld   string [mscorlib]System.String::Empty
0x12f87  call     instance void Microsoft.Crm.Asynchronous.BusinessManagement.ActionCards.Activity::set_PhoneNumber(string value)
0x12f8c  ret
```
