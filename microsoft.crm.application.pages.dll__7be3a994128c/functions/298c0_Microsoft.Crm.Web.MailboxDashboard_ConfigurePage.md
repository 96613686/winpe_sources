# Microsoft.Crm.Web.MailboxDashboard::ConfigurePage

- ea: `0x298c0`
- end: `0x2a0f3`
- name: `Microsoft.Crm.Web.MailboxDashboard::ConfigurePage`
- size: `2099`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x298c0`
- `0x2a100`

## string_xrefs

- `0x29947`: `processinglastattemptedon`
- `0x29c56`: `processinglastattemptedon`
- `0x29c6c`: `processinglastattemptedon`
- `0x2992e`: `incomingemaildeliverymethod`
- `0x29976`: `incomingemaildeliverymethod`
- `0x29a68`: `incomingemaildeliverymethod`
- `0x29a79`: `incomingemaildeliverymethod`
- `0x2990e`: `enabledforincomingemail`
- `0x29b25`: `enabledforincomingemail`
- `0x29b36`: `enabledforincomingemail`
- `0x29926`: `testemailconfigurationscheduled`
- `0x29a44`: `testemailconfigurationscheduled`
- `0x29a55`: `testemailconfigurationscheduled`
- `0x29959`: `incomingemailstatus`
- `0x29add`: `incomingemailstatus`
- `0x29da4`: `EmailConnector.MailboxDashboard.TotalMailboxesConfigured.Singular`
- `0x29dc4`: `EmailConnector.MailboxDashboard.TotalMailboxesConfigured`

## pseudocode

```c

```

## disassembly

```asm
0x298c0  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x298c5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x298ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x298cf  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x298d4  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x298d9  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_EmailConnectionChannel()
0x298de  brtrue   loc_29D70
0x298e3  ldstr    aMailbox// "mailbox"
0x298e8  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x298ed  stloc.0
0x298ee  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x298f3  stloc.1
0x298f4  ldloc.1
0x298f5  ldc.i4.s 0xE
0x298f7  newarr   [mscorlib]System.String
0x298fc  dup
0x298fd  ldc.i4.0
0x298fe  ldstr    aMailboxid// "mailboxid"
0x29903  stelem.ref
0x29904  dup
0x29905  ldc.i4.1
0x29906  ldstr    aTransientfailu// "transientfailurecount"
0x2990b  stelem.ref
0x2990c  dup
0x2990d  ldc.i4.2
0x2990e  ldstr    aEnabledforinco// "enabledforincomingemail"
0x29913  stelem.ref
0x29914  dup
0x29915  ldc.i4.3
0x29916  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x2991b  stelem.ref
0x2991c  dup
0x2991d  ldc.i4.4
0x2991e  ldstr    aEnabledforact// "enabledforact"
0x29923  stelem.ref
0x29924  dup
0x29925  ldc.i4.5
0x29926  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x2992b  stelem.ref
0x2992c  dup
0x2992d  ldc.i4.6
0x2992e  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x29933  stelem.ref
0x29934  dup
0x29935  ldc.i4.7
0x29936  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x2993b  stelem.ref
0x2993c  dup
0x2993d  ldc.i4.8
0x2993e  ldstr    aActdeliverymet// "actdeliverymethod"
0x29943  stelem.ref
0x29944  dup
0x29945  ldc.i4.s 9
0x29947  ldstr    aProcessinglast// "processinglastattemptedon"
0x2994c  stelem.ref
0x2994d  dup
0x2994e  ldc.i4.s 0xA
0x29950  ldstr    aActstatus// "actstatus"
0x29955  stelem.ref
0x29956  dup
0x29957  ldc.i4.s 0xB
0x29959  ldstr    aIncomingemails// "incomingemailstatus"
0x2995e  stelem.ref
0x2995f  dup
0x29960  ldc.i4.s 0xC
0x29962  ldstr    aOutgoingemails// "outgoingemailstatus"
0x29967  stelem.ref
0x29968  dup
0x29969  ldc.i4.s 0xD
0x2996b  ldstr    aStatecode// "statecode"
0x29970  stelem.ref
0x29971  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x29976  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x2997b  ldc.i4.0
0x2997c  ldc.i4.2
0x2997d  box      [mscorlib]System.Int32
0x29982  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x29987  stloc.2
0x29988  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x2998d  ldc.i4.0
0x2998e  ldc.i4.2
0x2998f  box      [mscorlib]System.Int32
0x29994  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x29999  stloc.3
0x2999a  ldstr    aActdeliverymet// "actdeliverymethod"
0x2999f  ldc.i4.0
0x299a0  ldc.i4.1
0x299a1  box      [mscorlib]System.Int32
0x299a6  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression::.ctor(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x299ab  stloc.s  4
0x299ad  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::.ctor()
0x299b2  stloc.s  5
0x299b4  ldloc.s  5
0x299b6  ldc.i4.1
0x299b7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::set_FilterOperator(valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.LogicalOperator)
0x299bc  ldloc.s  5
0x299be  ldloc.2
0x299bf  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x299c4  ldloc.s  5
0x299c6  ldloc.3
0x299c7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x299cc  ldloc.s  5
0x299ce  ldloc.s  4
0x299d0  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionExpression)
0x299d5  ldloc.0
0x299d6  ldloc.1
0x299d7  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::set_ColumnSet(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase)
0x299dc  ldloc.0
0x299dd  ldloc.s  5
0x299df  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::set_Criteria(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression)
0x299e4  ldloc.0
0x299e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x299ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x299ef  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x299f4  stloc.s  6
0x299f6  br       loc_29D56
0x299fb  ldloc.s  6
0x299fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x29a02  stloc.s  7
0x29a04  ldloc.s  7
0x29a06  ldstr    aStatecode// "statecode"
0x29a0b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a10  brfalse.s loc_29A34
0x29a12  ldloc.s  7
0x29a14  ldstr    aStatecode// "statecode"
0x29a19  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a1e  callvirt instance string [mscorlib]System.Object::ToString()
0x29a23  ldloca.s 8
0x29a25  call     T0x2B000009
0x29a2a  brfalse.s loc_29A34
0x29a2c  ldloc.s  8
0x29a2e  ldc.i4.1
0x29a2f  beq      loc_29D56
0x29a34  ldarg.0
0x29a35  ldarg.0
0x29a36  ldfld    int32 Microsoft.Crm.Web.MailboxDashboard::sssMB
0x29a3b  ldc.i4.1
0x29a3c  add
0x29a3d  stfld    int32 Microsoft.Crm.Web.MailboxDashboard::sssMB
0x29a42  ldloc.s  7
0x29a44  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x29a49  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a4e  brtrue.s loc_29A53
0x29a50  ldc.i4.0
0x29a51  br.s     loc_29A64
0x29a53  ldloc.s  7
0x29a55  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x29a5a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a5f  unbox.any [mscorlib]System.Boolean
0x29a64  stloc.s  9
0x29a66  ldloc.s  7
0x29a68  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x29a6d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a72  brtrue.s loc_29A77
0x29a74  ldc.i4.0
0x29a75  br.s     loc_29A8B
0x29a77  ldloc.s  7
0x29a79  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x29a7e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a83  unbox.any [mscorlib]System.Int32
0x29a88  ldc.i4.2
0x29a89  ceq
0x29a8b  stloc.s  0xA
0x29a8d  ldloc.s  7
0x29a8f  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x29a94  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29a99  brtrue.s loc_29A9E
0x29a9b  ldc.i4.0
0x29a9c  br.s     loc_29AB2
0x29a9e  ldloc.s  7
0x29aa0  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x29aa5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29aaa  unbox.any [mscorlib]System.Int32
0x29aaf  ldc.i4.2
0x29ab0  ceq
0x29ab2  stloc.s  0xB
0x29ab4  ldloc.s  7
0x29ab6  ldstr    aActdeliverymet// "actdeliverymethod"
0x29abb  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29ac0  brtrue.s loc_29AC5
0x29ac2  ldc.i4.0
0x29ac3  br.s     loc_29AD9
0x29ac5  ldloc.s  7
0x29ac7  ldstr    aActdeliverymet// "actdeliverymethod"
0x29acc  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29ad1  unbox.any [mscorlib]System.Int32
0x29ad6  ldc.i4.1
0x29ad7  ceq
0x29ad9  stloc.s  0xC
0x29adb  ldloc.s  7
0x29add  ldstr    aIncomingemails// "incomingemailstatus"
0x29ae2  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29ae7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29aec  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x29af1  stloc.s  0xD
0x29af3  ldloc.s  7
0x29af5  ldstr    aOutgoingemails// "outgoingemailstatus"
0x29afa  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29aff  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b04  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x29b09  stloc.s  0xE
0x29b0b  ldloc.s  7
0x29b0d  ldstr    aActstatus// "actstatus"
0x29b12  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x29b1c  call     bool [mscorlib]System.Convert::ToBoolean(object, class [mscorlib]System.IFormatProvider)
0x29b21  stloc.s  0xF
0x29b23  ldloc.s  7
0x29b25  ldstr    aEnabledforinco// "enabledforincomingemail"
0x29b2a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b2f  brtrue.s loc_29B34
0x29b31  ldc.i4.0
0x29b32  br.s     loc_29B45
0x29b34  ldloc.s  7
0x29b36  ldstr    aEnabledforinco// "enabledforincomingemail"
0x29b3b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b40  unbox.any [mscorlib]System.Boolean
0x29b45  stloc.s  0x10
0x29b47  ldloc.s  7
0x29b49  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x29b4e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b53  brtrue.s loc_29B58
0x29b55  ldc.i4.0
0x29b56  br.s     loc_29B69
0x29b58  ldloc.s  7
0x29b5a  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x29b5f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b64  unbox.any [mscorlib]System.Boolean
0x29b69  stloc.s  0x11
0x29b6b  ldloc.s  7
0x29b6d  ldstr    aEnabledforact// "enabledforact"
0x29b72  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b77  brtrue.s loc_29B7C
0x29b79  ldc.i4.0
0x29b7a  br.s     loc_29B8D
0x29b7c  ldloc.s  7
0x29b7e  ldstr    aEnabledforact// "enabledforact"
0x29b83  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b88  unbox.any [mscorlib]System.Boolean
0x29b8d  stloc.s  0x12
0x29b8f  ldloc.s  7
0x29b91  ldstr    aTransientfailu// "transientfailurecount"
0x29b96  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29b9b  brtrue.s loc_29BA0
0x29b9d  ldc.i4.0
0x29b9e  br.s     loc_29BB1
0x29ba0  ldloc.s  7
0x29ba2  ldstr    aTransientfailu// "transientfailurecount"
0x29ba7  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x29bac  unbox.any [mscorlib]System.Int32
0x29bb1  dup
0x29bb2  ldc.i4   0xF00000
0x29bb7  and
0x29bb8  ldc.i4.s 0x14
0x29bba  shr
0x29bbb  stloc.s  0x13
0x29bbd  dup
0x29bbe  ldc.i4   0xF000000
0x29bc3  and
0x29bc4  ldc.i4.s 0x18
0x29bc6  shr
0x29bc7  stloc.s  0x14
0x29bc9  ldc.i4   0xF0000
0x29bce  and
0x29bcf  ldc.i4.s 0x10
0x29bd1  shr
0x29bd2  stloc.s  0x15
0x29bd4  ldarg.0
0x29bd5  ldloc.s  0x13
0x29bd7  call     instance int32 Microsoft.Crm.Web.MailboxDashboard::InspectTransientFailureCount(int32 tranientFailureCount)
0x29bdc  stloc.s  0x16
0x29bde  ldarg.0
0x29bdf  ldloc.s  0x14
0x29be1  call     instance int32 Microsoft.Crm.Web.MailboxDashboard::InspectTransientFailureCount(int32 tranientFailureCount)
0x29be6  stloc.s  0x17
0x29be8  ldarg.0
0x29be9  ldloc.s  0x15
0x29beb  call     instance int32 Microsoft.Crm.Web.MailboxDashboard::InspectTransientFailureCount(int32 tranientFailureCount)
0x29bf0  stloc.s  0x18
0x29bf2  ldloc.s  0xA
0x29bf4  ldloc.s  0x10
0x29bf6  and
0x29bf7  ldloc.s  0xD
0x29bf9  and
0x29bfa  brfalse.s loc_29C00
0x29bfc  ldloc.s  0x16
0x29bfe  brfalse.s loc_29C04
0x29c00  ldloc.s  0xA
0x29c02  brtrue.s loc_29C3F
0x29c04  ldloc.s  0xB
0x29c06  ldloc.s  0x11
0x29c08  and
0x29c09  ldloc.s  0xE
0x29c0b  and
0x29c0c  brfalse.s loc_29C12
0x29c0e  ldloc.s  0x17
0x29c10  brfalse.s loc_29C16
0x29c12  ldloc.s  0xB
0x29c14  brtrue.s loc_29C3F
0x29c16  ldloc.s  0xC
  ... truncated ...
```
