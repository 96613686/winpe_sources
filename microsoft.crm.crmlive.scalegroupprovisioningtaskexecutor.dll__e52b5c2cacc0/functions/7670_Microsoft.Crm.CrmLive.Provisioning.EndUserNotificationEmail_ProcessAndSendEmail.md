# Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::ProcessAndSendEmail

- ea: `0x7670`
- end: `0x77b5`
- name: `Microsoft.Crm.CrmLive.Provisioning.EndUserNotificationEmail::ProcessAndSendEmail`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x30350`
- `0x30410`

## callees

- `0x70e0`
- `0x7100`
- `0x7120`
- `0x7140`
- `0x7160`
- `0x7670`

## string_xrefs

- `0x7680`: `PlatformSharedServiceURL`
- `0x76fc`: `CRM Live E-Mail Service`

## pseudocode

```c

```

## disassembly

```asm
0x7670  ldc.i4.0
0x7671  stloc.0
0x7672  ldarg.0
0x7673  brfalse.s loc_7679
0x7675  ldarg.0
0x7676  ldlen
0x7677  brtrue.s loc_767B
0x7679  ldloc.0
0x767a  ret
0x767b  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x7680  ldstr    aPlatformshared// "PlatformSharedServiceURL"
0x7685  ldc.i4.0
0x7686  callvirt T0x2B000011
0x768b  newobj   instance void [System]System.Uri::.ctor(string)
0x7690  stloc.1
0x7691  ldarg.0
0x7692  stloc.2
0x7693  ldc.i4.0
0x7694  stloc.3
0x7695  br       loc_77AA
0x769a  ldloc.2
0x769b  ldloc.3
0x769c  ldelem.ref
0x769d  stloc.s  4
0x769f  ldloc.1
0x76a0  ldc.i4   0x10000
0x76a5  newobj   instance void [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::.ctor(class [System]System.Uri, valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.CrmLiveConnections)
0x76aa  stloc.s  5
0x76ac  ldloc.s  5
0x76ae  callvirt instance class [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.PlatformClient::get_LivePlatformService()
0x76b3  ldarg.1
0x76b4  ldarg.2
0x76b5  ldloc.s  4
0x76b7  callvirt instance int32 Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_LocaleId()
0x76bc  ldloc.s  4
0x76be  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_FirstName()
0x76c3  ldloc.s  4
0x76c5  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_LastName()
0x76ca  ldloc.s  4
0x76cc  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_WindowsLiveId()
0x76d1  ldloc.s  4
0x76d3  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_EmailAddress()
0x76d8  callvirt instance valuetype [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.EndUserNotificationType [Microsoft.Crm.SiteServicesClient]Microsoft.Crm.SiteClient.LivePlatformService.LivePlatformService::SendEndUserNotificationEmail(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32, string, string, string, string)
0x76dd  stloc.0
0x76de  leave.s  loc_76EC
0x76e0  ldloc.s  5
0x76e2  brfalse.s loc_76EB
0x76e4  ldloc.s  5
0x76e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x76eb  endfinally
0x76ec  leave    loc_77A6
0x76f1  stloc.s  6
0x76f3  call     class [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::NewEventLog()
0x76f8  stloc.s  7
0x76fa  ldloc.s  7
0x76fc  ldstr    aCrmLiveEMailSe// "CRM Live E-Mail Service"
0x7701  ldc.i4.1
0x7702  ldc.i4   0xC0004604
0x7707  conv.u8
0x7708  ldc.i4.3
0x7709  newarr   [mscorlib]System.Object
0x770e  dup
0x770f  ldc.i4.0
0x7710  ldstr    aEndusernotific// "EndUserNotification Engine"
0x7715  stelem.ref
0x7716  dup
0x7717  ldc.i4.1
0x7718  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x771d  ldstr    aOrganization0A// "Organization: {0}, Admin: {1} {2}, Emai"...
0x7722  ldc.i4.4
0x7723  newarr   [mscorlib]System.Object
0x7728  dup
0x7729  ldc.i4.0
0x772a  ldarg.2
0x772b  box      [mscorlib]System.Guid
0x7730  stelem.ref
0x7731  dup
0x7732  ldc.i4.1
0x7733  ldloc.s  4
0x7735  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_FirstName()
0x773a  stelem.ref
0x773b  dup
0x773c  ldc.i4.2
0x773d  ldloc.s  4
0x773f  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_LastName()
0x7744  stelem.ref
0x7745  dup
0x7746  ldc.i4.3
0x7747  ldloc.s  4
0x7749  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_EmailAddress()
0x774e  stelem.ref
0x774f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7754  stelem.ref
0x7755  dup
0x7756  ldc.i4.2
0x7757  ldloc.s  6
0x7759  callvirt instance string [mscorlib]System.Object::ToString()
0x775e  stelem.ref
0x775f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x7764  leave.s  loc_7772
0x7766  ldloc.s  7
0x7768  brfalse.s loc_7771
0x776a  ldloc.s  7
0x776c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7771  endfinally
0x7772  ldloc.s  6
0x7774  ldarg.2
0x7775  ldc.i4.s 0xA
0x7777  ldstr    aSendemailFaile_0// "SendEmail Failed for Admin User {0} of "...
0x777c  ldc.i4.3
0x777d  newarr   [mscorlib]System.Object
0x7782  dup
0x7783  ldc.i4.0
0x7784  ldloc.s  4
0x7786  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_EmailAddress()
0x778b  stelem.ref
0x778c  dup
0x778d  ldc.i4.1
0x778e  ldarg.2
0x778f  box      [mscorlib]System.Guid
0x7794  stelem.ref
0x7795  dup
0x7796  ldc.i4.2
0x7797  ldloc.s  6
0x7799  callvirt instance string [mscorlib]System.Object::ToString()
0x779e  stelem.ref
0x779f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x77a4  leave.s  loc_77A6
0x77a6  ldloc.3
0x77a7  ldc.i4.1
0x77a8  add
0x77a9  stloc.3
0x77aa  ldloc.3
0x77ab  ldloc.2
0x77ac  ldlen
0x77ad  conv.i4
0x77ae  blt      loc_769A
0x77b3  ldloc.0
0x77b4  ret
```
