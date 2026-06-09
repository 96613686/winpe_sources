# Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetLogInformation

- ea: `0x1c680`
- end: `0x1cb1f`
- name: `Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetLogInformation`
- size: `1183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1c1e0`

## callees

- `0x1c680`
- `0x1cc00`
- `0x1cd30`

## string_xrefs

- `0x1c70b`: `processinglastattemptedon`
- `0x1c736`: `incomingemaildeliverymethod`
- `0x1c791`: `enabledforincomingemail`
- `0x1c8a2`: `testemailconfigurationscheduled`
- `0x1c8ba`: `testemailconfigurationretrycount`
- `0x1c8d2`: `testmailboxaccesscompletedon`
- `0x1c8ea`: `postponetestemailconfigurationuntil`
- `0x1c915`: `lastsuccessfulsynccompletedon`
- `0x1ca47`: `incomingauthenticationprotocol`
- `0x1ca5a`: `incomingcredentialretrieval`
- `0x1ca6d`: `incominguseimpersonation`
- `0x1ca80`: `incomingusessl`
- `0x1ca93`: `incomingportnumber`
- `0x1cab9`: `outgoingauthenticationprotocol`
- `0x1cadf`: `outgoinguseimpersonation`
- `0x1c68f`: `Your mailbox is not configured correctly for Server Side Sync.`
- `0x1c729`: `Mailbox Synchronization Methods (2 is server-side sync or email router, 1 is Outlook sync, 0 is none)`
- `0x1c7df`: `Mailbox Idle State (shows how many times the mailbox was processed with no email items or Appointments, Contacts and Tasks to synchronize)`
- `0x1c822`: `Mailbox Backoff Parameters (shows when the mailbox is scheduled to process next time)`
- `0x1ca3a`: `Email Server Profile Incoming Email Settings`

## pseudocode

```c

```

## disassembly

```asm
0x1c680  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1c685  stloc.0
0x1c686  ldarg.1
0x1c687  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x1c68c  brtrue.s loc_1C69C
0x1c68e  ldloc.0
0x1c68f  ldstr    aYourMailboxIsN// "Your mailbox is not configured correctl"...
0x1c694  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c699  pop
0x1c69a  ldloc.0
0x1c69b  ret
0x1c69c  ldarg.1
0x1c69d  ldc.i4.0
0x1c69e  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0x1c6a3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_InnerEntity()
0x1c6a8  stloc.1
0x1c6a9  ldloc.0
0x1c6aa  ldstr    aMailboxAsyncPr// "Mailbox Async Processing State"
0x1c6af  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c6b4  pop
0x1c6b5  ldloc.0
0x1c6b6  ldarg.0
0x1c6b7  ldstr    aMailboxid// "mailboxid"
0x1c6bc  ldloc.1
0x1c6bd  ldarg.0
0x1c6be  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::mailboxId
0x1c6c3  constrained. [mscorlib]System.Guid
0x1c6c9  callvirt instance string [mscorlib]System.Object::ToString()
0x1c6ce  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c6d3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c6d8  pop
0x1c6d9  ldloc.0
0x1c6da  ldarg.0
0x1c6db  ldstr    aHostid// "hostid"
0x1c6e0  ldloc.1
0x1c6e1  ldstr    asc_11EF2A// ""
0x1c6e6  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c6eb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c6f0  pop
0x1c6f1  ldloc.0
0x1c6f2  ldarg.0
0x1c6f3  ldstr    aProcessingstat// "processingstatecode"
0x1c6f8  ldloc.1
0x1c6f9  ldstr    asc_11EF2A// ""
0x1c6fe  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c703  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c708  pop
0x1c709  ldloc.0
0x1c70a  ldarg.0
0x1c70b  ldstr    aProcessinglast// "processinglastattemptedon"
0x1c710  ldloc.1
0x1c711  ldstr    asc_11EF2A// ""
0x1c716  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c71b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c720  pop
0x1c721  ldloc.0
0x1c722  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c727  pop
0x1c728  ldloc.0
0x1c729  ldstr    aMailboxSynchro// "Mailbox Synchronization Methods (2 is s"...
0x1c72e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c733  pop
0x1c734  ldloc.0
0x1c735  ldarg.0
0x1c736  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1c73b  ldloc.1
0x1c73c  ldstr    asc_11EF2A// ""
0x1c741  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c746  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c74b  pop
0x1c74c  ldloc.0
0x1c74d  ldarg.0
0x1c74e  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1c753  ldloc.1
0x1c754  ldstr    asc_11EF2A// ""
0x1c759  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c75e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c763  pop
0x1c764  ldloc.0
0x1c765  ldarg.0
0x1c766  ldstr    aActdeliverymet// "actdeliverymethod"
0x1c76b  ldloc.1
0x1c76c  ldstr    asc_11EF2A// ""
0x1c771  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c776  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c77b  pop
0x1c77c  ldloc.0
0x1c77d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c782  pop
0x1c783  ldloc.0
0x1c784  ldstr    aMailboxEnabled// "Mailbox Enabled State"
0x1c789  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c78e  pop
0x1c78f  ldloc.0
0x1c790  ldarg.0
0x1c791  ldstr    aEnabledforinco// "enabledforincomingemail"
0x1c796  ldloc.1
0x1c797  ldstr    asc_11EF2A// ""
0x1c79c  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c7a1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c7a6  pop
0x1c7a7  ldloc.0
0x1c7a8  ldarg.0
0x1c7a9  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1c7ae  ldloc.1
0x1c7af  ldstr    asc_11EF2A// ""
0x1c7b4  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c7b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c7be  pop
0x1c7bf  ldloc.0
0x1c7c0  ldarg.0
0x1c7c1  ldstr    aEnabledforact// "enabledforact"
0x1c7c6  ldloc.1
0x1c7c7  ldstr    asc_11EF2A// ""
0x1c7cc  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c7d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c7d6  pop
0x1c7d7  ldloc.0
0x1c7d8  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c7dd  pop
0x1c7de  ldloc.0
0x1c7df  ldstr    aMailboxIdleSta// "Mailbox Idle State (shows how many time"...
0x1c7e4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c7e9  pop
0x1c7ea  ldloc.0
0x1c7eb  ldarg.0
0x1c7ec  ldstr    aNoemailcount// "noemailcount"
0x1c7f1  ldloc.1
0x1c7f2  ldstr    asc_11EF2A// ""
0x1c7f7  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c7fc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c801  pop
0x1c802  ldloc.0
0x1c803  ldarg.0
0x1c804  ldstr    aNoactcount// "noactcount"
0x1c809  ldloc.1
0x1c80a  ldstr    asc_11EF2A// ""
0x1c80f  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c814  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c819  pop
0x1c81a  ldloc.0
0x1c81b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c820  pop
0x1c821  ldloc.0
0x1c822  ldstr    aMailboxBackoff// "Mailbox Backoff Parameters (shows when "...
0x1c827  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c82c  pop
0x1c82d  ldloc.0
0x1c82e  ldarg.0
0x1c82f  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x1c834  ldloc.1
0x1c835  ldstr    asc_11EF2A// ""
0x1c83a  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c83f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c844  pop
0x1c845  ldloc.0
0x1c846  ldarg.0
0x1c847  ldstr    aPostponesendin// "postponesendinguntil"
0x1c84c  ldloc.1
0x1c84d  ldstr    asc_11EF2A// ""
0x1c852  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c857  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c85c  pop
0x1c85d  ldloc.0
0x1c85e  ldarg.0
0x1c85f  ldstr    aReceivingpostp// "receivingpostponeduntil"
0x1c864  ldloc.1
0x1c865  ldstr    asc_11EF2A// ""
0x1c86a  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c86f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c874  pop
0x1c875  ldloc.0
0x1c876  ldarg.0
0x1c877  ldstr    aReceivingpostp_0// "receivingpostponeduntilforact"
0x1c87c  ldloc.1
0x1c87d  ldstr    asc_11EF2A// ""
0x1c882  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c887  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c88c  pop
0x1c88d  ldloc.0
0x1c88e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c893  pop
0x1c894  ldloc.0
0x1c895  ldstr    aMailboxTestAnd// "Mailbox Test and Enable Parameters"
0x1c89a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c89f  pop
0x1c8a0  ldloc.0
0x1c8a1  ldarg.0
0x1c8a2  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x1c8a7  ldloc.1
0x1c8a8  ldstr    asc_11EF2A// ""
0x1c8ad  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c8b2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c8b7  pop
0x1c8b8  ldloc.0
0x1c8b9  ldarg.0
0x1c8ba  ldstr    aTestemailconfi_0// "testemailconfigurationretrycount"
0x1c8bf  ldloc.1
0x1c8c0  ldstr    asc_11EF2A// ""
0x1c8c5  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c8ca  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c8cf  pop
0x1c8d0  ldloc.0
0x1c8d1  ldarg.0
0x1c8d2  ldstr    aTestmailboxacc// "testmailboxaccesscompletedon"
0x1c8d7  ldloc.1
0x1c8d8  ldstr    asc_11EF2A// ""
0x1c8dd  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c8e2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c8e7  pop
0x1c8e8  ldloc.0
0x1c8e9  ldarg.0
0x1c8ea  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x1c8ef  ldloc.1
0x1c8f0  ldstr    asc_11EF2A// ""
0x1c8f5  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c8fa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c8ff  pop
0x1c900  ldloc.0
0x1c901  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c906  pop
0x1c907  ldloc.0
0x1c908  ldstr    aMailboxLastSyn// "Mailbox Last Sync Cycle Information"
0x1c90d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c912  pop
0x1c913  ldloc.0
0x1c914  ldarg.0
0x1c915  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x1c91a  ldloc.1
0x1c91b  ldstr    asc_11EF2A// ""
0x1c920  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c925  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c92a  pop
0x1c92b  ldloc.0
0x1c92c  ldarg.0
0x1c92d  ldstr    aLastsyncerror// "lastsyncerror"
0x1c932  ldloc.1
0x1c933  ldstr    asc_11EF2A// ""
0x1c938  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c93d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c942  pop
0x1c943  ldloc.0
0x1c944  ldarg.0
0x1c945  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x1c94a  ldloc.1
0x1c94b  ldstr    asc_11EF2A// ""
0x1c950  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c955  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c95a  pop
0x1c95b  ldloc.0
0x1c95c  ldarg.0
0x1c95d  ldstr    aLastsyncerrorc_0// "lastsyncerrorcount"
0x1c962  ldloc.1
0x1c963  ldstr    asc_11EF2A// ""
0x1c968  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c96d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c972  pop
0x1c973  ldloc.0
0x1c974  ldarg.0
0x1c975  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x1c97a  ldloc.1
0x1c97b  ldstr    asc_11EF2A// ""
0x1c980  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c985  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c98a  pop
0x1c98b  ldloc.0
0x1c98c  ldarg.0
0x1c98d  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x1c992  ldloc.1
0x1c993  ldstr    asc_11EF2A// ""
0x1c998  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c99d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c9a2  pop
0x1c9a3  ldloc.0
0x1c9a4  ldarg.0
0x1c9a5  ldstr    aItemsfailedfor// "itemsfailedforlastsync"
0x1c9aa  ldloc.1
0x1c9ab  ldstr    asc_11EF2A// ""
0x1c9b0  call     instance string Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxLogLine(string key, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity entity, [opt] string value)
0x1c9b5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c9ba  pop
0x1c9bb  ldloc.0
0x1c9bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c9c1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c9c6  pop
0x1c9c7  ldloc.0
0x1c9c8  ldstr    aEmailServerPro// "Email Server Profile Details"
0x1c9cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c9d2  pop
0x1c9d3  ldloc.0
0x1c9d4  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine()
0x1c9d9  pop
0x1c9da  ldloc.0
0x1c9db  ldstr    aEmailServerPro_0// "Email Server Profile General Settings ("...
0x1c9e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1c9e5  pop
0x1c9e6  ldloc.0
0x1c9e7  ldarg.0
0x1c9e8  ldstr    aServertype// "servertype"
0x1c9ed  ldloc.1
  ... truncated ...
```
