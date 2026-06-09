# Microsoft.Crm.ServerLocatorService::SaveChangeNotificationEventHubConnectionString

- ea: `0x8190`
- end: `0x8362`
- name: `Microsoft.Crm.ServerLocatorService::SaveChangeNotificationEventHubConnectionString`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa00`
- `0xde0`
- `0x72b0`
- `0x8190`
- `0x9710`
- `0x1be90`
- `0x1c060`
- `0x44400`
- `0x444f0`
- `0x44510`
- `0x4d750`
- `0x61910`
- `0x62500`

## string_xrefs

- `0x81fb`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x826f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x8316`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0x82e2`: `CreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x8190  ldarg.1
0x8191  ldstr    aSubscriptionid// "subscriptionId"
0x8196  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0x819b  ldarg.2
0x819c  ldstr    aEventhubconnec// "eventHubConnectionString"
0x81a1  call     void Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string parameter, string name)
0x81a6  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x81ab  stloc.0
0x81ac  ldloc.0
0x81ad  ldstr    aScopeid// "ScopeId"
0x81b2  call     class Microsoft.Crm.IDataCenterInfoProvider Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x81b7  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x81bc  box      [mscorlib]System.Guid
0x81c1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x81c6  ldloc.0
0x81c7  ldstr    aName// "Name"
0x81cc  ldstr    aCrmchangenotif// "CrmChangeNotificationEventHub"
0x81d1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x81d6  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x81db  stloc.1
0x81dc  ldarg.0
0x81dd  ldstr    aAzureresource// "AzureResource"
0x81e2  ldc.i4.1
0x81e3  newarr   [mscorlib]System.String
0x81e8  dup
0x81e9  ldc.i4.0
0x81ea  ldstr    aId// "Id"
0x81ef  stelem.ref
0x81f0  ldloc.0
0x81f1  ldc.i4   0x41C
0x81f6  ldstr    aSavechangenoti// "SaveChangeNotificationEventHubConnectio"...
0x81fb  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8200  call     instance class Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ServerLocatorService::RetrieveSingleRow(string tableName, string[] columns, class Microsoft.Crm.Data.PropertyBag conditions, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8205  stloc.2
0x8206  ldloc.2
0x8207  brfalse  loc_8296
0x820c  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x8211  stloc.3
0x8212  ldloc.3
0x8213  ldstr    aId// "Id"
0x8218  ldloc.2
0x8219  ldstr    aId// "Id"
0x821e  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8223  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8228  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x822d  stloc.s  4
0x822f  ldloc.s  4
0x8231  ldstr    aAzureresourcec// "AzureResourceConnectionString"
0x8236  ldarg.2
0x8237  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x823c  ldloc.s  4
0x823e  ldstr    aModifiedon// "ModifiedOn"
0x8243  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x8248  box      [mscorlib]System.DateTime
0x824d  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8252  ldloc.1
0x8253  ldstr    aAzureresource// "AzureResource"
0x8258  ldloc.s  4
0x825a  ldc.i4.1
0x825b  newarr   Microsoft.Crm.Data.PropertyBag
0x8260  dup
0x8261  ldc.i4.0
0x8262  ldloc.3
0x8263  stelem.ref
0x8264  ldc.i4.0
0x8265  ldc.i4   0x426
0x826a  ldstr    aSavechangenoti// "SaveChangeNotificationEventHubConnectio"...
0x826f  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x8274  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8279  pop
0x827a  ldloc.2
0x827b  ldstr    aId// "Id"
0x8280  callvirt instance object Microsoft.Crm.Data.PropertyBag::get_Item(string propertyName)
0x8285  callvirt instance string [mscorlib]System.Object::ToString()
0x828a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x828f  stloc.s  5
0x8291  leave    loc_835F
0x8296  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x829b  stloc.s  6
0x829d  ldloc.0
0x829e  ldstr    aId// "Id"
0x82a3  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x82a8  box      [mscorlib]System.Guid
0x82ad  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x82b2  ldloc.0
0x82b3  ldstr    aAzuresubscript// "AzureSubscriptionId"
0x82b8  ldarg.1
0x82b9  box      [mscorlib]System.Guid
0x82be  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x82c3  ldloc.0
0x82c4  ldstr    aAzureresourcet// "AzureResourceType"
0x82c9  ldc.i4.s 0xA
0x82cb  box      [mscorlib]System.Int32
0x82d0  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x82d5  ldloc.0
0x82d6  ldstr    aAzureresourcec// "AzureResourceConnectionString"
0x82db  ldarg.2
0x82dc  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x82e1  ldloc.0
0x82e2  ldstr    aCreatedon// "CreatedOn"
0x82e7  ldloc.s  6
0x82e9  box      [mscorlib]System.DateTime
0x82ee  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x82f3  ldloc.0
0x82f4  ldstr    aModifiedon// "ModifiedOn"
0x82f9  ldloc.s  6
0x82fb  box      [mscorlib]System.DateTime
0x8300  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8305  ldloc.1
0x8306  ldstr    aAzureresource// "AzureResource"
0x830b  ldloc.0
0x830c  ldc.i4   0x435
0x8311  ldstr    aSavechangenoti// "SaveChangeNotificationEventHubConnectio"...
0x8316  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0x831b  callvirt instance object Microsoft.Crm.SharedDatabase.DatabaseService::Create(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0x8320  unbox.any [mscorlib]System.Guid
0x8325  stloc.s  7
0x8327  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0x832c  stloc.s  8
0x832e  ldloc.s  8
0x8330  ldstr    aChangenotifica// "ChangeNotificationEventHubId"
0x8335  ldloca.s 7
0x8337  constrained. [mscorlib]System.Guid
0x833d  callvirt instance string [mscorlib]System.Object::ToString()
0x8342  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0x8347  ldarg.0
0x8348  ldloc.s  8
0x834a  call     instance void Microsoft.Crm.ServerLocatorService::UpdateSiteSetting(class Microsoft.Crm.Data.PropertyBag values)
0x834f  ldloc.s  7
0x8351  stloc.s  5
0x8353  leave.s  loc_835F
0x8355  ldloc.1
0x8356  brfalse.s loc_835E
0x8358  ldloc.1
0x8359  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x835e  endfinally
0x835f  ldloc.s  5
0x8361  ret
```
