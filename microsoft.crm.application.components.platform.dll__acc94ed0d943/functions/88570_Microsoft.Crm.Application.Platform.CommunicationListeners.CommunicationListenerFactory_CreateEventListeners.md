# Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::CreateEventListeners

- ea: `0x88570`
- end: `0x88705`
- name: `Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::CreateEventListeners`
- size: `405`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x88530`

## callees

- `0x88560`
- `0x88570`
- `0x88a80`
- `0x88d60`
- `0x88da0`
- `0x88dd0`
- `0x88df0`
- `0x88e10`
- `0x88e50`
- `0x88e70`
- `0x88eb0`
- `0x9ca50`

## string_xrefs

- `0x88645`: `CreateRequest`
- `0x88657`: `DeleteRequest`
- `0x88699`: `UpdateRequest`
- `0x886a8`: `UpdateUserSettingsSystemUserRequest`

## pseudocode

```c

```

## disassembly

```asm
0x88570  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::.ctor()
0x88575  stloc.0
0x88576  call     class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::get_GlobalListeners()
0x8857b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::GetEnumerator()
0x88580  stloc.2
0x88581  br.s     loc_88591
0x88583  ldloc.2
0x88584  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::get_Current()
0x88589  stloc.3
0x8858a  ldloc.0
0x8858b  ldloc.3
0x8858c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener>::Add(var<u1>)
0x88591  ldloc.2
0x88592  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x88597  brtrue.s loc_88583
0x88599  leave.s  loc_885A5
0x8859b  ldloc.2
0x8859c  brfalse.s loc_885A4
0x8859e  ldloc.2
0x8859f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x885a4  endfinally
0x885a5  ldarg.1
0x885a6  stloc.1
0x885a7  ldloc.1
0x885a8  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x885ad  stloc.s  4
0x885af  ldloc.s  4
0x885b1  ldc.i4   0x4D74C27A
0x885b6  bgt.un.s loc_885F8
0x885b8  ldloc.s  4
0x885ba  ldc.i4   0x3554600D
0x885bf  bgt.un.s loc_885DE
0x885c1  ldloc.s  4
0x885c3  ldc.i4   0x112CEC8D
0x885c8  beq      loc_88698
0x885cd  ldloc.s  4
0x885cf  ldc.i4   0x3554600D
0x885d4  beq      loc_88689
0x885d9  br       loc_886FB
0x885de  ldloc.s  4
0x885e0  ldc.i4   0x3D930E29
0x885e5  beq.s    loc_88632
0x885e7  ldloc.s  4
0x885e9  ldc.i4   0x4D74C27A
0x885ee  beq      loc_8867A
0x885f3  br       loc_886FB
0x885f8  ldloc.s  4
0x885fa  ldc.i4   0xDC6068F1
0x885ff  bgt.un.s loc_8861B
0x88601  ldloc.s  4
0x88603  ldc.i4   0x50D8588C
0x88608  beq.s    loc_88668
0x8860a  ldloc.s  4
0x8860c  ldc.i4   0xDC6068F1
0x88611  beq      loc_886A7
0x88616  br       loc_886FB
0x8861b  ldloc.s  4
0x8861d  ldc.i4   0xF663FCDA
0x88622  beq.s    loc_88644
0x88624  ldloc.s  4
0x88626  ldc.i4   0xFC7AC9A7
0x8862b  beq.s    loc_88656
0x8862d  br       loc_886FB
0x88632  ldloc.1
0x88633  ldstr    aBookrequest// "BookRequest"
0x88638  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8863d  brtrue.s loc_886B6
0x8863f  br       loc_886FB
0x88644  ldloc.1
0x88645  ldstr    aCreaterequest// "CreateRequest"
0x8864a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8864f  brtrue.s loc_886BF
0x88651  br       loc_886FB
0x88656  ldloc.1
0x88657  ldstr    aDeleterequest// "DeleteRequest"
0x8865c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88661  brtrue.s loc_886C8
0x88663  br       loc_886FB
0x88668  ldloc.1
0x88669  ldstr    aInviteuserrequ// "InviteUserRequest"
0x8866e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88673  brtrue.s loc_886D1
0x88675  br       loc_886FB
0x8867a  ldloc.1
0x8867b  ldstr    aReschedulerequ// "RescheduleRequest"
0x88680  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88685  brtrue.s loc_886DA
0x88687  br.s     loc_886FB
0x88689  ldloc.1
0x8868a  ldstr    aSetstatereques// "SetStateRequest"
0x8868f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x88694  brtrue.s loc_886E3
0x88696  br.s     loc_886FB
0x88698  ldloc.1
0x88699  ldstr    aUpdaterequest// "UpdateRequest"
0x8869e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x886a3  brtrue.s loc_886EC
0x886a5  br.s     loc_886FB
0x886a7  ldloc.1
0x886a8  ldstr    aUpdateusersett// "UpdateUserSettingsSystemUserRequest"
0x886ad  call     bool [mscorlib]System.String::op_Equality(string, string)
0x886b2  brtrue.s loc_886F5
0x886b4  br.s     loc_886FB
0x886b6  ldloc.0
0x886b7  ldarg.0
0x886b8  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForBookRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886bd  br.s     loc_886FB
0x886bf  ldloc.0
0x886c0  ldarg.0
0x886c1  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForCreateRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886c6  br.s     loc_886FB
0x886c8  ldloc.0
0x886c9  ldarg.0
0x886ca  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForDeleteRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886cf  br.s     loc_886FB
0x886d1  ldloc.0
0x886d2  ldarg.0
0x886d3  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForInviteUserRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886d8  br.s     loc_886FB
0x886da  ldloc.0
0x886db  ldarg.0
0x886dc  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForRescheduleRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886e1  br.s     loc_886FB
0x886e3  ldloc.0
0x886e4  ldarg.0
0x886e5  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForSetStateRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886ea  br.s     loc_886FB
0x886ec  ldloc.0
0x886ed  ldarg.0
0x886ee  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForUpdateRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string entityName)
0x886f3  br.s     loc_886FB
0x886f5  ldloc.0
0x886f6  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddHandlersForUpdateUserSettingsSystemUserRequest(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners)
0x886fb  ldloc.0
0x886fc  ldloc.1
0x886fd  ldarg.0
0x886fe  call     void Microsoft.Crm.Application.Platform.CommunicationListeners.CommunicationListenerFactory::AddSolutionListenerByRequestName(class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Application.Platform.CommunicationListeners.EventListener> eventListeners, string requestName, string entityName)
0x88703  ldloc.0
0x88704  ret
```
