# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_3

- ea: `0x3820`
- end: `0x3897`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_3`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x230`

## callees

- `0x3820`

## pseudocode

```c

```

## disassembly

```asm
0x3820  ldarg.0
0x3821  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3826  ldc.i4.s 0x11
0x3828  box      Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x382d  call     string [mscorlib]System.String::Concat(object, object)
0x3832  ldc.i4.s 0x78
0x3834  box      [mscorlib]System.Int32
0x3839  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x383e  stloc.0
0x383f  ldloc.0
0x3840  brfalse.s loc_3866
0x3842  ldloc.0
0x3843  isinst   [mscorlib]System.Int32
0x3848  brfalse.s loc_3866
0x384a  ldloc.0
0x384b  unbox.any [mscorlib]System.Int32
0x3850  ldc.i4.0
0x3851  ble.s    loc_3866
0x3853  ldarg.1
0x3854  ldc.i4.0
0x3855  ldc.i4.0
0x3856  ldloc.0
0x3857  unbox.any [mscorlib]System.Int32
0x385c  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x3861  callvirt instance void [System.ServiceModel]System.ServiceModel.IContextChannel::set_OperationTimeout(valuetype [mscorlib]System.TimeSpan)
0x3866  ldarg.0
0x3867  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x386c  ldc.i4.s 0x2F
0x386e  ldstr    a0// "{0}"
0x3873  ldc.i4.1
0x3874  newarr   [mscorlib]System.Object
0x3879  dup
0x387a  ldc.i4.0
0x387b  ldstr    aChannelOperati// "channel.OperationTimeoutInSec:"
0x3880  ldarg.1
0x3881  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.IContextChannel::get_OperationTimeout()
0x3886  box      [mscorlib]System.TimeSpan
0x388b  call     string [mscorlib]System.String::Concat(object, object)
0x3890  stelem.ref
0x3891  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3896  ret
```
