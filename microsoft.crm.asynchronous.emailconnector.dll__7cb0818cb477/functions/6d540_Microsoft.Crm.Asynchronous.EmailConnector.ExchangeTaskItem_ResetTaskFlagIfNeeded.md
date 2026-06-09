# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::ResetTaskFlagIfNeeded

- ea: `0x6d540`
- end: `0x6d5a3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::ResetTaskFlagIfNeeded`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x6d520`

## callees

- `0x589c0`
- `0x6d420`
- `0x6d540`
- `0x70330`
- `0x70460`

## string_xrefs

- `0x6d574`: `taskflagstatus`
- `0x6d588`: `taskflagstatus`

## pseudocode

```c

```

## disassembly

```asm
0x6d540  ldarg.0
0x6d541  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d546  callvirt instance float64 [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_PercentComplete()
0x6d54b  conv.i4
0x6d54c  ldc.i4.s 0x64
0x6d54e  bne.un.s loc_6D573
0x6d550  ldarg.0
0x6d551  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d556  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.TaskStatus [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_Status()
0x6d55b  ldc.i4.2
0x6d55c  bne.un.s loc_6D573
0x6d55e  ldarg.0
0x6d55f  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task Microsoft.Crm.Asynchronous.EmailConnector.ExchangeTaskItem::get_TaskItem()
0x6d564  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Task::get_CompleteDate()
0x6d569  stloc.0
0x6d56a  ldloca.s 0
0x6d56c  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::get_HasValue()
0x6d571  brtrue.s loc_6D59D
0x6d573  ldarg.0
0x6d574  ldstr    aTaskflagstatus_0// "taskflagstatus"
0x6d579  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::GetProperty(string propertyName)
0x6d57e  ldc.i4.0
0x6d57f  call     int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeSyncUtility::ToIntValue(string propertyValue, [opt] int32 defaultValue)
0x6d584  ldc.i4.1
0x6d585  bne.un.s loc_6D59D
0x6d587  ldarg.0
0x6d588  ldstr    aTaskflagstatus_0// "taskflagstatus"
0x6d58d  ldc.i4.0
0x6d58e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6d593  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x6d598  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::SetPropertyValue(string propertyName, string propertyValue)
0x6d59d  leave.s  loc_6D5A2
0x6d59f  pop
0x6d5a0  leave.s  loc_6D5A2
0x6d5a2  ret
```
