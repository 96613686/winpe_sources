# Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::CreateCrmExecutionContext

- ea: `0x24aa0`
- end: `0x24ae3`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataExecutionContext::CreateCrmExecutionContext`
- size: `67`
- prototype: ``
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xf970`
- `0x17d50`
- `0x1a480`
- `0x21690`
- `0x29140`
- `0x2e290`
- `0x327e0`

## callees

- `0x6200`
- `0x9e50`
- `0x24aa0`
- `0x24ec0`
- `0x24f30`

## pseudocode

```c

```

## disassembly

```asm
0x24aa0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationId()
0x24aa5  ldc.i4.0
0x24aa6  ldc.i4.0
0x24aa7  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x24aac  stloc.0
0x24aad  ldloc.0
0x24aae  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x24ab3  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_CorrelationToken(class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken)
0x24ab8  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.OrganizationServiceFactory::GetOrganizationContext()
0x24abd  call     bool Microsoft.Crm.Extensibility.FeatureControlBitHelper::IsApiInstrumentationEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext context)
0x24ac2  brfalse.s loc_24AD6
0x24ac4  ldloc.0
0x24ac5  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_OData4Origin()
0x24aca  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x24acf  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_CallerOriginToken(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken)
0x24ad4  br.s     loc_24AE1
0x24ad6  ldloc.0
0x24ad7  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken Microsoft.Crm.Extensibility.OrganizationSdkService::get_CallerOriginToken()
0x24adc  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::set_CallerOriginToken(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken)
0x24ae1  ldloc.0
0x24ae2  ret
```
