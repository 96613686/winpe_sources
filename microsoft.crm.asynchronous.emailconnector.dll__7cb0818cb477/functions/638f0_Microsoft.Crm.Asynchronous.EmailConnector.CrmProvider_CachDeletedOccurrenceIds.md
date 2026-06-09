# Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CachDeletedOccurrenceIds

- ea: `0x638f0`
- end: `0x63956`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::CachDeletedOccurrenceIds`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x638b0`

## callees

- `0x638f0`
- `0x63960`
- `0x63980`
- `0x65230`
- `0x6f560`

## string_xrefs

- `0x638f1`: `deletedexceptionslist`
- `0x63901`: `deletedexceptionslist`

## pseudocode

```c

```

## disassembly

```asm
0x638f0  ldarg.2
0x638f1  ldstr    aDeletedexcepti// "deletedexceptionslist"
0x638f6  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x638fb  brtrue.s loc_63900
0x638fd  ldnull
0x638fe  br.s     loc_63910
0x63900  ldarg.2
0x63901  ldstr    aDeletedexcepti// "deletedexceptionslist"
0x63906  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x6390b  castclass [mscorlib]System.String
0x63910  call     class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.DateTime> Microsoft.Crm.Asynchronous.EmailConnector.OriginalPropertiesForRecurringAppointment::GetExceptionOriginalDates(string deletedExceptionListXml)
0x63915  callvirt instance valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<var<u1>> class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.DateTime>::GetEnumerator()
0x6391a  stloc.0
0x6391b  br.s     loc_6393C
0x6391d  ldloca.s 0
0x6391f  call     instance var<u1> valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.DateTime>::get_Current()
0x63924  stloc.1
0x63925  ldarg.1
0x63926  ldloc.1
0x63927  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.AlternateOccurrenceAppointmentId::.ctor(string recurringMasterId, valuetype [mscorlib]System.DateTime originalStartDate)
0x6392c  stloc.2
0x6392d  ldarg.0
0x6392e  call     instance string Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::GetSurrogateOccurrenceAppointmentId()
0x63933  stloc.3
0x63934  ldarg.0
0x63935  ldloc.3
0x63936  ldloc.2
0x63937  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmProvider::AddOccurrenceIds(string occurrenceAppointmentId, class Microsoft.Crm.Asynchronous.EmailConnector.AlternateOccurrenceAppointmentId alternateOccurrenceAppointmentId)
0x6393c  ldloca.s 0
0x6393e  call     instance bool valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.DateTime>::MoveNext()
0x63943  brtrue.s loc_6391D
0x63945  leave.s  loc_63955
0x63947  ldloca.s 0
0x63949  constrained. valuetype [System.Core]System.Collections.Generic.HashSet`1/Enumerator<valuetype [mscorlib]System.DateTime>
0x6394f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x63954  endfinally
0x63955  ret
```
