# Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::SelectOutgoingActivities

- ea: `0x7520`
- end: `0x7688`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::SelectOutgoingActivities`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7490`

## callees

- `0x4d20`
- `0x7520`
- `0x7b90`
- `0xaf90`

## string_xrefs

- `0x7558`: `UPDATE ActivityPointerBase\n		SET\n			DeliveryAttempts = COALESCE(DeliveryAttempts, 0) + 1, \n			DeliveryLastAttemptedOn = @dateTimeNow,\n			PostponeActivityProcessingUntil = @sendingDelayAllowed\n		OUTPUT\n			INSERTED.ActivityId,\n			INSERTED.ActivityTypeCode,\n			INSERTED.Subject,\n			INSERTED.Description,\n			INSERTED.PriorityCode,\n			INSERTED.EmailAttachmentCount,\n			INSERTED.SenderMailboxId,\n			INSERTED.DeliveryAttempts,\n			INSERTED.ConversationIndex,\n			INSERTED.Message`

## pseudocode

```c

```

## disassembly

```asm
0x7520  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x7525  stloc.0
0x7526  ldloc.0
0x7527  ldarg.0
0x7528  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess <>c__DisplayClass2_0::<>4__this
0x752d  ldarg.1
0x752e  ldarg.0
0x752f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x7534  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x7539  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_MaximumActivitiesPerSelect()
0x753e  ble.s    loc_7552
0x7540  ldarg.0
0x7541  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x7546  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x754b  callvirt instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_MaximumActivitiesPerSelect()
0x7550  starg.s  1
0x7552  ldarg.0
0x7553  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7558  ldstr    aUpdateActivity// "UPDATE ActivityPointerBase\r\n\t\tSET\r"...
0x755d  ldc.i4.3
0x755e  newarr   [mscorlib]System.Object
0x7563  dup
0x7564  ldc.i4.0
0x7565  ldc.i4   0x106A
0x756a  box      [mscorlib]System.Int32
0x756f  stelem.ref
0x7570  dup
0x7571  ldc.i4.1
0x7572  ldc.i4.1
0x7573  box      [mscorlib]System.Int32
0x7578  stelem.ref
0x7579  dup
0x757a  ldc.i4.2
0x757b  ldc.i4.0
0x757c  box      [mscorlib]System.Int32
0x7581  stelem.ref
0x7582  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x7587  call     instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::QueryWithLowDeadlockPriority(string)
0x758c  stloc.1
0x758d  ldloc.0
0x758e  ldloc.1
0x758f  ldc.i4.1
0x7590  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x7595  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x759a  ldloc.0
0x759b  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x75a0  ldstr    aRecordstoselec// "@recordsToSelect"
0x75a5  ldarg.1
0x75a6  box      [mscorlib]System.Int32
0x75ab  ldloca.s 2
0x75ad  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x75b3  ldloc.2
0x75b4  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x75b9  ldloc.0
0x75ba  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x75bf  ldstr    aDatetimenow// "@dateTimeNow"
0x75c4  ldarg.0
0x75c5  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x75ca  box      [mscorlib]System.DateTime
0x75cf  ldloca.s 2
0x75d1  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x75d7  ldloc.2
0x75d8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x75dd  ldloc.0
0x75de  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x75e3  ldstr    aEmailconnectio// "@emailConnectionChannel"
0x75e8  ldarg.0
0x75e9  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x75ee  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x75f3  box      [mscorlib]System.Int32
0x75f8  ldloca.s 2
0x75fa  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x7600  ldloc.2
0x7601  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x7606  ldloc.0
0x7607  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass2_0::selectCommand
0x760c  ldstr    aSendingdelayal// "@sendingDelayAllowed"
0x7611  ldarg.0
0x7612  call     instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::GetUTCDateWithoutMilliseconds()
0x7617  ldarg.0
0x7618  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x761d  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager::get_FullConfiguration()
0x7622  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IActivityQueueConfiguration::get_SendingEmailsRetryInterval()
0x7627  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x762c  box      [mscorlib]System.DateTime
0x7631  ldloca.s 2
0x7633  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x7639  ldloc.2
0x763a  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x763f  ldloc.0
0x7640  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper>::.ctor()
0x7645  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper> <>c__DisplayClass2_0::activities
0x764a  ldarg.0
0x764b  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_operationsFactory
0x7650  ldarg.0
0x7651  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueManager Microsoft.Crm.Asynchronous.EmailConnector.ActivityQueueDataAccess::_queueManager
0x7656  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x765b  ldstr    aSelectevents// "_SelectEvents"
0x7660  call     string [mscorlib]System.String::Concat(string, string)
0x7665  ldarg.0
0x7666  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x766b  ldloc.0
0x766c  ldftn    instance void <>c__DisplayClass2_0::<SelectOutgoingActivities>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x7672  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x7677  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x767c  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x7681  ldloc.0
0x7682  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.ActivityEntityWrapper> <>c__DisplayClass2_0::activities
0x7687  ret
```
