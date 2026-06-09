# Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::VerifyAndUpdateExchangeCategories

- ea: `0x497f0`
- end: `0x4993e`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::VerifyAndUpdateExchangeCategories`
- size: `334`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x496a0`
- `0x49790`

## callees

- `0x497f0`
- `0x4b030`
- `0x4b540`
- `0x4b580`
- `0x4b590`
- `0x4b5a0`
- `0x4b5b0`
- `0x4b5c0`
- `0x4b5d0`
- `0x4b610`
- `0x4b6d0`
- `0x4b6f0`
- `0x4b710`
- `0x71300`
- `0x824f0`

## string_xrefs

- `0x49880`: `The Category with Id: {0}, Name: {1} and Color: {2} does not exist in Exchange. It will be created in Exchange`
- `0x498e2`: `The Category with Id: {0}, Name: {1} and Color: {2} is being removed from Exchange.`

## pseudocode

```c

```

## disassembly

```asm
0x497f0  ldc.i4.0
0x497f1  stloc.0
0x497f2  ldarg.1
0x497f3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::GetEnumerator()
0x497f8  stloc.1
0x497f9  br       loc_49917
0x497fe  newobj   instance void <>c__DisplayClass7_0::.ctor()
0x49803  stloc.2
0x49804  ldloc.2
0x49805  ldloc.1
0x49806  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::get_Current()
0x4980b  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x49810  ldarg.2
0x49811  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x49816  ldloc.2
0x49817  ldftn    instance bool <>c__DisplayClass7_0::<VerifyAndUpdateExchangeCategories>b__0(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory category)
0x4981d  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory, bool>::.ctor(object, native int)
0x49822  call     T0x2B000080
0x49827  stloc.3
0x49828  ldloc.3
0x49829  brtrue   loc_498C4
0x4982e  ldarg.3
0x4982f  brtrue   loc_498C4
0x49834  ldarg.2
0x49835  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4983a  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::.ctor()
0x4983f  dup
0x49840  ldloc.2
0x49841  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x49846  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x4984b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::set_CategoryName(string value)
0x49850  dup
0x49851  ldloc.2
0x49852  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x49857  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryColor()
0x4985c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::set_CategoryColor(int32 value)
0x49861  dup
0x49862  ldloc.2
0x49863  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x49868  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryId()
0x4986d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::set_CategoryId(valuetype [mscorlib]System.Guid value)
0x49872  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::Add(var<u1>)
0x49877  ldc.i4.1
0x49878  stloc.0
0x49879  ldarg.0
0x4987a  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::traceHandler
0x4987f  ldc.i4.3
0x49880  ldstr    aTheCategoryWit// "The Category with Id: {0}, Name: {1} an"...
0x49885  ldc.i4.3
0x49886  newarr   [mscorlib]System.Object
0x4988b  dup
0x4988c  ldc.i4.0
0x4988d  ldloc.2
0x4988e  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x49893  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryId()
0x49898  box      [mscorlib]System.Guid
0x4989d  stelem.ref
0x4989e  dup
0x4989f  ldc.i4.1
0x498a0  ldloc.2
0x498a1  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x498a6  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x498ab  stelem.ref
0x498ac  dup
0x498ad  ldc.i4.2
0x498ae  ldloc.2
0x498af  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory <>c__DisplayClass7_0::mailboxTrackingCategory
0x498b4  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryColor()
0x498b9  box      [mscorlib]System.Int32
0x498be  stelem.ref
0x498bf  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x498c4  ldloc.3
0x498c5  ldnull
0x498c6  cgt.un
0x498c8  ldarg.3
0x498c9  and
0x498ca  brfalse.s loc_49917
0x498cc  ldarg.2
0x498cd  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x498d2  ldloc.3
0x498d3  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::Remove(var<u1>)
0x498d8  pop
0x498d9  ldc.i4.1
0x498da  stloc.0
0x498db  ldarg.0
0x498dc  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::traceHandler
0x498e1  ldc.i4.3
0x498e2  ldstr    aTheCategoryWit_0// "The Category with Id: {0}, Name: {1} an"...
0x498e7  ldc.i4.3
0x498e8  newarr   [mscorlib]System.Object
0x498ed  dup
0x498ee  ldc.i4.0
0x498ef  ldloc.3
0x498f0  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryId()
0x498f5  box      [mscorlib]System.Guid
0x498fa  stelem.ref
0x498fb  dup
0x498fc  ldc.i4.1
0x498fd  ldloc.3
0x498fe  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryName()
0x49903  stelem.ref
0x49904  dup
0x49905  ldc.i4.2
0x49906  ldloc.3
0x49907  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryColor()
0x4990c  box      [mscorlib]System.Int32
0x49911  stelem.ref
0x49912  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x49917  ldloc.1
0x49918  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4991d  brtrue   loc_497FE
0x49922  leave.s  loc_4992E
0x49924  ldloc.1
0x49925  brfalse.s loc_4992D
0x49927  ldloc.1
0x49928  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4992d  endfinally
0x4992e  ldloc.0
0x4992f  brfalse.s loc_4993D
0x49931  ldarg.0
0x49932  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoriesManager Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::exchangeCategoriesManager
0x49937  ldarg.2
0x49938  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeCategoriesManager::UpdateCategoriesToExchange(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories updatedExchangeCategories)
0x4993d  ret
```
