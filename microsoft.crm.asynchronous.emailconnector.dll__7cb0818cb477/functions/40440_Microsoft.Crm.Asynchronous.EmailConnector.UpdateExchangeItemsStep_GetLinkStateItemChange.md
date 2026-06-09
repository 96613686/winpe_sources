# Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetLinkStateItemChange

- ea: `0x40440`
- end: `0x40653`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetLinkStateItemChange`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x40970`

## callees

- `0x32840`
- `0x32860`
- `0x3ab40`
- `0x40380`
- `0x40440`
- `0x41a10`
- `0x41a20`
- `0x41ab0`
- `0x41b30`
- `0x41b40`
- `0x41c70`
- `0x41ca0`
- `0x41d20`
- `0x41e30`
- `0x41e40`
- `0x4af40`
- `0x4af80`
- `0x4af90`
- `0x4afa0`

## string_xrefs

- `0x404c7`: `Linkstate: {0}.`
- `0x4059a`: `Removed Dynamics Categories with count: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x40440  ldstr    a20// "2.0"
0x40445  stloc.0
0x40446  ldarg.1
0x40447  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4044c  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x40451  ldc.i4.1
0x40452  bne.un.s loc_40470
0x40454  ldarg.1
0x40455  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_CrmId()
0x4045a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4045f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x40464  brfalse.s loc_40468
0x40466  ldnull
0x40467  ret
0x40468  ldstr    a20// "2.0"
0x4046d  stloc.0
0x4046e  br.s     loc_404C6
0x40470  ldarg.1
0x40471  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40476  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x4047b  ldc.i4.3
0x4047c  beq.s    loc_4048C
0x4047e  ldarg.1
0x4047f  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40484  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x40489  ldc.i4.4
0x4048a  bne.un.s loc_40494
0x4048c  ldstr    a00// "0.0"
0x40491  stloc.0
0x40492  br.s     loc_404C6
0x40494  ldarg.1
0x40495  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4049a  callvirt instance valuetype Microsoft.Crm.Asynchronous.EmailConnector.LinkState Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_LinkState()
0x4049f  ldc.i4.2
0x404a0  bne.un.s loc_404A4
0x404a2  ldnull
0x404a3  ret
0x404a4  ldarg.0
0x404a5  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x404aa  ldarg.1
0x404ab  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x404b0  callvirt instance string Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_ParentFolderId()
0x404b5  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::IsFolderBasedTrackingFolder(string p)
0x404ba  brfalse.s loc_404C4
0x404bc  ldstr    a20// "2.0"
0x404c1  stloc.0
0x404c2  br.s     loc_404C6
0x404c4  ldnull
0x404c5  ret
0x404c6  ldarg.2
0x404c7  ldstr    aLinkstate0// "Linkstate: {0}."
0x404cc  ldloc.0
0x404cd  call     string [mscorlib]System.String::Format(string, object)
0x404d2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x404d7  pop
0x404d8  ldarg.0
0x404d9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x404de  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategoriesSearchFoldersManager()
0x404e3  callvirt instance bool Microsoft.Crm.Asynchronous.EmailConnector.ICategoriesSearchFoldersManager::IsCategorizedTrackingEnabled()
0x404e8  brfalse  loc_40635
0x404ed  ldstr    a1// "1"
0x404f2  stloc.1
0x404f3  ldloc.0
0x404f4  ldstr    a20// "2.0"
0x404f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x404fe  brfalse.s loc_40566
0x40500  ldstr    a1// "1"
0x40505  stloc.1
0x40506  ldarg.1
0x40507  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4050c  ldarg.0
0x4050d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40512  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategorizedItemManager()
0x40517  ldarg.1
0x40518  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4051d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Categories()
0x40522  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::AddDynamicsCategory(class [mscorlib]System.Collections.Generic.IList`1<string> categories)
0x40527  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::set_Categories(class [mscorlib]System.Collections.Generic.IList`1<string> value)
0x4052c  ldarg.2
0x4052d  ldstr    aCrmcategorytra_0// "CrmCategoryTracker: {0}."
0x40532  ldloc.1
0x40533  call     string [mscorlib]System.String::Format(string, object)
0x40538  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4053d  pop
0x4053e  ldarg.2
0x4053f  ldstr    aAddedCategoryW// "Added Category with count: {0}."
0x40544  ldarg.1
0x40545  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4054a  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Categories()
0x4054f  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x40554  box      [mscorlib]System.Int32
0x40559  call     string [mscorlib]System.String::Format(string, object)
0x4055e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x40563  pop
0x40564  br.s     loc_405BF
0x40566  ldstr    a0// "0"
0x4056b  stloc.1
0x4056c  ldarg.0
0x4056d  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x40572  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategorizedItemManager()
0x40577  ldarg.1
0x40578  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4057d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Categories()
0x40582  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::RemoveAllDynamicsCategories(class [mscorlib]System.Collections.Generic.IList`1<string> categories)
0x40587  ldarg.2
0x40588  ldstr    aCrmcategorytra_0// "CrmCategoryTracker: {0}."
0x4058d  ldloc.1
0x4058e  call     string [mscorlib]System.String::Format(string, object)
0x40593  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x40598  pop
0x40599  ldarg.2
0x4059a  ldstr    aRemovedDynamic// "Removed Dynamics Categories with count:"...
0x4059f  ldarg.1
0x405a0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x405a5  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Categories()
0x405aa  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<string>::get_Count()
0x405af  box      [mscorlib]System.Int32
0x405b4  call     string [mscorlib]System.String::Format(string, object)
0x405b9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x405be  pop
0x405bf  ldarg.0
0x405c0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x405c5  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::get_CategorizedItemManager()
0x405ca  ldarg.1
0x405cb  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x405d0  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Categories()
0x405d5  ldarg.1
0x405d6  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x405db  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x405e0  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.ICategorizedItemManager::GetCategoriesChangeType(class [mscorlib]System.Collections.Generic.IList`1<string> categories, class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType emailMessageId)
0x405e5  stloc.2
0x405e6  ldloc.2
0x405e7  brfalse.s loc_40615
0x405e9  ldarg.3
0x405ea  ldloc.2
0x405eb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x405f0  ldarg.3
0x405f1  ldarg.0
0x405f2  ldarg.0
0x405f3  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x405f8  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetCategoryTrackerExtendedFieldTypePath()
0x405fd  ldloc.1
0x405fe  ldarg.1
0x405ff  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40604  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x40609  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetItemChangeType(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType extendedFieldTypePath, object extendedPropertyItem, class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType emailMessageId)
0x4060e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType>::Add(var<u1>)
0x40613  br.s     loc_40635
0x40615  ldarg.0
0x40616  ldc.i4.1
0x40617  ldstr    aFailedToGetThe// "Failed to get the Categories change typ"...
0x4061c  ldc.i4.1
0x4061d  newarr   [mscorlib]System.Object
0x40622  dup
0x40623  ldc.i4.0
0x40624  ldarg.1
0x40625  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x4062a  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x4062f  stelem.ref
0x40630  call     instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x40635  ldarg.0
0x40636  ldarg.0
0x40637  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider Microsoft.Crm.Asynchronous.EmailConnector.ExchangeIncomingEmailProviderStep::provider
0x4063c  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeIncomingEmailProvider::GetLinkStateExtendedFieldTypePath()
0x40641  ldloc.0
0x40642  ldarg.1
0x40643  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage Microsoft.Crm.Asynchronous.EmailConnector.CrmExchangeEmailMessage::get_EmailMessage()
0x40648  callvirt instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType Microsoft.Crm.Asynchronous.EmailConnector.IExchangeEmailMessage::get_Id()
0x4064d  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ItemChangeType Microsoft.Crm.Asynchronous.EmailConnector.UpdateExchangeItemsStep::GetItemChangeType(class Microsoft.Crm.Asynchronous.EmailConnector.PathToExtendedFieldType extendedFieldTypePath, object extendedPropertyItem, class Microsoft.Crm.Asynchronous.EmailConnector.ItemIdType emailMessageId)
0x40652  ret
```
