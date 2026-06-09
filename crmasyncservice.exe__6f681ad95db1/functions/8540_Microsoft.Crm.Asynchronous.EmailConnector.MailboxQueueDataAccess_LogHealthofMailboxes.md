# Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogHealthofMailboxes

- ea: `0x8540`
- end: `0x8831`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::LogHealthofMailboxes`
- size: `753`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x81e0`

## callees

- `0x4d20`
- `0x8540`
- `0x8840`
- `0xb340`

## string_xrefs

- `0x854d`: `SELECT MailboxId, LastSyncErrorCode, LastSyncErrorOccurredOn, LastSyncError, IncomingEmailDeliveryMethod, ACTDeliveryMethod, OutgoingEmailDeliveryMethod,\n									EnabledForACT, EnabledForIncomingEmail, EnabledForOutgoingEmail, ACTStatus, IncomingEmailStatus, OutgoingEmailStatus, LastSuccessfulSyncCompletedOn\n								FROM MailboxBase WITH (NOLOCK) \n								WHERE\n									ProcessingStateCode = @lockedState\n									OR\n									PostponeMailboxProcessingUntil < @maxDateTime\n								OR`

## pseudocode

```c

```

## disassembly

```asm
0x8540  newobj   instance void <>c__DisplayClass13_0::.ctor()
0x8545  stloc.0
0x8546  ldloc.0
0x8547  ldarg.0
0x8548  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess <>c__DisplayClass13_0::<>4__this
0x854d  ldstr    aSelectMailboxi_1// "SELECT MailboxId, LastSyncErrorCode, La"...
0x8552  stloc.1
0x8553  ldloc.0
0x8554  ldloc.1
0x8555  ldc.i4.1
0x8556  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x855b  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass13_0::selectSSSConfiguredMailboxesCommand
0x8560  ldloc.0
0x8561  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass13_0::selectSSSConfiguredMailboxesCommand
0x8566  ldstr    aMaxdatetime// "@maxDateTime"
0x856b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x8570  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x8575  stloc.2
0x8576  ldloca.s 2
0x8578  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0x857d  conv.r8
0x857e  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x8583  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x8588  box      [mscorlib]System.DateTime
0x858d  ldloca.s 3
0x858f  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x8595  ldloc.3
0x8596  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x859b  ldloc.0
0x859c  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo <>c__DisplayClass13_0::selectSSSConfiguredMailboxesCommand
0x85a1  ldstr    aLockedstate// "@lockedState"
0x85a6  ldc.i4.1
0x85a7  box      [mscorlib]System.Int32
0x85ac  ldloca.s 3
0x85ae  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x85b4  ldloc.3
0x85b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x85ba  ldloc.0
0x85bb  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x85c0  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x85c5  ldarg.0
0x85c6  ldfld    class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_operationsFactory
0x85cb  ldarg.0
0x85cc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueManager Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::_queueManager
0x85d1  callvirt instance string [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x85d6  ldstr    aReportevents_0// "_ReportEvents"
0x85db  call     string [mscorlib]System.String::Concat(string, string)
0x85e0  ldarg.0
0x85e1  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x85e6  ldloc.0
0x85e7  ldftn    instance void <>c__DisplayClass13_0::<LogHealthofMailboxes>b__0(class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation operation)
0x85ed  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction::.ctor(object, native int)
0x85f2  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperationsFactory::CreateOrganizationOperation(string, class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.ServiceOperationAction)
0x85f7  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.Operations.IServiceOperation::Execute()
0x85fc  ldloc.0
0x85fd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x8602  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x8607  ldc.i4.0
0x8608  ble      loc_87EA
0x860d  ldloc.0
0x860e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x8613  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x8618  stloc.s  4
0x861a  ldloc.0
0x861b  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x8620  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_2
0x8625  dup
0x8626  brtrue.s loc_863F
0x8628  pop
0x8629  ldsfld   class <>c <>c::<>9
0x862e  ldftn    instance bool <>c::<LogHealthofMailboxes>b__13_2(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x8634  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x8639  dup
0x863a  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_2
0x863f  call     T0x2B00001B
0x8644  call     T0x2B00001C
0x8649  dup
0x864a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x864f  stloc.s  5
0x8651  dup
0x8652  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_3
0x8657  dup
0x8658  brtrue.s loc_8671
0x865a  pop
0x865b  ldsfld   class <>c <>c::<>9
0x8660  ldftn    instance bool <>c::<LogHealthofMailboxes>b__13_3(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x8666  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x866b  dup
0x866c  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_3
0x8671  call     T0x2B00001B
0x8676  call     T0x2B00001C
0x867b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x8680  stloc.s  6
0x8682  dup
0x8683  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_4
0x8688  dup
0x8689  brtrue.s loc_86A2
0x868b  pop
0x868c  ldsfld   class <>c <>c::<>9
0x8691  ldftn    instance bool <>c::<LogHealthofMailboxes>b__13_4(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x8697  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x869c  dup
0x869d  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_4
0x86a2  call     T0x2B00001B
0x86a7  call     T0x2B00001C
0x86ac  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x86b1  stloc.s  7
0x86b3  dup
0x86b4  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_5
0x86b9  dup
0x86ba  brtrue.s loc_86D3
0x86bc  pop
0x86bd  ldsfld   class <>c <>c::<>9
0x86c2  ldftn    instance bool <>c::<LogHealthofMailboxes>b__13_5(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x86c8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x86cd  dup
0x86ce  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_5
0x86d3  call     T0x2B00001B
0x86d8  call     T0x2B00001C
0x86dd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x86e2  stloc.s  8
0x86e4  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_6
0x86e9  dup
0x86ea  brtrue.s loc_8703
0x86ec  pop
0x86ed  ldsfld   class <>c <>c::<>9
0x86f2  ldftn    instance bool <>c::<LogHealthofMailboxes>b__13_6(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox)
0x86f8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x86fd  dup
0x86fe  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool> <>c::<>9__13_6
0x8703  call     T0x2B00001B
0x8708  call     T0x2B00001C
0x870d  stloc.s  9
0x870f  ldc.i4.0
0x8710  stloc.s  0xA
0x8712  ldc.i4.0
0x8713  stloc.s  0xB
0x8715  ldc.i4.0
0x8716  stloc.s  0xC
0x8718  ldloc.s  9
0x871a  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x871f  ldc.i4.0
0x8720  ble.s    loc_8730
0x8722  ldarg.0
0x8723  ldloc.s  9
0x8725  ldloca.s 0xA
0x8727  ldloca.s 0xB
0x8729  ldloca.s 0xC
0x872b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::SegregateErrors(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> mailboxesInError, [out] int32& totalSSSRelatedErrors, [out] int32& totalExchangeRelatedErrors, [out] int32& totalConfigurationRelatedErrors)
0x8730  ldloc.s  9
0x8732  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x8737  stloc.s  0xD
0x8739  ldloc.0
0x873a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x873f  ldc.i4.0
0x8740  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x8745  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x874a  ldstr    aLastsyncerroro// "lastsyncerroroccurredon"
0x874f  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8754  unbox.any [mscorlib]System.DateTime
0x8759  stloc.s  0xE
0x875b  ldloc.0
0x875c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x8761  ldc.i4.0
0x8762  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x8767  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x876c  ldstr    aLastsyncerrorc// "lastsyncerrorcode"
0x8771  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8776  unbox.any [mscorlib]System.Int32
0x877b  stloc.s  0xF
0x877d  ldloc.0
0x877e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> <>c__DisplayClass13_0::sssConfiguredMailBoxes
0x8783  ldc.i4.0
0x8784  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x8789  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x878e  ldstr    aLastsyncerror// "lastsyncerror"
0x8793  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x8798  castclass [mscorlib]System.String
0x879d  stloc.s  0x10
0x879f  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x87a4  ldarg.0
0x87a5  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x87aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x87af  ldloc.s  4
0x87b1  ldloc.s  5
0x87b3  ldloc.s  6
0x87b5  ldloc.s  7
0x87b7  ldloc.s  8
0x87b9  ldloc.s  0xD
0x87bb  ldloc.s  0xA
0x87bd  ldloc.s  0xB
0x87bf  ldloc.s  0xC
0x87c1  ldloc.s  0xE
0x87c3  ldloc.s  0xF
0x87c5  ldloc.s  0x10
0x87c7  ldarg.0
0x87c8  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationState
0x87cd  ldarg.0
0x87ce  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationType
0x87d3  ldarg.0
0x87d4  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::versionNumber
0x87d9  ldarg.0
0x87da  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x87df  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x87e4  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogHealthofMailboxes(valuetype [mscorlib]System.Guid, int32, int32, int32, int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTime, int32, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType, string, int32)
0x87e9  ret
0x87ea  call     class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::get_Instance()
0x87ef  ldarg.0
0x87f0  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x87f5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x87fa  ldc.i4.0
0x87fb  ldc.i4.0
0x87fc  ldc.i4.0
0x87fd  ldc.i4.0
0x87fe  ldc.i4.0
0x87ff  ldc.i4.0
0x8800  ldc.i4.0
0x8801  ldc.i4.0
0x8802  ldc.i4.0
0x8803  ldsfld   valuetype [mscorlib]System.DateTime [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::DefaultDateTimeValue
0x8808  ldc.i4.0
0x8809  ldsfld   string [mscorlib]System.String::Empty
0x880e  ldarg.0
0x880f  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationState
0x8814  ldarg.0
0x8815  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::organizationType
0x881a  ldarg.0
0x881b  ldfld    string Microsoft.Crm.Asynchronous.EmailConnector.MailboxQueueDataAccess::versionNumber
0x8820  ldarg.0
0x8821  call     instance class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::get_Configuration()
0x8826  call     valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailConnectionChannelType Microsoft.Crm.Asynchronous.OrgServerSideSyncSettings::GetEmailConnectionChannel(class [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration orgConfiguration)
0x882b  callvirt instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncServiceTelemetryLogger::LogHealthofMailboxes(valuetype [mscorlib]System.Guid, int32, int32, int32, int32, int32, int32, int32, int32, int32, valuetype [mscorlib]System.DateTime, int32, string, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationState, valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType, string, int32)
0x8830  ret
```
