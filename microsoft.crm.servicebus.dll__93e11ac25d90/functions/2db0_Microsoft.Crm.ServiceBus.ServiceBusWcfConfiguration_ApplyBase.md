# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::ApplyBase

- ea: `0x2db0`
- end: `0x2f8f`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::ApplyBase`
- size: `479`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2f90`
- `0x33f0`
- `0x3520`

## callees

- `0x2db0`

## string_xrefs

- `0x2e85`: `binding.OpenTimeout:`

## pseudocode

```c

```

## disassembly

```asm
0x2db0  ldnull
0x2db1  stloc.0
0x2db2  ldarg.0
0x2db3  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2db8  ldc.i4.5
0x2db9  stloc.1
0x2dba  ldloca.s 1
0x2dbc  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2dc2  callvirt instance string [mscorlib]System.Object::ToString()
0x2dc7  call     string [mscorlib]System.String::Concat(string, string)
0x2dcc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2dd1  stloc.0
0x2dd2  ldloc.0
0x2dd3  brfalse.s loc_2DF9
0x2dd5  ldloc.0
0x2dd6  isinst   [mscorlib]System.Int32
0x2ddb  brfalse.s loc_2DF9
0x2ddd  ldloc.0
0x2dde  unbox.any [mscorlib]System.Int32
0x2de3  ldc.i4.0
0x2de4  ble.s    loc_2DF9
0x2de6  ldarg.1
0x2de7  ldc.i4.0
0x2de8  ldc.i4.0
0x2de9  ldloc.0
0x2dea  unbox.any [mscorlib]System.Int32
0x2def  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x2df4  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_CloseTimeout(valuetype [mscorlib]System.TimeSpan)
0x2df9  ldarg.0
0x2dfa  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2dff  ldc.i4.s 0x2F
0x2e01  ldstr    a0// "{0}"
0x2e06  ldc.i4.1
0x2e07  newarr   [mscorlib]System.Object
0x2e0c  dup
0x2e0d  ldc.i4.0
0x2e0e  ldstr    aBindingCloseti// "binding.CloseTimeout:"
0x2e13  ldarg.1
0x2e14  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_CloseTimeout()
0x2e19  box      [mscorlib]System.TimeSpan
0x2e1e  call     string [mscorlib]System.String::Concat(object, object)
0x2e23  stelem.ref
0x2e24  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2e29  ldarg.0
0x2e2a  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2e2f  ldc.i4.6
0x2e30  stloc.1
0x2e31  ldloca.s 1
0x2e33  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2e39  callvirt instance string [mscorlib]System.Object::ToString()
0x2e3e  call     string [mscorlib]System.String::Concat(string, string)
0x2e43  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2e48  stloc.0
0x2e49  ldloc.0
0x2e4a  brfalse.s loc_2E70
0x2e4c  ldloc.0
0x2e4d  isinst   [mscorlib]System.Int32
0x2e52  brfalse.s loc_2E70
0x2e54  ldloc.0
0x2e55  unbox.any [mscorlib]System.Int32
0x2e5a  ldc.i4.0
0x2e5b  ble.s    loc_2E70
0x2e5d  ldarg.1
0x2e5e  ldc.i4.0
0x2e5f  ldc.i4.0
0x2e60  ldloc.0
0x2e61  unbox.any [mscorlib]System.Int32
0x2e66  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x2e6b  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_OpenTimeout(valuetype [mscorlib]System.TimeSpan)
0x2e70  ldarg.0
0x2e71  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2e76  ldc.i4.s 0x2F
0x2e78  ldstr    a0// "{0}"
0x2e7d  ldc.i4.1
0x2e7e  newarr   [mscorlib]System.Object
0x2e83  dup
0x2e84  ldc.i4.0
0x2e85  ldstr    aBindingOpentim// "binding.OpenTimeout:"
0x2e8a  ldarg.1
0x2e8b  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_OpenTimeout()
0x2e90  box      [mscorlib]System.TimeSpan
0x2e95  call     string [mscorlib]System.String::Concat(object, object)
0x2e9a  stelem.ref
0x2e9b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2ea0  ldarg.0
0x2ea1  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2ea6  ldc.i4.7
0x2ea7  stloc.1
0x2ea8  ldloca.s 1
0x2eaa  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2eb0  callvirt instance string [mscorlib]System.Object::ToString()
0x2eb5  call     string [mscorlib]System.String::Concat(string, string)
0x2eba  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2ebf  stloc.0
0x2ec0  ldloc.0
0x2ec1  brfalse.s loc_2EE7
0x2ec3  ldloc.0
0x2ec4  isinst   [mscorlib]System.Int32
0x2ec9  brfalse.s loc_2EE7
0x2ecb  ldloc.0
0x2ecc  unbox.any [mscorlib]System.Int32
0x2ed1  ldc.i4.0
0x2ed2  ble.s    loc_2EE7
0x2ed4  ldarg.1
0x2ed5  ldc.i4.0
0x2ed6  ldc.i4.0
0x2ed7  ldloc.0
0x2ed8  unbox.any [mscorlib]System.Int32
0x2edd  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x2ee2  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x2ee7  ldarg.0
0x2ee8  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2eed  ldc.i4.s 0x2F
0x2eef  ldstr    a0// "{0}"
0x2ef4  ldc.i4.1
0x2ef5  newarr   [mscorlib]System.Object
0x2efa  dup
0x2efb  ldc.i4.0
0x2efc  ldstr    aBindingReceive// "binding.ReceiveTimeout:"
0x2f01  ldarg.1
0x2f02  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_ReceiveTimeout()
0x2f07  box      [mscorlib]System.TimeSpan
0x2f0c  call     string [mscorlib]System.String::Concat(object, object)
0x2f11  stelem.ref
0x2f12  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f17  ldarg.0
0x2f18  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2f1d  ldc.i4.8
0x2f1e  stloc.1
0x2f1f  ldloca.s 1
0x2f21  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2f27  callvirt instance string [mscorlib]System.Object::ToString()
0x2f2c  call     string [mscorlib]System.String::Concat(string, string)
0x2f31  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2f36  stloc.0
0x2f37  ldloc.0
0x2f38  brfalse.s loc_2F5E
0x2f3a  ldloc.0
0x2f3b  isinst   [mscorlib]System.Int32
0x2f40  brfalse.s loc_2F5E
0x2f42  ldloc.0
0x2f43  unbox.any [mscorlib]System.Int32
0x2f48  ldc.i4.0
0x2f49  ble.s    loc_2F5E
0x2f4b  ldarg.1
0x2f4c  ldc.i4.0
0x2f4d  ldc.i4.0
0x2f4e  ldloc.0
0x2f4f  unbox.any [mscorlib]System.Int32
0x2f54  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x2f59  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.Binding::set_SendTimeout(valuetype [mscorlib]System.TimeSpan)
0x2f5e  ldarg.0
0x2f5f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2f64  ldc.i4.s 0x2F
0x2f66  ldstr    a0// "{0}"
0x2f6b  ldc.i4.1
0x2f6c  newarr   [mscorlib]System.Object
0x2f71  dup
0x2f72  ldc.i4.0
0x2f73  ldstr    aBindingSendtim// "binding.SendTimeout:"
0x2f78  ldarg.1
0x2f79  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_SendTimeout()
0x2f7e  box      [mscorlib]System.TimeSpan
0x2f83  call     string [mscorlib]System.String::Concat(object, object)
0x2f88  stelem.ref
0x2f89  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2f8e  ret
```
