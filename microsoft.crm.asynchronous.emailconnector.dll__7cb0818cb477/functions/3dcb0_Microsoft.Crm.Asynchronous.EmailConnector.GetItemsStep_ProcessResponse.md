# Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessResponse

- ea: `0x3dcb0`
- end: `0x3e38d`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessResponse`
- size: `1757`
- prototype: ``
- caller_count: `1`
- callee_count: `82`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3dcb0`

## callees

- `0xabc0`
- `0xb950`
- `0x13fd0`
- `0x13ff0`
- `0x14070`
- `0x14090`
- `0x17d90`
- `0x18200`
- `0x18260`
- `0x18300`
- `0x18320`
- `0x18760`
- `0x18770`
- `0x23760`
- `0x242d0`
- `0x25060`
- `0x25110`
- `0x30600`
- `0x30620`
- `0x30640`
- `0x30660`
- `0x32960`
- `0x32970`
- `0x32980`
- `0x329a0`
- `0x329c0`
- `0x32a00`
- `0x32a20`
- `0x3a170`
- `0x3ab40`
- `0x3ab80`
- `0x3ae70`
- `0x3aed0`
- `0x3dcb0`
- `0x3e390`
- `0x3e6e0`
- `0x3f050`
- `0x3f3e0`
- `0x40cc0`
- `0x417a0`
- `0x417f0`
- `0x41850`
- `0x41ab0`
- `0x41ac0`
- `0x41ad0`
- `0x41b80`
- `0x41ba0`
- `0x41bd0`
- `0x41d40`
- `0x41d60`

## string_xrefs

- `0x3e251`: `Server-Side Synchronization (Incoming): Items Failed`
- `0x3e25b`: `Server-Side Synchronization (Incoming): Items Failed Throughput`
- `0x3dd59`: `Server-Side Synchronization (Incoming): Emails Processed`
- `0x3dd63`: `Server-Side Synchronization (Incoming): Items Processed Throughput`

## pseudocode

```c

```

## disassembly

```asm
0x3dcb0  ldarg.0
0x3dcb1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dcb6  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_RetreiveEmailIndex()
0x3dcbb  stloc.0
0x3dcbc  ldarg.0
0x3dcbd  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dcc2  dup
0x3dcc3  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_RetreiveEmailIndex()
0x3dcc8  ldarg.0
0x3dcc9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dcce  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_RetreiveBatchSize()
0x3dcd3  add
0x3dcd4  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_RetreiveEmailIndex(int32 value)
0x3dcd9  ldarg.0
0x3dcda  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dcdf  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_RetreiveEmailIndex()
0x3dce4  ldarg.0
0x3dce5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dcea  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_RetreiveBatchSize()
0x3dcef  div
0x3dcf0  call     int16 [mscorlib]System.Convert::ToInt16(int32)
0x3dcf5  stloc.1
0x3dcf6  ldarg.0
0x3dcf7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.GetItemResponseType Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::response
0x3dcfc  brfalse  loc_3E2E3
0x3dd01  ldarg.0
0x3dd02  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Response()
0x3dd07  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3dd0c  brfalse  loc_3E2E3
0x3dd11  ldarg.0
0x3dd12  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Response()
0x3dd17  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3dd1c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x3dd21  brfalse  loc_3E2E3
0x3dd26  ldarg.0
0x3dd27  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::get_Response()
0x3dd2c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3dd31  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x3dd36  ldlen
0x3dd37  brfalse  loc_3E2E3
0x3dd3c  ldarg.0
0x3dd3d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.GetItemResponseType Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::response
0x3dd42  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3dd47  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x3dd4c  stloc.2
0x3dd4d  ldc.i4.0
0x3dd4e  stloc.3
0x3dd4f  br       loc_3E2DA
0x3dd54  ldloc.2
0x3dd55  ldloc.3
0x3dd56  ldelem.ref
0x3dd57  stloc.s  4
0x3dd59  ldstr    aServerSideSync_12// "Server-Side Synchronization (Incoming):"...
0x3dd5e  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3dd63  ldstr    aServerSideSync_13// "Server-Side Synchronization (Incoming):"...
0x3dd68  call     void Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorPerformanceCounters::IncrementPerformanceCounter(string performanceCounterName)
0x3dd6d  ldarg.0
0x3dd6e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dd73  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3dd78  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemType> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_MessageIds()
0x3dd7d  ldloc.0
0x3dd7e  dup
0x3dd7f  ldc.i4.1
0x3dd80  add
0x3dd81  stloc.0
0x3dd82  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemType>::get_Item(!!T0)
0x3dd87  castclass Microsoft.Crm.Asynchronous.EmailConnector.MessageType
0x3dd8c  stloc.s  5
0x3dd8e  ldnull
0x3dd8f  stloc.s  6
0x3dd91  ldnull
0x3dd92  stloc.s  7
0x3dd94  ldloc.s  4
0x3dd96  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x3dd9b  brfalse  loc_3DE5E
0x3dda0  ldloc.s  4
0x3dda2  call     T0x2B000070
0x3dda7  stloc.s  8
0x3dda9  ldstr    aUnsuccessfulRe// "Unsuccessful response found for Mailbox"...
0x3ddae  ldarg.0
0x3ddaf  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ddb4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3ddb9  ldstr    aMailboxid// "mailboxid"
0x3ddbe  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3ddc3  ldloc.s  8
0x3ddc5  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatTraceLogErrorDetail(string message)
0x3ddca  call     string [mscorlib]System.String::Format(string, object, object)
0x3ddcf  stloc.s  9
0x3ddd1  ldarg.0
0x3ddd2  ldc.i4.1
0x3ddd3  ldloc.s  9
0x3ddd5  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3ddda  call     class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::get_Instance()
0x3dddf  ldloc.s  4
0x3dde1  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseCodeType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseCode()
0x3dde6  ldloc.s  4
0x3dde8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageText()
0x3dded  ldc.i4.0
0x3ddee  ldloc.s  4
0x3ddf0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageXml()
0x3ddf5  ldarg.0
0x3ddf6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ddfb  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_DefaultErrorType()
0x3de00  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ExchangeErrorCodeProcessor::GetErrorInfo(int32 errorCode, string responseMessage, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageTypeMessageXml responseMessageXml, [opt] valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType)
0x3de05  stloc.s  6
0x3de07  ldloc.s  6
0x3de09  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3de0e  ldloc.s  9
0x3de10  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3de15  ldarg.0
0x3de16  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de1b  ldc.i4.0
0x3de1c  callvirt instance void LoadingEmailCollection::set_LoadSucceeded(bool value)
0x3de21  ldarg.0
0x3de22  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de27  ldarg.0
0x3de28  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de2d  callvirt instance valuetype [mscorlib]System.DateTime LoadingEmailCollection::get_LoadingStartTimeStamp()
0x3de32  callvirt instance void LoadingEmailCollection::set_LoadingStartTimeStamp(valuetype [mscorlib]System.DateTime value)
0x3de37  ldarg.0
0x3de38  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de3d  ldarg.0
0x3de3e  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de43  callvirt instance valuetype [mscorlib]System.DateTime LoadingEmailCollection::get_LoadingEndTimeStamp()
0x3de48  callvirt instance void LoadingEmailCollection::set_LoadingEndTimeStamp(valuetype [mscorlib]System.DateTime value)
0x3de4d  ldarg.0
0x3de4e  ldarg.0
0x3de4f  ldfld    class LoadingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::loadEmailCollections
0x3de54  call     T0x2B000077
0x3de59  br       loc_3E1DE
0x3de5e  ldloc.s  4
0x3de60  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ItemInfoResponseMessageType
0x3de65  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfRealItemsType Microsoft.Crm.Asynchronous.EmailConnector.ItemInfoResponseMessageType::get_Items()
0x3de6a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfRealItemsType::get_Items()
0x3de6f  ldc.i4.0
0x3de70  ldelem.ref
0x3de71  castclass Microsoft.Crm.Asynchronous.EmailConnector.MessageType
0x3de76  stloc.s  0xA
0x3de78  ldarg.0
0x3de79  ldloc.s  5
0x3de7b  ldloc.s  0xA
0x3de7d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::GetExchangeEmailMessage(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType messageWithOnlyId, class Microsoft.Crm.Asynchronous.EmailConnector.MessageType messageWithOnlyRequestedFields)
0x3de82  stloc.s  7
0x3de84  ldloc.s  7
0x3de86  brfalse  loc_3DF4F
0x3de8b  ldarg.0
0x3de8c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3de91  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x3de96  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x3de9b  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsSSSCustomPropertyFCBEnabled(valuetype [mscorlib]System.Guid organizationId)
0x3dea0  brfalse.s loc_3DEBC
0x3dea2  ldloc.s  0xA
0x3dea4  call     bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeHelper::DoesItemContainLinkState(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType message)
0x3dea9  brtrue.s loc_3DEBC
0x3deab  ldloc.s  0xA
0x3dead  ldarg.0
0x3deae  ldloc.s  7
0x3deb0  ldloc.s  0xA
0x3deb2  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::ProcessCustomProperties(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.MessageType messageWithOnlyRequestedFields)
0x3deb7  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemType::set_ExtendedProperty(class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] value)
0x3debc  ldloc.s  0xA
0x3debe  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_ExtendedProperty()
0x3dec3  brfalse.s loc_3DEE3
0x3dec5  ldloc.s  0xA
0x3dec7  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_ExtendedProperty()
0x3decc  ldlen
0x3decd  brfalse.s loc_3DEE3
0x3decf  ldarg.0
0x3ded0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3ded5  ldloc.s  7
0x3ded7  ldloc.s  0xA
0x3ded9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_ExtendedProperty()
0x3dede  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::SetExtendedPropertyTypes(class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage exchangeEmailMessage, class Microsoft.Crm.Asynchronous.EmailConnector.ExtendedPropertyType[] extendedPropertyType)
0x3dee3  ldarg.0
0x3dee4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3dee9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategoriesSearchFoldersManager()
0x3deee  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager::IsCategorizedTrackingEnabled()
0x3def3  brfalse.s loc_3DF41
0x3def5  ldarg.0
0x3def6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoryItemMapper Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::exchangeCategoryItemMapper
0x3defb  ldloc.s  0xA
0x3defd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoryItemMapper::MapMessageTypeToExchangeCategoryItem(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType messageType)
0x3df02  stloc.s  0xB
0x3df04  ldloc.s  7
0x3df06  ldarg.0
0x3df07  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ILinkStateEvaluator Microsoft.Crm.Asynchronous.EmailConnector.GetItemsStep::linkStateEvaluator
0x3df0c  ldloc.s  7
0x3df0e  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x3df13  ldarg.0
0x3df14  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3df19  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategorizedItemManager()
0x3df1e  ldloc.s  0xB
0x3df20  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::IsTrackedUsingCategories(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem exchangeCategoryItem)
0x3df25  ldarg.0
0x3df26  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3df2b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategorizedItemManager()
0x3df30  ldloc.s  0xB
0x3df32  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::IsUnTrackedUsingCategories(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoryItem exchangeCategoryItem)
0x3df37  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.ILinkStateEvaluator::GetLinkStateWhenCategoryTrackingIsEnabled(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState exchangeLinkState, bool isTrackedUsingCategories, bool isUnTrackedUsingCategories)
0x3df3c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_LinkState(valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState value)
0x3df41  ldloc.s  7
0x3df43  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_EmailProcessNeeded()
0x3df48  brtrue.s loc_3DF4F
0x3df4a  leave    loc_3E2D6
0x3df4f  leave    loc_3DFEF
0x3df54  stloc.s  0xC
0x3df56  ldarg.0
0x3df57  ldc.i4.1
0x3df58  ldstr    aExceptionOccur_11// "Exception occurred while trying to get "...
0x3df5d  ldc.i4.2
0x3df5e  newarr   [mscorlib]System.Object
0x3df63  dup
0x3df64  ldc.i4.0
0x3df65  ldarg.0
0x3df66  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3df6b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3df70  ldstr    aMailboxid// "mailboxid"
0x3df75  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3df7a  stelem.ref
0x3df7b  dup
0x3df7c  ldc.i4.1
0x3df7d  ldloc.s  0xC
0x3df7f  ldarg.0
0x3df80  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3df85  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3df8a  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x3df8f  stelem.ref
0x3df90  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3df95  ldarg.0
0x3df96  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3df9b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3dfa0  ldc.i4.s 0x1D
0x3dfa2  ldc.i4.2
0x3dfa3  ldc.i4.3
0x3dfa4  ldc.i4.0
0x3dfa5  ldc.i4.0
0x3dfa6  ldstr    aExchangerespon// "ExchangeResponseError"
0x3dfab  call     class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo Microsoft.Crm.Asynchronous.EmailConnector.ErrorHandler::MailboxErrorInfoWithDynamicLink(valuetype [mscorlib]System.Guid organizationId, int32 traceCode, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorType errorType, valuetype Microsoft.Crm.Asynchronous.EmailConnector.ErrorSource errorSource, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorScope errorScope, valuetype Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationType mailboxOperationType, [opt] string errorString)
0x3dfb0  stloc.s  6
0x3dfb2  ldloc.s  6
0x3dfb4  callvirt instance class [Microsoft.Crm]Microsoft.Crm.TraceData Microsoft.Crm.Asynchronous.EmailConnector.ErrorInfo::get_TraceData()
0x3dfb9  ldstr    aExceptionOccur_12// "Exception occurred while trying to get "...
0x3dfbe  ldloc.s  0xC
0x3dfc0  callvirt instance string [mscorlib]System.Object::ToString()
0x3dfc5  ldc.i4   0x400
0x3dfca  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::FormatExceptionMessage(string message, int32 maxLength)
0x3dfcf  call     string [mscorlib]System.String::Concat(string, string)
0x3dfd4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.TraceData::set_ErrorDetails(string)
0x3dfd9  ldloc.s  6
0x3dfdb  ldloc.s  0xA
0x3dfdd  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_Subject()
0x3dfe2  call     string Microsoft.Crm.Asynchronous.EmailConnector.Utility::FilterNull(string source)
0x3dfe7  ldc.i4.0
0x3dfe8  call     void Microsoft.Crm.Asynchronous.EmailConnector.TraceLogHelper::InsertTextTypeTraceParameter(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxErrorInfo errorInfo, string data, int32 index)
0x3dfed  leave.s  loc_3DFEF
0x3dfef  ldloc.s  6
0x3dff1  brtrue   loc_3E1DE
0x3dff6  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x3dffb  ldc.i4.1
0x3dffc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::SpecifyKind(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTimeKind)
0x3e001  stloc.s  0xD
0x3e003  ldnull
0x3e004  stloc.s  0xE
0x3e006  ldloc.s  7
0x3e008  brtrue   loc_3E0F0
0x3e00d  ldstr    aEmailForMailbo// "Email for Mailbox {0} was rejected beca"...
0x3e012  stloc.s  0xF
0x3e014  ldarg.0
0x3e015  ldc.i4.1
0x3e016  ldloc.s  0xF
0x3e018  ldc.i4.3
0x3e019  newarr   [mscorlib]System.Object
0x3e01e  dup
0x3e01f  ldc.i4.0
0x3e020  ldarg.0
0x3e021  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e026  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3e02b  ldstr    aMailboxid// "mailboxid"
0x3e030  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3e035  stelem.ref
0x3e036  dup
0x3e037  ldc.i4.1
0x3e038  ldarg.0
0x3e039  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3e03e  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_MaximumMessageSizeLimit()
0x3e043  box      [mscorlib]System.Int32
0x3e048  stelem.ref
0x3e049  dup
0x3e04a  ldc.i4.2
0x3e04b  ldloc.s  4
0x3e04d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_MessageText()
0x3e052  stelem.ref
0x3e053  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3e058  ldarg.0
0x3e059  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3e05e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x3e063  ldc.i4.s 0x1D
0x3e065  ldc.i4.1
0x3e066  ldc.i4.0
0x3e067  ldc.i4.0
  ... truncated ...
```
