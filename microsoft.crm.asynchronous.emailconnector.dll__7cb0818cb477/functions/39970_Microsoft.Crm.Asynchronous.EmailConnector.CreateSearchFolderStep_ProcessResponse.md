# Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::ProcessResponse

- ea: `0x39970`
- end: `0x39b11`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::ProcessResponse`
- size: `417`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0xabc0`
- `0x14090`
- `0x16c60`
- `0x21720`
- `0x21780`
- `0x245c0`
- `0x25060`
- `0x25110`
- `0x39970`
- `0x39b20`
- `0x3ac40`
- `0x417a0`
- `0x41be0`
- `0x41df0`
- `0x41e00`
- `0x41e10`
- `0x41e20`
- `0x41e30`
- `0x4af20`

## string_xrefs

- `0x399ee`: `CrmEmailMessagesPendingLinking`

## pseudocode

```c

```

## disassembly

```asm
0x39970  ldarg.0
0x39971  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39976  ldc.i4.s 0xA
0x39978  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_ExecutionStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionStatus value)
0x3997d  ldarg.0
0x3997e  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::IsInvalidResponse()
0x39983  brtrue   loc_39B0F
0x39988  ldarg.0
0x39989  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IEmailProviderContext Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::Context
0x3998e  callvirt instance class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent Microsoft.Crm.Asynchronous.EmailConnector.IActivityProviderContext::get_AsyncEvent()
0x39993  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.IAsyncEvent::get_OrganizationId()
0x39998  call     bool Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::IsSSSCustomPropertyFCBEnabled(valuetype [mscorlib]System.Guid organizationId)
0x3999d  stloc.0
0x3999e  ldc.i4.0
0x3999f  stloc.1
0x399a0  br       loc_39AF2
0x399a5  ldarg.0
0x399a6  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::response
0x399ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x399b0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x399b5  ldloc.1
0x399b6  ldelem.ref
0x399b7  stloc.2
0x399b8  ldloc.2
0x399b9  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.ResponseClassType Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType::get_ResponseClass()
0x399be  brfalse.s loc_399DD
0x399c0  ldarg.0
0x399c1  ldloc.2
0x399c2  ldarg.0
0x399c3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::searchFolders
0x399c8  ldloc.1
0x399c9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Item(!!T0)
0x399ce  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_DisplayName()
0x399d3  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::ReportError(class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType responseItem, string displayName)
0x399d8  br       loc_39AEE
0x399dd  ldarg.0
0x399de  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::searchFolders
0x399e3  ldloc.1
0x399e4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Item(!!T0)
0x399e9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_DisplayName()
0x399ee  ldstr    aCrmemailmessag// "CrmEmailMessagesPendingLinking"
0x399f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x399f8  brfalse.s loc_39A44
0x399fa  ldarg.0
0x399fb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39a00  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_SearchFolderId()
0x39a05  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x39a0a  brfalse.s loc_39A44
0x39a0c  ldarg.0
0x39a0d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39a12  ldarg.0
0x39a13  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::response
0x39a18  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x39a1d  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x39a22  ldloc.1
0x39a23  ldelem.ref
0x39a24  castclass Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType
0x39a29  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType[] Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType::get_Folders()
0x39a2e  ldc.i4.0
0x39a2f  ldelem.ref
0x39a30  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_FolderId()
0x39a35  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x39a3a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_SearchFolderId(string value)
0x39a3f  br       loc_39AEE
0x39a44  ldarg.0
0x39a45  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::searchFolders
0x39a4a  ldloc.1
0x39a4b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Item(!!T0)
0x39a50  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_DisplayName()
0x39a55  ldstr    aCrmemailmessag_0// "CrmEmailMessagesWithCustomProperty"
0x39a5a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39a5f  ldloc.0
0x39a60  and
0x39a61  brfalse.s loc_39AAA
0x39a63  ldarg.0
0x39a64  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39a69  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CustomPropertySearchFolderId()
0x39a6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x39a73  brfalse.s loc_39AAA
0x39a75  ldarg.0
0x39a76  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39a7b  ldarg.0
0x39a7c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::response
0x39a81  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x39a86  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x39a8b  ldloc.1
0x39a8c  ldelem.ref
0x39a8d  castclass Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType
0x39a92  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType[] Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType::get_Folders()
0x39a97  ldc.i4.0
0x39a98  ldelem.ref
0x39a99  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_FolderId()
0x39a9e  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x39aa3  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_CustomPropertySearchFolderId(string value)
0x39aa8  br.s     loc_39AEE
0x39aaa  ldarg.0
0x39aab  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39ab0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategoriesSearchFoldersManager()
0x39ab5  ldarg.0
0x39ab6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::searchFolders
0x39abb  ldloc.1
0x39abc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Item(!!T0)
0x39ac1  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_DisplayName()
0x39ac6  ldarg.0
0x39ac7  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.CreateFolderResponseType Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::response
0x39acc  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType Microsoft.Crm.Asynchronous.EmailConnector.BaseResponseMessageType::get_ResponseMessages()
0x39ad1  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ResponseMessageType[] Microsoft.Crm.Asynchronous.EmailConnector.ArrayOfResponseMessagesType::get_Items()
0x39ad6  ldloc.1
0x39ad7  ldelem.ref
0x39ad8  castclass Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType
0x39add  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType[] Microsoft.Crm.Asynchronous.EmailConnector.FolderInfoResponseMessageType::get_Folders()
0x39ae2  ldc.i4.0
0x39ae3  ldelem.ref
0x39ae4  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType::get_FolderId()
0x39ae9  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager::AssignCreatedSearchFolderId(string searchFolderDisplayName, class Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType folderId)
0x39aee  ldloc.1
0x39aef  ldc.i4.1
0x39af0  add
0x39af1  stloc.1
0x39af2  ldloc.1
0x39af3  ldarg.0
0x39af4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType> Microsoft.Crm.Asynchronous.EmailConnector.CreateSearchFolderStep::searchFolders
0x39af9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::get_Count()
0x39afe  blt      loc_399A5
0x39b03  ldarg.0
0x39b04  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x39b09  ldc.i4.2
0x39b0a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::set_ExecutionStatus(valuetype Microsoft.Crm.Asynchronous.EmailConnector.ExecutionStatus value)
0x39b0f  ldc.i4.1
0x39b10  ret
```
