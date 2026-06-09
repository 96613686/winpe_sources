# Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::GetHttpConfig

- ea: `0x5e90`
- end: `0x5f1d`
- name: `Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::GetHttpConfig`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6c10`

## callees

- `0x5e00`
- `0x5e20`
- `0x5e40`
- `0x5e60`
- `0x5e80`
- `0x5e90`
- `0x5f20`
- `0x5f40`
- `0x6090`

## pseudocode

```c

```

## disassembly

```asm
0x5e90  ldarg.0
0x5e91  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5e96  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x5e9b  brfalse.s loc_5EAE
0x5e9d  ldc.i4   0x80044248
0x5ea2  ldc.i4.0
0x5ea3  newarr   [mscorlib]System.Object
0x5ea8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x5ead  throw
0x5eae  newobj   instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::.ctor()
0x5eb3  stloc.0
0x5eb4  ldloc.0
0x5eb5  ldc.i4.5
0x5eb6  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_ConnectionLimit(int32 value)
0x5ebb  ldloc.0
0x5ebc  ldc.i4   0x927C0
0x5ec1  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_ConnectionLeaseTimeoutInMilliSeconds(int32 value)
0x5ec6  ldloc.0
0x5ec7  ldc.i4   0x1D4C0
0x5ecc  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_MaxIdleTimeInMilliSeconds(int32 value)
0x5ed1  ldloc.0
0x5ed2  ldc.i4   0xEA60
0x5ed7  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_HttpRequestTimeoutInMilliSeconds(int32 value)
0x5edc  ldloc.0
0x5edd  ldc.i4.1
0x5ede  callvirt instance void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::set_RetryCountForTransientHttpErrors(int32 value)
0x5ee3  ldloc.0
0x5ee4  call     void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithDeploymentSettings(class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpRequestConfig)
0x5ee9  ldloc.0
0x5eea  ldarg.0
0x5eeb  call     void Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::UpdateHttpConfigWithOrganizationSettings(class Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig httpRequestConfig, valuetype [mscorlib]System.Guid orgId)
0x5ef0  leave.s  loc_5F1B
0x5ef2  stloc.1
0x5ef3  ldloc.1
0x5ef4  ldarg.0
0x5ef5  ldc.i4.s 0x40
0x5ef7  ldstr    aHitExceptionWh_0// "Hit exception when trying to fetch depl"...
0x5efc  ldc.i4.2
0x5efd  newarr   [mscorlib]System.Object
0x5f02  dup
0x5f03  ldc.i4.0
0x5f04  ldarg.0
0x5f05  box      [mscorlib]System.Guid
0x5f0a  stelem.ref
0x5f0b  dup
0x5f0c  ldc.i4.1
0x5f0d  ldloc.1
0x5f0e  callvirt instance string [mscorlib]System.Object::ToString()
0x5f13  stelem.ref
0x5f14  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5f19  leave.s  loc_5F1B
0x5f1b  ldloc.0
0x5f1c  ret
```
