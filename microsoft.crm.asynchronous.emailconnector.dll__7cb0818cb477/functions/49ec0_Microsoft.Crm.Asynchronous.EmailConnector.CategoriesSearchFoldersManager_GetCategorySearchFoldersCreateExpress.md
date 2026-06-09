# Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::GetCategorySearchFoldersCreateExpressions

- ea: `0x49ec0`
- end: `0x49fca`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::GetCategorySearchFoldersCreateExpressions`
- size: `266`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x49c20`
- `0x49ec0`
- `0x4a1c0`
- `0x4a2a0`
- `0x4b6d0`
- `0x71300`

## string_xrefs

- `0x49f1f`: `Added the Tracked search folder create expression for the Category with Name: {0}`
- `0x49f9b`: `Added the Untracked search folder create expression for the Category with Name: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x49ec0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::.ctor()
0x49ec5  stloc.0
0x49ec6  ldarg.0
0x49ec7  call     instance bool Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::IsCategorizedTrackingEnabled()
0x49ecc  brtrue.s loc_49ED0
0x49ece  ldloc.0
0x49ecf  ret
0x49ed0  ldarg.0
0x49ed1  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory> Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::mailboxTrackingCategories
0x49ed6  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool> <>c::<>9__11_0
0x49edb  dup
0x49edc  brtrue.s loc_49EF5
0x49ede  pop
0x49edf  ldsfld   class <>c <>c::<>9
0x49ee4  ldftn    instance bool <>c::<GetCategorySearchFoldersCreateExpressions>b__11_0(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mtc)
0x49eea  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool>::.ctor(object, native int)
0x49eef  dup
0x49ef0  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool> <>c::<>9__11_0
0x49ef5  call     T0x2B000083
0x49efa  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::GetEnumerator()
0x49eff  stloc.1
0x49f00  br.s     loc_49F38
0x49f02  ldloc.1
0x49f03  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::get_Current()
0x49f08  stloc.2
0x49f09  ldloc.0
0x49f0a  ldarg.0
0x49f0b  ldloc.2
0x49f0c  ldarg.1
0x49f0d  ldarg.2
0x49f0e  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SearchFolderType Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::CreateCategoryTrackerSearchFolder(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mailboxTrackingCategory, class Microsoft.Crm.Asynchronous.EmailConnector.DistinguishedFolderIdType baseFolderId, class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType categoryTrackedExtendedFieldType)
0x49f13  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::Add(var<u1>)
0x49f18  ldarg.0
0x49f19  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::traceHandler
0x49f1e  ldc.i4.3
0x49f1f  ldstr    aAddedTheTracke// "Added the Tracked search folder create "...
0x49f24  ldc.i4.1
0x49f25  newarr   [mscorlib]System.Object
0x49f2a  dup
0x49f2b  ldc.i4.0
0x49f2c  ldloc.2
0x49f2d  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x49f32  stelem.ref
0x49f33  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x49f38  ldloc.1
0x49f39  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x49f3e  brtrue.s loc_49F02
0x49f40  leave.s  loc_49F4C
0x49f42  ldloc.1
0x49f43  brfalse.s loc_49F4B
0x49f45  ldloc.1
0x49f46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49f4b  endfinally
0x49f4c  ldarg.0
0x49f4d  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory> Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::mailboxTrackingCategories
0x49f52  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool> <>c::<>9__11_1
0x49f57  dup
0x49f58  brtrue.s loc_49F71
0x49f5a  pop
0x49f5b  ldsfld   class <>c <>c::<>9
0x49f60  ldftn    instance bool <>c::<GetCategorySearchFoldersCreateExpressions>b__11_1(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mtc)
0x49f66  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool>::.ctor(object, native int)
0x49f6b  dup
0x49f6c  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool> <>c::<>9__11_1
0x49f71  call     T0x2B000083
0x49f76  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::GetEnumerator()
0x49f7b  stloc.1
0x49f7c  br.s     loc_49FB4
0x49f7e  ldloc.1
0x49f7f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::get_Current()
0x49f84  stloc.3
0x49f85  ldloc.0
0x49f86  ldarg.0
0x49f87  ldloc.3
0x49f88  ldarg.1
0x49f89  ldarg.2
0x49f8a  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.SearchFolderType Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::CreateCategoryUnTrackedSearchFolder(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mailboxTrackingCategory, class Microsoft.Crm.Asynchronous.EmailConnector.DistinguishedFolderIdType baseFolderId, class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType categoryTrackedExtendedFieldType)
0x49f8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.BaseFolderType>::Add(var<u1>)
0x49f94  ldarg.0
0x49f95  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesSearchFoldersManager::traceHandler
0x49f9a  ldc.i4.3
0x49f9b  ldstr    aAddedTheUntrac// "Added the Untracked search folder creat"...
0x49fa0  ldc.i4.1
0x49fa1  newarr   [mscorlib]System.Object
0x49fa6  dup
0x49fa7  ldc.i4.0
0x49fa8  ldloc.3
0x49fa9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x49fae  stelem.ref
0x49faf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x49fb4  ldloc.1
0x49fb5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x49fba  brtrue.s loc_49F7E
0x49fbc  leave.s  loc_49FC8
0x49fbe  ldloc.1
0x49fbf  brfalse.s loc_49FC7
0x49fc1  ldloc.1
0x49fc2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49fc7  endfinally
0x49fc8  ldloc.0
0x49fc9  ret
```
