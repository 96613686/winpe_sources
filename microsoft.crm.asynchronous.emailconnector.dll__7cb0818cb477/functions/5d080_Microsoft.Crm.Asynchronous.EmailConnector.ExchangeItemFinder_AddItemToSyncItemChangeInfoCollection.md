# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddItemToSyncItemChangeInfoCollection

- ea: `0x5d080`
- end: `0x5d3a6`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::AddItemToSyncItemChangeInfoCollection`
- size: `806`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `broker_com_uri`

## callers

- `0x5ced0`
- `0x5cfd0`
- `0x5d040`
- `0x5d4d0`

## callees

- `0x4da80`
- `0x52650`
- `0x549e0`
- `0x56ec0`
- `0x58270`
- `0x58c10`
- `0x59a30`
- `0x5a9e0`
- `0x5d080`
- `0x5d3b0`
- `0x5e1e0`
- `0x5e4b0`
- `0x5e4c0`
- `0x5e500`
- `0x5e530`
- `0x5e560`
- `0x5e610`
- `0x5ead0`
- `0x5eaf0`
- `0x5eb00`
- `0x5eb10`
- `0x5eb30`
- `0x5eb50`
- `0x5eb80`
- `0x5eb90`
- `0x5ebb0`
- `0x5ebd0`
- `0x5ebe0`
- `0x69840`
- `0x70b20`
- `0x829c0`

## string_xrefs

- `0x5d1b8`: `ExchangeItem not found for item {0} with CRM Id {1} mailbox: {2}. Change type: {3}, Object Type: {4}, ItemSSSPromoteTracker: {5}, Item created time: {6}, Item last modified time: {7}.`
- `0x5d249`: `The item {0} with CRM Id {1} has been added to the sync item collection for the mailbox: {2}. Change type: {3}, Object Type: {4}, ItemSSSPromoteTracker: {5}, Item created time: {6}, Item last modified time: {7}.`

## pseudocode

```c

```

## disassembly

```asm
0x5d080  ldarg.2
0x5d081  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5d086  brfalse.s loc_5D093
0x5d088  ldstr    aInvalidInput// "Invalid input."
0x5d08d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x5d092  throw
0x5d093  ldc.i4.0
0x5d094  ldarg.0
0x5d095  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5d09a  ldstr    aAdditemstosync// "AddItemsToSyncItemChangeInfoCollection"
0x5d09f  ldstr    asc_8A7C2// ""
0x5d0a4  ldstr    asc_8A7C2// ""
0x5d0a9  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::WriteVerboseEvent(valuetype Microsoft.Crm.Asynchronous.EmailConnector.EtwLogType etwLogType, class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, string functionName, [opt] string functionParam1, [opt] string functionParam2)
0x5d0ae  ldarg.3
0x5d0af  brtrue.s loc_5D0EA
0x5d0b1  ldarg.0
0x5d0b2  ldc.i4.4
0x5d0b3  ldstr    aTheChangeTypeO// "The change type of the item {0}, crmid "...
0x5d0b8  ldc.i4.3
0x5d0b9  newarr   [mscorlib]System.Object
0x5d0be  dup
0x5d0bf  ldc.i4.0
0x5d0c0  ldarg.2
0x5d0c1  stelem.ref
0x5d0c2  dup
0x5d0c3  ldc.i4.1
0x5d0c4  ldarg.s  5
0x5d0c6  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5d0cb  brtrue.s loc_5D0D1
0x5d0cd  ldarg.s  5
0x5d0cf  br.s     loc_5D0D6
0x5d0d1  ldsfld   string [mscorlib]System.String::Empty
0x5d0d6  stelem.ref
0x5d0d7  dup
0x5d0d8  ldc.i4.2
0x5d0d9  ldarg.0
0x5d0da  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5d0df  stelem.ref
0x5d0e0  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5d0e5  leave    loc_5D3A5
0x5d0ea  ldarg.3
0x5d0eb  ldc.i4.2
0x5d0ec  beq.s    loc_5D11F
0x5d0ee  ldarg.s  4
0x5d0f0  brtrue.s loc_5D11F
0x5d0f2  ldarg.0
0x5d0f3  ldc.i4.4
0x5d0f4  ldstr    aTheObjectTypeO// "The object type of the item {0} is none"...
0x5d0f9  ldc.i4.3
0x5d0fa  newarr   [mscorlib]System.Object
0x5d0ff  dup
0x5d100  ldc.i4.0
0x5d101  ldarg.2
0x5d102  stelem.ref
0x5d103  dup
0x5d104  ldc.i4.1
0x5d105  ldarg.0
0x5d106  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5d10b  stelem.ref
0x5d10c  dup
0x5d10d  ldc.i4.2
0x5d10e  ldarg.3
0x5d10f  box      Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5d114  stelem.ref
0x5d115  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5d11a  leave    loc_5D3A5
0x5d11f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::.ctor()
0x5d124  stloc.0
0x5d125  ldloc.0
0x5d126  ldarg.0
0x5d127  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5d12c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_Provider(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider value)
0x5d131  ldloc.0
0x5d132  ldarg.2
0x5d133  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ExchangeEntryId(string value)
0x5d138  ldloc.0
0x5d139  ldarg.s  5
0x5d13b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_CrmId(string value)
0x5d140  ldloc.0
0x5d141  ldarg.3
0x5d142  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemChangeType(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType value)
0x5d147  ldloc.0
0x5d148  ldarg.s  4
0x5d14a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemObjectType(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType value)
0x5d14f  ldloc.0
0x5d150  ldarg.1
0x5d151  call     valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetSssPromoteTracker(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5d156  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_ItemSSSPromoteTracker(valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker value)
0x5d15b  ldarg.3
0x5d15c  ldc.i4.2
0x5d15d  beq      loc_5D235
0x5d162  ldarg.0
0x5d163  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5d168  ldarg.s  4
0x5d16a  ldarg.0
0x5d16b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_InputProvider()
0x5d170  ldarg.1
0x5d171  ldarg.0
0x5d172  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncPropertiesMappings()
0x5d177  ldarg.s  4
0x5d179  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMappings::GetSyncPropertiesMapping(valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType objectType)
0x5d17e  call     class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase Microsoft.Crm.Asynchronous.EmailConnector.SyncItemFactory::GetSyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context, valuetype [Microsoft.Crm]Microsoft.Crm.ItemObjectType itemObjectType, class Microsoft.Crm.Asynchronous.EmailConnector.IProvider provider, object item, class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncPropertiesMapping syncPropertiesMapping)
0x5d183  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem
0x5d188  stloc.1
0x5d189  ldloc.1
0x5d18a  brfalse.s loc_5D1B6
0x5d18c  ldloc.1
0x5d18d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x5d192  brfalse.s loc_5D1B6
0x5d194  ldloc.0
0x5d195  ldloc.1
0x5d196  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_SyncItem(class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase value)
0x5d19b  ldloc.0
0x5d19c  ldloc.1
0x5d19d  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x5d1a2  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x5d1a7  stloc.2
0x5d1a8  ldloca.s 2
0x5d1aa  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x5d1af  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::set_Timestamp(valuetype [mscorlib]System.DateTime value)
0x5d1b4  br.s     loc_5D235
0x5d1b6  ldarg.0
0x5d1b7  ldc.i4.2
0x5d1b8  ldstr    aExchangeitemNo// "ExchangeItem not found for item {0} wit"...
0x5d1bd  ldc.i4.8
0x5d1be  newarr   [mscorlib]System.Object
0x5d1c3  dup
0x5d1c4  ldc.i4.0
0x5d1c5  ldarg.2
0x5d1c6  stelem.ref
0x5d1c7  dup
0x5d1c8  ldc.i4.1
0x5d1c9  ldarg.s  5
0x5d1cb  brfalse.s loc_5D1D1
0x5d1cd  ldarg.s  5
0x5d1cf  br.s     loc_5D1D6
0x5d1d1  ldsfld   string [mscorlib]System.String::Empty
0x5d1d6  stelem.ref
0x5d1d7  dup
0x5d1d8  ldc.i4.2
0x5d1d9  ldarg.0
0x5d1da  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5d1df  stelem.ref
0x5d1e0  dup
0x5d1e1  ldc.i4.3
0x5d1e2  ldarg.3
0x5d1e3  box      Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5d1e8  stelem.ref
0x5d1e9  dup
0x5d1ea  ldc.i4.4
0x5d1eb  ldarg.s  4
0x5d1ed  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5d1f2  stelem.ref
0x5d1f3  dup
0x5d1f4  ldc.i4.5
0x5d1f5  ldloc.0
0x5d1f6  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemSSSPromoteTracker()
0x5d1fb  box      Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker
0x5d200  stelem.ref
0x5d201  dup
0x5d202  ldc.i4.6
0x5d203  ldarg.1
0x5d204  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_DateTimeCreated()
0x5d209  pop
0x5d20a  ldarg.1
0x5d20b  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_DateTimeCreated()
0x5d210  box      [mscorlib]System.DateTime
0x5d215  stelem.ref
0x5d216  dup
0x5d217  ldc.i4.7
0x5d218  ldarg.1
0x5d219  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x5d21e  pop
0x5d21f  ldarg.1
0x5d220  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x5d225  box      [mscorlib]System.DateTime
0x5d22a  stelem.ref
0x5d22b  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5d230  leave    loc_5D3A5
0x5d235  ldarg.0
0x5d236  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo> Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_SyncItemChangeInfoCollection()
0x5d23b  ldloc.0
0x5d23c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ExchangeEntryId()
0x5d241  ldloc.0
0x5d242  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo>::set_Item(var<u1>, !!T0)
0x5d247  ldarg.0
0x5d248  ldc.i4.4
0x5d249  ldstr    aTheItem0WithCr// "The item {0} with CRM Id {1} has been a"...
0x5d24e  ldc.i4.8
0x5d24f  newarr   [mscorlib]System.Object
0x5d254  dup
0x5d255  ldc.i4.0
0x5d256  ldarg.2
0x5d257  stelem.ref
0x5d258  dup
0x5d259  ldc.i4.1
0x5d25a  ldarg.s  5
0x5d25c  brfalse.s loc_5D262
0x5d25e  ldarg.s  5
0x5d260  br.s     loc_5D267
0x5d262  ldsfld   string [mscorlib]System.String::Empty
0x5d267  stelem.ref
0x5d268  dup
0x5d269  ldc.i4.2
0x5d26a  ldarg.0
0x5d26b  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5d270  stelem.ref
0x5d271  dup
0x5d272  ldc.i4.3
0x5d273  ldarg.3
0x5d274  box      Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType
0x5d279  stelem.ref
0x5d27a  dup
0x5d27b  ldc.i4.4
0x5d27c  ldarg.s  4
0x5d27e  box      [Microsoft.Crm]Microsoft.Crm.ItemObjectType
0x5d283  stelem.ref
0x5d284  dup
0x5d285  ldc.i4.5
0x5d286  ldloc.0
0x5d287  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeInfo::get_ItemSSSPromoteTracker()
0x5d28c  box      Microsoft.Crm.Asynchronous.EmailConnector.SssPromoteTracker
0x5d291  stelem.ref
0x5d292  dup
0x5d293  ldc.i4.6
0x5d294  ldarg.1
0x5d295  brfalse.s loc_5D2A0
0x5d297  ldarg.1
0x5d298  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_DateTimeCreated()
0x5d29d  pop
0x5d29e  br.s     loc_5D2A7
0x5d2a0  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x5d2a5  br.s     loc_5D2AD
0x5d2a7  ldarg.1
0x5d2a8  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_DateTimeCreated()
0x5d2ad  box      [mscorlib]System.DateTime
0x5d2b2  stelem.ref
0x5d2b3  dup
0x5d2b4  ldc.i4.7
0x5d2b5  ldarg.1
0x5d2b6  brfalse.s loc_5D2C1
0x5d2b8  ldarg.1
0x5d2b9  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x5d2be  pop
0x5d2bf  br.s     loc_5D2C8
0x5d2c1  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MaxValue
0x5d2c6  br.s     loc_5D2CE
0x5d2c8  ldarg.1
0x5d2c9  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_LastModifiedTime()
0x5d2ce  box      [mscorlib]System.DateTime
0x5d2d3  stelem.ref
0x5d2d4  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5d2d9  leave    loc_5D3A5
0x5d2de  stloc.3
0x5d2df  ldloc.3
0x5d2e0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5d2e5  ldstr    aShutdownEventR// "Shutdown event received"
0x5d2ea  callvirt instance bool [mscorlib]System.String::Contains(string)
0x5d2ef  brfalse.s loc_5D2F3
0x5d2f1  rethrow
0x5d2f3  ldarg.0
0x5d2f4  ldc.i4.1
0x5d2f5  ldstr    aFailedToAddThe_3// "Failed to add the item {0} to the sync "...
0x5d2fa  ldc.i4.3
0x5d2fb  newarr   [mscorlib]System.Object
0x5d300  dup
0x5d301  ldc.i4.0
0x5d302  ldarg.2
0x5d303  stelem.ref
0x5d304  dup
0x5d305  ldc.i4.1
0x5d306  ldarg.0
0x5d307  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5d30c  stelem.ref
0x5d30d  dup
0x5d30e  ldc.i4.2
0x5d30f  ldloc.3
0x5d310  ldarg.0
0x5d311  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_Context()
0x5d316  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5d31b  call     string Microsoft.Crm.Asynchronous.EmailConnector.EmailConnectorTraceHandler::EmailConnectorExceptionToString(class [mscorlib]System.Exception e, valuetype [mscorlib]System.Guid orgId)
0x5d320  stelem.ref
0x5d321  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5d326  ldarg.1
0x5d327  brtrue.s loc_5D330
0x5d329  ldsfld   string [mscorlib]System.String::Empty
0x5d32e  br.s     loc_5D336
0x5d330  ldarg.1
0x5d331  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Subject()
0x5d336  stloc.s  4
0x5d338  ldloc.3
0x5d339  ldarg.0
0x5d33a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncWorker Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::_exchangeSyncWorker
0x5d33f  callvirt instance class ACTState Microsoft.Crm.Asynchronous.EmailConnector.ACTProviderBase::get_Mailbox()
0x5d344  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox ACTState::get_InternalMailbox()
0x5d349  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5d34e  ldarg.s  4
0x5d350  ldloc.s  4
0x5d352  ldc.i4.0
0x5d353  call     void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::LogError(class [mscorlib]System.Exception ex, class Microsoft.Crm.Asynchronous.EmailConnector.Mailbox mailbox, [opt] valuetype [mscorlib]System.Guid itemObjectId, [opt] int32 itemObjectTypeCode, [opt] string itemSubject, [opt] bool forceItemLevel)
  ... truncated ...
```
