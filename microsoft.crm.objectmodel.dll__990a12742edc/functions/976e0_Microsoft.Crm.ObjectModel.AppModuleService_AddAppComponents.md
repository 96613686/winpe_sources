# Microsoft.Crm.ObjectModel.AppModuleService::AddAppComponents

- ea: `0x976e0`
- end: `0x97b46`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::AddAppComponents`
- size: `1126`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f9b0`
- `0x93f40`
- `0x946c0`
- `0x94a50`
- `0x958c0`
- `0x96f40`
- `0x97050`
- `0x97140`
- `0x972d0`
- `0x97480`
- `0x97550`
- `0x976e0`

## string_xrefs

- `0x97895`: `componenttype`
- `0x97920`: `componenttype`
- `0x979d4`: `componenttype`
- `0x978a5`: `appmodulecomponentid`
- `0x97750`: `AppModuleComponent`
- `0x97875`: `AppModuleComponent`
- `0x977a2`: `componentstate`
- `0x97852`: `componentstate`
- `0x977eb`: `descriptor`
- `0x976f8`: `components`
- `0x97708`: `components`
- `0x97767`: `AppModule_BEGIN_{0}.AddAppComponents`
- `0x9782b`: `AppModuleService.AddAppComponents(): [appmoduleid:{0}], Doesnt exists.`
- `0x9796e`: `AppModuleService.AddAppComponents(): [appmoduleid:{0}], Invalid component type {1}`
- `0x97a34`: `AppModuleService.AddAppComponents(): [appmoduleid:{0}] No components to be added.`
- `0x97abd`: `AppModuleService.AddAppComponents(): Exception: {0}`
- `0x97ae1`: `Exception while executing AddAppComponents : {0}`
- `0x97b0e`: `AppModule_END_{0}.AddAppComponents(appModule={1})`
- `0x97b34`: `AddAppComponents`

## pseudocode

```c

```

## disassembly

```asm
0x976e0  ldarg.0
0x976e1  ldarg.3
0x976e2  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x976e7  ldarg.1
0x976e8  box      [mscorlib]System.Guid
0x976ed  ldstr    aAppid// "appId"
0x976f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x976f7  ldarg.2
0x976f8  ldstr    aComponents// "components"
0x976fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x97702  ldarg.2
0x97703  call     T0x2B0000B2
0x97708  ldstr    aComponents// "components"
0x9770d  call     T0x2B00016C
0x97712  ldarg.2
0x97713  call     T0x2B00016D
0x97718  call     T0x2B0000B2
0x9771d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>)
0x97722  starg.s  2
0x97724  ldarg.3
0x97725  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9772a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x9772f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x97734  stloc.0
0x97735  ldarg.0
0x97736  ldloc.0
0x97737  ldarg.3
0x97738  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::getListOfAppModuleEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9773d  stloc.1
0x9773e  ldc.i4.m1
0x9773f  stloc.2
0x97740  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97745  stloc.3
0x97746  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x9774b  stloc.s  6
0x9774d  ldnull
0x9774e  stloc.s  7
0x97750  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x97755  ldarg.3
0x97756  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9775b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x97760  stloc.s  8
0x97762  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97767  ldstr    aAppmoduleBegin_0// "AppModule_BEGIN_{0}.AddAppComponents"
0x9776c  ldc.i4.1
0x9776d  newarr   [mscorlib]System.Object
0x97772  dup
0x97773  ldc.i4.0
0x97774  ldarg.0
0x97775  stelem.ref
0x97776  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9777b  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x97780  ldarg.0
0x97781  ldstr    aAppmodule// "AppModule"
0x97786  ldstr    aAppmoduleid// "appmoduleid"
0x9778b  ldc.i4.1
0x9778c  newarr   [mscorlib]System.Guid
0x97791  dup
0x97792  ldc.i4.0
0x97793  ldarg.1
0x97794  stelem   [mscorlib]System.Guid
0x97799  ldc.i4.s 0xB
0x9779b  newarr   [mscorlib]System.String
0x977a0  dup
0x977a1  ldc.i4.0
0x977a2  ldstr    aComponentstate_0// "componentstate"
0x977a7  stelem.ref
0x977a8  dup
0x977a9  ldc.i4.1
0x977aa  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x977af  stelem.ref
0x977b0  dup
0x977b1  ldc.i4.2
0x977b2  ldstr    aSolutionid// "solutionid"
0x977b7  stelem.ref
0x977b8  dup
0x977b9  ldc.i4.3
0x977ba  ldstr    aUniquename// "uniquename"
0x977bf  stelem.ref
0x977c0  dup
0x977c1  ldc.i4.4
0x977c2  ldstr    aName// "name"
0x977c7  stelem.ref
0x977c8  dup
0x977c9  ldc.i4.5
0x977ca  ldstr    aDescription// "description"
0x977cf  stelem.ref
0x977d0  dup
0x977d1  ldc.i4.6
0x977d2  ldstr    aModifiedon_0// "modifiedon"
0x977d7  stelem.ref
0x977d8  dup
0x977d9  ldc.i4.7
0x977da  ldstr    aUrl// "url"
0x977df  stelem.ref
0x977e0  dup
0x977e1  ldc.i4.8
0x977e2  ldstr    aClienttype// "clienttype"
0x977e7  stelem.ref
0x977e8  dup
0x977e9  ldc.i4.s 9
0x977eb  ldstr    aDescriptor// "descriptor"
0x977f0  stelem.ref
0x977f1  dup
0x977f2  ldc.i4.s 0xA
0x977f4  ldstr    aVersionnumber// "versionnumber"
0x977f9  stelem.ref
0x977fa  ldarg.3
0x977fb  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97800  stloc.s  5
0x97802  ldarg.0
0x97803  ldarg.1
0x97804  ldstr    aAppmodule// "AppModule"
0x97809  ldarg.3
0x9780a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9780f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x97814  ldloc.s  5
0x97816  ldarg.3
0x97817  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x9781c  stloc.s  9
0x9781e  ldloc.s  9
0x97820  brtrue.s loc_97850
0x97822  ldnull
0x97823  ldarg.3
0x97824  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97829  ldc.i4.s 0x47
0x9782b  ldstr    aAppmoduleservi_115// "AppModuleService.AddAppComponents(): [a"...
0x97830  ldc.i4.1
0x97831  newarr   [mscorlib]System.Object
0x97836  dup
0x97837  ldc.i4.0
0x97838  ldarg.1
0x97839  box      [mscorlib]System.Guid
0x9783e  stelem.ref
0x9783f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x97844  ldstr    aAppmodule// "AppModule"
0x97849  ldarg.1
0x9784a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string, valuetype [mscorlib]System.Guid)
0x9784f  throw
0x97850  ldloc.s  9
0x97852  ldstr    aComponentstate_0// "componentstate"
0x97857  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x9785c  unbox.any [mscorlib]System.Int32
0x97861  stloc.2
0x97862  ldloc.s  9
0x97864  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x97869  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x9786e  unbox.any [mscorlib]System.Guid
0x97873  stloc.3
0x97874  ldarg.0
0x97875  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x9787a  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x9787f  ldc.i4.1
0x97880  newarr   [mscorlib]System.Guid
0x97885  dup
0x97886  ldc.i4.0
0x97887  ldloc.3
0x97888  stelem   [mscorlib]System.Guid
0x9788d  ldc.i4.3
0x9788e  newarr   [mscorlib]System.String
0x97893  dup
0x97894  ldc.i4.0
0x97895  ldstr    aComponenttype// "componenttype"
0x9789a  stelem.ref
0x9789b  dup
0x9789c  ldc.i4.1
0x9789d  ldstr    aObjectid// "objectid"
0x978a2  stelem.ref
0x978a3  dup
0x978a4  ldc.i4.2
0x978a5  ldstr    aAppmodulecompo// "appmodulecomponentid"
0x978aa  stelem.ref
0x978ab  ldarg.3
0x978ac  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x978b1  stloc.s  5
0x978b3  ldloc.s  6
0x978b5  ldloc.s  5
0x978b7  ldarg.3
0x978b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x978bd  stloc.s  7
0x978bf  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x978c4  stloc.s  0xA
0x978c6  ldarg.2
0x978c7  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::GetEnumerator()
0x978cc  stloc.s  0xB
0x978ce  br       loc_97A09
0x978d3  ldloc.s  0xB
0x978d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Current()
0x978da  stloc.s  0xC
0x978dc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x978e1  stloc.s  0xD
0x978e3  ldc.i4.m1
0x978e4  stloc.s  0xE
0x978e6  ldc.i4.0
0x978e7  stloc.s  0xF
0x978e9  ldarg.0
0x978ea  ldloc.1
0x978eb  ldloc.s  0xC
0x978ed  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::appModuleOdataPayloadTransalation(class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> entitiesName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0x978f2  ldarg.0
0x978f3  ldloc.s  0xC
0x978f5  call     instance int32 Microsoft.Crm.ObjectModel.AppModuleService::getComponentTypeFromLogicalName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0x978fa  stloc.s  0x10
0x978fc  ldc.i4.0
0x978fd  stloc.s  0x11
0x978ff  br.s     loc_9794E
0x97901  ldloc.s  7
0x97903  ldloc.s  0x11
0x97905  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x9790a  ldstr    aObjectid// "objectid"
0x9790f  ldloca.s 0xD
0x97911  callvirt T0x2B00003B
0x97916  pop
0x97917  ldloc.s  7
0x97919  ldloc.s  0x11
0x9791b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x97920  ldstr    aComponenttype// "componenttype"
0x97925  ldloca.s 0xE
0x97927  callvirt T0x2B00003C
0x9792c  pop
0x9792d  ldloc.s  0x10
0x9792f  ldloc.s  0xE
0x97931  bne.un.s loc_97948
0x97933  ldloc.s  0xC
0x97935  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x9793a  ldloc.s  0xD
0x9793c  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x97941  brfalse.s loc_97948
0x97943  ldc.i4.1
0x97944  stloc.s  0xF
0x97946  br.s     loc_97959
0x97948  ldloc.s  0x11
0x9794a  ldc.i4.1
0x9794b  add
0x9794c  stloc.s  0x11
0x9794e  ldloc.s  0x11
0x97950  ldloc.s  7
0x97952  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x97957  blt.s    loc_97901
0x97959  ldloc.s  0xF
0x9795b  brtrue   loc_97A09
0x97960  ldloc.s  0x10
0x97962  ldc.i4.m1
0x97963  bne.un.s loc_979B2
0x97965  ldnull
0x97966  ldarg.3
0x97967  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9796c  ldc.i4.s 0x47
0x9796e  ldstr    aAppmoduleservi_116// "AppModuleService.AddAppComponents(): [a"...
0x97973  ldc.i4.2
0x97974  newarr   [mscorlib]System.Object
0x97979  dup
0x9797a  ldc.i4.0
0x9797b  ldarg.1
0x9797c  box      [mscorlib]System.Guid
0x97981  stelem.ref
0x97982  dup
0x97983  ldc.i4.1
0x97984  ldloc.s  0x10
0x97986  box      [mscorlib]System.Int32
0x9798b  stelem.ref
0x9798c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x97991  ldc.i4   0x80050112
0x97996  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x9799b  ldloc.s  0xC
0x9799d  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x979a2  call     string [mscorlib]System.String::Format(string, object)
0x979a7  ldc.i4   0x80050112
0x979ac  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x979b1  throw
0x979b2  ldarg.3
0x979b3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x979b8  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponent::.ctor(valuetype [mscorlib]System.Guid)
0x979bd  stloc.s  0x12
0x979bf  ldloc.s  0x12
0x979c1  ldstr    aObjectid// "objectid"
0x979c6  ldloc.s  0xD
0x979c8  box      [mscorlib]System.Guid
0x979cd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x979d2  ldloc.s  0x12
0x979d4  ldstr    aComponenttype// "componenttype"
0x979d9  ldloc.s  0xE
0x979db  box      [mscorlib]System.Int32
0x979e0  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x979e5  ldloc.s  0xA
0x979e7  ldloc.s  0xC
0x979e9  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x979ee  ldloc.s  0xC
0x979f0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x979f5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x979fa  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Add(var<u1>)
0x979ff  ldloc.s  8
0x97a01  ldloc.s  0x12
0x97a03  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x97a08  pop
0x97a09  ldloc.s  0xB
0x97a0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x97a10  brtrue   loc_978D3
0x97a15  leave.s  loc_97A23
0x97a17  ldloc.s  0xB
  ... truncated ...
```
