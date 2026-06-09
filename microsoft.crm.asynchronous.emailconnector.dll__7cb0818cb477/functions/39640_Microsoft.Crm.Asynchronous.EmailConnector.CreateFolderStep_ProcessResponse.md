# Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::ProcessResponse

- ea: `0x39640`
- end: `0x397b3`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::ProcessResponse`
- size: `371`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x14090`
- `0x16c60`
- `0x21720`
- `0x245c0`
- `0x25060`
- `0x25110`
- `0x32970`
- `0x32a00`
- `0x39640`
- `0x3ab40`
- `0x3ac40`
- `0x41180`
- `0x41be0`
- `0x41d90`
- `0x41da0`
- `0x42060`

## string_xrefs

- `0x39673`: `Failure returned when trying to Create Undeliverable Folder.\nResponse from Server:\n{0}`
- `0x3976f`: `No folder returned in the response after CreateFolderStep. Mailbox: {0}. Response from Server:\n{1}`

## pseudocode

```c

```

## disassembly

```asm
0x39640  ldarg.0
0x39641  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39646  ldc.i4.s 0xA
0x39648  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_ExecutionStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionStatus value)
0x3964d  ldarg.0
0x3964e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::IsInvalidResponse()
0x39653  brtrue   loc_397B1
0x39658  ldarg.0
0x39659  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::response
0x3965e  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x39663  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x39668  ldc.i4.0
0x39669  ldelem.ref
0x3966a  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x3966f  brfalse.s loc_396B7
0x39671  ldarg.0
0x39672  ldc.i4.1
0x39673  ldstr    aFailureReturne// "Failure returned when trying to Create "...
0x39678  ldc.i4.1
0x39679  newarr   [mscorlib]System.Object
0x3967e  dup
0x3967f  ldc.i4.0
0x39680  ldarg.0
0x39681  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::response
0x39686  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3968b  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x39690  ldc.i4.0
0x39691  ldelem.ref
0x39692  call     T0x2B000070
0x39697  stelem.ref
0x39698  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x3969d  ldarg.0
0x3969e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x396a3  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x396a8  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType> Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_FailedEmails()
0x396ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType>::Clear()
0x396b2  br       loc_397B1
0x396b7  ldarg.0
0x396b8  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::response
0x396bd  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x396c2  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x396c7  ldc.i4.0
0x396c8  ldelem.ref
0x396c9  isinst   Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType
0x396ce  brtrue.s loc_396D3
0x396d0  ldnull
0x396d1  br.s     loc_396EF
0x396d3  ldarg.0
0x396d4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::response
0x396d9  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x396de  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x396e3  ldc.i4.0
0x396e4  ldelem.ref
0x396e5  castclass Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType
0x396ea  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType[] Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType::get_Folders()
0x396ef  stloc.0
0x396f0  ldloc.0
0x396f1  brfalse.s loc_3976D
0x396f3  ldloc.0
0x396f4  ldlen
0x396f5  conv.i4
0x396f6  ldc.i4.1
0x396f7  bne.un.s loc_3976D
0x396f9  ldloc.0
0x396fa  ldc.i4.0
0x396fb  ldelem.ref
0x396fc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_FolderId()
0x39701  brfalse.s loc_3976D
0x39703  ldarg.0
0x39704  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39709  ldloc.0
0x3970a  ldc.i4.0
0x3970b  ldelem.ref
0x3970c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_FolderId()
0x39711  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x39716  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_UndeliverableFolder(string value)
0x3971b  ldstr    aMailbox// "mailbox"
0x39720  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x39725  dup
0x39726  ldarg.0
0x39727  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x3972c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x39731  ldstr    aMailboxid// "mailboxid"
0x39736  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x3973b  unbox.any [mscorlib]System.Guid
0x39740  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x39745  dup
0x39746  ldstr    aUndeliverablef// "undeliverablefolder"
0x3974b  ldarg.0
0x3974c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39751  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_UndeliverableFolder()
0x39756  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x3975b  ldarg.0
0x3975c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x39761  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x39766  call     void Microsoft.Crm.Asynchronous.EmailConnector.Utility::UpdateMailboxEntity(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity mailbox, valuetype [mscorlib]System.Guid organizationId)
0x3976b  br.s     loc_397B1
0x3976d  ldarg.0
0x3976e  ldc.i4.1
0x3976f  ldstr    aNoFolderReturn// "No folder returned in the response afte"...
0x39774  ldc.i4.2
0x39775  newarr   [mscorlib]System.Object
0x3977a  dup
0x3977b  ldc.i4.0
0x3977c  ldarg.0
0x3977d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39782  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState Microsoft.Crm.Asynchronous.EmailConnector.IIncomingEmailProvider::get_Mailbox()
0x39787  ldstr    aMailboxid// "mailboxid"
0x3978c  callvirt instance object Microsoft.Crm.Asynchronous.EmailConnector.IncomingEmailState::get_Item(string attributeName)
0x39791  stelem.ref
0x39792  dup
0x39793  ldc.i4.1
0x39794  ldarg.0
0x39795  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderStep::response
0x3979a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x3979f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x397a4  ldc.i4.0
0x397a5  ldelem.ref
0x397a6  call     T0x2B000070
0x397ab  stelem.ref
0x397ac  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x397b1  ldc.i4.1
0x397b2  ret
```
