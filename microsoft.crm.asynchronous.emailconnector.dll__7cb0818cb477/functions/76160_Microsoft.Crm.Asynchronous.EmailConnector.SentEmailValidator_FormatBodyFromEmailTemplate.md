# Microsoft.Crm.Asynchronous.EmailConnector.SentEmailValidator::FormatBodyFromEmailTemplate

- ea: `0x76160`
- end: `0x76386`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.SentEmailValidator::FormatBodyFromEmailTemplate`
- size: `550`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x76100`

## callees

- `0xa6b0`
- `0xac10`
- `0x4d8c0`
- `0x4da80`
- `0x76160`

## string_xrefs

- `0x76290`: `https://www.microsoft.com/en-US/dynamics/crm-customer-center/set-personal-options-that-affect-tracking-and-synchronization-between-dynamics-365-and-outlook-or-exchange.aspx`
- `0x762ab`: `https://www.microsoft.com/en-US/dynamics/crm-customer-center/frequently-asked-questions-about-synchronizing-records-between-microsoft-dynamics-365-and-microsoft-outlook.aspx`
- `0x7632b`: `https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx`
- `0x76339`: `EmailConnector.TestEmail.Body.Email.FooterLink.First`
- `0x76348`: `https://mbs.microsoft.com/customersource/northamerica/CRM/support/support-lifecycle/CRMSupport`
- `0x76356`: `EmailConnector.TestEmail.Body.Email.FooterLink.Second`

## pseudocode

```c

```

## disassembly

```asm
0x76160  ldsfld   string [mscorlib]System.String::Empty
0x76165  stloc.0
0x76166  ldnull
0x76167  stloc.1
0x76168  ldarg.2
0x76169  brfalse.s loc_7619A
0x7616b  ldarg.2
0x7616c  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OwnerType()
0x76171  ldc.i4.8
0x76172  bne.un.s loc_7619A
0x76174  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x76179  ldarg.2
0x7617a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OwnerId()
0x7617f  ldarg.2
0x76180  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x76185  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x7618a  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x7618f  stloc.1
0x76190  ldloc.1
0x76191  brfalse.s loc_7619A
0x76193  ldloc.1
0x76194  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_FirstName()
0x76199  stloc.0
0x7619a  ldsfld   string [mscorlib]System.String::Empty
0x7619f  stloc.2
0x761a0  ldsfld   string [mscorlib]System.String::Empty
0x761a5  stloc.3
0x761a6  ldarg.2
0x761a7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x761ac  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetOrgUrl(valuetype [mscorlib]System.Guid organizationId)
0x761b1  stloc.2
0x761b2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x761b7  ldarg.2
0x761b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x761bd  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationUrlName(valuetype [mscorlib]System.Guid)
0x761c2  stloc.3
0x761c3  leave.s  loc_76206
0x761c5  stloc.s  4
0x761c7  ldarg.2
0x761c8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x761cd  ldarg.2
0x761ce  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x761d3  ldc.i4.s 0x3D
0x761d5  ldc.i4.1
0x761d6  ldstr    aErrorGettingOr// "Error getting org url while sending out"...
0x761db  ldc.i4.2
0x761dc  newarr   [mscorlib]System.Object
0x761e1  dup
0x761e2  ldc.i4.0
0x761e3  ldarg.2
0x761e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_MailboxId()
0x761e9  box      [mscorlib]System.Guid
0x761ee  stelem.ref
0x761ef  dup
0x761f0  ldc.i4.1
0x761f1  ldloc.s  4
0x761f3  ldarg.2
0x761f4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_OrganizationId()
0x761f9  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x761fe  stelem.ref
0x761ff  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorTraceFormat(valuetype [mscorlib]System.Guid orgId, object mailbox, valuetype [mscorlib]System.Guid asyncEventId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x76204  leave.s  loc_76206
0x76206  ldarg.0
0x76207  ldc.i4.s 0x15
0x76209  newarr   [mscorlib]System.Object
0x7620e  dup
0x7620f  ldc.i4.0
0x76210  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76215  ldstr    aEmailconnector_43// "EmailConnector.TestEmail.Body.Subject"
0x7621a  ldarg.1
0x7621b  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76220  stelem.ref
0x76221  dup
0x76222  ldc.i4.1
0x76223  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76228  ldstr    aEmailconnector_44// "EmailConnector.TestEmail.Body.Status"
0x7622d  ldarg.1
0x7622e  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76233  stelem.ref
0x76234  dup
0x76235  ldc.i4.2
0x76236  ldloc.1
0x76237  brtrue.s loc_7624B
0x76239  ldarg.2
0x7623a  brtrue.s loc_76243
0x7623c  ldsfld   string [mscorlib]System.String::Empty
0x76241  br.s     loc_76261
0x76243  ldarg.2
0x76244  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IMailboxData::get_Name()
0x76249  br.s     loc_76261
0x7624b  ldstr    a01_6// "{0} {1}"
0x76250  ldloc.1
0x76251  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_FirstName()
0x76256  ldloc.1
0x76257  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_LastName()
0x7625c  call     string [mscorlib]System.String::Format(string, object, object)
0x76261  stelem.ref
0x76262  dup
0x76263  ldc.i4.3
0x76264  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76269  ldstr    aEmailconnector_45// "EmailConnector.TestEmail.Body.Email.Sal"...
0x7626e  ldarg.1
0x7626f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76274  ldloc.0
0x76275  call     string [mscorlib]System.String::Format(string, object)
0x7627a  stelem.ref
0x7627b  dup
0x7627c  ldc.i4.4
0x7627d  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76282  ldstr    aEmailconnector_46// "EmailConnector.TestEmail.Body.Email.Con"...
0x76287  ldarg.1
0x76288  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x7628d  stelem.ref
0x7628e  dup
0x7628f  ldc.i4.5
0x76290  ldstr    aHttpsWwwMicros// "https://www.microsoft.com/en-US/dynamic"...
0x76295  stelem.ref
0x76296  dup
0x76297  ldc.i4.6
0x76298  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x7629d  ldstr    aEmailconnector_47// "EmailConnector.TestEmail.Body.Email.But"...
0x762a2  ldarg.1
0x762a3  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x762a8  stelem.ref
0x762a9  dup
0x762aa  ldc.i4.7
0x762ab  ldstr    aHttpsWwwMicros_0// "https://www.microsoft.com/en-US/dynamic"...
0x762b0  stelem.ref
0x762b1  dup
0x762b2  ldc.i4.8
0x762b3  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x762b8  ldstr    aEmailconnector_48// "EmailConnector.TestEmail.Body.Email.But"...
0x762bd  ldarg.1
0x762be  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x762c3  stelem.ref
0x762c4  dup
0x762c5  ldc.i4.s 9
0x762c7  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x762cc  ldstr    aEmailconnector_49// "EmailConnector.TestEmail.Body.Email.But"...
0x762d1  ldarg.1
0x762d2  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x762d7  stelem.ref
0x762d8  dup
0x762d9  ldc.i4.s 0xA
0x762db  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x762e0  ldstr    aEmailconnector_50// "EmailConnector.TestEmail.Body.Email.But"...
0x762e5  ldarg.1
0x762e6  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x762eb  stelem.ref
0x762ec  dup
0x762ed  ldc.i4.s 0xB
0x762ef  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x762f4  ldstr    aEmailconnector_51// "EmailConnector.TestEmail.Body.Email.Sig"...
0x762f9  ldarg.1
0x762fa  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x762ff  stelem.ref
0x76300  dup
0x76301  ldc.i4.s 0xC
0x76303  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76308  ldstr    aEmailconnector_52// "EmailConnector.TestEmail.Body.Email.Sig"...
0x7630d  ldarg.1
0x7630e  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76313  stelem.ref
0x76314  dup
0x76315  ldc.i4.s 0xD
0x76317  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x7631c  ldstr    aEmailconnector_53// "EmailConnector.TestEmail.Body.Email.Not"...
0x76321  ldarg.1
0x76322  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76327  stelem.ref
0x76328  dup
0x76329  ldc.i4.s 0xE
0x7632b  ldstr    aHttpsWwwMicros_1// "https://www.microsoft.com/en-us/privacy"...
0x76330  stelem.ref
0x76331  dup
0x76332  ldc.i4.s 0xF
0x76334  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76339  ldstr    aEmailconnector_54// "EmailConnector.TestEmail.Body.Email.Foo"...
0x7633e  ldarg.1
0x7633f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76344  stelem.ref
0x76345  dup
0x76346  ldc.i4.s 0x10
0x76348  ldstr    aHttpsMbsMicros// "https://mbs.microsoft.com/customersourc"...
0x7634d  stelem.ref
0x7634e  dup
0x7634f  ldc.i4.s 0x11
0x76351  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x76356  ldstr    aEmailconnector_55// "EmailConnector.TestEmail.Body.Email.Foo"...
0x7635b  ldarg.1
0x7635c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76361  stelem.ref
0x76362  dup
0x76363  ldc.i4.s 0x12
0x76365  call     class [mscorlib]System.Resources.ResourceManager Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::get_ResourceManager()
0x7636a  ldstr    aEmailconnector_56// "EmailConnector.TestEmail.Body.Email.Foo"...
0x7636f  ldarg.1
0x76370  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x76375  stelem.ref
0x76376  dup
0x76377  ldc.i4.s 0x13
0x76379  ldloc.2
0x7637a  stelem.ref
0x7637b  dup
0x7637c  ldc.i4.s 0x14
0x7637e  ldloc.3
0x7637f  stelem.ref
0x76380  call     string [mscorlib]System.String::Format(string, object[])
0x76385  ret
```
