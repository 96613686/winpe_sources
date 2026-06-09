# Microsoft.Crm.ServiceBus.ServiceBusClientFactory::CreateClient

- ea: `0x46f0`
- end: `0x47a3`
- name: `Microsoft.Crm.ServiceBus.ServiceBusClientFactory::CreateClient`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x47d0`

## callees

- `0x1b10`
- `0x46f0`
- `0x4a90`
- `0x4c70`
- `0x4e20`
- `0x5550`

## pseudocode

```c

```

## disassembly

```asm
0x46f0  ldnull
0x46f1  stloc.0
0x46f2  ldarg.0
0x46f3  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0x46f8  stloc.1
0x46f9  ldloc.1
0x46fa  ldc.i4.1
0x46fb  sub
0x46fc  switch   loc_471F, loc_4727, loc_4750, loc_4758, loc_4760, loc_4768, loc_4770
0x471d  br.s     loc_4778
0x471f  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusOneWayClient::.ctor()
0x4724  stloc.0
0x4725  br.s     loc_47A1
0x4727  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x472c  ldstr    aQueueContractI// "Queue contract is not supported : {0}"
0x4731  ldc.i4.1
0x4732  newarr   [mscorlib]System.Object
0x4737  dup
0x4738  ldc.i4.0
0x4739  ldarg.0
0x473a  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0x473f  box      ContractType
0x4744  stelem.ref
0x4745  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x474a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x474f  throw
0x4750  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusRestClient::.ctor()
0x4755  stloc.0
0x4756  br.s     loc_47A1
0x4758  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusTwoWayClient::.ctor()
0x475d  stloc.0
0x475e  br.s     loc_47A1
0x4760  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::.ctor()
0x4765  stloc.0
0x4766  br.s     loc_47A1
0x4768  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::.ctor()
0x476d  stloc.0
0x476e  br.s     loc_47A1
0x4770  newobj   instance void Microsoft.Crm.ServiceBus.ServiceBusBrokeredMessageClient::.ctor()
0x4775  stloc.0
0x4776  br.s     loc_47A1
0x4778  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x477d  ldstr    aUnsupportedCon// "Unsupported contract found : {0}"
0x4782  ldc.i4.1
0x4783  newarr   [mscorlib]System.Object
0x4788  dup
0x4789  ldc.i4.0
0x478a  ldarg.0
0x478b  callvirt instance valuetype ContractType Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::get_Contract()
0x4790  box      ContractType
0x4795  stelem.ref
0x4796  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x479b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x47a0  throw
0x47a1  ldloc.0
0x47a2  ret
```
