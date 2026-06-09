# Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1::VerifyData

- ea: `0x66de0`
- end: `0x66ff9`
- name: `Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1::VerifyData`
- size: `537`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x66de0`

## string_xrefs

- `0x66eac`: `plugintypeid`
- `0x66eb9`: `plugintypeid`
- `0x66e7a`: `asyncautodelete`
- `0x66e8a`: `asyncautodelete`
- `0x66ea0`: `asyncautodelete`
- `0x66f9c`: `sdkmessageprocessingstepsecureconfigid`
- `0x66e69`: `Asynchronous steps are only supported in AfterMainOperationInsideTransaction stages and AfterMainOperationOutsideTransaction stage`
- `0x66e9b`: `Async auto delete can only be set for asynchronous steps.`
- `0x66ed8`: `Only asynchronous steps are supported for service bus plug-in`
- `0x66f10`: `Service integration issuer information not found.`
- `0x66fc7`: `Only SdkMessageProcessingStep with ServerOnly supported deployment can have secure configuration.`

## pseudocode

```c

```

## disassembly

```asm
0x66de0  ldarg.1
0x66de1  ldstr    aStage_0// "stage"
0x66de6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66deb  brtrue.s loc_66E05
0x66ded  ldarg.1
0x66dee  ldstr    aStage_0// "stage"
0x66df3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66df8  unbox.any [mscorlib]System.Int32
0x66dfd  stloc.0
0x66dfe  ldarg.0
0x66dff  ldloc.0
0x66e00  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifyIsValidStage(int32)
0x66e05  ldarg.1
0x66e06  ldstr    aMode// "mode"
0x66e0b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66e10  brtrue   loc_66F20
0x66e15  ldarg.1
0x66e16  ldstr    aMode// "mode"
0x66e1b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66e20  unbox.any [mscorlib]System.Int32
0x66e25  stloc.1
0x66e26  ldloc.1
0x66e27  ldc.i4.0
0x66e28  ldc.i4.1
0x66e29  ldstr    aMode// "mode"
0x66e2e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0x66e33  ldarg.1
0x66e34  ldstr    aStage_0// "stage"
0x66e39  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66e3e  brtrue.s loc_66E79
0x66e40  ldarg.1
0x66e41  ldstr    aStage_0// "stage"
0x66e46  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66e4b  unbox.any [mscorlib]System.Int32
0x66e50  stloc.2
0x66e51  ldloc.1
0x66e52  ldc.i4.1
0x66e53  bne.un.s loc_66E79
0x66e55  ldloc.2
0x66e56  ldc.i4.s 0x23
0x66e58  beq.s    loc_66E79
0x66e5a  ldloc.2
0x66e5b  ldc.i4.s 0x28
0x66e5d  beq.s    loc_66E79
0x66e5f  ldloc.2
0x66e60  ldc.i4.s 0x2D
0x66e62  beq.s    loc_66E79
0x66e64  ldloc.2
0x66e65  ldc.i4.s 0x32
0x66e67  beq.s    loc_66E79
0x66e69  ldstr    aAsynchronousSt// "Asynchronous steps are only supported i"...
0x66e6e  ldstr    aStage_0// "stage"
0x66e73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x66e78  throw
0x66e79  ldarg.1
0x66e7a  ldstr    aAsyncautodelet// "asyncautodelete"
0x66e7f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66e84  brtrue.s loc_66EAB
0x66e86  ldloc.1
0x66e87  brtrue.s loc_66EAB
0x66e89  ldarg.1
0x66e8a  ldstr    aAsyncautodelet// "asyncautodelete"
0x66e8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66e94  unbox.any [mscorlib]System.Boolean
0x66e99  brfalse.s loc_66EAB
0x66e9b  ldstr    aAsyncAutoDelet// "Async auto delete can only be set for a"...
0x66ea0  ldstr    aAsyncautodelet// "asyncautodelete"
0x66ea5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x66eaa  throw
0x66eab  ldarg.1
0x66eac  ldstr    aPlugintypeid// "plugintypeid"
0x66eb1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66eb6  brtrue.s loc_66F20
0x66eb8  ldarg.1
0x66eb9  ldstr    aPlugintypeid// "plugintypeid"
0x66ebe  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66ec3  unbox.any [mscorlib]System.Guid
0x66ec8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.ObjectModel.ServiceEndpointService::ServiceEndpointPluginId
0x66ecd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x66ed2  brfalse.s loc_66F20
0x66ed4  ldloc.1
0x66ed5  ldc.i4.1
0x66ed6  beq.s    loc_66EE8
0x66ed8  ldstr    aOnlyAsynchrono// "Only asynchronous steps are supported f"...
0x66edd  ldstr    aMode// "mode"
0x66ee2  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x66ee7  throw
0x66ee8  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::.ctor()
0x66eed  stloc.3
0x66eee  ldloc.3
0x66eef  ldc.i4.1
0x66ef0  newarr   [mscorlib]System.String
0x66ef5  dup
0x66ef6  ldc.i4.0
0x66ef7  ldstr    aAppfabricissue// "AppFabricIssuer"
0x66efc  stelem.ref
0x66efd  callvirt instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter::set_CertificateTypes(string[])
0x66f02  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::.ctor()
0x66f07  ldloc.3
0x66f08  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData[] [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateFilter)
0x66f0d  ldlen
0x66f0e  brtrue.s loc_66F20
0x66f10  ldstr    aServiceIntegra// "Service integration issuer information "...
0x66f15  ldc.i4   0x80044176
0x66f1a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x66f1f  throw
0x66f20  ldarg.1
0x66f21  ldstr    aSupporteddeplo// "supporteddeployment"
0x66f26  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66f2b  brtrue.s loc_66F9B
0x66f2d  ldarg.1
0x66f2e  ldstr    aSupporteddeplo// "supporteddeployment"
0x66f33  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66f38  unbox.any [mscorlib]System.Int32
0x66f3d  ldc.i4.0
0x66f3e  ldc.i4.2
0x66f3f  ldstr    aSupporteddeplo// "supporteddeployment"
0x66f44  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0x66f49  ldarg.1
0x66f4a  ldstr    aMode// "mode"
0x66f4f  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66f54  brtrue.s loc_66F93
0x66f56  ldarg.1
0x66f57  ldstr    aMode// "mode"
0x66f5c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66f61  unbox.any [mscorlib]System.Int32
0x66f66  stloc.s  4
0x66f68  ldarg.1
0x66f69  ldstr    aSupporteddeplo// "supporteddeployment"
0x66f6e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66f73  unbox.any [mscorlib]System.Int32
0x66f78  stloc.s  5
0x66f7a  ldc.i4.1
0x66f7b  ldloc.s  4
0x66f7d  bne.un.s loc_66F93
0x66f7f  ldloc.s  5
0x66f81  brfalse.s loc_66F93
0x66f83  ldstr    aAsynchronousSt_0// "Asynchronous steps are only supported i"...
0x66f88  ldstr    aSupporteddeplo// "supporteddeployment"
0x66f8d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x66f92  throw
0x66f93  ldarg.0
0x66f94  ldarg.1
0x66f95  ldarg.3
0x66f96  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifySupportedDeployment(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x66f9b  ldarg.1
0x66f9c  ldstr    aSdkmessageproc_3// "sdkmessageprocessingstepsecureconfigid"
0x66fa1  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66fa6  brtrue.s loc_66FD7
0x66fa8  ldarg.1
0x66fa9  ldstr    aSupporteddeplo// "supporteddeployment"
0x66fae  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x66fb3  brtrue.s loc_66FD7
0x66fb5  ldarg.1
0x66fb6  ldstr    aSupporteddeplo// "supporteddeployment"
0x66fbb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x66fc0  unbox.any [mscorlib]System.Int32
0x66fc5  brfalse.s loc_66FD7
0x66fc7  ldstr    aOnlySdkmessage// "Only SdkMessageProcessingStep with Serv"...
0x66fcc  ldc.i4   0x80044185
0x66fd1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x66fd6  throw
0x66fd7  ldarg.0
0x66fd8  ldarg.1
0x66fd9  ldarg.2
0x66fda  ldarg.3
0x66fdb  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifyStageAndSetInvocationSource(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x66fe0  ldarg.0
0x66fe1  ldarg.1
0x66fe2  ldarg.3
0x66fe3  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifyIsCustomAllowedOnFilter(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x66fe8  ldarg.0
0x66fe9  ldarg.1
0x66fea  ldarg.3
0x66feb  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifyIsolationLevel(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x66ff0  ldarg.0
0x66ff1  ldarg.1
0x66ff2  ldarg.3
0x66ff3  call     instance void class Microsoft.Crm.ObjectModel.SdkMessageProcessingStepServiceInternal`1<var<u1>>::VerifyIntent(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x66ff8  ret
```
