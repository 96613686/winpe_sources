# Microsoft.Crm.ObjectModel.GenericActivityServiceBase::SetScheduledDurationMinute

- ea: `0x5d1c0`
- end: `0x5d308`
- name: `Microsoft.Crm.ObjectModel.GenericActivityServiceBase::SetScheduledDurationMinute`
- size: `328`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x5cef0`
- `0x5cf20`

## callees

- `0x5d1c0`
- `0x5d310`

## string_xrefs

- `0x5d206`: `scheduledstart`
- `0x5d23d`: `scheduledstart`
- `0x5d25b`: `scheduledstart`
- `0x5d222`: `scheduledend`
- `0x5d24a`: `scheduledend`
- `0x5d271`: `scheduledend`
- `0x5d1c1`: `scheduleddurationminutes`
- `0x5d1ea`: `scheduleddurationminutes`
- `0x5d2e7`: `scheduleddurationminutes`
- `0x5d282`: `scheduled start must be less than or equal to scheduled end`

## pseudocode

```c

```

## disassembly

```asm
0x5d1c0  ldarg.1
0x5d1c1  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x5d1c6  ldnull
0x5d1c7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d1cc  ldarg.2
0x5d1cd  brfalse.s loc_5D1D7
0x5d1cf  ldarg.2
0x5d1d0  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d1d5  bne.un.s loc_5D1FA
0x5d1d7  ldarg.3
0x5d1d8  brfalse.s loc_5D1E2
0x5d1da  ldarg.3
0x5d1db  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d1e0  bne.un.s loc_5D1FA
0x5d1e2  ldarg.s  5
0x5d1e4  brtrue   loc_5D307
0x5d1e9  ldarg.1
0x5d1ea  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x5d1ef  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d1f4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d1f9  ret
0x5d1fa  ldarg.2
0x5d1fb  brfalse.s loc_5D205
0x5d1fd  ldarg.2
0x5d1fe  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d203  bne.un.s loc_5D216
0x5d205  ldarg.1
0x5d206  ldstr    aScheduledstart// "scheduledstart"
0x5d20b  ldarg.3
0x5d20c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d211  ldarg.3
0x5d212  starg.s  2
0x5d214  br.s     loc_5D28D
0x5d216  ldarg.3
0x5d217  brfalse.s loc_5D221
0x5d219  ldarg.3
0x5d21a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5d21f  bne.un.s loc_5D232
0x5d221  ldarg.1
0x5d222  ldstr    aScheduledend// "scheduledend"
0x5d227  ldarg.2
0x5d228  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d22d  ldarg.2
0x5d22e  starg.s  3
0x5d230  br.s     loc_5D28D
0x5d232  ldarg.0
0x5d233  ldarg.2
0x5d234  ldarg.3
0x5d235  call     instance bool Microsoft.Crm.ObjectModel.GenericActivityServiceBase::IsScheduledStartAfterScheduledEnd(object scheduledStart, object scheduledEnd)
0x5d23a  brfalse.s loc_5D28D
0x5d23c  ldarg.1
0x5d23d  ldstr    aScheduledstart// "scheduledstart"
0x5d242  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d247  stloc.s  4
0x5d249  ldarg.1
0x5d24a  ldstr    aScheduledend// "scheduledend"
0x5d24f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d254  stloc.s  5
0x5d256  ldloc.s  4
0x5d258  brtrue.s loc_5D26C
0x5d25a  ldarg.1
0x5d25b  ldstr    aScheduledstart// "scheduledstart"
0x5d260  ldloc.s  5
0x5d262  dup
0x5d263  starg.s  2
0x5d265  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d26a  br.s     loc_5D28D
0x5d26c  ldloc.s  5
0x5d26e  brtrue.s loc_5D282
0x5d270  ldarg.1
0x5d271  ldstr    aScheduledend// "scheduledend"
0x5d276  ldloc.s  4
0x5d278  dup
0x5d279  starg.s  3
0x5d27b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d280  br.s     loc_5D28D
0x5d282  ldstr    aScheduledStart// "scheduled start must be less than or eq"...
0x5d287  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5d28c  throw
0x5d28d  ldc.i4.m1
0x5d28e  stloc.0
0x5d28f  ldarg.1
0x5d290  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x5d295  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::IsAttributeNull(string)
0x5d29a  brfalse.s loc_5D2AD
0x5d29c  ldarg.s  4
0x5d29e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x5d2a3  ldarg.s  4
0x5d2a5  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetUserTimeZoneCode(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x5d2aa  stloc.0
0x5d2ab  br.s     loc_5D2BE
0x5d2ad  ldarg.1
0x5d2ae  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x5d2b3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x5d2b8  unbox.any [mscorlib]System.Int32
0x5d2bd  stloc.0
0x5d2be  ldloc.0
0x5d2bf  ldarg.s  4
0x5d2c1  call     class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.DynamicTimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ServerTimeZoneFactory::GetDynamicTimeZone(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x5d2c6  stloc.1
0x5d2c7  ldarg.2
0x5d2c8  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x5d2cd  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x5d2d2  ldarg.3
0x5d2d3  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime
0x5d2d8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::get_UniversalTime()
0x5d2dd  stloc.2
0x5d2de  ldloc.2
0x5d2df  ldloc.1
0x5d2e0  call     valuetype [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class [mscorlib]System.TimeZone)
0x5d2e5  stloc.3
0x5d2e6  ldarg.1
0x5d2e7  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x5d2ec  ldloca.s 3
0x5d2ee  call     instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Core.Extensions]Microsoft.Crm.Scheduling.TimeInterval::get_Duration()
0x5d2f3  stloc.s  6
0x5d2f5  ldloca.s 6
0x5d2f7  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x5d2fc  conv.i4
0x5d2fd  box      [mscorlib]System.Int32
0x5d302  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x5d307  ret
```
