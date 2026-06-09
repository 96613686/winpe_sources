# Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::UpsertByEntityTypeCodeAndUser

- ea: `0x4ea40`
- end: `0x4ebea`
- name: `Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::UpsertByEntityTypeCodeAndUser`
- size: `426`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x4ebf0`

## callees

- `0x4ddb0`
- `0x4de60`
- `0x4df40`
- `0x4df60`
- `0x4ea40`
- `0x55a50`
- `0x55ac0`
- `0x66b90`
- `0x66d80`
- `0x66ff0`

## string_xrefs

- `0x4ea69`: `recentlyviewedxml`
- `0x4eaec`: `recentlyviewedxml`
- `0x4ea9d`: `AlreadyMergedRecentlyViewedXml`
- `0x4eb17`: `userentityuisettingsid`
- `0x4eb2e`: `userentityuisettingsid`
- `0x4eb39`: `userentityuisettingsid`
- `0x4ebae`: `CrmSecurityException on UserEntityUISettingsServiceAdapter.UpsertByEntityTypeCodeAndUser: CallerOrigin: {0}, CurrentClientType: {1}, ExceptionString: {2}`

## pseudocode

```c

```

## disassembly

```asm
0x4ea40  ldarg.1
0x4ea41  ldc.i4.0
0x4ea42  ble      loc_4EB9D
0x4ea47  ldarg.s  4
0x4ea49  brfalse.s loc_4EAC9
0x4ea4b  ldarg.s  4
0x4ea4d  ldarg.1
0x4ea4e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::ContainsKey(var<u1>)
0x4ea53  brfalse.s loc_4EAC9
0x4ea55  ldarg.s  4
0x4ea57  ldarg.1
0x4ea58  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::get_Item(void)
0x4ea5d  brfalse.s loc_4EAC9
0x4ea5f  ldarg.s  4
0x4ea61  ldarg.1
0x4ea62  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity>::get_Item(void)
0x4ea67  stloc.0
0x4ea68  ldloc.0
0x4ea69  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x4ea6e  ldarg.3
0x4ea6f  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4ea74  ldloc.0
0x4ea75  ldstr    aObjecttypecode_81// "objecttypecode"
0x4ea7a  ldnull
0x4ea7b  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x4ea80  ldarg.0
0x4ea81  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4ea86  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4ea8b  brfalse.s loc_4EAAD
0x4ea8d  ldarg.0
0x4ea8e  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4ea93  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4ea98  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x4ea9d  ldstr    aAlreadymergedr// "AlreadyMergedRecentlyViewedXml"
0x4eaa2  ldc.i4.1
0x4eaa3  box      [mscorlib]System.Boolean
0x4eaa8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4eaad  ldarg.0
0x4eaae  ldfld    class Microsoft.Crm.BusinessEntities.IBusinessProcessObject Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::service
0x4eab3  ldloc.0
0x4eab4  ldarg.0
0x4eab5  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eaba  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4eabf  callvirt instance void Microsoft.Crm.BusinessEntities.IBusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4eac4  br       loc_4EB9D
0x4eac9  ldstr    aUserentityuise// "UserEntityUISettings"
0x4eace  ldarg.0
0x4eacf  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4ead4  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4ead9  stloc.1
0x4eada  ldloc.1
0x4eadb  ldstr    aObjecttypecode_81// "objecttypecode"
0x4eae0  ldarg.1
0x4eae1  box      [mscorlib]System.Int32
0x4eae6  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4eaeb  ldloc.1
0x4eaec  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x4eaf1  ldarg.3
0x4eaf2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4eaf7  ldarg.0
0x4eaf8  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eafd  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4eb02  brfalse.s loc_4EB16
0x4eb04  ldarg.0
0x4eb05  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eb0a  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4eb0f  callvirt instance class Microsoft.Crm.BusinessEntities.SoapContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_SoapPacket()
0x4eb14  brtrue.s loc_4EB2D
0x4eb16  ldloc.1
0x4eb17  ldstr    aUserentityuise_0// "userentityuisettingsid"
0x4eb1c  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4eb21  box      [mscorlib]System.Guid
0x4eb26  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4eb2b  br.s     loc_4EB4D
0x4eb2d  ldloc.1
0x4eb2e  ldstr    aUserentityuise_0// "userentityuisettingsid"
0x4eb33  ldarg.0
0x4eb34  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eb39  ldstr    aUserentityuise_0// "userentityuisettingsid"
0x4eb3e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Platform.Server.IExecutionContext::InitializeGuidFromOfflineData(string key)
0x4eb43  box      [mscorlib]System.Guid
0x4eb48  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x4eb4d  ldarg.0
0x4eb4e  ldfld    class Microsoft.Crm.Platform.Server.IDynamicMetadataCache Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::metadataCache
0x4eb53  ldstr    aSystemuser_0// "SystemUser"
0x4eb58  callvirt instance class Microsoft.Crm.Platform.Server.IEntityMetadata Microsoft.Crm.Platform.Server.IDynamicMetadataCache::GetEntity(string entityPlatformName)
0x4eb5d  stloc.2
0x4eb5e  ldloc.1
0x4eb5f  ldstr    aOwnerid// "ownerid"
0x4eb64  ldarg.2
0x4eb65  box      [mscorlib]System.Guid
0x4eb6a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x4eb6f  ldloc.1
0x4eb70  ldstr    aOwneridtype// "owneridtype"
0x4eb75  ldloc.2
0x4eb76  callvirt instance int32 Microsoft.Crm.Platform.Server.IEntityMetadata::get_Code()
0x4eb7b  box      [mscorlib]System.Int32
0x4eb80  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::SetAttributeValue(string, object)
0x4eb85  ldarg.0
0x4eb86  ldfld    class Microsoft.Crm.BusinessEntities.IBusinessProcessObject Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::service
0x4eb8b  ldloc.1
0x4eb8c  ldarg.0
0x4eb8d  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eb92  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4eb97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.BusinessEntities.IBusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4eb9c  pop
0x4eb9d  leave.s  loc_4EBE9
0x4eb9f  stloc.3
0x4eba0  ldloc.3
0x4eba1  ldarg.0
0x4eba2  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4eba7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x4ebac  ldc.i4.s 0x1E
0x4ebae  ldstr    aCrmsecurityexc// "CrmSecurityException on UserEntityUISet"...
0x4ebb3  ldc.i4.3
0x4ebb4  newarr   [mscorlib]System.Object
0x4ebb9  dup
0x4ebba  ldc.i4.0
0x4ebbb  ldarg.0
0x4ebbc  ldfld    class Microsoft.Crm.Platform.Server.IExecutionContext Microsoft.Crm.Platform.Server.UserEntityUISettingsServiceAdapter::context
0x4ebc1  callvirt instance class Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Platform.Server.IExecutionContext::get_Instance()
0x4ebc6  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.BusinessEntities.ExecutionContext::get_CallerOriginToken()
0x4ebcb  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::get_CallerOrigin()
0x4ebd0  stelem.ref
0x4ebd1  dup
0x4ebd2  ldc.i4.1
0x4ebd3  call     string [Microsoft.Crm.Core]Microsoft.Crm.MetricsReporting::get_CurrentClientType()
0x4ebd8  stelem.ref
0x4ebd9  dup
0x4ebda  ldc.i4.2
0x4ebdb  ldloc.3
0x4ebdc  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x4ebe1  stelem.ref
0x4ebe2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4ebe7  leave.s  loc_4EBE9
0x4ebe9  ret
```
