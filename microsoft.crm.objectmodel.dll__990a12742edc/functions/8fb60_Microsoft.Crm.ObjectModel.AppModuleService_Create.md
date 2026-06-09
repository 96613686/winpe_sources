# Microsoft.Crm.ObjectModel.AppModuleService::Create

- ea: `0x8fb60`
- end: `0x8fe56`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::Create`
- size: `758`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0x15bc0`
- `0x15c50`
- `0x8fb60`
- `0x8feb0`
- `0x90b60`
- `0x93f60`
- `0x93fc0`
- `0x94040`
- `0x942e0`
- `0x94380`
- `0x94470`
- `0x944f0`
- `0x94a50`
- `0x97050`

## string_xrefs

- `0x8fd33`: `welcomepageid`
- `0x8fb68`: `AppModuleService.Create(): START`
- `0x8fc58`: `AppModuleService.Create(): Exception while creating AppModule : {0}`
- `0x8fc7d`: `AppModuleService.Create(): Attribute validation success`
- `0x8fcae`: `AppModuleService.Create(): AppModuleCreated with [appModuleId:{0}]`
- `0x8fcdc`: `AppModuleService.Create(): Default roles associated.`
- `0x8fcff`: `AppModuleCreate`
- `0x8fdb9`: `AppModuleService.Create(): Exception:{0}`
- `0x8fe1f`: `AppModuleService.Create(): Exception:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x8fb60  ldarg.2
0x8fb61  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fb66  ldc.i4.s 0x47
0x8fb68  ldstr    aAppmoduleservi// "AppModuleService.Create(): START"
0x8fb6d  ldc.i4.0
0x8fb6e  newarr   [mscorlib]System.Object
0x8fb73  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fb78  ldarg.0
0x8fb79  ldarg.2
0x8fb7a  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fb7f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x8fb84  stloc.1
0x8fb85  ldarg.0
0x8fb86  ldarg.1
0x8fb87  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::setDefaultsForAppModule(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule)
0x8fb8c  ldarg.0
0x8fb8d  ldarg.1
0x8fb8e  ldarg.2
0x8fb8f  ldc.i4.0
0x8fb90  call     instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor Microsoft.Crm.ObjectModel.AppModuleService::PopulateAppModuleDescriptor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool fetchPersistedDescriptor)
0x8fb95  stloc.2
0x8fb96  ldarg.0
0x8fb97  ldarg.1
0x8fb98  ldarg.2
0x8fb99  ldloca.s 0
0x8fb9b  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsClientTypeValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& validationErrorCode)
0x8fba0  brtrue.s loc_8FBA9
0x8fba2  ldloc.1
0x8fba3  ldloc.0
0x8fba4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fba9  ldarg.0
0x8fbaa  ldarg.1
0x8fbab  ldarg.2
0x8fbac  ldloca.s 0
0x8fbae  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsClientTypeCreateAlowed(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& validationErrorCode)
0x8fbb3  brtrue.s loc_8FBBC
0x8fbb5  ldloc.1
0x8fbb6  ldloc.0
0x8fbb7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fbbc  ldarg.0
0x8fbbd  ldarg.1
0x8fbbe  ldarg.2
0x8fbbf  ldloca.s 0
0x8fbc1  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsAppURLValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& validationErrorCode)
0x8fbc6  brtrue.s loc_8FBCF
0x8fbc8  ldloc.1
0x8fbc9  ldloc.0
0x8fbca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fbcf  ldarg.0
0x8fbd0  ldarg.1
0x8fbd1  ldarg.2
0x8fbd2  ldloca.s 0
0x8fbd4  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsAppUniqueNameValid(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity appModule, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& validationErrorCode)
0x8fbd9  brtrue.s loc_8FBE2
0x8fbdb  ldloc.1
0x8fbdc  ldloc.0
0x8fbdd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fbe2  ldarg.0
0x8fbe3  ldloc.2
0x8fbe4  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::get_webResourceInfo()
0x8fbe9  ldloca.s 0
0x8fbeb  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsWebResourceTypeValid(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation webResourceInfo, [out] string& validationErrorCode)
0x8fbf0  brtrue.s loc_8FBF9
0x8fbf2  ldloc.1
0x8fbf3  ldloc.0
0x8fbf4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fbf9  ldarg.0
0x8fbfa  ldloc.2
0x8fbfb  callvirt instance class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.AppModuleDescriptor::get_welcomePageInfo()
0x8fc00  ldloca.s 0
0x8fc02  call     instance bool Microsoft.Crm.ObjectModel.AppModuleService::IsWelcomePageTypeValid(class [Microsoft.Crm.Sdk.Proxy]Microsoft.Crm.Sdk.Messages.WebResourceInformation welcomePageInfo, [out] string& validationErrorCode)
0x8fc07  brtrue.s loc_8FC10
0x8fc09  ldloc.1
0x8fc0a  ldloc.0
0x8fc0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x8fc10  ldloc.1
0x8fc11  call     T0x2B000158
0x8fc16  brfalse.s loc_8FC75
0x8fc18  ldstr    asc_24F050// ","
0x8fc1d  ldloc.1
0x8fc1e  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x8fc23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8fc28  stloc.s  4
0x8fc2a  ldloc.s  4
0x8fc2c  ldarg.2
0x8fc2d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fc32  ldc.i4.s 0x14
0x8fc34  ldstr    aExceptionWhile_1// "Exception while creating AppModule : {0"...
0x8fc39  ldc.i4.1
0x8fc3a  newarr   [mscorlib]System.Object
0x8fc3f  dup
0x8fc40  ldc.i4.0
0x8fc41  ldloc.s  4
0x8fc43  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fc48  stelem.ref
0x8fc49  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fc4e  ldloc.s  4
0x8fc50  ldarg.2
0x8fc51  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fc56  ldc.i4.s 0x47
0x8fc58  ldstr    aAppmoduleservi_0// "AppModuleService.Create(): Exception wh"...
0x8fc5d  ldc.i4.1
0x8fc5e  newarr   [mscorlib]System.Object
0x8fc63  dup
0x8fc64  ldc.i4.0
0x8fc65  ldloc.s  4
0x8fc67  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fc6c  stelem.ref
0x8fc6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fc72  ldloc.s  4
0x8fc74  throw
0x8fc75  ldarg.2
0x8fc76  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fc7b  ldc.i4.s 0x47
0x8fc7d  ldstr    aAppmoduleservi_1// "AppModuleService.Create(): Attribute va"...
0x8fc82  ldnull
0x8fc83  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fc88  ldnull
0x8fc89  stloc.3
0x8fc8a  ldarg.2
0x8fc8b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoDisablePublishOnCreateModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fc90  stloc.s  5
0x8fc92  ldarg.2
0x8fc93  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8fc98  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x8fc9d  ldarg.0
0x8fc9e  ldarg.1
0x8fc9f  ldarg.2
0x8fca0  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x8fca5  stloc.3
0x8fca6  ldarg.2
0x8fca7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fcac  ldc.i4.s 0x47
0x8fcae  ldstr    aAppmoduleservi_2// "AppModuleService.Create(): AppModuleCre"...
0x8fcb3  ldc.i4.1
0x8fcb4  newarr   [mscorlib]System.Object
0x8fcb9  dup
0x8fcba  ldc.i4.0
0x8fcbb  ldloc.3
0x8fcbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8fcc1  box      [mscorlib]System.Guid
0x8fcc6  stelem.ref
0x8fcc7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fccc  ldarg.0
0x8fccd  ldloc.3
0x8fcce  ldarg.2
0x8fccf  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::AssociateDefaultRoles(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x8fcd4  ldarg.2
0x8fcd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fcda  ldc.i4.s 0x47
0x8fcdc  ldstr    aAppmoduleservi_3// "AppModuleService.Create(): Default role"...
0x8fce1  ldc.i4.0
0x8fce2  newarr   [mscorlib]System.Object
0x8fce7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fcec  ldarg.2
0x8fced  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8fcf2  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::CommitTransaction()
0x8fcf7  ldarg.0
0x8fcf8  ldarg.2
0x8fcf9  ldloc.3
0x8fcfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8fcff  ldstr    aAppmodulecreat// "AppModuleCreate"
0x8fd04  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd09  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x8fd0e  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::AddLogAppModuleEvent(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, valuetype [mscorlib]System.Guid appModuleId, string appEvent, [opt] valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> appModuleUniqueId)
0x8fd13  ldc.i4.0
0x8fd14  stloc.s  6
0x8fd16  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd1b  stloc.s  7
0x8fd1d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd22  stloc.s  8
0x8fd24  ldarg.1
0x8fd25  ldstr    aClienttype// "clienttype"
0x8fd2a  ldloca.s 6
0x8fd2c  callvirt T0x2B000101
0x8fd31  pop
0x8fd32  ldarg.1
0x8fd33  ldstr    aWelcomepageid// "welcomepageid"
0x8fd38  ldloca.s 7
0x8fd3a  callvirt T0x2B0000EF
0x8fd3f  pop
0x8fd40  ldarg.1
0x8fd41  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x8fd46  ldloca.s 8
0x8fd48  callvirt T0x2B0000EF
0x8fd4d  pop
0x8fd4e  ldloc.s  7
0x8fd50  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8fd55  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8fd5a  brtrue.s loc_8FD5F
0x8fd5c  ldc.i4.1
0x8fd5d  br.s     loc_8FD60
0x8fd5f  ldc.i4.0
0x8fd60  stloc.s  9
0x8fd62  call     class Microsoft.Crm.AppModule.AppModuleTelemetryEvents Microsoft.Crm.AppModule.AppModuleTelemetryEvents::get_Instance()
0x8fd67  ldarg.2
0x8fd68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fd6d  ldstr    aAppmoduleprope// "AppModuleProperties"
0x8fd72  ldloc.3
0x8fd73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x8fd78  ldloc.s  6
0x8fd7a  ldloc.s  9
0x8fd7c  callvirt instance void Microsoft.Crm.AppModule.AppModuleTelemetryEvents::AppModuleProperties(valuetype [mscorlib]System.Guid OrganizationId, string AppProperty, valuetype [mscorlib]System.Guid AppModuleId, int32 ClientType, int32 IsConfWelcomePage)
0x8fd81  ldloc.3
0x8fd82  stloc.s  0xA
0x8fd84  leave    loc_8FE53
0x8fd89  stloc.s  0xB
0x8fd8b  ldloc.s  0xB
0x8fd8d  ldarg.2
0x8fd8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fd93  ldc.i4.s 0x14
0x8fd95  ldstr    a0_0// "{0}"
0x8fd9a  ldc.i4.1
0x8fd9b  newarr   [mscorlib]System.Object
0x8fda0  dup
0x8fda1  ldc.i4.0
0x8fda2  ldloc.s  0xB
0x8fda4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fda9  stelem.ref
0x8fdaa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fdaf  ldloc.s  0xB
0x8fdb1  ldarg.2
0x8fdb2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fdb7  ldc.i4.s 0x47
0x8fdb9  ldstr    aAppmoduleservi_4// "AppModuleService.Create(): Exception:{0"...
0x8fdbe  ldc.i4.1
0x8fdbf  newarr   [mscorlib]System.Object
0x8fdc4  dup
0x8fdc5  ldc.i4.0
0x8fdc6  ldloc.s  0xB
0x8fdc8  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fdcd  stelem.ref
0x8fdce  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fdd3  ldarg.2
0x8fdd4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8fdd9  ldc.i4.0
0x8fdda  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x8fddf  ldstr    aCannotInsertDu// "Cannot insert duplicate key."
0x8fde4  ldc.i4   0x80040237
0x8fde9  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmDuplicateRecordException::.ctor(string, int32)
0x8fdee  throw
0x8fdef  stloc.s  0xC
0x8fdf1  ldloc.s  0xC
0x8fdf3  ldarg.2
0x8fdf4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fdf9  ldc.i4.s 0x14
0x8fdfb  ldstr    a0_0// "{0}"
0x8fe00  ldc.i4.1
0x8fe01  newarr   [mscorlib]System.Object
0x8fe06  dup
0x8fe07  ldc.i4.0
0x8fe08  ldloc.s  0xC
0x8fe0a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fe0f  stelem.ref
0x8fe10  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fe15  ldloc.s  0xC
0x8fe17  ldarg.2
0x8fe18  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x8fe1d  ldc.i4.s 0x47
0x8fe1f  ldstr    aAppmoduleservi_4// "AppModuleService.Create(): Exception:{0"...
0x8fe24  ldc.i4.1
0x8fe25  newarr   [mscorlib]System.Object
0x8fe2a  dup
0x8fe2b  ldc.i4.0
0x8fe2c  ldloc.s  0xC
0x8fe2e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x8fe33  stelem.ref
0x8fe34  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8fe39  ldarg.2
0x8fe3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x8fe3f  ldc.i4.0
0x8fe40  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::RollbackTransaction(bool)
0x8fe45  rethrow
0x8fe47  ldloc.s  5
0x8fe49  brfalse.s loc_8FE52
0x8fe4b  ldloc.s  5
0x8fe4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8fe52  endfinally
0x8fe53  ldloc.s  0xA
0x8fe55  ret
```
