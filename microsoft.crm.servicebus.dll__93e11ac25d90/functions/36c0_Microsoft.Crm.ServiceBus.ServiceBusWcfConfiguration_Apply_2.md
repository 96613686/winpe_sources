# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_2

- ea: `0x36c0`
- end: `0x3817`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_2`
- size: `343`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3e60`

## callees

- `0x36c0`

## pseudocode

```c

```

## disassembly

```asm
0x36c0  newobj   instance void [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::.ctor()
0x36c5  stloc.0
0x36c6  ldarg.0
0x36c7  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x36cc  ldc.i4.s 0x12
0x36ce  box      Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x36d3  call     string [mscorlib]System.String::Concat(object, object)
0x36d8  ldc.i4.s 0x64
0x36da  box      [mscorlib]System.Int32
0x36df  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x36e4  stloc.1
0x36e5  ldloc.1
0x36e6  brfalse.s loc_3705
0x36e8  ldloc.1
0x36e9  isinst   [mscorlib]System.Int32
0x36ee  brfalse.s loc_3705
0x36f0  ldloc.1
0x36f1  unbox.any [mscorlib]System.Int32
0x36f6  ldc.i4.0
0x36f7  ble.s    loc_3705
0x36f9  ldloc.0
0x36fa  ldloc.1
0x36fb  unbox.any [mscorlib]System.Int32
0x3700  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::set_MaxConcurrentCalls(int32)
0x3705  ldarg.0
0x3706  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x370b  ldc.i4.s 0x2F
0x370d  ldstr    a0// "{0}"
0x3712  ldc.i4.1
0x3713  newarr   [mscorlib]System.Object
0x3718  dup
0x3719  ldc.i4.0
0x371a  ldstr    aThrottleMaxcon// "throttle.MaxConcurrentCalls:"
0x371f  ldloc.0
0x3720  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::get_MaxConcurrentCalls()
0x3725  box      [mscorlib]System.Int32
0x372a  call     string [mscorlib]System.String::Concat(object, object)
0x372f  stelem.ref
0x3730  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3735  ldarg.0
0x3736  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x373b  ldc.i4.s 0x13
0x373d  box      Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x3742  call     string [mscorlib]System.String::Concat(object, object)
0x3747  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x374c  stloc.1
0x374d  ldloc.1
0x374e  brfalse.s loc_376D
0x3750  ldloc.1
0x3751  isinst   [mscorlib]System.Int32
0x3756  brfalse.s loc_376D
0x3758  ldloc.1
0x3759  unbox.any [mscorlib]System.Int32
0x375e  ldc.i4.0
0x375f  ble.s    loc_376D
0x3761  ldloc.0
0x3762  ldloc.1
0x3763  unbox.any [mscorlib]System.Int32
0x3768  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::set_MaxConcurrentInstances(int32)
0x376d  ldarg.0
0x376e  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3773  ldc.i4.s 0x2F
0x3775  ldstr    a0// "{0}"
0x377a  ldc.i4.1
0x377b  newarr   [mscorlib]System.Object
0x3780  dup
0x3781  ldc.i4.0
0x3782  ldstr    aThrottleMaxcon_0// "throttle.MaxConcurrentInstances:"
0x3787  ldloc.0
0x3788  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::get_MaxConcurrentInstances()
0x378d  box      [mscorlib]System.Int32
0x3792  call     string [mscorlib]System.String::Concat(object, object)
0x3797  stelem.ref
0x3798  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x379d  ldarg.0
0x379e  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x37a3  ldc.i4.s 0x14
0x37a5  box      Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x37aa  call     string [mscorlib]System.String::Concat(object, object)
0x37af  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x37b4  stloc.1
0x37b5  ldloc.1
0x37b6  brfalse.s loc_37D5
0x37b8  ldloc.1
0x37b9  isinst   [mscorlib]System.Int32
0x37be  brfalse.s loc_37D5
0x37c0  ldloc.1
0x37c1  unbox.any [mscorlib]System.Int32
0x37c6  ldc.i4.0
0x37c7  ble.s    loc_37D5
0x37c9  ldloc.0
0x37ca  ldloc.1
0x37cb  unbox.any [mscorlib]System.Int32
0x37d0  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::set_MaxConcurrentSessions(int32)
0x37d5  ldarg.0
0x37d6  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x37db  ldc.i4.s 0x2F
0x37dd  ldstr    a0// "{0}"
0x37e2  ldc.i4.1
0x37e3  newarr   [mscorlib]System.Object
0x37e8  dup
0x37e9  ldc.i4.0
0x37ea  ldstr    aThrottleMaxcon_1// "throttle.MaxConcurrentSessions:"
0x37ef  ldloc.0
0x37f0  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Description.ServiceThrottlingBehavior::get_MaxConcurrentSessions()
0x37f5  box      [mscorlib]System.Int32
0x37fa  call     string [mscorlib]System.String::Concat(object, object)
0x37ff  stelem.ref
0x3800  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3805  ldarg.1
0x3806  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceDescription [System.ServiceModel]System.ServiceModel.ServiceHostBase::get_Description()
0x380b  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceDescription::get_Behaviors()
0x3810  ldloc.0
0x3811  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IServiceBehavior>::Add(var<u1>)
0x3816  ret
```
