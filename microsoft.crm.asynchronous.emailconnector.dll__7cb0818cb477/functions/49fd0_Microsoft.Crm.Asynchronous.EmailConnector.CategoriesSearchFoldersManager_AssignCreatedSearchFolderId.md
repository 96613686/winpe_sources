# Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::AssignCreatedSearchFolderId

- ea: `0x49fd0`
- end: `0x4a087`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::AssignCreatedSearchFolderId`
- size: `183`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x16c60`
- `0x49c20`
- `0x49fd0`
- `0x4b6d0`
- `0x4b740`
- `0x4b760`
- `0x71300`
- `0x82660`

## string_xrefs

- `0x4a02e`: `Tracked search folder with Id: {0} created for Category with name: {1}`
- `0x4a064`: `Untracked search folder with Id: {0} created for Category with name: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x49fd0  newobj   instance void <>c__DisplayClass12_0::.ctor()
0x49fd5  stloc.0
0x49fd6  ldloc.0
0x49fd7  ldarg.0
0x49fd8  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager <>c__DisplayClass12_0::<>4__this
0x49fdd  ldloc.0
0x49fde  ldarg.1
0x49fdf  stfld    string <>c__DisplayClass12_0::searchFolderDisplayName
0x49fe4  ldarg.0
0x49fe5  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::IsCategorizedTrackingEnabled()
0x49fea  brtrue.s loc_49FED
0x49fec  ret
0x49fed  ldarg.0
0x49fee  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory> Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::mailboxTrackingCategories
0x49ff3  ldloc.0
0x49ff4  ldftn    instance bool <>c__DisplayClass12_0::<AssignCreatedSearchFolderId>b__0(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mtc)
0x49ffa  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool>::.ctor(object, native int)
0x49fff  call     T0x2B000081
0x4a004  stloc.1
0x4a005  ldloc.1
0x4a006  brfalse.s loc_4A086
0x4a008  ldloc.1
0x4a009  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x4a00e  ldloc.0
0x4a00f  ldfld    string <>c__DisplayClass12_0::searchFolderDisplayName
0x4a014  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a019  brfalse.s loc_4A051
0x4a01b  ldloc.1
0x4a01c  ldarg.2
0x4a01d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x4a022  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::set_ExchangeCategorySearchFolderId(string value)
0x4a027  ldarg.0
0x4a028  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::traceHandler
0x4a02d  ldc.i4.3
0x4a02e  ldstr    aTrackedSearchF// "Tracked search folder with Id: {0} crea"...
0x4a033  ldc.i4.2
0x4a034  newarr   [mscorlib]System.Object
0x4a039  dup
0x4a03a  ldc.i4.0
0x4a03b  ldarg.2
0x4a03c  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x4a041  stelem.ref
0x4a042  dup
0x4a043  ldc.i4.1
0x4a044  ldloc.1
0x4a045  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x4a04a  stelem.ref
0x4a04b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4a050  ret
0x4a051  ldloc.1
0x4a052  ldarg.2
0x4a053  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x4a058  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::set_ExchangeCategoryUntrackSearchFolderId(string value)
0x4a05d  ldarg.0
0x4a05e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::traceHandler
0x4a063  ldc.i4.3
0x4a064  ldstr    aUntrackedSearc// "Untracked search folder with Id: {0} cr"...
0x4a069  ldc.i4.2
0x4a06a  newarr   [mscorlib]System.Object
0x4a06f  dup
0x4a070  ldc.i4.0
0x4a071  ldarg.2
0x4a072  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.FolderIdType::get_Id()
0x4a077  stelem.ref
0x4a078  dup
0x4a079  ldc.i4.1
0x4a07a  ldloc.1
0x4a07b  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x4a080  stelem.ref
0x4a081  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4a086  ret
```
