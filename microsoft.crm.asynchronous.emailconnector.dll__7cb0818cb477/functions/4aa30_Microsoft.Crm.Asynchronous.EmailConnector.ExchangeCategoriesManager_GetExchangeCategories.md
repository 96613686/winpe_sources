# Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::GetExchangeCategories

- ea: `0x4aa30`
- end: `0x4ab67`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::GetExchangeCategories`
- size: `311`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4aa30`
- `0x4ac30`
- `0x4acb0`
- `0x4b540`
- `0x4b550`
- `0x4b560`
- `0x71300`

## string_xrefs

- `0x4aa7f`: `Empty XmlData from userConfiguration from Exchange while fetching categories`
- `0x4aa86`: `Failed to get the UserConfiguration from Exchange while fetching categories`

## pseudocode

```c

```

## disassembly

```asm
0x4aa30  ldarg.0
0x4aa31  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4aa36  ldc.i4.3
0x4aa37  ldstr    aTryingToFetchT// "Trying to fetch the existing Categories"...
0x4aa3c  ldc.i4.0
0x4aa3d  newarr   [mscorlib]System.Object
0x4aa42  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4aa47  newobj   instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::.ctor()
0x4aa4c  dup
0x4aa4d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::.ctor()
0x4aa52  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::set_Categories(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> value)
0x4aa57  stloc.0
0x4aa58  ldarg.0
0x4aa59  call     instance class [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::GetUserConfiguration()
0x4aa5e  stloc.1
0x4aa5f  ldloc.1
0x4aa60  brfalse.s loc_4AA75
0x4aa62  ldloc.1
0x4aa63  callvirt instance unsigned int8[] [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration::get_XmlData()
0x4aa68  brfalse.s loc_4AA75
0x4aa6a  ldloc.1
0x4aa6b  callvirt instance unsigned int8[] [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration::get_XmlData()
0x4aa70  ldlen
0x4aa71  conv.i4
0x4aa72  ldc.i4.1
0x4aa73  bge.s    loc_4AA9D
0x4aa75  ldarg.0
0x4aa76  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4aa7b  ldc.i4.2
0x4aa7c  ldloc.1
0x4aa7d  brfalse.s loc_4AA86
0x4aa7f  ldstr    aEmptyXmldataFr// "Empty XmlData from userConfiguration fr"...
0x4aa84  br.s     loc_4AA8B
0x4aa86  ldstr    aFailedToGetThe_0// "Failed to get the UserConfiguration fro"...
0x4aa8b  ldc.i4.0
0x4aa8c  newarr   [mscorlib]System.Object
0x4aa91  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4aa96  ldloc.0
0x4aa97  stloc.2
0x4aa98  leave    loc_4AB65
0x4aa9d  ldloc.1
0x4aa9e  callvirt instance unsigned int8[] [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.UserConfiguration::get_XmlData()
0x4aaa3  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x4aaa8  stloc.3
0x4aaa9  ldloc.3
0x4aaaa  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x4aaaf  ldc.i4.1
0x4aab0  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream, class [mscorlib]System.Text.Encoding, bool)
0x4aab5  stloc.s  4
0x4aab7  ldtoken  Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories
0x4aabc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4aac1  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0x4aac6  ldloc.s  4
0x4aac8  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [mscorlib]System.IO.TextReader)
0x4aacd  castclass Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories
0x4aad2  stloc.0
0x4aad3  leave.s  loc_4AAE1
0x4aad5  ldloc.s  4
0x4aad7  brfalse.s loc_4AAE0
0x4aad9  ldloc.s  4
0x4aadb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4aae0  endfinally
0x4aae1  leave.s  loc_4AAED
0x4aae3  ldloc.3
0x4aae4  brfalse.s loc_4AAEC
0x4aae6  ldloc.3
0x4aae7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4aaec  endfinally
0x4aaed  ldloc.0
0x4aaee  brfalse.s loc_4AB26
0x4aaf0  ldloc.0
0x4aaf1  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4aaf6  brfalse.s loc_4AB26
0x4aaf8  ldarg.0
0x4aaf9  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4aafe  ldc.i4.3
0x4aaff  ldstr    aGot0Categories// "Got {0} Categories from Exchange"
0x4ab04  ldc.i4.1
0x4ab05  newarr   [mscorlib]System.Object
0x4ab0a  dup
0x4ab0b  ldc.i4.0
0x4ab0c  ldloc.0
0x4ab0d  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory> Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories::get_Categories()
0x4ab12  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategory>::get_Count()
0x4ab17  box      [mscorlib]System.Int32
0x4ab1c  stelem.ref
0x4ab1d  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4ab22  ldloc.0
0x4ab23  stloc.2
0x4ab24  leave.s  loc_4AB65
0x4ab26  ldloc.0
0x4ab27  stloc.2
0x4ab28  leave.s  loc_4AB65
0x4ab2a  callvirt instance valuetype [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceError [Microsoft.Exchange.WebServices]Microsoft.Exchange.WebServices.Data.ServiceResponseException::get_ErrorCode()
0x4ab2f  ldc.i4   0xF9
0x4ab34  bne.un.s loc_4AB3F
0x4ab36  ldarg.0
0x4ab37  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategories Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::CreateExchangeMasterCategoryList()
0x4ab3c  stloc.2
0x4ab3d  leave.s  loc_4AB65
0x4ab3f  ldnull
0x4ab40  stloc.2
0x4ab41  leave.s  loc_4AB65
0x4ab43  stloc.s  5
0x4ab45  ldarg.0
0x4ab46  ldfld    class Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler Microsoft.Crm.Asynchronous.EmailConnector.ExchangeCategoriesManager::traceHandler
0x4ab4b  ldc.i4.1
0x4ab4c  ldstr    aThereWasAnExce// "There was an exception when fetching ca"...
0x4ab51  ldc.i4.1
0x4ab52  newarr   [mscorlib]System.Object
0x4ab57  dup
0x4ab58  ldc.i4.0
0x4ab59  ldloc.s  5
0x4ab5b  stelem.ref
0x4ab5c  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.ITraceHandler::HandleTrace(valuetype [System]System.Diagnostics.TraceLevel traceLevel, string format, object[] args)
0x4ab61  ldnull
0x4ab62  stloc.2
0x4ab63  leave.s  loc_4AB65
0x4ab65  ldloc.2
0x4ab66  ret
```
