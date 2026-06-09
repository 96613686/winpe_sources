# Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxColumnSet

- ea: `0x1c3e0`
- end: `0x1c520`
- name: `Microsoft.Crm.Dialogs.CreateMailboxOneClickLogPage::GetMailboxColumnSet`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1c1e0`

## string_xrefs

- `0x1c3ff`: `processinglastattemptedon`
- `0x1c413`: `incomingemaildeliverymethod`
- `0x1c44b`: `enabledforincomingemail`
- `0x1c4b7`: `testemailconfigurationscheduled`
- `0x1c4bf`: `testemailconfigurationretrycount`
- `0x1c4c7`: `testmailboxaccesscompletedon`
- `0x1c4cf`: `postponetestemailconfigurationuntil`
- `0x1c4e3`: `lastsuccessfulsynccompletedon`

## pseudocode

```c

```

## disassembly

```asm
0x1c3e0  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSet::.ctor()
0x1c3e5  stloc.0
0x1c3e6  ldloc.0
0x1c3e7  ldc.i4.3
0x1c3e8  newarr   [mscorlib]System.String
0x1c3ed  dup
0x1c3ee  ldc.i4.0
0x1c3ef  ldstr    aHostid// "hostid"
0x1c3f4  stelem.ref
0x1c3f5  dup
0x1c3f6  ldc.i4.1
0x1c3f7  ldstr    aProcessingstat// "processingstatecode"
0x1c3fc  stelem.ref
0x1c3fd  dup
0x1c3fe  ldc.i4.2
0x1c3ff  ldstr    aProcessinglast// "processinglastattemptedon"
0x1c404  stelem.ref
0x1c405  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c40a  ldloc.0
0x1c40b  ldc.i4.3
0x1c40c  newarr   [mscorlib]System.String
0x1c411  dup
0x1c412  ldc.i4.0
0x1c413  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x1c418  stelem.ref
0x1c419  dup
0x1c41a  ldc.i4.1
0x1c41b  ldstr    aOutgoingemaild// "outgoingemaildeliverymethod"
0x1c420  stelem.ref
0x1c421  dup
0x1c422  ldc.i4.2
0x1c423  ldstr    aActdeliverymet// "actdeliverymethod"
0x1c428  stelem.ref
0x1c429  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c42e  ldloc.0
0x1c42f  ldc.i4.1
0x1c430  newarr   [mscorlib]System.String
0x1c435  dup
0x1c436  ldc.i4.0
0x1c437  ldstr    aName// "name"
0x1c43c  stelem.ref
0x1c43d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c442  ldloc.0
0x1c443  ldc.i4.3
0x1c444  newarr   [mscorlib]System.String
0x1c449  dup
0x1c44a  ldc.i4.0
0x1c44b  ldstr    aEnabledforinco// "enabledforincomingemail"
0x1c450  stelem.ref
0x1c451  dup
0x1c452  ldc.i4.1
0x1c453  ldstr    aEnabledforoutg// "enabledforoutgoingemail"
0x1c458  stelem.ref
0x1c459  dup
0x1c45a  ldc.i4.2
0x1c45b  ldstr    aEnabledforact// "enabledforact"
0x1c460  stelem.ref
0x1c461  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c466  ldloc.0
0x1c467  ldc.i4.2
0x1c468  newarr   [mscorlib]System.String
0x1c46d  dup
0x1c46e  ldc.i4.0
0x1c46f  ldstr    aNoactcount// "noactcount"
0x1c474  stelem.ref
0x1c475  dup
0x1c476  ldc.i4.1
0x1c477  ldstr    aNoemailcount// "noemailcount"
0x1c47c  stelem.ref
0x1c47d  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c482  ldloc.0
0x1c483  ldc.i4.4
0x1c484  newarr   [mscorlib]System.String
0x1c489  dup
0x1c48a  ldc.i4.0
0x1c48b  ldstr    aPostponemailbo// "postponemailboxprocessinguntil"
0x1c490  stelem.ref
0x1c491  dup
0x1c492  ldc.i4.1
0x1c493  ldstr    aPostponesendin// "postponesendinguntil"
0x1c498  stelem.ref
0x1c499  dup
0x1c49a  ldc.i4.2
0x1c49b  ldstr    aReceivingpostp// "receivingpostponeduntil"
0x1c4a0  stelem.ref
0x1c4a1  dup
0x1c4a2  ldc.i4.3
0x1c4a3  ldstr    aReceivingpostp_0// "receivingpostponeduntilforact"
0x1c4a8  stelem.ref
0x1c4a9  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c4ae  ldloc.0
0x1c4af  ldc.i4.4
0x1c4b0  newarr   [mscorlib]System.String
0x1c4b5  dup
0x1c4b6  ldc.i4.0
0x1c4b7  ldstr    aTestemailconfi// "testemailconfigurationscheduled"
0x1c4bc  stelem.ref
0x1c4bd  dup
0x1c4be  ldc.i4.1
0x1c4bf  ldstr    aTestemailconfi_0// "testemailconfigurationretrycount"
0x1c4c4  stelem.ref
0x1c4c5  dup
0x1c4c6  ldc.i4.2
0x1c4c7  ldstr    aTestmailboxacc// "testmailboxaccesscompletedon"
0x1c4cc  stelem.ref
0x1c4cd  dup
0x1c4ce  ldc.i4.3
0x1c4cf  ldstr    aPostponetestem// "postponetestemailconfigurationuntil"
0x1c4d4  stelem.ref
0x1c4d5  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c4da  ldloc.0
0x1c4db  ldc.i4.7
0x1c4dc  newarr   [mscorlib]System.String
0x1c4e1  dup
0x1c4e2  ldc.i4.0
0x1c4e3  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x1c4e8  stelem.ref
0x1c4e9  dup
0x1c4ea  ldc.i4.1
0x1c4eb  ldstr    aLastsyncerror// "lastsyncerror"
0x1c4f0  stelem.ref
0x1c4f1  dup
0x1c4f2  ldc.i4.2
0x1c4f3  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x1c4f8  stelem.ref
0x1c4f9  dup
0x1c4fa  ldc.i4.3
0x1c4fb  ldstr    aLastsyncerrorc_0// "lastsyncerrorcount"
0x1c500  stelem.ref
0x1c501  dup
0x1c502  ldc.i4.4
0x1c503  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x1c508  stelem.ref
0x1c509  dup
0x1c50a  ldc.i4.5
0x1c50b  ldstr    aItemsprocessed// "itemsprocessedforlastsync"
0x1c510  stelem.ref
0x1c511  dup
0x1c512  ldc.i4.6
0x1c513  ldstr    aItemsfailedfor// "itemsfailedforlastsync"
0x1c518  stelem.ref
0x1c519  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumns(string[])
0x1c51e  ldloc.0
0x1c51f  ret
```
