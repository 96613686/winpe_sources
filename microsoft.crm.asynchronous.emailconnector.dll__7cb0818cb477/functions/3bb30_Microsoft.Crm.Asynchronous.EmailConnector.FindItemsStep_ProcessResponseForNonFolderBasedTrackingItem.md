# Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::ProcessResponseForNonFolderBasedTrackingItem

- ea: `0x3bb30`
- end: `0x3c046`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::ProcessResponseForNonFolderBasedTrackingItem`
- size: `1302`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3b850`

## callees

- `0xb850`
- `0x17d90`
- `0x18260`
- `0x18300`
- `0x187e0`
- `0x18800`
- `0x234d0`
- `0x23560`
- `0x23620`
- `0x23760`
- `0x272b0`
- `0x27490`
- `0x274a0`
- `0x32970`
- `0x3ab40`
- `0x3ab80`
- `0x3b370`
- `0x3bb30`
- `0x3c280`
- `0x3c300`
- `0x3c430`
- `0x42010`
- `0x42020`
- `0x42060`
- `0x81e20`
- `0x81e40`
- `0x81e90`
- `0x81ea0`
- `0x81eb0`
- `0x81ec0`
- `0x81f00`

## string_xrefs

- `0x3bd7a`: `Ignoring item {0} because it is already processed by manual. Mailbox: {1}.`
- `0x3bdbd`: `Considering Item {0} for auto tracking. Mailbox: {1}.`
- `0x3bf2a`: `Considering item {0} as a custom property item with link state tracker set. Custom property value {1}. Mailbox: {2}.`
- `0x3bf56`: `Considering Item {0} as a regular manually tracked item. Mailbox: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x3bb30  ldc.i4.0
0x3bb31  stloc.0
0x3bb32  ldarg.1
0x3bb33  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FindItemParentType Microsoft.Crm.Asynchronous.EmailConnector.FindItemResponseMessageType::get_RootFolder()
0x3bb38  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.FindItemParentType::get_IncludesLastItemInRange()
0x3bb3d  brtrue.s loc_3BB5C
0x3bb3f  ldarg.1
0x3bb40  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FindItemParentType Microsoft.Crm.Asynchronous.EmailConnector.FindItemResponseMessageType::get_RootFolder()
0x3bb45  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.FindItemParentType::get_IndexedPagingOffset()
0x3bb4a  ldarg.0
0x3bb4b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IndexedPageViewType Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::get_IndexedView()
0x3bb50  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.IndexedPageViewType::get_Offset()
0x3bb55  cgt
0x3bb57  ldc.i4.0
0x3bb58  ceq
0x3bb5a  br.s     loc_3BB5D
0x3bb5c  ldc.i4.1
0x3bb5d  stloc.1
0x3bb5e  ldarg.0
0x3bb5f  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bb64  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3bb69  ldstr    aLastmessageid// "lastmessageid"
0x3bb6e  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3bb73  castclass [mscorlib]System.String
0x3bb78  stloc.2
0x3bb79  ldarg.0
0x3bb7a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bb7f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::GetMailboxThresholdTime()
0x3bb84  stloc.s  4
0x3bb86  ldloca.s 4
0x3bb88  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x3bb8d  stloc.3
0x3bb8e  ldarg.0
0x3bb8f  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bb94  ldc.i4.0
0x3bb95  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3bb9a  ldarg.2
0x3bb9b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfRealItemsType::get_Items()
0x3bba0  stloc.s  5
0x3bba2  ldc.i4.0
0x3bba3  stloc.s  6
0x3bba5  br       loc_3BFF3
0x3bbaa  ldloc.s  5
0x3bbac  ldloc.s  6
0x3bbae  ldelem.ref
0x3bbaf  castclass Microsoft.Crm.Asynchronous.EmailConnector.MessageType
0x3bbb4  stloc.s  7
0x3bbb6  ldsfld   string [mscorlib]System.String::Empty
0x3bbbb  stloc.s  8
0x3bbbd  ldarg.0
0x3bbbe  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bbc3  ldloc.s  7
0x3bbc5  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bbca  callvirt instance void RetrievingEmailCollection::set_messageId(string value)
0x3bbcf  ldarg.0
0x3bbd0  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bbd5  ldloc.s  7
0x3bbd7  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_Subject()
0x3bbdc  callvirt instance void RetrievingEmailCollection::set_subject(string value)
0x3bbe1  ldarg.0
0x3bbe2  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bbe7  callvirt instance bool RetrievingEmailCollection::get_discardDuetoOlderModifiedOn()
0x3bbec  brtrue   loc_3BFAD
0x3bbf1  ldarg.0
0x3bbf2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bbf7  isinst   Microsoft.Crm.Asynchronous.EmailConnector.ManualIncomingEmailProvider
0x3bbfc  brtrue   loc_3BDEA
0x3bc01  ldloc.s  7
0x3bc03  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_LastModifiedTimeSpecified()
0x3bc08  brfalse  loc_3BDEA
0x3bc0d  ldloc.s  7
0x3bc0f  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_DateTimeReceived()
0x3bc14  stloc.s  4
0x3bc16  ldloca.s 4
0x3bc18  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x3bc1d  stloc.s  9
0x3bc1f  ldloc.s  9
0x3bc21  ldloc.3
0x3bc22  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3bc27  brtrue.s loc_3BC55
0x3bc29  ldloc.s  9
0x3bc2b  ldloc.3
0x3bc2c  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3bc31  brfalse  loc_3BD56
0x3bc36  ldloc.2
0x3bc37  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bc3c  brtrue   loc_3BD56
0x3bc41  ldloc.s  7
0x3bc43  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bc48  ldloc.2
0x3bc49  ldc.i4.5
0x3bc4a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3bc4f  ldc.i4.0
0x3bc50  bgt      loc_3BD56
0x3bc55  ldstr    aIgnoringItem0F// "Ignoring item {0} from processing becau"...
0x3bc5a  ldc.i4.4
0x3bc5b  newarr   [mscorlib]System.Object
0x3bc60  dup
0x3bc61  ldc.i4.0
0x3bc62  ldloc.s  7
0x3bc64  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bc69  stelem.ref
0x3bc6a  dup
0x3bc6b  ldc.i4.1
0x3bc6c  ldloc.s  9
0x3bc6e  box      [mscorlib]System.DateTime
0x3bc73  stelem.ref
0x3bc74  dup
0x3bc75  ldc.i4.2
0x3bc76  ldloc.3
0x3bc77  box      [mscorlib]System.DateTime
0x3bc7c  stelem.ref
0x3bc7d  dup
0x3bc7e  ldc.i4.3
0x3bc7f  ldarg.0
0x3bc80  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bc85  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3bc8a  ldstr    aMailboxid// "mailboxid"
0x3bc8f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3bc94  stelem.ref
0x3bc95  call     string [mscorlib]System.String::Format(string, object[])
0x3bc9a  stloc.s  8
0x3bc9c  ldarg.0
0x3bc9d  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bca2  ldc.i4.0
0x3bca3  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3bca8  ldloc.s  7
0x3bcaa  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_LastModifiedTime()
0x3bcaf  stloc.s  4
0x3bcb1  ldloca.s 4
0x3bcb3  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x3bcb8  stloc.s  0xA
0x3bcba  ldloc.s  0xA
0x3bcbc  ldloc.3
0x3bcbd  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3bcc2  brtrue.s loc_3BCE7
0x3bcc4  ldloc.s  0xA
0x3bcc6  ldloc.3
0x3bcc7  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3bccc  brfalse.s loc_3BD3C
0x3bcce  ldloc.2
0x3bccf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3bcd4  brtrue.s loc_3BD3C
0x3bcd6  ldloc.s  7
0x3bcd8  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bcdd  ldloc.2
0x3bcde  ldc.i4.5
0x3bcdf  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3bce4  ldc.i4.0
0x3bce5  bgt.s    loc_3BD3C
0x3bce7  ldc.i4.1
0x3bce8  stloc.1
0x3bce9  ldarg.0
0x3bcea  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bcef  ldc.i4.1
0x3bcf0  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3bcf5  ldstr    aIgnoringItem0A// "Ignoring item {0} and rest of the items"...
0x3bcfa  ldc.i4.4
0x3bcfb  newarr   [mscorlib]System.Object
0x3bd00  dup
0x3bd01  ldc.i4.0
0x3bd02  ldloc.s  7
0x3bd04  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bd09  stelem.ref
0x3bd0a  dup
0x3bd0b  ldc.i4.1
0x3bd0c  ldloc.s  0xA
0x3bd0e  box      [mscorlib]System.DateTime
0x3bd13  stelem.ref
0x3bd14  dup
0x3bd15  ldc.i4.2
0x3bd16  ldloc.3
0x3bd17  box      [mscorlib]System.DateTime
0x3bd1c  stelem.ref
0x3bd1d  dup
0x3bd1e  ldc.i4.3
0x3bd1f  ldarg.0
0x3bd20  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bd25  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3bd2a  ldstr    aMailboxid// "mailboxid"
0x3bd2f  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3bd34  stelem.ref
0x3bd35  call     string [mscorlib]System.String::Format(string, object[])
0x3bd3a  stloc.s  8
0x3bd3c  ldarg.0
0x3bd3d  ldarg.0
0x3bd3e  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bd43  call     T0x2B000071
0x3bd48  ldarg.0
0x3bd49  ldc.i4.4
0x3bd4a  ldloc.s  8
0x3bd4c  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format)
0x3bd51  br       loc_3BFED
0x3bd56  ldarg.0
0x3bd57  ldloc.s  7
0x3bd59  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::IsEmailAlreadyPromotedToCrm(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType message)
0x3bd5e  brfalse.s loc_3BDBD
0x3bd60  ldarg.0
0x3bd61  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bd66  ldc.i4.1
0x3bd67  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3bd6c  ldarg.0
0x3bd6d  ldarg.0
0x3bd6e  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bd73  call     T0x2B000071
0x3bd78  ldarg.0
0x3bd79  ldc.i4.4
0x3bd7a  ldstr    aIgnoringItem0B// "Ignoring item {0} because it is already"...
0x3bd7f  ldc.i4.2
0x3bd80  newarr   [mscorlib]System.Object
0x3bd85  dup
0x3bd86  ldc.i4.0
0x3bd87  ldloc.s  7
0x3bd89  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bd8e  stelem.ref
0x3bd8f  dup
0x3bd90  ldc.i4.1
0x3bd91  ldarg.0
0x3bd92  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bd97  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3bd9c  ldstr    aMailboxid// "mailboxid"
0x3bda1  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3bda6  stelem.ref
0x3bda7  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3bdac  ldarg.0
0x3bdad  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3bdb2  ldc.i4.0
0x3bdb3  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3bdb8  br       loc_3BFED
0x3bdbd  ldstr    aConsideringIte// "Considering Item {0} for auto tracking."...
0x3bdc2  ldloc.s  7
0x3bdc4  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3bdc9  ldarg.0
0x3bdca  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3bdcf  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x3bdd4  ldstr    aMailboxid// "mailboxid"
0x3bdd9  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3bdde  call     string [mscorlib]System.String::Format(string, object, object)
0x3bde3  stloc.s  8
0x3bde5  br       loc_3BF7E
0x3bdea  ldloc.s  7
0x3bdec  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_LastModifiedTimeSpecified()
0x3bdf1  brfalse  loc_3BF56
0x3bdf6  ldarg.0
0x3bdf7  ldloc.s  7
0x3bdf9  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::RestrictByDateTimeReceived(class Microsoft.Crm.Asynchronous.EmailConnector.MessageType message)
0x3bdfe  brfalse  loc_3BF56
0x3be03  ldsfld   string [mscorlib]System.String::Empty
0x3be08  stloc.s  0xB
0x3be0a  ldloc.s  7
0x3be0c  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.ItemType::get_LastModifiedTime()
0x3be11  stloc.s  4
0x3be13  ldloca.s 4
0x3be15  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x3be1a  stloc.s  0xC
0x3be1c  ldloc.s  0xC
0x3be1e  ldloc.3
0x3be1f  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3be24  brtrue.s loc_3BE4F
0x3be26  ldloc.s  0xC
0x3be28  ldloc.3
0x3be29  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x3be2e  brfalse  loc_3BEBE
0x3be33  ldloc.2
0x3be34  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3be39  brtrue   loc_3BEBE
0x3be3e  ldloc.s  7
0x3be40  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3be45  ldloc.2
0x3be46  ldc.i4.5
0x3be47  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3be4c  ldc.i4.0
0x3be4d  bgt.s    loc_3BEBE
0x3be4f  ldc.i4.1
0x3be50  stloc.1
0x3be51  ldarg.0
0x3be52  ldfld    class RetrievingEmailCollection Microsoft.Crm.Asynchronous.EmailConnector.FindItemsStep::retrieveEmailsCollections
0x3be57  ldc.i4.1
0x3be58  callvirt instance void RetrievingEmailCollection::set_discardDuetoOlderModifiedOn(bool value)
0x3be5d  ldstr    aIgnoringItem0A_0// "Ignoring item {0} and rest of the custo"...
0x3be62  ldc.i4.4
0x3be63  newarr   [mscorlib]System.Object
0x3be68  dup
0x3be69  ldc.i4.0
0x3be6a  ldloc.s  7
0x3be6c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MessageType::get_InternetMessageId()
0x3be71  stelem.ref
0x3be72  dup
0x3be73  ldc.i4.1
0x3be74  ldloc.s  0xC
0x3be76  box      [mscorlib]System.DateTime
0x3be7b  stelem.ref
0x3be7c  dup
0x3be7d  ldc.i4.2
0x3be7e  ldloc.3
0x3be7f  box      [mscorlib]System.DateTime
0x3be84  stelem.ref
0x3be85  dup
0x3be86  ldc.i4.3
0x3be87  ldarg.0
  ... truncated ...
```
