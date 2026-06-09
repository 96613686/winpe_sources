# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::ReportEvents

- ea: `0x81e0`
- end: `0x82d7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::ReportEvents`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0xbb20`

## callees

- `0x4d20`
- `0x4e40`
- `0x81e0`
- `0x82e0`
- `0x8490`
- `0x8540`

## string_xrefs

- `0x8200`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\MailboxQueue\MailboxQueueDataAccess.cs`
- `0x8234`: `d:\dbs\sh\dccm2\1101_190851\cmd\34\src\Core\ObjectModel\Async\AsyncService\MailboxQueue\MailboxQueueDataAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0x81e0  ldarg.0
0x81e1  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x81e6  ldarg.0
0x81e7  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x81ec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x81f1  ldstr    aType// "Type"
0x81f6  ldc.i4   0xB3
0x81fb  ldstr    aReportevents// "ReportEvents"
0x8200  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x8205  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x820a  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType
0x820f  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationType
0x8214  ldarg.0
0x8215  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x821a  ldarg.0
0x821b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8220  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8225  ldstr    aState// "State"
0x822a  ldc.i4   0xB4
0x822f  ldstr    aReportevents// "ReportEvents"
0x8234  ldstr    aDDbsShDccm2110_3// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\3"...
0x8239  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x823e  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState
0x8243  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationState
0x8248  ldarg.0
0x8249  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x824e  call     bool Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::IsMailboxQueueEnabled(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x8253  brtrue.s loc_829C
0x8255  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x825a  ldarg.0
0x825b  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8260  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x8265  ldc.i4.0
0x8266  ldc.i4.0
0x8267  ldc.i4.0
0x8268  ldc.i4.0
0x8269  ldc.i4.0
0x826a  ldc.i4.0
0x826b  ldc.i4.0
0x826c  ldc.i4.0
0x826d  ldc.i4.0
0x826e  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::DefaultDateTimeValue
0x8273  ldc.i4.0
0x8274  ldsfld   string [mscorlib]System.String::Empty
0x8279  ldarg.0
0x827a  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationState
0x827f  ldarg.0
0x8280  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationType
0x8285  ldarg.0
0x8286  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::versionNumber
0x828b  ldarg.0
0x828c  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8291  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x8296  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogHealthofMailboxes(valuetype [mscorlib]System.Guid, int32, int32, int32, int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTime, int32, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType, string, int32)
0x829b  ret
0x829c  nop
0x829d  ldarg.0
0x829e  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogLongProcessingMailboxes()
0x82a3  ldarg.0
0x82a4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogUnpickedMailboxes()
0x82a9  ldarg.0
0x82aa  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogHealthofMailboxes()
0x82af  leave.s  loc_82D6
0x82b1  stloc.0
0x82b2  ldloc.0
0x82b3  ldarg.0
0x82b4  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x82b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x82be  ldc.i4.s 0x3D
0x82c0  ldstr    aExceptionWhile_11// "Exception while trying to report teleme"...
0x82c5  ldc.i4.1
0x82c6  newarr   [mscorlib]System.Object
0x82cb  dup
0x82cc  ldc.i4.0
0x82cd  ldloc.0
0x82ce  stelem.ref
0x82cf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x82d4  leave.s  loc_82D6
0x82d6  ret
```
