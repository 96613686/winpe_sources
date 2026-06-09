# Microsoft.Crm.ObjectModel.AppModuleService::PublishAppModule

- ea: `0x926d0`
- end: `0x92a79`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::PublishAppModule`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x15bc0`
- `0x15be0`
- `0x283d0`
- `0x91df0`
- `0x926d0`
- `0x92a80`
- `0x946c0`
- `0x95680`
- `0x958f0`
- `0x959b0`
- `0x95a40`
- `0x95bb0`
- `0x95c40`
- `0x95cd0`

## string_xrefs

- `0x92707`: `AppModuleService.PublishAppModule(): User does not have {0} Privilege.`
- `0x92751`: `AppModuleService.PublishAppModule(): Cannont publish AppModule, Exception: {0}.`
- `0x927e9`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Publishing [{1}] [{2}].`
- `0x92838`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Publishing [{1}] [{2}].`
- `0x9289b`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Publishing [{1}] [{2}].`
- `0x928f9`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Publishing [{1}] [{2}].`
- `0x92948`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Publishing [{1}] [{2}].`
- `0x92a2d`: `AppModuleService.PublishAppModule(): [appmoduleid:{0}], Exception: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x926d0  ldarg.2
0x926d1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x926d6  call     class [Microsoft.Crm]Microsoft.Xrm.PrivilegeDefinition [Microsoft.Crm]Microsoft.Xrm.Privileges::get_PublishCustomization()
0x926db  ldfld    string [Microsoft.Crm]Microsoft.Xrm.PrivilegeDefinition::guid
0x926e0  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x926e5  ldarg.2
0x926e6  call     int32 [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::TryCheckPrivilege(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x926eb  brfalse.s loc_92721
0x926ed  ldc.i4   0x80040277
0x926f2  ldc.i4.0
0x926f3  newarr   [mscorlib]System.Object
0x926f8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x926fd  stloc.1
0x926fe  ldloc.1
0x926ff  ldarg.2
0x92700  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92705  ldc.i4.s 0x47
0x92707  ldstr    aAppmoduleservi_55// "AppModuleService.PublishAppModule(): Us"...
0x9270c  ldc.i4.1
0x9270d  newarr   [mscorlib]System.Object
0x92712  dup
0x92713  ldc.i4.0
0x92714  call     class [Microsoft.Crm]Microsoft.Xrm.PrivilegeDefinition [Microsoft.Crm]Microsoft.Xrm.Privileges::get_PublishCustomization()
0x92719  stelem.ref
0x9271a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9271f  ldloc.1
0x92720  throw
0x92721  ldarg.0
0x92722  ldarg.1
0x92723  ldarg.2
0x92724  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleValidationResponse Microsoft.Crm.ObjectModel.AppModuleService::ValidateAppModule(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92729  callvirt instance bool [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleValidationResponse::get_CanBeActivated()
0x9272e  brtrue.s loc_92792
0x92730  ldc.i4   0x80050114
0x92735  stloc.3
0x92736  ldloca.s 3
0x92738  call     instance string [mscorlib]System.Int32::ToString()
0x9273d  ldc.i4   0x80050114
0x92742  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x92747  stloc.2
0x92748  ldloc.2
0x92749  ldarg.2
0x9274a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9274f  ldc.i4.s 0x47
0x92751  ldstr    aAppmoduleservi_56// "AppModuleService.PublishAppModule(): Ca"...
0x92756  ldc.i4.1
0x92757  newarr   [mscorlib]System.Object
0x9275c  dup
0x9275d  ldc.i4.0
0x9275e  ldloc.2
0x9275f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x92764  stelem.ref
0x92765  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9276a  ldloc.2
0x9276b  ldarg.2
0x9276c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92771  ldc.i4.s 0x14
0x92773  ldstr    aExceptionWhile_4// "Exception while publishing AppModule : "...
0x92778  ldc.i4.1
0x92779  newarr   [mscorlib]System.Object
0x9277e  dup
0x9277f  ldc.i4.0
0x92780  ldc.i4   0x80050114
0x92785  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x9278a  stelem.ref
0x9278b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92790  ldloc.2
0x92791  throw
0x92792  ldarg.0
0x92793  ldarg.1
0x92794  ldarg.2
0x92795  ldloca.s 4
0x92797  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x9279d  ldloc.s  4
0x9279f  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>> Microsoft.Crm.ObjectModel.AppModuleService::GetAppModulePublishData(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> appModuleUniqueId)
0x927a4  stloc.0
0x927a5  ldloc.0
0x927a6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Count()
0x927ab  ldc.i4.0
0x927ac  ble      loc_92A78
0x927b1  ldarg.2
0x927b2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x927b7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::StartTransaction()
0x927bc  ldc.i4.0
0x927bd  stloc.s  5
0x927bf  ldc.i4.0
0x927c0  stloc.s  6
0x927c2  ldc.i4.0
0x927c3  stloc.s  7
0x927c5  ldc.i4.0
0x927c6  stloc.s  8
0x927c8  ldloc.0
0x927c9  ldc.i4.s 0x1A
0x927cb  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x927d0  brfalse.s loc_92826
0x927d2  ldloc.0
0x927d3  ldc.i4.s 0x1A
0x927d5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x927da  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x927df  stloc.s  8
0x927e1  ldarg.2
0x927e2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x927e7  ldc.i4.s 0x47
0x927e9  ldstr    aAppmoduleservi_57// "AppModuleService.PublishAppModule(): [a"...
0x927ee  ldc.i4.3
0x927ef  newarr   [mscorlib]System.Object
0x927f4  dup
0x927f5  ldc.i4.0
0x927f6  ldarg.1
0x927f7  box      [mscorlib]System.Guid
0x927fc  stelem.ref
0x927fd  dup
0x927fe  ldc.i4.1
0x927ff  ldc.i4.s 0x1A
0x92801  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x92806  stelem.ref
0x92807  dup
0x92808  ldc.i4.2
0x92809  ldloc.0
0x9280a  ldc.i4.s 0x1A
0x9280c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92811  stelem.ref
0x92812  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92817  ldarg.0
0x92818  ldloc.0
0x92819  ldc.i4.s 0x1A
0x9281b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92820  ldarg.2
0x92821  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishViewsForAppModule(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> viewsList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92826  ldloc.0
0x92827  ldc.i4.s 0x3E
0x92829  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9282e  brfalse.s loc_9287A
0x92830  ldarg.2
0x92831  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92836  ldc.i4.s 0x47
0x92838  ldstr    aAppmoduleservi_57// "AppModuleService.PublishAppModule(): [a"...
0x9283d  ldc.i4.3
0x9283e  newarr   [mscorlib]System.Object
0x92843  dup
0x92844  ldc.i4.0
0x92845  ldarg.1
0x92846  box      [mscorlib]System.Guid
0x9284b  stelem.ref
0x9284c  dup
0x9284d  ldc.i4.1
0x9284e  ldc.i4.s 0x3E
0x92850  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x92855  stelem.ref
0x92856  dup
0x92857  ldc.i4.2
0x92858  ldloc.0
0x92859  ldc.i4.s 0x3E
0x9285b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92860  stelem.ref
0x92861  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92866  ldarg.0
0x92867  ldloc.0
0x92868  ldc.i4.s 0x3E
0x9286a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x9286f  call     T0x2B00015D
0x92874  ldarg.2
0x92875  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishSitemapForAppModule(valuetype [mscorlib]System.Guid siteMap, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9287a  ldloc.0
0x9287b  ldc.i4.s 0x3C
0x9287d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x92882  brfalse.s loc_928D8
0x92884  ldloc.0
0x92885  ldc.i4.s 0x3C
0x92887  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x9288c  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x92891  stloc.s  5
0x92893  ldarg.2
0x92894  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92899  ldc.i4.s 0x47
0x9289b  ldstr    aAppmoduleservi_57// "AppModuleService.PublishAppModule(): [a"...
0x928a0  ldc.i4.3
0x928a1  newarr   [mscorlib]System.Object
0x928a6  dup
0x928a7  ldc.i4.0
0x928a8  ldarg.1
0x928a9  box      [mscorlib]System.Guid
0x928ae  stelem.ref
0x928af  dup
0x928b0  ldc.i4.1
0x928b1  ldc.i4.s 0x3C
0x928b3  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x928b8  stelem.ref
0x928b9  dup
0x928ba  ldc.i4.2
0x928bb  ldloc.0
0x928bc  ldc.i4.s 0x3C
0x928be  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x928c3  stelem.ref
0x928c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x928c9  ldarg.0
0x928ca  ldloc.0
0x928cb  ldc.i4.s 0x3C
0x928cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x928d2  ldarg.2
0x928d3  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishFormsForAppModule(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> formList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x928d8  ldloc.0
0x928d9  ldc.i4.s 0x3B
0x928db  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x928e0  brfalse.s loc_92936
0x928e2  ldloc.0
0x928e3  ldc.i4.s 0x3B
0x928e5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x928ea  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x928ef  stloc.s  7
0x928f1  ldarg.2
0x928f2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x928f7  ldc.i4.s 0x47
0x928f9  ldstr    aAppmoduleservi_57// "AppModuleService.PublishAppModule(): [a"...
0x928fe  ldc.i4.3
0x928ff  newarr   [mscorlib]System.Object
0x92904  dup
0x92905  ldc.i4.0
0x92906  ldarg.1
0x92907  box      [mscorlib]System.Guid
0x9290c  stelem.ref
0x9290d  dup
0x9290e  ldc.i4.1
0x9290f  ldc.i4.s 0x3B
0x92911  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x92916  stelem.ref
0x92917  dup
0x92918  ldc.i4.2
0x92919  ldloc.0
0x9291a  ldc.i4.s 0x3B
0x9291c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92921  stelem.ref
0x92922  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92927  ldarg.0
0x92928  ldloc.0
0x92929  ldc.i4.s 0x3B
0x9292b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92930  ldarg.2
0x92931  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishChartsForAppModule(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> visualizationList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92936  ldloc.0
0x92937  ldc.i4.s 0x30
0x92939  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x9293e  brfalse.s loc_92985
0x92940  ldarg.2
0x92941  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x92946  ldc.i4.s 0x47
0x92948  ldstr    aAppmoduleservi_57// "AppModuleService.PublishAppModule(): [a"...
0x9294d  ldc.i4.3
0x9294e  newarr   [mscorlib]System.Object
0x92953  dup
0x92954  ldc.i4.0
0x92955  ldarg.1
0x92956  box      [mscorlib]System.Guid
0x9295b  stelem.ref
0x9295c  dup
0x9295d  ldc.i4.1
0x9295e  ldc.i4.s 0x30
0x92960  box      [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType
0x92965  stelem.ref
0x92966  dup
0x92967  ldc.i4.2
0x92968  ldloc.0
0x92969  ldc.i4.s 0x30
0x9296b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x92970  stelem.ref
0x92971  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x92976  ldarg.0
0x92977  ldloc.0
0x92978  ldc.i4.s 0x30
0x9297a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x9297f  ldarg.2
0x92980  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishRibbonCommandForAppModule(class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid> ribbonCommandList, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x92985  ldarg.0
0x92986  ldarg.1
0x92987  ldarg.2
0x92988  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishAppConfigForAppModule(valuetype [mscorlib]System.Guid appmoduleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x9298d  ldloc.0
0x9298e  ldc.i4   0xA1
0x92993  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::ContainsKey(var<u1>)
0x92998  brfalse.s loc_929AB
0x9299a  ldloc.0
0x9299b  ldc.i4   0xA1
0x929a0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Item(void)
0x929a5  callvirt instance int32 class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::get_Count()
0x929aa  pop
0x929ab  ldarg.0
0x929ac  ldarg.1
0x929ad  ldarg.2
0x929ae  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::PublishAppModuleInternal(valuetype [mscorlib]System.Guid appModuleId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x929b3  ldloc.0
0x929b4  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>>::get_Keys()
0x929b9  ldsfld   class [mscorlib]System.Func`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, int32> <>c::<>9__99_0
0x929be  dup
0x929bf  brtrue.s loc_929D8
0x929c1  pop
0x929c2  ldsfld   class <>c <>c::<>9
0x929c7  ldftn    instance int32 <>c::<PublishAppModule>b__99_0(valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType c)
0x929cd  newobj   instance void class [mscorlib]System.Func`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, int32>::.ctor(object, native int)
0x929d2  dup
0x929d3  stsfld   class [mscorlib]System.Func`2<valuetype [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponentType, int32> <>c::<>9__99_0
  ... truncated ...
```
