# Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest

- ea: `0xab70`
- end: `0xabfa`
- name: `Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequest`
- size: `138`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xa400`
- `0xa4f0`
- `0xa610`
- `0xa6e0`
- `0xa7c0`
- `0xa830`
- `0xa950`
- `0xaa70`

## callees

- `0xab70`
- `0xac00`
- `0xe390`
- `0x2f800`

## pseudocode

```c

```

## disassembly

```asm
0xab70  newobj   instance void <>c__DisplayClass14_0::.ctor()
0xab75  stloc.0
0xab76  ldloc.0
0xab77  ldarg.0
0xab78  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest <>c__DisplayClass14_0::request
0xab7d  ldloc.0
0xab7e  ldarg.1
0xab7f  stfld    class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken <>c__DisplayClass14_0::correlationToken
0xab84  ldloc.0
0xab85  ldarg.2
0xab86  stfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken <>c__DisplayClass14_0::callerOriginToken
0xab8b  ldloc.0
0xab8c  ldarg.3
0xab8d  stfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType <>c__DisplayClass14_0::serviceType
0xab92  ldloc.0
0xab93  ldarg.s  4
0xab95  stfld    bool <>c__DisplayClass14_0::checkAdminMode
0xab9a  ldloc.0
0xab9b  ldarg.s  5
0xab9d  stfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass14_0::executionContext
0xaba2  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetCallerAndBusinessGuids()
0xaba7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth::get_OrganizationId()
0xabac  stloc.1
0xabad  ldloc.0
0xabae  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest <>c__DisplayClass14_0::request
0xabb3  ldloc.1
0xabb4  call     class Microsoft.Crm.Extensibility.Retry.Executer.OrganizationRequestBaseRetryExecuter Microsoft.Crm.Extensibility.Retry.Executer.OrganizationRequestBaseRetryExecuter::GetExecuterForCurrentRequest(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, valuetype [mscorlib]System.Guid organizationId)
0xabb9  stloc.2
0xabba  ldloc.2
0xabbb  brfalse.s loc_ABD0
0xabbd  ldloc.2
0xabbe  ldloc.0
0xabbf  ldftn    instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse <>c__DisplayClass14_0::<ExecuteRequest>b__0()
0xabc5  newobj   instance void class [mscorlib]System.Func`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse>::.ctor(object, native int)
0xabca  call     T0x2B00003E
0xabcf  ret
0xabd0  ldloc.0
0xabd1  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest <>c__DisplayClass14_0::request
0xabd6  ldloc.0
0xabd7  ldfld    class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken <>c__DisplayClass14_0::correlationToken
0xabdc  ldloc.0
0xabdd  ldfld    class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken <>c__DisplayClass14_0::callerOriginToken
0xabe2  ldloc.0
0xabe3  ldfld    valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType <>c__DisplayClass14_0::serviceType
0xabe8  ldloc.0
0xabe9  ldfld    bool <>c__DisplayClass14_0::checkAdminMode
0xabee  ldloc.0
0xabef  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass14_0::executionContext
0xabf4  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse Microsoft.Crm.Extensibility.OrganizationSdkServiceInternal::ExecuteRequestInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest request, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken callerOriginToken, valuetype [Microsoft.Crm.Core]Microsoft.Crm.Performance.WebServiceType serviceType, bool checkAdminMode, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext executionContext)
0xabf9  ret
```
