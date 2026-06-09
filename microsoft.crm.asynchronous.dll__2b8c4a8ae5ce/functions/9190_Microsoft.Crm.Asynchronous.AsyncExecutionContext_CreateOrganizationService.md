# Microsoft.Crm.Asynchronous.AsyncExecutionContext::CreateOrganizationService

- ea: `0x9190`
- end: `0x91f3`
- name: `Microsoft.Crm.Asynchronous.AsyncExecutionContext::CreateOrganizationService`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x2e40`
- `0x8fa0`
- `0x90a0`
- `0x90d0`
- `0x9190`
- `0x9200`

## pseudocode

```c

```

## disassembly

```asm
0x9190  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AsyncServiceOrigin::.ctor()
0x9195  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x919a  stloc.0
0x919b  ldarga.s 1
0x919d  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x91a2  brfalse.s loc_91C4
0x91a4  ldarga.s 1
0x91a6  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x91ab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x91b0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x91b5  brfalse.s loc_91C4
0x91b7  ldarga.s 1
0x91b9  ldarg.0
0x91ba  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_UserId()
0x91bf  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x91c4  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x91c9  ldarg.0
0x91ca  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_OrganizationId()
0x91cf  ldarga.s 1
0x91d1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x91d6  ldarg.0
0x91d7  call     instance class Microsoft.Crm.Asynchronous.AsyncEvent Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_AsyncEvent()
0x91dc  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken Microsoft.Crm.Asynchronous.AsyncEvent::get_CorrelationToken()
0x91e1  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::FromLegacyToken(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken)
0x91e6  ldloc.0
0x91e7  ldarg.0
0x91e8  call     instance class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Asynchronous.AsyncExecutionContext::get_ProxyTypesAssembly()
0x91ed  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x91f2  ret
```
