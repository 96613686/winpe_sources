# Microsoft.Crm.ObjectModel.UserEntityUISettingsService::FlushUserEntityUISettingsCache

- ea: `0x1b9fb0`
- end: `0x1ba1f2`
- name: `Microsoft.Crm.ObjectModel.UserEntityUISettingsService::FlushUserEntityUISettingsCache`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1b9fb0`

## string_xrefs

- `0x1b9fc8`: `taborderxml`
- `0x1ba123`: `taborderxml`
- `0x1b9fb6`: `readingpanexml`
- `0x1ba10e`: `readingpanexml`
- `0x1b9fec`: `lastviewedformxml`
- `0x1ba14d`: `lastviewedformxml`
- `0x1b9ffe`: `recentlyviewedxml`
- `0x1ba162`: `recentlyviewedxml`
- `0x1ba1a5`: `recentlyviewedxml`

## pseudocode

```c

```

## disassembly

```asm
0x1b9fb0  ldarg.2
0x1b9fb1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1b9fb6  ldstr    aReadingpanexml// "readingpanexml"
0x1b9fbb  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b9fc0  brfalse.s loc_1BA00B
0x1b9fc2  ldarg.2
0x1b9fc3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1b9fc8  ldstr    aTaborderxml// "taborderxml"
0x1b9fcd  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b9fd2  brfalse.s loc_1BA00B
0x1b9fd4  ldarg.2
0x1b9fd5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1b9fda  ldstr    aShowinaddressb// "showinaddressbook"
0x1b9fdf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b9fe4  brfalse.s loc_1BA00B
0x1b9fe6  ldarg.2
0x1b9fe7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1b9fec  ldstr    aLastviewedform// "lastviewedformxml"
0x1b9ff1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b9ff6  brfalse.s loc_1BA00B
0x1b9ff8  ldarg.2
0x1b9ff9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1b9ffe  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x1ba003  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba008  brfalse.s loc_1BA00B
0x1ba00a  ret
0x1ba00b  ldarg.2
0x1ba00c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba011  ldstr    aOwnerid// "ownerid"
0x1ba016  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba01b  brtrue.s loc_1BA032
0x1ba01d  ldarg.2
0x1ba01e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba023  ldstr    aObjecttypecode// "objecttypecode"
0x1ba028  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba02d  brfalse  loc_1BA0DC
0x1ba032  ldarg.2
0x1ba033  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba038  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x1ba03d  unbox.any [mscorlib]System.Guid
0x1ba042  ldstr    aUserentityuise_0// "UserEntityUISettings"
0x1ba047  ldarg.2
0x1ba048  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba04d  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba052  stloc.2
0x1ba053  ldstr    aUserentityuise_0// "UserEntityUISettings"
0x1ba058  ldarg.2
0x1ba059  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba05e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x1ba063  stloc.3
0x1ba064  ldloc.3
0x1ba065  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x1ba06a  ldc.i4.2
0x1ba06b  newarr   [mscorlib]System.String
0x1ba070  dup
0x1ba071  ldc.i4.0
0x1ba072  ldstr    aOwnerid// "ownerid"
0x1ba077  stelem.ref
0x1ba078  dup
0x1ba079  ldc.i4.1
0x1ba07a  ldstr    aObjecttypecode// "objecttypecode"
0x1ba07f  stelem.ref
0x1ba080  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x1ba085  ldarg.2
0x1ba086  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba08b  ldc.i4.1
0x1ba08c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x1ba091  stloc.s  5
0x1ba093  ldarg.0
0x1ba094  ldloc.2
0x1ba095  ldloc.3
0x1ba096  ldarg.2
0x1ba097  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba09c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Retrieve(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1ba0a1  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.UserEntityUISettings
0x1ba0a6  stloc.s  4
0x1ba0a8  leave.s  loc_1BA0B6
0x1ba0aa  ldloc.s  5
0x1ba0ac  brfalse.s loc_1BA0B5
0x1ba0ae  ldloc.s  5
0x1ba0b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ba0b5  endfinally
0x1ba0b6  ldloc.s  4
0x1ba0b8  ldstr    aOwnerid// "ownerid"
0x1ba0bd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba0c2  unbox.any [mscorlib]System.Guid
0x1ba0c7  stloc.0
0x1ba0c8  ldloc.s  4
0x1ba0ca  ldstr    aObjecttypecode// "objecttypecode"
0x1ba0cf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1ba0d4  unbox.any [mscorlib]System.Int32
0x1ba0d9  stloc.1
0x1ba0da  br.s     loc_1BA108
0x1ba0dc  ldarg.2
0x1ba0dd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba0e2  ldstr    aOwnerid// "ownerid"
0x1ba0e7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba0ec  unbox.any [mscorlib]System.Guid
0x1ba0f1  stloc.0
0x1ba0f2  ldarg.2
0x1ba0f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba0f8  ldstr    aObjecttypecode// "objecttypecode"
0x1ba0fd  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba102  unbox.any [mscorlib]System.Int32
0x1ba107  stloc.1
0x1ba108  ldarg.2
0x1ba109  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba10e  ldstr    aReadingpanexml// "readingpanexml"
0x1ba113  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba118  brfalse  loc_1BA1DF
0x1ba11d  ldarg.2
0x1ba11e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba123  ldstr    aTaborderxml// "taborderxml"
0x1ba128  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba12d  brfalse  loc_1BA1DF
0x1ba132  ldarg.2
0x1ba133  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba138  ldstr    aShowinaddressb// "showinaddressbook"
0x1ba13d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba142  brfalse  loc_1BA1DF
0x1ba147  ldarg.2
0x1ba148  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba14d  ldstr    aLastviewedform// "lastviewedformxml"
0x1ba152  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba157  brfalse  loc_1BA1DF
0x1ba15c  ldarg.2
0x1ba15d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba162  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x1ba167  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1ba16c  brtrue.s loc_1BA1DF
0x1ba16e  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x1ba173  ldloc.1
0x1ba174  ldloc.0
0x1ba175  ldarg.2
0x1ba176  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba17b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::TryLookupEntry(int32, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba180  stloc.s  6
0x1ba182  ldloc.s  6
0x1ba184  brfalse.s loc_1BA1DF
0x1ba186  ldloc.s  6
0x1ba188  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_UserEntityUISettingsId()
0x1ba18d  stloc.s  7
0x1ba18f  ldloca.s 7
0x1ba191  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ba196  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x1ba19b  brtrue.s loc_1BA1DF
0x1ba19d  ldloc.s  6
0x1ba19f  ldarg.2
0x1ba1a0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entity()
0x1ba1a5  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x1ba1aa  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1ba1af  isinst   [mscorlib]System.String
0x1ba1b4  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::set_RecentlyViewedXml(string)
0x1ba1b9  ldloc.s  6
0x1ba1bb  ldloc.s  6
0x1ba1bd  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::get_RecentlyViewedXml()
0x1ba1c2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(string)
0x1ba1c7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUserEntityUISettings::set_RecentlyViewedXmlDoc(class [System.Xml]System.Xml.XmlDocument)
0x1ba1cc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x1ba1d1  ldloc.1
0x1ba1d2  ldloc.0
0x1ba1d3  ldarg.2
0x1ba1d4  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba1d9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::FireCacheItemRemoveNotification(int32, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ba1de  ret
0x1ba1df  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::Instance()
0x1ba1e4  ldarg.2
0x1ba1e5  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Context()
0x1ba1ea  ldloc.1
0x1ba1eb  ldloc.0
0x1ba1ec  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserEntityUISettingsCache::RemoveEntry(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext, int32, valuetype [mscorlib]System.Guid)
0x1ba1f1  ret
```
