# Microsoft.Crm.ObjectModel.AppModuleService::AddEditAppModule

- ea: `0x910e0`
- end: `0x916cb`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::AddEditAppModule`
- size: `1515`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x19b50`
- `0x8f9b0`
- `0x910e0`
- `0x93f40`
- `0x946c0`
- `0x94800`
- `0x94a50`
- `0x95500`
- `0x958c0`
- `0x96f40`
- `0x97050`

## string_xrefs

- `0x91358`: `componenttype`
- `0x91486`: `componenttype`
- `0x914a1`: `componenttype`
- `0x915b1`: `componenttype`
- `0x91368`: `appmodulecomponentid`
- `0x91338`: `AppModuleComponent`
- `0x91225`: `componentstate`
- `0x912a3`: `componentstate`
- `0x913bf`: `componentstate`
- `0x9126e`: `descriptor`
- `0x910f4`: `appModuleComponents`
- `0x9118f`: `AppModuleService.AddEditAppModule(): Atempt to create multiple Sitemap component for appmodule`
- `0x912cc`: `AppModuleService.AddEditAppModule(): [appmoduleid:{0}] [existingAppModuleIdUnique:{1}] [appmodulestate:{2}].`
- `0x9131e`: `AppModuleService.AddEditAppModule(): [new appmoduleidunique:{0}]`
- `0x913a1`: `AppModuleService.AddEditAppModule(): Updating Published AppModule [{0}:{1}][{2}:{3}][appModuleComponents.count:{4}]`
- `0x91432`: `AppModuleService.AddEditAppModule(): [appModuleComponentIdsToBeDeleted:{0}]`
- `0x914f0`: `AppModuleService.AddEditAppModule(): Invalid appmodule [componenttype:{0}], Exception:{1}`
- `0x9155d`: `AppModuleService.AddEditAppModule(): Invalid appmodule component object [componenttype:{0}] [objectid:{1}], Exception:{2}`
- `0x91619`: `AppModuleService.AddEditAppModule(): Exception: {0}`
- `0x9166e`: `AppDesigner.Error_EditEntityFormOpen`

## pseudocode

```c

```

## disassembly

```asm
0x910e0  ldarg.0
0x910e1  ldarg.s  4
0x910e3  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x910e8  ldarg.2
0x910e9  ldstr    aAppmodule_1// "appModule"
0x910ee  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x910f3  ldarg.1
0x910f4  ldstr    aAppmodulecompo_3// "appModuleComponents"
0x910f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x910fe  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x91103  stloc.0
0x91104  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x91109  stloc.1
0x9110a  ldc.i4.m1
0x9110b  stloc.2
0x9110c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x91111  stloc.3
0x91112  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x91117  stloc.s  5
0x91119  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor()
0x9111e  stloc.s  6
0x91120  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x91125  ldstr    aAppmoduleBegin// "AppModule_BEGIN_{0}.AddEditAppModule"
0x9112a  ldc.i4.1
0x9112b  newarr   [mscorlib]System.Object
0x91130  dup
0x91131  ldc.i4.0
0x91132  ldarg.0
0x91133  stelem.ref
0x91134  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x91139  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9113e  ldnull
0x9113f  stloc.s  7
0x91141  ldarg.1
0x91142  call     class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionExtensions::ToCollection(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntityCollection)
0x91147  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool> <>c::<>9__93_0
0x9114c  dup
0x9114d  brtrue.s loc_91166
0x9114f  pop
0x91150  ldsfld   class <>c <>c::<>9
0x91155  ldftn    instance bool <>c::<AddEditAppModule>b__93_0(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity amc)
0x9115b  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool>::.ctor(object, native int)
0x91160  dup
0x91161  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool> <>c::<>9__93_0
0x91166  call     T0x2B00015C
0x9116b  ldc.i4.1
0x9116c  ble.s    loc_911C7
0x9116e  ldc.i4   0x80050111
0x91173  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x91178  ldc.i4   0x80050111
0x9117d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x91182  stloc.s  8
0x91184  ldloc.s  8
0x91186  ldarg.s  4
0x91188  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9118d  ldc.i4.s 0x47
0x9118f  ldstr    aAppmoduleservi_35// "AppModuleService.AddEditAppModule(): At"...
0x91194  ldc.i4.0
0x91195  newarr   [mscorlib]System.Object
0x9119a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9119f  ldloc.s  8
0x911a1  ldarg.s  4
0x911a3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x911a8  ldc.i4.s 0x14
0x911aa  ldstr    a0_0// "{0}"
0x911af  ldc.i4.1
0x911b0  newarr   [mscorlib]System.Object
0x911b5  dup
0x911b6  ldc.i4.0
0x911b7  ldloc.s  8
0x911b9  callvirt instance string [mscorlib]System.Exception::get_Message()
0x911be  stelem.ref
0x911bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x911c4  ldloc.s  8
0x911c6  throw
0x911c7  nop
0x911c8  ldarg.s  4
0x911ca  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x911cf  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x911d4  ldarg.3
0x911d5  brfalse.s loc_911F5
0x911d7  ldarg.0
0x911d8  ldarg.2
0x911d9  ldarg.s  4
0x911db  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x911e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x911e5  stloc.1
0x911e6  ldarg.0
0x911e7  ldloc.1
0x911e8  ldarg.s  4
0x911ea  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppModuleService::GetAppModuleIdUnique(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x911ef  stloc.0
0x911f0  br       loc_91457
0x911f5  ldarg.2
0x911f6  ldstr    aAppmoduleid// "appmoduleid"
0x911fb  ldloca.s 1
0x911fd  callvirt T0x2B0000EF
0x91202  pop
0x91203  ldarg.0
0x91204  ldstr    aAppmodule// "AppModule"
0x91209  ldstr    aAppmoduleid// "appmoduleid"
0x9120e  ldc.i4.1
0x9120f  newarr   [mscorlib]System.Guid
0x91214  dup
0x91215  ldc.i4.0
0x91216  ldloc.1
0x91217  stelem   [mscorlib]System.Guid
0x9121c  ldc.i4.s 0xB
0x9121e  newarr   [mscorlib]System.String
0x91223  dup
0x91224  ldc.i4.0
0x91225  ldstr    aComponentstate_0// "componentstate"
0x9122a  stelem.ref
0x9122b  dup
0x9122c  ldc.i4.1
0x9122d  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x91232  stelem.ref
0x91233  dup
0x91234  ldc.i4.2
0x91235  ldstr    aSolutionid// "solutionid"
0x9123a  stelem.ref
0x9123b  dup
0x9123c  ldc.i4.3
0x9123d  ldstr    aUniquename// "uniquename"
0x91242  stelem.ref
0x91243  dup
0x91244  ldc.i4.4
0x91245  ldstr    aName// "name"
0x9124a  stelem.ref
0x9124b  dup
0x9124c  ldc.i4.5
0x9124d  ldstr    aDescription// "description"
0x91252  stelem.ref
0x91253  dup
0x91254  ldc.i4.6
0x91255  ldstr    aModifiedon_0// "modifiedon"
0x9125a  stelem.ref
0x9125b  dup
0x9125c  ldc.i4.7
0x9125d  ldstr    aUrl// "url"
0x91262  stelem.ref
0x91263  dup
0x91264  ldc.i4.8
0x91265  ldstr    aClienttype// "clienttype"
0x9126a  stelem.ref
0x9126b  dup
0x9126c  ldc.i4.s 9
0x9126e  ldstr    aDescriptor// "descriptor"
0x91273  stelem.ref
0x91274  dup
0x91275  ldc.i4.s 0xA
0x91277  ldstr    aVersionnumber// "versionnumber"
0x9127c  stelem.ref
0x9127d  ldarg.s  4
0x9127f  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91284  stloc.s  4
0x91286  ldarg.0
0x91287  ldloc.1
0x91288  ldstr    aAppmodule// "AppModule"
0x9128d  ldarg.s  4
0x9128f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x91294  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x91299  ldloc.s  4
0x9129b  ldarg.s  4
0x9129d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x912a2  dup
0x912a3  ldstr    aComponentstate_0// "componentstate"
0x912a8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x912ad  unbox.any [mscorlib]System.Int32
0x912b2  stloc.2
0x912b3  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x912b8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x912bd  unbox.any [mscorlib]System.Guid
0x912c2  stloc.3
0x912c3  ldarg.s  4
0x912c5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x912ca  ldc.i4.s 0x47
0x912cc  ldstr    aAppmoduleservi_36// "AppModuleService.AddEditAppModule(): [a"...
0x912d1  ldc.i4.3
0x912d2  newarr   [mscorlib]System.Object
0x912d7  dup
0x912d8  ldc.i4.0
0x912d9  ldloc.1
0x912da  box      [mscorlib]System.Guid
0x912df  stelem.ref
0x912e0  dup
0x912e1  ldc.i4.1
0x912e2  ldloc.3
0x912e3  box      [mscorlib]System.Guid
0x912e8  stelem.ref
0x912e9  dup
0x912ea  ldc.i4.2
0x912eb  ldloc.2
0x912ec  box      [mscorlib]System.Int32
0x912f1  stelem.ref
0x912f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x912f7  ldloc.1
0x912f8  ldstr    aAppmoduleid// "appmoduleid"
0x912fd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x91302  ldarg.0
0x91303  ldarg.2
0x91304  ldarg.s  4
0x91306  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::UpdateApp(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9130b  ldarg.0
0x9130c  ldloc.1
0x9130d  ldarg.s  4
0x9130f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.AppModuleService::GetAppModuleIdUnique(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91314  stloc.0
0x91315  ldarg.s  4
0x91317  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9131c  ldc.i4.s 0x47
0x9131e  ldstr    aAppmoduleservi_37// "AppModuleService.AddEditAppModule(): [n"...
0x91323  ldc.i4.1
0x91324  newarr   [mscorlib]System.Object
0x91329  dup
0x9132a  ldc.i4.0
0x9132b  ldloc.0
0x9132c  box      [mscorlib]System.Guid
0x91331  stelem.ref
0x91332  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x91337  ldarg.0
0x91338  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x9133d  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x91342  ldc.i4.1
0x91343  newarr   [mscorlib]System.Guid
0x91348  dup
0x91349  ldc.i4.0
0x9134a  ldloc.3
0x9134b  stelem   [mscorlib]System.Guid
0x91350  ldc.i4.3
0x91351  newarr   [mscorlib]System.String
0x91356  dup
0x91357  ldc.i4.0
0x91358  ldstr    aComponenttype// "componenttype"
0x9135d  stelem.ref
0x9135e  dup
0x9135f  ldc.i4.1
0x91360  ldstr    aObjectid// "objectid"
0x91365  stelem.ref
0x91366  dup
0x91367  ldc.i4.2
0x91368  ldstr    aAppmodulecompo// "appmodulecomponentid"
0x9136d  stelem.ref
0x9136e  ldarg.s  4
0x91370  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x91375  stloc.s  4
0x91377  ldloc.s  5
0x91379  ldloc.s  4
0x9137b  ldarg.s  4
0x9137d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x91382  stloc.s  7
0x91384  ldloc.2
0x91385  brtrue.s loc_91392
0x91387  ldarg.1
0x91388  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x9138d  ldc.i4.0
0x9138e  ceq
0x91390  br.s     loc_91393
0x91392  ldc.i4.0
0x91393  ldarg.s  5
0x91395  and
0x91396  brfalse.s loc_913EE
0x91398  ldarg.s  4
0x9139a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9139f  ldc.i4.s 0x47
0x913a1  ldstr    aAppmoduleservi_38// "AppModuleService.AddEditAppModule(): Up"...
0x913a6  ldc.i4.5
0x913a7  newarr   [mscorlib]System.Object
0x913ac  dup
0x913ad  ldc.i4.0
0x913ae  ldstr    aAppmoduleid// "appmoduleid"
0x913b3  stelem.ref
0x913b4  dup
0x913b5  ldc.i4.1
0x913b6  ldloc.1
0x913b7  box      [mscorlib]System.Guid
0x913bc  stelem.ref
0x913bd  dup
0x913be  ldc.i4.2
0x913bf  ldstr    aComponentstate_0// "componentstate"
0x913c4  stelem.ref
0x913c5  dup
0x913c6  ldc.i4.3
0x913c7  ldloc.2
0x913c8  box      [mscorlib]System.Int32
0x913cd  stelem.ref
0x913ce  dup
0x913cf  ldc.i4.4
0x913d0  ldarg.1
0x913d1  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x913d6  box      [mscorlib]System.Int32
0x913db  stelem.ref
0x913dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x913e1  ldarg.0
0x913e2  ldloc.s  7
0x913e4  ldloc.0
0x913e5  ldarg.s  4
0x913e7  call     instance class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::UpdatePublishAppModuleWithNoComponents(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection existingAppModuleComponents, valuetype [mscorlib]System.Guid newAppModuleIdUnique, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x913ec  stloc.s  6
0x913ee  ldloc.2
  ... truncated ...
```
