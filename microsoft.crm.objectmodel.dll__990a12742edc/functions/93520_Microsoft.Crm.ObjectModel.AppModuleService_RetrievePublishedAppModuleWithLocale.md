# Microsoft.Crm.ObjectModel.AppModuleService::RetrievePublishedAppModuleWithLocale

- ea: `0x93520`
- end: `0x93c2c`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::RetrievePublishedAppModuleWithLocale`
- size: `1804`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x93520`
- `0x93ca0`
- `0x96d10`
- `0xce270`

## string_xrefs

- `0x9358d`: `welcomepageid`
- `0x93ae5`: `welcomepageid`
- `0x93b04`: `welcomepageid`
- `0x9357d`: `createdon`
- `0x93a1b`: `createdon`
- `0x93626`: `componentstate`
- `0x93525`: `AppModuleComponent_BEGIN_{0}.RetrievePublishedAppModuleWithLocale`
- `0x93be4`: `AppModuleService.RetrievePublishedAppModuleWithLocale(): User doesnt have [{0}] privilege on [{1}].`
- `0x93c11`: `AppModuleComponent_END_{0}.RetrievePublishedAppModuleWithLocale`

## pseudocode

```c

```

## disassembly

```asm
0x93520  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x93525  ldstr    aAppmodulecompo_4// "AppModuleComponent_BEGIN_{0}.RetrievePu"...
0x9352a  ldc.i4.1
0x9352b  newarr   [mscorlib]System.Object
0x93530  dup
0x93531  ldc.i4.0
0x93532  ldarg.0
0x93533  stelem.ref
0x93534  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x93539  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9353e  ldarg.1
0x9353f  box      [mscorlib]System.Int32
0x93544  ldstr    aAppmodule_0// "appmodule"
0x93549  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9354e  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleCollection::.ctor()
0x93553  stloc.0
0x93554  ldc.i4.s 0xA
0x93556  newarr   [mscorlib]System.String
0x9355b  dup
0x9355c  ldc.i4.0
0x9355d  ldstr    aAppmoduleid// "appmoduleid"
0x93562  stelem.ref
0x93563  dup
0x93564  ldc.i4.1
0x93565  ldstr    aName// "name"
0x9356a  stelem.ref
0x9356b  dup
0x9356c  ldc.i4.2
0x9356d  ldstr    aDescription// "description"
0x93572  stelem.ref
0x93573  dup
0x93574  ldc.i4.3
0x93575  ldstr    aUrl// "url"
0x9357a  stelem.ref
0x9357b  dup
0x9357c  ldc.i4.4
0x9357d  ldstr    aCreatedon// "createdon"
0x93582  stelem.ref
0x93583  dup
0x93584  ldc.i4.5
0x93585  ldstr    aWebresourceid// "webresourceid"
0x9358a  stelem.ref
0x9358b  dup
0x9358c  ldc.i4.6
0x9358d  ldstr    aWelcomepageid// "welcomepageid"
0x93592  stelem.ref
0x93593  dup
0x93594  ldc.i4.7
0x93595  ldstr    aUniquename// "uniquename"
0x9359a  stelem.ref
0x9359b  dup
0x9359c  ldc.i4.8
0x9359d  ldstr    aAppmoduleversi// "appmoduleversion"
0x935a2  stelem.ref
0x935a3  dup
0x935a4  ldc.i4.s 9
0x935a6  ldstr    aClienttype// "clienttype"
0x935ab  stelem.ref
0x935ac  stloc.1
0x935ad  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleInfo>::.ctor()
0x935b2  stloc.2
0x935b3  newobj   instance void Microsoft.Crm.ObjectModel.OrganizationService::.ctor()
0x935b8  ldc.i4.0
0x935b9  ldarg.2
0x935ba  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Organization.OrganizationDetail class Microsoft.Crm.ObjectModel.OrganizationServiceInternal`1<class Microsoft.Crm.ObjectModel.ProvisioningOff>::RetrieveCurrentOrganization(valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Organization.EndpointAccessType, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x935bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Organization.EndpointCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Organization.OrganizationDetail::get_Endpoints()
0x935c4  ldc.i4.2
0x935c5  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Organization.EndpointType, string>::get_Item(void)
0x935ca  stloc.3
0x935cb  ldarg.0
0x935cc  ldarg.1
0x935cd  ldloc.3
0x935ce  ldarg.2
0x935cf  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleInfo Microsoft.Crm.ObjectModel.AppModuleService::GetLegacyCRMApp(int32 LcId, string baseUrl, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x935d4  stloc.s  4
0x935d6  ldloc.s  4
0x935d8  brfalse.s loc_935E2
0x935da  ldloc.2
0x935db  ldloc.s  4
0x935dd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleInfo>::Add(var<u1>)
0x935e2  ldarg.2
0x935e3  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x935e8  ldstr    aAppmodule// "AppModule"
0x935ed  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string)
0x935f2  ldc.i4.1
0x935f3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetPrivilege(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType)
0x935f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Privilege::get_Id()
0x935fd  stloc.s  5
0x935ff  ldarg.2
0x93600  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x93605  ldloc.s  5
0x93607  ldarg.2
0x93608  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9360d  brtrue   loc_93BDC
0x93612  ldstr    aAppmodule// "AppModule"
0x93617  ldarg.2
0x93618  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x9361d  stloc.s  6
0x9361f  ldloc.s  6
0x93621  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x93626  ldstr    aComponentstate_0// "componentstate"
0x9362b  ldc.i4.0
0x9362c  ldc.i4.0
0x9362d  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x93632  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x93637  pop
0x93638  ldloc.s  6
0x9363a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x9363f  ldstr    aClienttype// "clienttype"
0x93644  ldc.i4.1
0x93645  ldc.i4.8
0x93646  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ClientType
0x9364b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x93650  pop
0x93651  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x93656  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x9365b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppDesignerClientTypeSelection()
0x93660  ldarg.2
0x93661  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureAvailable(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x93666  brfalse.s loc_93698
0x93668  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x9366d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x93672  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_AppDesignerClientTypeSelection()
0x93677  ldarg.2
0x93678  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9367d  brtrue.s loc_93698
0x9367f  ldloc.s  6
0x93681  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x93686  ldstr    aClienttype// "clienttype"
0x9368b  ldc.i4.1
0x9368c  ldc.i4.4
0x9368d  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.ClientType
0x93692  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x93697  pop
0x93698  ldloc.s  6
0x9369a  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x9369f  ldloc.1
0x936a0  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x936a5  ldarg.0
0x936a6  ldloc.s  6
0x936a8  ldarg.2
0x936a9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x936ae  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x936b3  stloc.s  7
0x936b5  ldc.i4.0
0x936b6  stloc.s  8
0x936b8  br       loc_93BC6
0x936bd  ldloc.s  7
0x936bf  ldloc.s  8
0x936c1  ldc.i4   0x1F4
0x936c6  mul
0x936c7  call     T0x2B00015F
0x936cc  ldc.i4   0x1F4
0x936d1  call     T0x2B000160
0x936d6  call     T0x2B000161
0x936db  stloc.s  9
0x936dd  ldloc.s  9
0x936df  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_0
0x936e4  dup
0x936e5  brtrue.s loc_936FE
0x936e7  pop
0x936e8  ldsfld   class <>c <>c::<>9
0x936ed  ldftn    instance valuetype [mscorlib]System.Guid <>c::<RetrievePublishedAppModuleWithLocale>b__111_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule)
0x936f3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x936f8  dup
0x936f9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_0
0x936fe  call     T0x2B000073
0x93703  call     T0x2B00005B
0x93708  stloc.s  0xA
0x9370a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.LocalizedLabelService::.ctor()
0x9370f  stloc.s  0xB
0x93711  ldstr    aLocalizedlabel// "LocalizedLabel"
0x93716  ldarg.2
0x93717  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9371c  stloc.s  0xC
0x9371e  ldloc.s  0xC
0x93720  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x93725  ldstr    aObjectcolumnna// "objectcolumnname"
0x9372a  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x9372f  ldloc.s  0xC
0x93731  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x93736  ldstr    aLabel// "label"
0x9373b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x93740  ldloc.s  0xC
0x93742  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Columns()
0x93747  ldstr    aObjectid// "objectid"
0x9374c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.ColumnCollection::AddColumn(string)
0x93751  ldloc.s  0xC
0x93753  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x93758  ldstr    aLanguageid// "languageid"
0x9375d  ldc.i4.1
0x9375e  newarr   [mscorlib]System.Object
0x93763  dup
0x93764  ldc.i4.0
0x93765  ldarg.1
0x93766  box      [mscorlib]System.Int32
0x9376b  stelem.ref
0x9376c  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, class [mscorlib]System.Array)
0x93771  ldloc.s  0xC
0x93773  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x93778  ldstr    aObjectid// "objectid"
0x9377d  ldc.i4.2
0x9377e  ldloc.s  0xA
0x93780  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x93785  ldloc.s  0xC
0x93787  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression::get_Conditions()
0x9378c  ldstr    aObjectcolumnna// "objectcolumnname"
0x93791  ldc.i4.2
0x93792  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x93797  dup
0x93798  ldstr    aName// "name"
0x9379d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x937a2  dup
0x937a3  ldstr    aDescription// "description"
0x937a8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x937ad  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x937b2  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionCollection::AddCondition(string, valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleConditionOperator, class [mscorlib]System.Array)
0x937b7  ldloc.s  0xB
0x937b9  ldloc.s  0xC
0x937bb  ldarg.2
0x937bc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x937c1  ldc.i4.1
0x937c2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.MetadataBusinessEntities.SimpleQueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext, bool)
0x937c7  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_1
0x937cc  dup
0x937cd  brtrue.s loc_937E6
0x937cf  pop
0x937d0  ldsfld   class <>c <>c::<>9
0x937d5  ldftn    instance valuetype [mscorlib]System.Guid <>c::<RetrievePublishedAppModuleWithLocale>b__111_1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity label)
0x937db  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x937e0  dup
0x937e1  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_1
0x937e6  call     T0x2B000162
0x937eb  stloc.s  0xD
0x937ed  ldloc.s  9
0x937ef  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_2
0x937f4  dup
0x937f5  brtrue.s loc_9380E
0x937f7  pop
0x937f8  ldsfld   class <>c <>c::<>9
0x937fd  ldftn    instance valuetype [mscorlib]System.Guid <>c::<RetrievePublishedAppModuleWithLocale>b__111_2(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModuleEntity)
0x93803  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x93808  dup
0x93809  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_2
0x9380e  ldarg.0
0x9380f  ldftn    instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::<RetrievePublishedAppModuleWithLocale>b__111_3(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModuleEntity)
0x93815  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>::.ctor(object, native int)
0x9381a  call     T0x2B000163
0x9381f  stloc.s  0xE
0x93821  ldloc.s  0xE
0x93823  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>> <>c::<>9__111_4
0x93828  dup
0x93829  brtrue.s loc_93842
0x9382b  pop
0x9382c  ldsfld   class <>c <>c::<>9
0x93831  ldftn    instance class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <>c::<RetrievePublishedAppModuleWithLocale>b__111_4(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>> ResIdDict)
0x93837  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>>::.ctor(object, native int)
0x9383c  dup
0x9383d  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid>>, class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>> <>c::<>9__111_4
0x93842  call     T0x2B000164
0x93847  call     T0x2B000039
0x9384c  stloc.s  0xF
0x9384e  ldarg.0
0x9384f  ldloc.s  0xF
0x93851  ldarg.2
0x93852  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppModuleService::GetWebResources(class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> webResIdList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x93857  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x9385c  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_5
0x93861  dup
0x93862  brtrue.s loc_9387B
0x93864  pop
0x93865  ldsfld   class <>c <>c::<>9
0x9386a  ldftn    instance valuetype [mscorlib]System.Guid <>c::<RetrievePublishedAppModuleWithLocale>b__111_5(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity webRes)
0x93870  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x93875  dup
0x93876  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, valuetype [mscorlib]System.Guid> <>c::<>9__111_5
0x9387b  call     T0x2B000165
0x93880  stloc.s  0x10
0x93882  ldloc.s  9
0x93884  stloc.s  0x11
0x93886  ldc.i4.0
0x93887  stloc.s  0x12
0x93889  br       loc_93BB5
0x9388e  ldloc.s  0x11
0x93890  ldloc.s  0x12
0x93892  ldelem.ref
0x93893  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x93898  stloc.s  0x13
0x9389a  newobj   instance void [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleInfo::.ctor()
0x9389f  stloc.s  0x14
0x938a1  ldstr    asc_24F76C// ""
0x938a6  stloc.s  0x15
0x938a8  ldstr    asc_24F76C// ""
0x938ad  stloc.s  0x16
0x938af  ldloc.s  0xD
0x938b1  ldloc.s  0x13
0x938b3  ldstr    aAppmoduleid// "appmoduleid"
0x938b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x938bd  callvirt instance string [mscorlib]System.Object::ToString()
0x938c2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
  ... truncated ...
```
