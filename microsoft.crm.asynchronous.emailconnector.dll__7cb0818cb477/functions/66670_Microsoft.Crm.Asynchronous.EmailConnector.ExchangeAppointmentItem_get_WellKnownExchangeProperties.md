# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::get_WellKnownExchangeProperties

- ea: `0x66670`
- end: `0x666f1`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::get_WellKnownExchangeProperties`
- size: `129`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x66700`
- `0x66770`
- `0x667c0`

## callees

- `0x66670`

## string_xrefs

- `0x666a0`: `scheduledstart`
- `0x666a8`: `scheduledend`

## pseudocode

```c

```

## disassembly

```asm
0x66670  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::_wellKnownExchangeProperties
0x66675  brtrue.s loc_666EB
0x66677  ldc.i4.s 0xC
0x66679  newarr   [mscorlib]System.String
0x6667e  dup
0x6667f  ldc.i4.0
0x66680  ldstr    aSubject// "subject"
0x66685  stelem.ref
0x66686  dup
0x66687  ldc.i4.1
0x66688  ldstr    aSetbody// "setbody"
0x6668d  stelem.ref
0x6668e  dup
0x6668f  ldc.i4.2
0x66690  ldstr    aLocation// "location"
0x66695  stelem.ref
0x66696  dup
0x66697  ldc.i4.3
0x66698  ldstr    aIsalldayevent// "isalldayevent"
0x6669d  stelem.ref
0x6669e  dup
0x6669f  ldc.i4.4
0x666a0  ldstr    aScheduledstart// "scheduledstart"
0x666a5  stelem.ref
0x666a6  dup
0x666a7  ldc.i4.5
0x666a8  ldstr    aScheduledend// "scheduledend"
0x666ad  stelem.ref
0x666ae  dup
0x666af  ldc.i4.6
0x666b0  ldstr    aSetrequiredatt// "setrequiredattendees"
0x666b5  stelem.ref
0x666b6  dup
0x666b7  ldc.i4.7
0x666b8  ldstr    aSetoptionalatt// "setoptionalattendees"
0x666bd  stelem.ref
0x666be  dup
0x666bf  ldc.i4.8
0x666c0  ldstr    aSetorganizer// "setorganizer"
0x666c5  stelem.ref
0x666c6  dup
0x666c7  ldc.i4.s 9
0x666c9  ldstr    aSetapptstatus// "setapptstatus"
0x666ce  stelem.ref
0x666cf  dup
0x666d0  ldc.i4.s 0xA
0x666d2  ldstr    aPrioritycode// "prioritycode"
0x666d7  stelem.ref
0x666d8  dup
0x666d9  ldc.i4.s 0xB
0x666db  ldstr    aSetrecurrencep// "setrecurrencepattern"
0x666e0  stelem.ref
0x666e1  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<string>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x666e6  stsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::_wellKnownExchangeProperties
0x666eb  ldsfld   class [System.Core]System.Collections.Generic.HashSet`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::_wellKnownExchangeProperties
0x666f0  ret
```
