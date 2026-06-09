# Microsoft.Crm.Asynchronous.ServerConfiguration::ShouldIgnoreNotification

- ea: `0xcc70`
- end: `0xce17`
- name: `Microsoft.Crm.Asynchronous.ServerConfiguration::ShouldIgnoreNotification`
- size: `423`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xcc30`

## callees

- `0xcc70`

## string_xrefs

- `0xcd7c`: `Ignoring Notification {0} for Organization {1} since it is not polled by current service instance.`
- `0xcdee`: `Ignoring Notification {0} for Scalegroup {1} since it is not polled by current service instance.`

## pseudocode

```c

```

## disassembly

```asm
0xcc70  ldc.i4.0
0xcc71  stloc.0
0xcc72  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0xcc77  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0xcc7c  ldc.i4.2
0xcc7d  bne.un   loc_CE15
0xcc82  call     class [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0xcc87  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0xcc8c  stloc.1
0xcc8d  ldarg.1
0xcc8e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xcc93  stloc.2
0xcc94  ldloc.2
0xcc95  ldc.i4.s 0x1A
0xcc97  sub
0xcc98  switch   loc_CDAA, loc_CE15, loc_CE15, loc_CCC1, loc_CCC1, loc_CE15, loc_CD5D
0xccb9  ldloc.2
0xccba  ldc.i4.s 0x45
0xccbc  bne.un   loc_CE15
0xccc1  nop
0xccc2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0xccc7  ldarg.1
0xccc8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xcccd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0xccd2  stloc.3
0xccd3  ldloc.1
0xccd4  ldloc.3
0xccd5  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xccda  brfalse.s loc_CD23
0xccdc  ldc.i4.1
0xccdd  stloc.0
0xccde  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcce3  ldc.i4.s 0x15
0xcce5  ldstr    aIgnoringNotifi// "Ignoring Notification {0} for Organizat"...
0xccea  ldc.i4.4
0xcceb  newarr   [mscorlib]System.Object
0xccf0  dup
0xccf1  ldc.i4.0
0xccf2  ldarg.1
0xccf3  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xccf8  box      [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0xccfd  stelem.ref
0xccfe  dup
0xccff  ldc.i4.1
0xcd00  ldarg.1
0xcd01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xcd06  box      [mscorlib]System.Guid
0xcd0b  stelem.ref
0xcd0c  dup
0xcd0d  ldc.i4.2
0xcd0e  ldloc.3
0xcd0f  box      [mscorlib]System.Guid
0xcd14  stelem.ref
0xcd15  dup
0xcd16  ldc.i4.3
0xcd17  ldloc.1
0xcd18  box      [mscorlib]System.Guid
0xcd1d  stelem.ref
0xcd1e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcd23  leave    loc_CE15
0xcd28  stloc.s  4
0xcd2a  ldc.i4.0
0xcd2b  stloc.0
0xcd2c  ldloc.s  4
0xcd2e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcd33  ldc.i4.s 0x15
0xcd35  ldstr    aErrorWhileDete// "Error while determining scalegroup id f"...
0xcd3a  ldc.i4.2
0xcd3b  newarr   [mscorlib]System.Object
0xcd40  dup
0xcd41  ldc.i4.0
0xcd42  ldarg.1
0xcd43  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xcd48  box      [mscorlib]System.Guid
0xcd4d  stelem.ref
0xcd4e  dup
0xcd4f  ldc.i4.1
0xcd50  ldloc.s  4
0xcd52  stelem.ref
0xcd53  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcd58  leave    loc_CE15
0xcd5d  ldarg.0
0xcd5e  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration> Microsoft.Crm.Asynchronous.ServerConfiguration::_organizations
0xcd63  ldarg.1
0xcd64  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xcd69  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration>::ContainsKey(var<u1>)
0xcd6e  brtrue   loc_CE15
0xcd73  ldc.i4.1
0xcd74  stloc.0
0xcd75  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcd7a  ldc.i4.s 0x15
0xcd7c  ldstr    aIgnoringNotifi_0// "Ignoring Notification {0} for Organizat"...
0xcd81  ldc.i4.2
0xcd82  newarr   [mscorlib]System.Object
0xcd87  dup
0xcd88  ldc.i4.0
0xcd89  ldarg.1
0xcd8a  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xcd8f  box      [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0xcd94  stelem.ref
0xcd95  dup
0xcd96  ldc.i4.1
0xcd97  ldarg.1
0xcd98  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_OrganizationId()
0xcd9d  box      [mscorlib]System.Guid
0xcda2  stelem.ref
0xcda3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xcda8  br.s     loc_CE15
0xcdaa  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcdaf  stloc.s  5
0xcdb1  ldarg.1
0xcdb2  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventData()
0xcdb7  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xcdbc  brtrue.s loc_CE15
0xcdbe  ldarg.1
0xcdbf  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventData()
0xcdc4  ldloca.s 5
0xcdc6  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0xcdcb  brfalse.s loc_CE15
0xcdcd  ldloc.s  5
0xcdcf  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xcdd4  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xcdd9  brfalse.s loc_CE15
0xcddb  ldloc.1
0xcddc  ldloc.s  5
0xcdde  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xcde3  brfalse.s loc_CE15
0xcde5  ldc.i4.1
0xcde6  stloc.0
0xcde7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xcdec  ldc.i4.s 0x15
0xcdee  ldstr    aIgnoringNotifi_1// "Ignoring Notification {0} for Scalegrou"...
0xcdf3  ldc.i4.2
0xcdf4  newarr   [mscorlib]System.Object
0xcdf9  dup
0xcdfa  ldc.i4.0
0xcdfb  ldarg.1
0xcdfc  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventArgs::get_EventId()
0xce01  box      [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType
0xce06  stelem.ref
0xce07  dup
0xce08  ldc.i4.1
0xce09  ldloc.1
0xce0a  box      [mscorlib]System.Guid
0xce0f  stelem.ref
0xce10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xce15  ldloc.0
0xce16  ret
```
