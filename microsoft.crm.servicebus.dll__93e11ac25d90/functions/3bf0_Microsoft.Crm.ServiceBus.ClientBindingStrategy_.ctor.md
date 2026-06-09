# Microsoft.Crm.ServiceBus.ClientBindingStrategy::.ctor

- ea: `0x3bf0`
- end: `0x3c49`
- name: `Microsoft.Crm.ServiceBus.ClientBindingStrategy::.ctor`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4550`

## callees

- `0x1450`
- `0x3bf0`
- `0x3c70`
- `0x3ce0`

## pseudocode

```c

```

## disassembly

```asm
0x3bf0  ldarg.0
0x3bf1  call     instance void [mscorlib]System.Object::.ctor()
0x3bf6  ldarg.1
0x3bf7  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_Contract()
0x3bfc  stloc.0
0x3bfd  ldloc.0
0x3bfe  ldc.i4.1
0x3bff  sub
0x3c00  switch   loc_3C17, loc_3C31, loc_3C24, loc_3C17
0x3c15  br.s     loc_3C39
0x3c17  ldarg.0
0x3c18  ldarg.1
0x3c19  newobj   instance void Microsoft.Crm.ServiceBus.WebServiceBindingStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3c1e  stfld    class Microsoft.Crm.ServiceBus.IClientBindingStrategy Microsoft.Crm.ServiceBus.ClientBindingStrategy::selectedStrategy
0x3c23  ret
0x3c24  ldarg.0
0x3c25  ldarg.1
0x3c26  newobj   instance void Microsoft.Crm.ServiceBus.WebClientBindingStrategy::.ctor(class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation endpointInfo)
0x3c2b  stfld    class Microsoft.Crm.ServiceBus.IClientBindingStrategy Microsoft.Crm.ServiceBus.ClientBindingStrategy::selectedStrategy
0x3c30  ret
0x3c31  ldarg.0
0x3c32  ldnull
0x3c33  stfld    class Microsoft.Crm.ServiceBus.IClientBindingStrategy Microsoft.Crm.ServiceBus.ClientBindingStrategy::selectedStrategy
0x3c38  ret
0x3c39  ldstr    aInvalidEndpoin// "Invalid endpoint contract"
0x3c3e  ldstr    aEndpointinfoCo// "endpointInfo.Contract"
0x3c43  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0x3c48  throw
```
