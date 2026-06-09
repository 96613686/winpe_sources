# Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::BuildAppMetadataFromDb

- ea: `0x1b1a0`
- end: `0x1b4e0`
- name: `Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::BuildAppMetadataFromDb`
- size: `832`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1b100`
- `0x1b540`

## callees

- `0x1a4e0`
- `0x1a690`
- `0x1a6f0`
- `0x1ad60`
- `0x1ad90`
- `0x1b1a0`
- `0x1b4e0`
- `0x1b500`

## string_xrefs

- `0x1b1ef`: `D:\a\1\s\src\ManagedPlatform\SDK\Metadata\MetadataCacheLoaders\DynamicAppModuleCacheLoader.cs`
- `0x1b29a`: `welcomePageId`
- `0x1b2ac`: `welcomePageId`
- `0x1b2bc`: `welcomePageName`
- `0x1b2cc`: `welcomePageDisplayName`
- `0x1b2dc`: `welcomePageType`
- `0x1b3ae`: `AppModuleComponentId`
- `0x1b3c0`: `AppModuleComponentId`
- `0x1b3e7`: `ComponentType`
- `0x1b3f9`: `ComponentType`
- `0x1b4bc`: `Exception while loading AppData Cache from Database with LoadMasks =  Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1b1a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>::.ctor()
0x1b1a5  stloc.0
0x1b1a6  ldarg.1
0x1b1a7  brtrue.s loc_1B1B8
0x1b1a9  ldarg.0
0x1b1aa  ldarg.3
0x1b1ab  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::CreateDbConnection(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext organizationContext)
0x1b1b0  starg.s  1
0x1b1b2  ldarg.1
0x1b1b3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x1b1b8  ldarg.1
0x1b1b9  stloc.1
0x1b1ba  ldarg.3
0x1b1bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x1b1c0  ldc.i4.s 0x14
0x1b1c2  ldstr    aFetchingAppmod// "Fetching AppModule {0} metadata from da"...
0x1b1c7  ldc.i4.1
0x1b1c8  newarr   [mscorlib]System.Object
0x1b1cd  dup
0x1b1ce  ldc.i4.0
0x1b1cf  ldarg.2
0x1b1d0  stelem.ref
0x1b1d1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b1d6  ldarg.0
0x1b1d7  ldfld    class Microsoft.Crm.Metadata.AppMetaDataLoader Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::dataLoader
0x1b1dc  ldarg.1
0x1b1dd  ldarg.2
0x1b1de  callvirt instance class [System.Data]System.Data.IDbCommand Microsoft.Crm.Metadata.AppMetaDataLoader::AppDataLoadQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection connection, string key)
0x1b1e3  stloc.2
0x1b1e4  ldloc.2
0x1b1e5  ldc.i4   0x117
0x1b1ea  ldstr    aBuildappmetada// "BuildAppMetadataFromDb"
0x1b1ef  ldstr    aDA1SSrcManaged_8// "D:\\a\\1\\s\\src\\ManagedPlatform\\SDK"...
0x1b1f4  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteReader(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x1b1f9  stloc.3
0x1b1fa  br       loc_1B454
0x1b1ff  ldloc.3
0x1b200  ldstr    aAppmoduleid_0// "AppModuleId"
0x1b205  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b20a  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b20f  beq.s    loc_1B223
0x1b211  ldloc.3
0x1b212  ldstr    aAppmoduleid_0// "AppModuleId"
0x1b217  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b21c  unbox.any [mscorlib]System.Guid
0x1b221  br.s     loc_1B228
0x1b223  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b228  stloc.s  4
0x1b22a  ldloc.0
0x1b22b  ldloc.s  4
0x1b22d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>::ContainsKey(var<u1>)
0x1b232  brtrue   loc_1B3A3
0x1b237  ldnull
0x1b238  stloc.s  7
0x1b23a  ldnull
0x1b23b  stloc.s  8
0x1b23d  ldc.i4.2
0x1b23e  stloc.s  9
0x1b240  ldloc.3
0x1b241  ldstr    aIconwebresourc// "iconWebresourceId"
0x1b246  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b24b  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b250  beq.s    loc_1B299
0x1b252  ldloc.3
0x1b253  ldstr    aIconwebresourc// "iconWebresourceId"
0x1b258  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b25d  unbox.any [mscorlib]System.Guid
0x1b262  ldloc.3
0x1b263  ldstr    aIconname// "iconName"
0x1b268  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b26d  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b272  ldloc.3
0x1b273  ldstr    aIcondisplaynam// "iconDisplayName"
0x1b278  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b27d  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b282  ldloc.3
0x1b283  ldstr    aIcontype// "iconType"
0x1b288  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b28d  callvirt instance string [mscorlib]System.Object::ToString()
0x1b292  newobj   instance void Microsoft.Crm.Metadata.WebResourceInfo::.ctor(valuetype [mscorlib]System.Guid id, string name, string displayName, string type)
0x1b297  stloc.s  7
0x1b299  ldloc.3
0x1b29a  ldstr    aWelcomepageid// "welcomePageId"
0x1b29f  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b2a4  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b2a9  beq.s    loc_1B2F2
0x1b2ab  ldloc.3
0x1b2ac  ldstr    aWelcomepageid// "welcomePageId"
0x1b2b1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b2b6  unbox.any [mscorlib]System.Guid
0x1b2bb  ldloc.3
0x1b2bc  ldstr    aWelcomepagenam// "welcomePageName"
0x1b2c1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b2c6  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b2cb  ldloc.3
0x1b2cc  ldstr    aWelcomepagedis// "welcomePageDisplayName"
0x1b2d1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b2d6  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b2db  ldloc.3
0x1b2dc  ldstr    aWelcomepagetyp// "welcomePageType"
0x1b2e1  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b2e6  callvirt instance string [mscorlib]System.Object::ToString()
0x1b2eb  newobj   instance void Microsoft.Crm.Metadata.WebResourceInfo::.ctor(valuetype [mscorlib]System.Guid id, string name, string displayName, string type)
0x1b2f0  stloc.s  8
0x1b2f2  ldtoken  Microsoft.Crm.Metadata.AppModuleClientType
0x1b2f7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1b2fc  ldloc.3
0x1b2fd  ldstr    aClienttype// "ClientType"
0x1b302  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b307  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x1b30c  brfalse.s loc_1B320
0x1b30e  ldloc.3
0x1b30f  ldstr    aClienttype// "ClientType"
0x1b314  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b319  unbox.any Microsoft.Crm.Metadata.AppModuleClientType
0x1b31e  stloc.s  9
0x1b320  ldloc.s  4
0x1b322  ldloc.3
0x1b323  ldstr    aName// "Name"
0x1b328  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b32d  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b332  ldloc.3
0x1b333  ldstr    aFormfactor// "FormFactor"
0x1b338  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b33d  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b342  beq.s    loc_1B35B
0x1b344  ldloc.3
0x1b345  ldstr    aFormfactor// "FormFactor"
0x1b34a  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b34f  unbox.any [mscorlib]System.Int32
0x1b354  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1b359  br.s     loc_1B365
0x1b35b  ldloca.s 0xA
0x1b35d  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1b363  ldloc.s  0xA
0x1b365  ldloc.s  9
0x1b367  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.AppModuleComponent>::.ctor()
0x1b36c  ldloc.3
0x1b36d  ldstr    aUrl_0// "Url"
0x1b372  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b377  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b37c  ldloc.3
0x1b37d  ldstr    aUniquename_0// "UniqueName"
0x1b382  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b387  call     string Microsoft.Crm.Metadata.DynamicAppModuleCacheLoader::DBValueToString(object value)
0x1b38c  ldloc.s  7
0x1b38e  ldloc.s  8
0x1b390  newobj   instance void Microsoft.Crm.Metadata.AppModuleMetadata::.ctor(valuetype [mscorlib]System.Guid appModuleId, string appModuleName, valuetype [mscorlib]System.Nullable`1<int32> formFactor, valuetype Microsoft.Crm.Metadata.AppModuleClientType clientType, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.AppModuleComponent> appModuleComponents, string url, string uniqueName, class Microsoft.Crm.Metadata.WebResourceInfo webResourceInfo, class Microsoft.Crm.Metadata.WebResourceInfo welcomePageInfo)
0x1b395  stloc.s  5
0x1b397  ldloc.0
0x1b398  ldloc.s  4
0x1b39a  ldloc.s  5
0x1b39c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>::Add(var<u1>, !!T0)
0x1b3a1  br.s     loc_1B3AD
0x1b3a3  ldloc.0
0x1b3a4  ldloc.s  4
0x1b3a6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>::get_Item(void)
0x1b3ab  stloc.s  5
0x1b3ad  ldloc.3
0x1b3ae  ldstr    aAppmodulecompo// "AppModuleComponentId"
0x1b3b3  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b3b8  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b3bd  beq.s    loc_1B3D1
0x1b3bf  ldloc.3
0x1b3c0  ldstr    aAppmodulecompo// "AppModuleComponentId"
0x1b3c5  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b3ca  unbox.any [mscorlib]System.Guid
0x1b3cf  br.s     loc_1B3D6
0x1b3d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b3d6  stloc.s  6
0x1b3d8  ldloc.s  6
0x1b3da  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b3df  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b3e4  brfalse.s loc_1B454
0x1b3e6  ldloc.3
0x1b3e7  ldstr    aComponenttype// "ComponentType"
0x1b3ec  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b3f1  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b3f6  beq.s    loc_1B40F
0x1b3f8  ldloc.3
0x1b3f9  ldstr    aComponenttype// "ComponentType"
0x1b3fe  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b403  unbox.any [mscorlib]System.Int32
0x1b408  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1b40d  br.s     loc_1B419
0x1b40f  ldloca.s 0xA
0x1b411  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1b417  ldloc.s  0xA
0x1b419  ldloc.s  6
0x1b41b  ldloc.3
0x1b41c  ldstr    aObjectid_0// "ObjectId"
0x1b421  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b426  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x1b42b  beq.s    loc_1B43F
0x1b42d  ldloc.3
0x1b42e  ldstr    aObjectid_0// "ObjectId"
0x1b433  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0x1b438  unbox.any [mscorlib]System.Guid
0x1b43d  br.s     loc_1B444
0x1b43f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1b444  newobj   instance void Microsoft.Crm.Metadata.AppModuleComponent::.ctor(valuetype [mscorlib]System.Nullable`1<int32> componentType, valuetype [mscorlib]System.Guid componentId, valuetype [mscorlib]System.Guid objectId)
0x1b449  stloc.s  0xB
0x1b44b  ldloc.s  5
0x1b44d  ldloc.s  0xB
0x1b44f  callvirt instance void Microsoft.Crm.Metadata.AppModuleMetadata::AddAppModuleComponent(class Microsoft.Crm.Metadata.AppModuleComponent appModuleComp)
0x1b454  ldloc.3
0x1b455  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x1b45a  brtrue   loc_1B1FF
0x1b45f  leave.s  loc_1B46B
0x1b461  ldloc.3
0x1b462  brfalse.s loc_1B46A
0x1b464  ldloc.3
0x1b465  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b46a  endfinally
0x1b46b  leave.s  loc_1B477
0x1b46d  ldloc.2
0x1b46e  brfalse.s loc_1B476
0x1b470  ldloc.2
0x1b471  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b476  endfinally
0x1b477  leave.s  loc_1B483
0x1b479  ldloc.1
0x1b47a  brfalse.s loc_1B482
0x1b47c  ldloc.1
0x1b47d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b482  endfinally
0x1b483  ldloc.0
0x1b484  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>, class Microsoft.Crm.Metadata.AppModuleMetadata> <>c::<>9__11_0
0x1b489  dup
0x1b48a  brtrue.s loc_1B4A3
0x1b48c  pop
0x1b48d  ldsfld   class <>c <>c::<>9
0x1b492  ldftn    instance class Microsoft.Crm.Metadata.AppModuleMetadata <>c::<BuildAppMetadataFromDb>b__11_0(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata> kvp)
0x1b498  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>, class Microsoft.Crm.Metadata.AppModuleMetadata>::.ctor(object, native int)
0x1b49d  dup
0x1b49e  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Metadata.AppModuleMetadata>, class Microsoft.Crm.Metadata.AppModuleMetadata> <>c::<>9__11_0
0x1b4a3  call     T0x2B00004A
0x1b4a8  call     T0x2B00004B
0x1b4ad  stloc.s  0xC
0x1b4af  leave.s  loc_1B4DD
0x1b4b1  stloc.s  0xD
0x1b4b3  ldloc.s  0xD
0x1b4b5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b4ba  ldc.i4.s 0x1D
0x1b4bc  ldstr    aExceptionWhile// "Exception while loading AppData Cache f"...
0x1b4c1  ldc.i4.1
0x1b4c2  newarr   [mscorlib]System.Object
0x1b4c7  dup
0x1b4c8  ldc.i4.0
0x1b4c9  ldloc.s  0xD
0x1b4cb  stelem.ref
0x1b4cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b4d1  rethrow
0x1b4d3  ldarg.1
0x1b4d4  brfalse.s loc_1B4DC
0x1b4d6  ldarg.1
0x1b4d7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Dispose()
0x1b4dc  endfinally
0x1b4dd  ldloc.s  0xC
0x1b4df  ret
```
