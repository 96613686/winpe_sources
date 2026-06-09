# Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationCommand::UnlockMailboxes

- ea: `0x718a0`
- end: `0x719a7`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.MailboxOperationCommand::UnlockMailboxes`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x71650`

## callees

- `0x413a0`
- `0x718a0`
- `0x725b0`
- `0x72600`
- `0x74970`

## string_xrefs

- `0x718b7`: `isserviceaccount`
- `0x718ce`: `isserviceaccount`
- `0x718e7`: `MailboxOperationCommand.UnlockMailboxes: Deleting Service Accounts for Mailbox: {0} StackTrace:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x718a0  ldarg.1
0x718a1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x718a6  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::.ctor(valuetype [mscorlib]System.Guid OrganizationId)
0x718ab  stloc.0
0x718ac  ldarg.1
0x718ad  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x718b2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x718b7  ldstr    aIsserviceaccou// "isserviceaccount"
0x718bc  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x718c1  brfalse.s loc_7193C
0x718c3  ldarg.1
0x718c4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x718c9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x718ce  ldstr    aIsserviceaccou// "isserviceaccount"
0x718d3  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x718d8  unbox.any [mscorlib]System.Boolean
0x718dd  brfalse.s loc_7193C
0x718df  ldarg.1
0x718e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x718e5  ldc.i4.s 0x3D
0x718e7  ldstr    aMailboxoperati_0// "MailboxOperationCommand.UnlockMailboxes"...
0x718ec  ldc.i4.2
0x718ed  newarr   [mscorlib]System.Object
0x718f2  dup
0x718f3  ldc.i4.0
0x718f4  ldarg.1
0x718f5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x718fa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x718ff  stloc.1
0x71900  ldloca.s 1
0x71902  constrained. [mscorlib]System.Guid
0x71908  callvirt instance string [mscorlib]System.Object::ToString()
0x7190d  stelem.ref
0x7190e  dup
0x7190f  ldc.i4.1
0x71910  call     string [mscorlib]System.Environment::get_StackTrace()
0x71915  stelem.ref
0x71916  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7191b  ldloc.0
0x7191c  ldarg.1
0x7191d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x71922  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x71927  stloc.1
0x71928  ldloca.s 1
0x7192a  constrained. [mscorlib]System.Guid
0x71930  callvirt instance string [mscorlib]System.Object::ToString()
0x71935  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::DeleteServiceAccountMailbox(string mailboxId)
0x7193a  br.s     loc_7195E
0x7193c  ldloc.0
0x7193d  ldarg.1
0x7193e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x71943  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.Asynchronous.EmailConnector.Utility::GetUTCDateWithoutMilliseconds()
0x71948  stloc.2
0x71949  ldloca.s 2
0x7194b  ldc.r8   5.0
0x71954  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddMinutes(float64)
0x71959  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxDataAccess::UnlockMailbox(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, valuetype [mscorlib]System.DateTime postponeUntil)
0x7195e  leave.s  loc_719A6
0x71960  stloc.3
0x71961  ldloc.3
0x71962  ldarg.1
0x71963  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_OrganizationId()
0x71968  ldc.i4.s 0x3D
0x7196a  ldstr    aExceptionUnloc// "Exception unlocking mailboxes for async"...
0x7196f  ldc.i4.3
0x71970  newarr   [mscorlib]System.Object
0x71975  dup
0x71976  ldc.i4.0
0x71977  ldarg.1
0x71978  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.AsyncEventBase::get_EventId()
0x7197d  box      [mscorlib]System.Guid
0x71982  stelem.ref
0x71983  dup
0x71984  ldc.i4.1
0x71985  ldarg.1
0x71986  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.EmailConnector.MailboxAsyncEvent::get_Mailbox()
0x7198b  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x71990  box      [mscorlib]System.Guid
0x71995  stelem.ref
0x71996  dup
0x71997  ldc.i4.2
0x71998  ldloc.3
0x71999  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x7199e  stelem.ref
0x7199f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x719a4  leave.s  loc_719A6
0x719a6  ret
```
