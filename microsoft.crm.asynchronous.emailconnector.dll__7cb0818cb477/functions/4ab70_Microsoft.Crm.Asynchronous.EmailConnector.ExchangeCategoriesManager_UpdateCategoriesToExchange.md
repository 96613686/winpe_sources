# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::UpdateCategoriesToExchange

- ea: `0x4ab70`
- end: `0x4ac23`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::UpdateCategoriesToExchange`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4ab70`
- `0x4ac30`
- `0x4ac50`
- `0x4b540`
- `0x71300`

## string_xrefs

- `0x4ab71`: `updatedExchangeCategories`
- `0x4ab81`: `updatedExchangeCategories.Categories`
- `0x4ab92`: `Trying to update the Categories with {0} categories to Exchange`
- `0x4abc6`: `Failed to get the UserConfiguration from Exchange while adding categories to Exchange`
- `0x4abf2`: `Updated the Categories to Exchange`

## pseudocode

```c

```

## disassembly

```asm
0x4ab70  ldarg.1
0x4ab71  ldstr    aUpdatedexchang// "updatedExchangeCategories"
0x4ab76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ab7b  ldarg.1
0x4ab7c  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4ab81  ldstr    aUpdatedexchang_0// "updatedExchangeCategories.Categories"
0x4ab86  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4ab8b  ldarg.0
0x4ab8c  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4ab91  ldc.i4.3
0x4ab92  ldstr    aTryingToUpdate_0// "Trying to update the Categories with {0"...
0x4ab97  ldc.i4.1
0x4ab98  newarr   [mscorlib]System.Object
0x4ab9d  dup
0x4ab9e  ldc.i4.0
0x4ab9f  ldarg.1
0x4aba0  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4aba5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::get_Count()
0x4abaa  box      [mscorlib]System.Int32
0x4abaf  stelem.ref
0x4abb0  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4abb5  ldarg.0
0x4abb6  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::GetUserConfiguration()
0x4abbb  stloc.0
0x4abbc  ldloc.0
0x4abbd  brtrue.s loc_4ABD8
0x4abbf  ldarg.0
0x4abc0  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4abc5  ldc.i4.2
0x4abc6  ldstr    aFailedToGetThe_1// "Failed to get the UserConfiguration fro"...
0x4abcb  ldc.i4.0
0x4abcc  newarr   [mscorlib]System.Object
0x4abd1  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4abd6  leave.s  loc_4AC22
0x4abd8  ldloc.0
0x4abd9  ldarg.0
0x4abda  ldarg.1
0x4abdb  call     instance unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::GetXmlData(class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories exchangeCategories)
0x4abe0  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration::set_XmlData(unsigned int8[])
0x4abe5  ldloc.0
0x4abe6  callvirt instance void [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration::Update()
0x4abeb  ldarg.0
0x4abec  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4abf1  ldc.i4.3
0x4abf2  ldstr    aUpdatedTheCate// "Updated the Categories to Exchange"
0x4abf7  ldc.i4.0
0x4abf8  newarr   [mscorlib]System.Object
0x4abfd  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4ac02  leave.s  loc_4AC22
0x4ac04  stloc.1
0x4ac05  ldarg.0
0x4ac06  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4ac0b  ldc.i4.1
0x4ac0c  ldstr    aThereWasAnExce_0// "There was an exception when updating ca"...
0x4ac11  ldc.i4.1
0x4ac12  newarr   [mscorlib]System.Object
0x4ac17  dup
0x4ac18  ldc.i4.0
0x4ac19  ldloc.1
0x4ac1a  stelem.ref
0x4ac1b  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4ac20  leave.s  loc_4AC22
0x4ac22  ret
```
