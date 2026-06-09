# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::.ctor

- ea: `0x65380`
- end: `0x655aa`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::.ctor`
- size: `554`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x65340`
- `0x69670`
- `0x6b510`
- `0x6cb10`

## callees

- `0x65380`
- `0x69840`
- `0x69850`
- `0x69890`
- `0x6add0`
- `0x70000`
- `0x70050`
- `0x700c0`
- `0x700d0`
- `0x701b0`
- `0x701c0`

## string_xrefs

- `0x6547b`: `scheduledstart`
- `0x65577`: `scheduledstart`
- `0x65497`: `scheduledend`
- `0x65593`: `scheduledend`
- `0x654b3`: `scheduleddurationminutes`

## pseudocode

```c

```

## disassembly

```asm
0x65380  ldarg.0
0x65381  ldarg.2
0x65382  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::.ctor(class Microsoft.Crm.Asynchronous.EmailConnector.IACTProviderContext context)
0x65387  ldarg.0
0x65388  ldarg.1
0x65389  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::set_Provider(class Microsoft.Crm.Asynchronous.EmailConnector.IProvider value)
0x6538e  ldarg.3
0x6538f  brtrue.s loc_653C6
0x65391  ldarg.0
0x65392  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x65397  brtrue.s loc_653CD
0x65399  ldarg.0
0x6539a  ldarg.0
0x6539b  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IProvider Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_Provider()
0x653a0  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider
0x653a5  callvirt instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService Microsoft.Crm.Asynchronous.EmailConnector.ExchangeProvider::get_ExchangeService()
0x653aa  newobj   instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Appointment::.ctor(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ExchangeService)
0x653af  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::set_Item(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item value)
0x653b4  ldarg.0
0x653b5  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::get_Item()
0x653ba  ldstr    aIpmAppointment// "IPM.Appointment"
0x653bf  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item::set_ItemClass(string)
0x653c4  br.s     loc_653CD
0x653c6  ldarg.0
0x653c7  ldarg.3
0x653c8  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeItem::set_Item(class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.Item value)
0x653cd  ldarg.0
0x653ce  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x653d3  ldstr    aSetrequiredatt// "setrequiredattendees"
0x653d8  ldarg.0
0x653d9  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetRequiredAttendees()
0x653df  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x653e4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x653e9  ldarg.0
0x653ea  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x653ef  ldstr    aSetoptionalatt// "setoptionalattendees"
0x653f4  ldarg.0
0x653f5  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetOptionalAttendees()
0x653fb  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x65400  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65405  ldarg.0
0x65406  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6540b  ldstr    aSetorganizer// "setorganizer"
0x65410  ldarg.0
0x65411  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetOrganizer()
0x65417  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6541c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65421  ldarg.0
0x65422  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x65427  ldstr    aSetcrmpartyinf// "setcrmpartyinfo"
0x6542c  ldarg.0
0x6542d  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetCrmPartyInfo()
0x65433  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x65438  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6543d  ldarg.0
0x6543e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x65443  ldstr    aSetapptstatus// "setapptstatus"
0x65448  ldarg.0
0x65449  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetApptStatus()
0x6544f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x65454  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65459  ldarg.0
0x6545a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6545f  ldstr    aSetglobalobjid// "setglobalobjidandownerapptid"
0x65464  ldarg.0
0x65465  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetGlobalObjIdAndOwnerApptId()
0x6546b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x65470  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65475  ldarg.0
0x65476  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x6547b  ldstr    aScheduledstart// "scheduledstart"
0x65480  ldarg.0
0x65481  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetScheduledStart()
0x65487  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x6548c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65491  ldarg.0
0x65492  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_SetPropertyDelegates()
0x65497  ldstr    aScheduledend// "scheduledend"
0x6549c  ldarg.0
0x6549d  ldftn    instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::SetScheduledEnd()
0x654a3  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction::.ctor(object object, native int method)
0x654a8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.SetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x654ad  ldarg.0
0x654ae  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x654b3  ldstr    aScheduleddurat// "scheduleddurationminutes"
0x654b8  ldarg.0
0x654b9  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetScheduledDurationMinutes()
0x654bf  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x654c4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x654c9  ldarg.0
0x654ca  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x654cf  ldstr    aOrganizer// "organizer"
0x654d4  ldarg.0
0x654d5  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetOrganizer()
0x654db  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x654e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x654e5  ldarg.0
0x654e6  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x654eb  ldstr    aGetstatuscode// "getstatuscode"
0x654f0  ldarg.0
0x654f1  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetStatusCode()
0x654f7  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x654fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65501  ldarg.0
0x65502  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x65507  ldstr    aOriginalstartd// "originalstartdate"
0x6550c  ldarg.0
0x6550d  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetOriginalStartDate()
0x65513  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x65518  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6551d  ldarg.0
0x6551e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x65523  ldstr    aLastmodificati// "lastmodificationdate"
0x65528  ldarg.0
0x65529  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetLastModificationDate()
0x6552f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x65534  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65539  ldarg.0
0x6553a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6553f  ldstr    aIsrecurring// "isrecurring"
0x65544  ldarg.0
0x65545  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetIsRecurring()
0x6554b  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x65550  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65555  ldarg.0
0x65556  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x6555b  ldstr    aBody// "body"
0x65560  ldarg.0
0x65561  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetAppointmenBody()
0x65567  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x6556c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x65571  ldarg.0
0x65572  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x65577  ldstr    aScheduledstart// "scheduledstart"
0x6557c  ldarg.0
0x6557d  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetScheduledStart()
0x65583  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x65588  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x6558d  ldarg.0
0x6558e  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction> Microsoft.Crm.Asynchronous.EmailConnector.SyncItemBase::get_GetPropertyDelegates()
0x65593  ldstr    aScheduledend// "scheduledend"
0x65598  ldarg.0
0x65599  ldftn    instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeAppointmentItem::GetScheduledEnd()
0x6559f  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction::.ctor(object object, native int method)
0x655a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Asynchronous.EmailConnector.GetPropertyDelegateFunction>::Add(var<u1>, !!T0)
0x655a9  ret
```
