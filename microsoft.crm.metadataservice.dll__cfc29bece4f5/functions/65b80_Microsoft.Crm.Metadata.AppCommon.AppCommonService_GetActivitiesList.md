# Microsoft.Crm.Metadata.AppCommon.AppCommonService::GetActivitiesList

- ea: `0x65b80`
- end: `0x65c12`
- name: `Microsoft.Crm.Metadata.AppCommon.AppCommonService::GetActivitiesList`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x64fb0`
- `0x65400`
- `0x78530`

## callees

- `0x65b80`
- `0x65c20`

## string_xrefs

- `0x65bf8`: `ServiceAppointment`
- `0x65c06`: `ServiceAppointment`

## pseudocode

```c

```

## disassembly

```asm
0x65b80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x65b85  dup
0x65b86  ldstr    aAppointment_0// "Appointment"
0x65b8b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65b90  dup
0x65b91  ldstr    aEmail_0// "Email"
0x65b96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65b9b  dup
0x65b9c  ldstr    aFax_0// "Fax"
0x65ba1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65ba6  dup
0x65ba7  ldstr    aLetter_0// "Letter"
0x65bac  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65bb1  dup
0x65bb2  ldstr    aPhonecall_0// "PhoneCall"
0x65bb7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65bbc  dup
0x65bbd  ldstr    aTask_0// "Task"
0x65bc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65bc7  dup
0x65bc8  ldstr    aRecurringappoi_0// "RecurringAppointmentMaster"
0x65bcd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65bd2  stloc.0
0x65bd3  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x65bd8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x65bdd  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_LeoServiceFeatures()
0x65be2  ldarg.0
0x65be3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x65be8  brfalse.s loc_65BF5
0x65bea  ldloc.0
0x65beb  ldstr    aSocialactivity// "SocialActivity"
0x65bf0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65bf5  ldarg.1
0x65bf6  brfalse.s loc_65C10
0x65bf8  ldstr    aServiceappoint_0// "ServiceAppointment"
0x65bfd  ldarg.0
0x65bfe  call     bool Microsoft.Crm.Metadata.AppCommon.AppCommonService::IfEntityExists(string entityName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x65c03  brfalse.s loc_65C10
0x65c05  ldloc.0
0x65c06  ldstr    aServiceappoint_0// "ServiceAppointment"
0x65c0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x65c10  ldloc.0
0x65c11  ret
```
