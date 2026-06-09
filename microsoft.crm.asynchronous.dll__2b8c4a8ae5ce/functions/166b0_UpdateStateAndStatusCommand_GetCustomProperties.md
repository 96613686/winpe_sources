# UpdateStateAndStatusCommand::GetCustomProperties

- ea: `0x166b0`
- end: `0x167e9`
- name: `UpdateStateAndStatusCommand::GetCustomProperties`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16870`

## callees

- `0x220`
- `0x2730`
- `0x2f10`
- `0x2f30`
- `0x2f50`
- `0x2fb0`
- `0x2fd0`
- `0x2ff0`
- `0x3010`
- `0x166b0`

## pseudocode

```c

```

## disassembly

```asm
0x166b0  ldnull
0x166b1  stloc.0
0x166b2  ldarg.0
0x166b3  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess UpdateStateAndStatusCommand::_queueDataAccess
0x166b8  dup
0x166b9  brtrue.s loc_166BF
0x166bb  pop
0x166bc  ldnull
0x166bd  br.s     loc_166D0
0x166bf  ldfld    class Microsoft.Crm.Asynchronous.AsyncOperationQueueManagerBase Microsoft.Crm.Asynchronous.AsyncOperationQueueDataAccess::_queueManager
0x166c4  dup
0x166c5  brtrue.s loc_166CB
0x166c7  pop
0x166c8  ldnull
0x166c9  br.s     loc_166D0
0x166cb  callvirt instance string Microsoft.Crm.Asynchronous.AsyncManagerBase::get_Name()
0x166d0  dup
0x166d1  brtrue.s loc_166D9
0x166d3  pop
0x166d4  ldsfld   string [mscorlib]System.String::Empty
0x166d9  stloc.1
0x166da  ldarg.0
0x166db  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x166e0  brtrue.s loc_1671A
0x166e2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x166e7  stloc.0
0x166e8  ldloc.0
0x166e9  ldstr    aAsyncoperation_1// "AsyncOperationId"
0x166ee  ldarg.0
0x166ef  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x166f4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncEventState::get_EventId()
0x166f9  stloc.2
0x166fa  ldloca.s 2
0x166fc  constrained. [mscorlib]System.Guid
0x16702  callvirt instance string [mscorlib]System.Object::ToString()
0x16707  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1670c  ldloc.0
0x1670d  ldstr    aAsyncmanagerna// "AsyncManagerNames"
0x16712  ldloc.1
0x16713  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x16718  br.s     loc_1674F
0x1671a  call     class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::get_Instance()
0x1671f  ldarg.0
0x16720  ldfld    class Microsoft.Crm.Asynchronous.AsyncEvent UpdateStateAndStatusCommand::_asyncEvent
0x16725  call     class Microsoft.Crm.Asynchronous.AsyncEventAdapter Microsoft.Crm.Asynchronous.AsyncEventAdapter::Create(class Microsoft.Crm.Asynchronous.AsyncEvent instance)
0x1672a  ldloc.1
0x1672b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncXrmLogger::GetCustomProperties(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.IAsyncExecutionUnit, string)
0x16730  stloc.0
0x16731  ldloc.0
0x16732  ldstr    aRetrycount// "RetryCount"
0x16737  ldarg.0
0x16738  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x1673d  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_CurrentRetryCount()
0x16742  stloc.3
0x16743  ldloca.s 3
0x16745  call     instance string [mscorlib]System.Int32::ToString()
0x1674a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1674f  ldloc.0
0x16750  ldstr    aAsyncoperation_2// "AsyncOperationState"
0x16755  ldarg.0
0x16756  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x1675b  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewState()
0x16760  stloc.3
0x16761  ldloca.s 3
0x16763  call     instance string [mscorlib]System.Int32::ToString()
0x16768  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1676d  ldloc.0
0x1676e  ldstr    aAsyncoperation_3// "AsyncOperationStatus"
0x16773  ldarg.0
0x16774  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x16779  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_NewStatus()
0x1677e  stloc.3
0x1677f  ldloca.s 3
0x16781  call     instance string [mscorlib]System.Int32::ToString()
0x16786  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1678b  ldloc.0
0x1678c  ldstr    aErrorcode_0// "ErrorCode"
0x16791  ldarg.0
0x16792  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x16797  callvirt instance int32 Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorCode()
0x1679c  stloc.3
0x1679d  ldloca.s 3
0x1679f  call     instance string [mscorlib]System.Int32::ToString()
0x167a4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x167a9  ldloc.0
0x167aa  ldstr    aErrormessage_0// "ErrorMessage"
0x167af  ldarg.0
0x167b0  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x167b5  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_ErrorMessage()
0x167ba  dup
0x167bb  brtrue.s loc_167C3
0x167bd  pop
0x167be  ldsfld   string [mscorlib]System.String::Empty
0x167c3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x167c8  ldloc.0
0x167c9  ldstr    aFriendlymessag_2// "FriendlyMessage"
0x167ce  ldarg.0
0x167cf  ldfld    class Microsoft.Crm.Asynchronous.AsyncEventState UpdateStateAndStatusCommand::_newEventState
0x167d4  callvirt instance string Microsoft.Crm.Asynchronous.AsyncEventState::get_FriendlyMessage()
0x167d9  dup
0x167da  brtrue.s loc_167E2
0x167dc  pop
0x167dd  ldsfld   string [mscorlib]System.String::Empty
0x167e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x167e7  ldloc.0
0x167e8  ret
```
