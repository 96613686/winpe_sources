# Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::GetMailboxTrackingCategoriesNeedingUpdate

- ea: `0x49940`
- end: `0x49a55`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::GetMailboxTrackingCategoriesNeedingUpdate`
- size: `277`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x496a0`

## callees

- `0x49940`
- `0x4b540`
- `0x4b580`
- `0x4b5a0`
- `0x4b6d0`
- `0x4b6e0`
- `0x4b6f0`
- `0x4b710`
- `0x4b720`
- `0x71300`
- `0x82530`

## string_xrefs

- `0x499b8`: `The Category with Id: {0} is updated in Exchange with the following. Exchange Name: {1}, CRM Name: {2}, Exchange Color: {3}, Crm Color: {4}. It will be updated in CRM`

## pseudocode

```c

```

## disassembly

```asm
0x49940  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::.ctor()
0x49945  stloc.0
0x49946  ldarg.2
0x49947  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4994c  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::GetEnumerator()
0x49951  stloc.1
0x49952  br       loc_49A37
0x49957  newobj   instance void <>c__DisplayClass8_0::.ctor()
0x4995c  stloc.2
0x4995d  ldloc.2
0x4995e  ldloca.s 1
0x49960  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::get_Current()
0x49965  stfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x4996a  ldarg.1
0x4996b  ldloc.2
0x4996c  ldftn    instance bool <>c__DisplayClass8_0::<GetMailboxTrackingCategoriesNeedingUpdate>b__0(class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory mtc)
0x49972  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory, bool>::.ctor(object, native int)
0x49977  call     T0x2B000081
0x4997c  stloc.3
0x4997d  ldloc.3
0x4997e  brfalse  loc_49A37
0x49983  ldloc.2
0x49984  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x49989  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryName()
0x4998e  ldloc.3
0x4998f  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x49994  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x49999  brtrue.s loc_499B1
0x4999b  ldloc.2
0x4999c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x499a1  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryColor()
0x499a6  ldloc.3
0x499a7  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryColor()
0x499ac  beq      loc_49A37
0x499b1  ldarg.0
0x499b2  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.CategoriesManager::traceHandler
0x499b7  ldc.i4.3
0x499b8  ldstr    aTheCategoryWit_1// "The Category with Id: {0} is updated in"...
0x499bd  ldc.i4.5
0x499be  newarr   [mscorlib]System.Object
0x499c3  dup
0x499c4  ldc.i4.0
0x499c5  ldloc.3
0x499c6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryId()
0x499cb  box      [mscorlib]System.Guid
0x499d0  stelem.ref
0x499d1  dup
0x499d2  ldc.i4.1
0x499d3  ldloc.2
0x499d4  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x499d9  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryName()
0x499de  stelem.ref
0x499df  dup
0x499e0  ldc.i4.2
0x499e1  ldloc.3
0x499e2  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryName()
0x499e7  stelem.ref
0x499e8  dup
0x499e9  ldc.i4.3
0x499ea  ldloc.2
0x499eb  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x499f0  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryColor()
0x499f5  box      [mscorlib]System.Int32
0x499fa  stelem.ref
0x499fb  dup
0x499fc  ldc.i4.4
0x499fd  ldloc.3
0x499fe  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::get_ExchangeCategoryColor()
0x49a03  box      [mscorlib]System.Int32
0x49a08  stelem.ref
0x49a09  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x49a0e  ldloc.3
0x49a0f  ldloc.2
0x49a10  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x49a15  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryName()
0x49a1a  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::set_ExchangeCategoryName(string value)
0x49a1f  ldloc.3
0x49a20  ldloc.2
0x49a21  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory <>c__DisplayClass8_0::exchangeCategory
0x49a26  callvirt instance int32 Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory::get_CategoryColor()
0x49a2b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory::set_ExchangeCategoryColor(int32 value)
0x49a30  ldloc.0
0x49a31  ldloc.3
0x49a32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.MailboxTrackingCategory>::Add(var<u1>)
0x49a37  ldloca.s 1
0x49a39  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::MoveNext()
0x49a3e  brtrue   loc_49957
0x49a43  leave.s  loc_49A53
0x49a45  ldloca.s 1
0x49a47  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>
0x49a4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x49a52  endfinally
0x49a53  ldloc.0
0x49a54  ret
```
