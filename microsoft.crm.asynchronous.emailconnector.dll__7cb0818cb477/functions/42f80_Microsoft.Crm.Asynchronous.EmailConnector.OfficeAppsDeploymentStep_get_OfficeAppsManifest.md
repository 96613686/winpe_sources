# Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::get_OfficeAppsManifest

- ea: `0x42f80`
- end: `0x432ca`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::get_OfficeAppsManifest`
- size: `842`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x42b50`

## callees

- `0x7d10`
- `0xac10`
- `0x32970`
- `0x32980`
- `0x3ab40`
- `0x417a0`
- `0x41910`
- `0x42060`
- `0x42940`
- `0x42f10`
- `0x42f80`
- `0x4da80`
- `0x71d00`

## string_xrefs

- `0x4301b`: `MetadataUri`
- `0x43162`: `<Rule ItemType="Appointment" xsi:type="ItemIs" FormType="Read"/>`
- `0x431f1`: `Office Apps manifest is set to '{0}' for mailbox {1}, organization {2} async event id {3}.`
- `0x43254`: `Failed to build the Office Apps manifest for mailbox {0}, organization {1}, async event id {2} : exception: {3}`

## pseudocode

```c

```

## disassembly

```asm
0x42f80  ldarg.0
0x42f81  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::_officeAppsManifest
0x42f86  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42f8b  brfalse  loc_432C3
0x42f90  ldsfld   string [mscorlib]System.String::Empty
0x42f95  stloc.0
0x42f96  ldsfld   string [mscorlib]System.String::Empty
0x42f9b  stloc.1
0x42f9c  ldarg.0
0x42f9d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x42fa2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x42fa7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x42fac  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailServerType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile::get_ServerType()
0x42fb1  stloc.2
0x42fb2  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x42fb7  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x42fbc  stloc.3
0x42fbd  ldloc.2
0x42fbe  brtrue.s loc_42FD8
0x42fc0  ldloc.3
0x42fc1  ldc.i4.2
0x42fc2  bne.un.s loc_42FCE
0x42fc4  ldstr    aOnline// "online"
0x42fc9  dup
0x42fca  stloc.1
0x42fcb  stloc.0
0x42fcc  br.s     loc_42FFA
0x42fce  ldstr    aOnprem// "onprem"
0x42fd3  dup
0x42fd4  stloc.1
0x42fd5  stloc.0
0x42fd6  br.s     loc_42FFA
0x42fd8  ldloc.2
0x42fd9  ldc.i4.3
0x42fda  bne.un.s loc_42FEA
0x42fdc  ldstr    aOnprem// "onprem"
0x42fe1  stloc.0
0x42fe2  ldstr    aOnline// "online"
0x42fe7  stloc.1
0x42fe8  br.s     loc_42FFA
0x42fea  ldloc.2
0x42feb  ldc.i4.2
0x42fec  bne.un.s loc_42FFA
0x42fee  ldstr    aOnline// "online"
0x42ff3  stloc.0
0x42ff4  ldstr    aOnprem// "onprem"
0x42ff9  stloc.1
0x42ffa  ldsfld   string [mscorlib]System.String::Empty
0x42fff  stloc.s  4
0x43001  ldsfld   string [mscorlib]System.String::Empty
0x43006  stloc.s  5
0x43008  ldloc.0
0x43009  ldstr    aOnprem// "onprem"
0x4300e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x43013  brfalse.s loc_43066
0x43015  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_DefaultFederationProvider()
0x4301a  dup
0x4301b  ldstr    aMetadatauri// "MetadataUri"
0x43020  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x43025  callvirt instance string [mscorlib]System.Object::ToString()
0x4302a  newobj   instance void [System]System.Uri::.ctor(string)
0x4302f  ldc.i4.1
0x43030  callvirt instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x43035  stloc.s  0xB
0x43037  ldstr    aAppdomain// "<AppDomain>"
0x4303c  ldloc.s  0xB
0x4303e  ldstr    aAppdomain_0// "</AppDomain>"
0x43043  call     string [mscorlib]System.String::Concat(string, string, string)
0x43048  stloc.s  4
0x4304a  ldstr    aExternalrelyin// "ExternalRelyingPartyPassiveIdentifier"
0x4304f  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x43054  callvirt instance string [mscorlib]System.Object::ToString()
0x43059  newobj   instance void [System]System.Uri::.ctor(string)
0x4305e  ldc.i4.1
0x4305f  call     instance string [System]System.Uri::GetLeftPart(valuetype [System]System.UriPartial)
0x43064  stloc.s  5
0x43066  ldarg.0
0x43067  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x4306c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43071  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetOrgUrl(valuetype [mscorlib]System.Guid organizationId)
0x43076  stloc.s  6
0x43078  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x4307d  ldarg.0
0x4307e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x43083  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x43088  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationUrlName(valuetype [mscorlib]System.Guid)
0x4308d  stloc.s  7
0x4308f  call     string Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::get_OfficeMailAppsManifestTemplate()
0x43094  stloc.s  8
0x43096  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x4309b  ldarg.0
0x4309c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x430a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x430a6  ldarg.0
0x430a7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x430ac  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x430b1  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x430b6  callvirt instance string [mscorlib]System.Object::ToString()
0x430bb  stloc.s  9
0x430bd  ldarg.0
0x430be  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x430c3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x430c8  ldarg.0
0x430c9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x430ce  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x430d3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x430d8  ldarg.0
0x430d9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x430de  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IEmailAccessConfiguration Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext::get_EmailAccessConfiguration()
0x430e3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile Microsoft.Crm.Asynchronous.EmailConnector.IMailboxAccessConfiguration::get_Profile()
0x430e8  call     bool Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsProvider::IsOfficeAppsAppointmentDeploymentEnabled(valuetype [mscorlib]System.Guid organizationId, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IEmailServerProfile profile)
0x430ed  stloc.s  0xA
0x430ef  ldloc.s  0xA
0x430f1  brfalse.s loc_43160
0x430f3  ldloc.s  0xA
0x430f5  brfalse.s loc_4313A
0x430f7  ldarg.0
0x430f8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x430fd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x43102  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x43107  ldstr    aActdeliverymet// "actdeliverymethod"
0x4310c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x43111  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ACTDeliveryMethod
0x43116  ldc.i4.1
0x43117  bne.un.s loc_4313A
0x43119  ldarg.0
0x4311a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x4311f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x43124  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x43129  ldstr    aEnabledforact// "enabledforact"
0x4312e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x43133  unbox.any [mscorlib]System.Boolean
0x43138  brfalse.s loc_43160
0x4313a  ldloc.s  0xA
0x4313c  brfalse.s loc_43186
0x4313e  ldarg.0
0x4313f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x43144  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x43149  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_InternalMailbox()
0x4314e  ldstr    aActdeliverymet// "actdeliverymethod"
0x43153  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.Mailbox::get_Item(string attributeName)
0x43158  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ACTDeliveryMethod
0x4315d  ldc.i4.1
0x4315e  beq.s    loc_43186
0x43160  ldloc.s  8
0x43162  ldstr    aRuleItemtypeAp// "<Rule ItemType=\"Appointment\" xsi:type"...
0x43167  ldstr    asc_8A7C2// ""
0x4316c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43171  stloc.s  8
0x43173  ldloc.s  8
0x43175  ldstr    aRuleItemtypeAp_0// "<Rule ItemType=\"Appointment\" xsi:type"...
0x4317a  ldstr    asc_8A7C2// ""
0x4317f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x43184  stloc.s  8
0x43186  ldarg.0
0x43187  ldloc.s  8
0x43189  ldc.i4.s 0xA
0x4318b  newarr   [mscorlib]System.Object
0x43190  dup
0x43191  ldc.i4.0
0x43192  ldstr    a270a343cCe6e4c// "270a343c-ce6e-4c7e-be25-f29abe0e089b"
0x43197  stelem.ref
0x43198  dup
0x43199  ldc.i4.1
0x4319a  ldloc.s  6
0x4319c  stelem.ref
0x4319d  dup
0x4319e  ldc.i4.2
0x4319f  ldloc.s  7
0x431a1  stelem.ref
0x431a2  dup
0x431a3  ldc.i4.3
0x431a4  ldloc.0
0x431a5  stelem.ref
0x431a6  dup
0x431a7  ldc.i4.4
0x431a8  ldloc.1
0x431a9  stelem.ref
0x431aa  dup
0x431ab  ldc.i4.5
0x431ac  ldloc.s  4
0x431ae  stelem.ref
0x431af  dup
0x431b0  ldc.i4.6
0x431b1  ldloc.s  5
0x431b3  stelem.ref
0x431b4  dup
0x431b5  ldc.i4.7
0x431b6  ldarg.0
0x431b7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x431bc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x431c1  box      [mscorlib]System.Guid
0x431c6  stelem.ref
0x431c7  dup
0x431c8  ldc.i4.8
0x431c9  ldarg.0
0x431ca  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x431cf  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x431d4  ldstr    aMailboxid// "mailboxid"
0x431d9  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x431de  stelem.ref
0x431df  dup
0x431e0  ldc.i4.s 9
0x431e2  ldloc.s  9
0x431e4  stelem.ref
0x431e5  call     string [mscorlib]System.String::Format(string, object[])
0x431ea  stfld    string Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::_officeAppsManifest
0x431ef  ldarg.0
0x431f0  ldc.i4.4
0x431f1  ldstr    aOfficeAppsMani// "Office Apps manifest is set to '{0}' fo"...
0x431f6  ldc.i4.4
0x431f7  newarr   [mscorlib]System.Object
0x431fc  dup
0x431fd  ldc.i4.0
0x431fe  ldloc.s  7
0x43200  stelem.ref
0x43201  dup
0x43202  ldc.i4.1
0x43203  ldarg.0
0x43204  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x43209  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x4320e  ldstr    aMailboxid// "mailboxid"
0x43213  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x43218  stelem.ref
0x43219  dup
0x4321a  ldc.i4.2
0x4321b  ldarg.0
0x4321c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x43221  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x43226  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x4322b  box      [mscorlib]System.Guid
0x43230  stelem.ref
0x43231  dup
0x43232  ldc.i4.3
0x43233  ldarg.0
0x43234  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x43239  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4323e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x43243  box      [mscorlib]System.Guid
0x43248  stelem.ref
0x43249  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4324e  leave.s  loc_432C3
0x43250  stloc.s  0xC
0x43252  ldarg.0
0x43253  ldc.i4.1
0x43254  ldstr    aFailedToBuildT// "Failed to build the Office Apps manifes"...
0x43259  ldc.i4.4
0x4325a  newarr   [mscorlib]System.Object
0x4325f  dup
0x43260  ldc.i4.0
0x43261  ldarg.0
0x43262  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x43267  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x4326c  ldstr    aMailboxid// "mailboxid"
0x43271  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x43276  stelem.ref
0x43277  dup
0x43278  ldc.i4.1
0x43279  ldarg.0
0x4327a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x4327f  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x43284  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x43289  box      [mscorlib]System.Guid
0x4328e  stelem.ref
0x4328f  dup
0x43290  ldc.i4.2
0x43291  ldarg.0
0x43292  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x43297  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x4329c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_EventId()
0x432a1  box      [mscorlib]System.Guid
0x432a6  stelem.ref
0x432a7  dup
0x432a8  ldc.i4.3
0x432a9  ldloc.s  0xC
0x432ab  ldarg.0
0x432ac  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x432b1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x432b6  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x432bb  stelem.ref
0x432bc  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x432c1  leave.s  loc_432C3
0x432c3  ldarg.0
0x432c4  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.OfficeAppsDeploymentStep::_officeAppsManifest
0x432c9  ret
```
