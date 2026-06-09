# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::IsCopiedItem

- ea: `0x5e290`
- end: `0x5e397`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::IsCopiedItem`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x5d9e0`

## callees

- `0x54bb0`
- `0x54d40`
- `0x5e240`
- `0x5e260`
- `0x5e290`
- `0x5e4c0`
- `0x5e610`

## string_xrefs

- `0x5e2f8`: `The appointment item {0} is considered to be a copy for the mailbox {1}. Details - CrmId: {2}, ExchangeIdFromIdMapping: {3} `
- `0x5e32b`: `The item {0} is considered to be a copy for the mailbox {1}. Details - CrmId: {2}, ExchangeIdFromIdMapping: {3} `
- `0x5e366`: `ExchangeId from IdMapping is not found for item {0} and hence considered as not a copy. Details - Mailbox: {1}, CrmId: {2}, ExchangeIdFromIdMapping: {3} `

## pseudocode

```c

```

## disassembly

```asm
0x5e290  ldarg.1
0x5e291  call     string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::GetCrmId(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item item)
0x5e296  stloc.0
0x5e297  ldloc.0
0x5e298  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e29d  brtrue   loc_5E395
0x5e2a2  ldarg.2
0x5e2a3  brtrue.s loc_5E2AC
0x5e2a5  ldsfld   string [mscorlib]System.String::Empty
0x5e2aa  br.s     loc_5E2B2
0x5e2ac  ldarg.2
0x5e2ad  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ExchangeEntryId()
0x5e2b2  stloc.1
0x5e2b3  ldarg.2
0x5e2b4  brtrue.s loc_5E2B9
0x5e2b6  ldc.i4.0
0x5e2b7  br.s     loc_5E2BF
0x5e2b9  ldarg.2
0x5e2ba  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.SyncItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncIdMappingEntityWrapper::get_ToCrmChangeType()
0x5e2bf  stloc.2
0x5e2c0  ldloc.1
0x5e2c1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5e2c6  brtrue.s loc_5E2DC
0x5e2c8  ldloc.1
0x5e2c9  ldarg.1
0x5e2ca  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x5e2cf  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x5e2d4  ldc.i4.5
0x5e2d5  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x5e2da  brtrue.s loc_5E2E0
0x5e2dc  ldloc.2
0x5e2dd  ldc.i4.6
0x5e2de  bne.un.s loc_5E35C
0x5e2e0  ldarg.1
0x5e2e1  isinst   [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment
0x5e2e6  stloc.3
0x5e2e7  ldloc.3
0x5e2e8  brfalse.s loc_5E329
0x5e2ea  ldarg.0
0x5e2eb  ldloc.3
0x5e2ec  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItemFinder::IsCopiedAppointment(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment appt)
0x5e2f1  brfalse  loc_5E395
0x5e2f6  ldarg.0
0x5e2f7  ldc.i4.4
0x5e2f8  ldstr    aTheAppointment_0// "The appointment item {0} is considered "...
0x5e2fd  ldc.i4.4
0x5e2fe  newarr   [mscorlib]System.Object
0x5e303  dup
0x5e304  ldc.i4.0
0x5e305  ldarg.1
0x5e306  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x5e30b  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x5e310  stelem.ref
0x5e311  dup
0x5e312  ldc.i4.1
0x5e313  ldarg.0
0x5e314  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5e319  stelem.ref
0x5e31a  dup
0x5e31b  ldc.i4.2
0x5e31c  ldloc.0
0x5e31d  stelem.ref
0x5e31e  dup
0x5e31f  ldc.i4.3
0x5e320  ldloc.1
0x5e321  stelem.ref
0x5e322  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5e327  ldc.i4.1
0x5e328  ret
0x5e329  ldarg.0
0x5e32a  ldc.i4.4
0x5e32b  ldstr    aTheItem0IsCons// "The item {0} is considered to be a copy"...
0x5e330  ldc.i4.4
0x5e331  newarr   [mscorlib]System.Object
0x5e336  dup
0x5e337  ldc.i4.0
0x5e338  ldarg.1
0x5e339  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x5e33e  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x5e343  stelem.ref
0x5e344  dup
0x5e345  ldc.i4.1
0x5e346  ldarg.0
0x5e347  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5e34c  stelem.ref
0x5e34d  dup
0x5e34e  ldc.i4.2
0x5e34f  ldloc.0
0x5e350  stelem.ref
0x5e351  dup
0x5e352  ldc.i4.3
0x5e353  ldloc.1
0x5e354  stelem.ref
0x5e355  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5e35a  ldc.i4.1
0x5e35b  ret
0x5e35c  ldloc.1
0x5e35d  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5e362  brfalse.s loc_5E395
0x5e364  ldarg.0
0x5e365  ldc.i4.4
0x5e366  ldstr    aExchangeidFrom// "ExchangeId from IdMapping is not found "...
0x5e36b  ldc.i4.4
0x5e36c  newarr   [mscorlib]System.Object
0x5e371  dup
0x5e372  ldc.i4.0
0x5e373  ldarg.1
0x5e374  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ItemId [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::get_Id()
0x5e379  callvirt instance string [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceId::get_UniqueId()
0x5e37e  stelem.ref
0x5e37f  dup
0x5e380  ldc.i4.1
0x5e381  ldarg.0
0x5e382  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::get_MailboxId()
0x5e387  stelem.ref
0x5e388  dup
0x5e389  ldc.i4.2
0x5e38a  ldloc.0
0x5e38b  stelem.ref
0x5e38c  dup
0x5e38d  ldc.i4.3
0x5e38e  ldloc.1
0x5e38f  stelem.ref
0x5e390  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ItemFinder::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x5e395  ldc.i4.0
0x5e396  ret
```
