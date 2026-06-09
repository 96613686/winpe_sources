# Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::.ctor

- ea: `0x7990`
- end: `0x79d1`
- name: `Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::.ctor`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf930`

## callees

- `0x124a0`

## string_xrefs

- `0x79a5`: `SELECT COUNT(*) AS Backlog,\n			CONVERT(INT, MAX(DATEDIFF(ss, PostPoneMailboxProcessingUntil , GETUTCDATE()))) AS Latency\n			FROM Mailbox with(nolock)\n			WHERE PostPoneMailboxProcessingUntil is not null AND\n			((EnabledForACT = 1 AND ACTStatus = 1 AND ACTDeliveryMethod = 1)\n			OR\n			(EnabledForIncomingEmail = 1 AND IncomingEmailStatus = 1 AND IncomingEmailDeliveryMethod = 2)) AND\n			PostPoneMailboxProcessingUntil < DateAdd(mi, @InternalSla, GETUTCDATE()) AND\n			DATEDIFF(YEAR, Post`

## pseudocode

```c

```

## disassembly

```asm
0x7990  ldarg.0
0x7991  ldstr    aDeclareInterna// "declare @InternalSla int = "
0x7996  ldsfld   int32 Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::InternalSlaForMailboxQueue
0x799b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x79a0  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x79a5  ldstr    aSelectCountAsB_0// "SELECT COUNT(*) AS Backlog,\r\n\t\t\tCO"...
0x79aa  call     string [mscorlib]System.String::Concat(string, string, string)
0x79af  stfld    string Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::MailboxQueueBacklogQuery
0x79b4  ldarg.0
0x79b5  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x79ba  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::_lastExecutionTime
0x79bf  ldarg.0
0x79c0  call     instance void [mscorlib]System.Object::.ctor()
0x79c5  ldarg.0
0x79c6  newobj   instance void Microsoft.Crm.Asynchronous.QueueStatisticsHelper::.ctor()
0x79cb  stfld    class Microsoft.Crm.Asynchronous.QueueStatisticsHelper Microsoft.Crm.Asynchronous.MailboxQueueStatisticsCollector::_queueStatisticsHelper
0x79d0  ret
```
