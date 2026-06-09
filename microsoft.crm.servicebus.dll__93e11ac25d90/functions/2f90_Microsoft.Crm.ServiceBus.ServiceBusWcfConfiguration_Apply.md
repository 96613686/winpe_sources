# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply

- ea: `0x2f90`
- end: `0x33ee`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply`
- size: `1118`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x230`
- `0x3e60`

## callees

- `0x2b60`
- `0x2db0`
- `0x2f90`

## string_xrefs

- `0x330b`: `HostNameComparisonMode:`
- `0x3339`: `binding.HostNameComparisonMode:`

## pseudocode

```c

```

## disassembly

```asm
0x2f90  ldarg.0
0x2f91  ldarg.1
0x2f92  call     instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::ApplyBase(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x2f97  ldnull
0x2f98  stloc.0
0x2f99  ldarg.0
0x2f9a  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2f9f  ldc.i4.s 9
0x2fa1  stloc.3
0x2fa2  ldloca.s 3
0x2fa4  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2faa  callvirt instance string [mscorlib]System.Object::ToString()
0x2faf  call     string [mscorlib]System.String::Concat(string, string)
0x2fb4  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2fb9  stloc.0
0x2fba  ldloc.0
0x2fbb  brfalse.s loc_2FDB
0x2fbd  ldloc.0
0x2fbe  isinst   [mscorlib]System.Int32
0x2fc3  brfalse.s loc_2FDB
0x2fc5  ldloc.0
0x2fc6  unbox.any [mscorlib]System.Int32
0x2fcb  ldc.i4.0
0x2fcc  ble.s    loc_2FDB
0x2fce  ldarg.1
0x2fcf  ldloc.0
0x2fd0  unbox.any [mscorlib]System.Int32
0x2fd5  conv.i8
0x2fd6  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxBufferPoolSize(int64)
0x2fdb  ldarg.0
0x2fdc  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2fe1  ldc.i4.s 0x2F
0x2fe3  ldstr    a0// "{0}"
0x2fe8  ldc.i4.1
0x2fe9  newarr   [mscorlib]System.Object
0x2fee  dup
0x2fef  ldc.i4.0
0x2ff0  ldstr    aBindingMaxbuff// "binding.MaxBufferPoolSize:"
0x2ff5  ldarg.1
0x2ff6  callvirt instance int64 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxBufferPoolSize()
0x2ffb  box      [mscorlib]System.Int64
0x3000  call     string [mscorlib]System.String::Concat(object, object)
0x3005  stelem.ref
0x3006  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x300b  ldarg.0
0x300c  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3011  ldc.i4.s 0xA
0x3013  stloc.3
0x3014  ldloca.s 3
0x3016  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x301c  callvirt instance string [mscorlib]System.Object::ToString()
0x3021  call     string [mscorlib]System.String::Concat(string, string)
0x3026  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x302b  stloc.0
0x302c  ldloc.0
0x302d  brfalse.s loc_304C
0x302f  ldloc.0
0x3030  isinst   [mscorlib]System.Int32
0x3035  brfalse.s loc_304C
0x3037  ldloc.0
0x3038  unbox.any [mscorlib]System.Int32
0x303d  ldc.i4.0
0x303e  ble.s    loc_304C
0x3040  ldarg.1
0x3041  ldloc.0
0x3042  unbox.any [mscorlib]System.Int32
0x3047  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxBufferSize(int32)
0x304c  ldarg.0
0x304d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3052  ldc.i4.s 0x2F
0x3054  ldstr    a0// "{0}"
0x3059  ldc.i4.1
0x305a  newarr   [mscorlib]System.Object
0x305f  dup
0x3060  ldc.i4.0
0x3061  ldstr    aBindingMaxbuff_0// "binding.MaxBufferSize:"
0x3066  ldarg.1
0x3067  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxBufferSize()
0x306c  box      [mscorlib]System.Int32
0x3071  call     string [mscorlib]System.String::Concat(object, object)
0x3076  stelem.ref
0x3077  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x307c  ldarg.0
0x307d  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3082  ldc.i4.s 0xC
0x3084  stloc.3
0x3085  ldloca.s 3
0x3087  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x308d  callvirt instance string [mscorlib]System.Object::ToString()
0x3092  call     string [mscorlib]System.String::Concat(string, string)
0x3097  ldc.i4.s 0x64
0x3099  box      [mscorlib]System.Int32
0x309e  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x30a3  stloc.0
0x30a4  ldloc.0
0x30a5  brfalse.s loc_30C4
0x30a7  ldloc.0
0x30a8  isinst   [mscorlib]System.Int32
0x30ad  brfalse.s loc_30C4
0x30af  ldloc.0
0x30b0  unbox.any [mscorlib]System.Int32
0x30b5  ldc.i4.0
0x30b6  ble.s    loc_30C4
0x30b8  ldarg.1
0x30b9  ldloc.0
0x30ba  unbox.any [mscorlib]System.Int32
0x30bf  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_ListenBacklog(int32)
0x30c4  ldarg.0
0x30c5  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x30ca  ldc.i4.s 0x2F
0x30cc  ldstr    a0// "{0}"
0x30d1  ldc.i4.1
0x30d2  newarr   [mscorlib]System.Object
0x30d7  dup
0x30d8  ldc.i4.0
0x30d9  ldstr    aBindingListenb// "binding.ListenBacklog:"
0x30de  ldarg.1
0x30df  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxConnections()
0x30e4  box      [mscorlib]System.Int32
0x30e9  call     string [mscorlib]System.String::Concat(object, object)
0x30ee  stelem.ref
0x30ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x30f4  ldarg.0
0x30f5  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x30fa  ldc.i4.s 0xB
0x30fc  stloc.3
0x30fd  ldloca.s 3
0x30ff  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x3105  callvirt instance string [mscorlib]System.Object::ToString()
0x310a  call     string [mscorlib]System.String::Concat(string, string)
0x310f  ldc.i4.s 0x64
0x3111  box      [mscorlib]System.Int32
0x3116  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x311b  stloc.0
0x311c  ldloc.0
0x311d  brfalse.s loc_313C
0x311f  ldloc.0
0x3120  isinst   [mscorlib]System.Int32
0x3125  brfalse.s loc_313C
0x3127  ldloc.0
0x3128  unbox.any [mscorlib]System.Int32
0x312d  ldc.i4.0
0x312e  ble.s    loc_313C
0x3130  ldarg.1
0x3131  ldloc.0
0x3132  unbox.any [mscorlib]System.Int32
0x3137  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxConnections(int32)
0x313c  ldarg.0
0x313d  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3142  ldc.i4.s 0x2F
0x3144  ldstr    a0// "{0}"
0x3149  ldc.i4.1
0x314a  newarr   [mscorlib]System.Object
0x314f  dup
0x3150  ldc.i4.0
0x3151  ldstr    aBindingMaxconn// "binding.MaxConnections:"
0x3156  ldarg.1
0x3157  callvirt instance int32 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxConnections()
0x315c  box      [mscorlib]System.Int32
0x3161  call     string [mscorlib]System.String::Concat(object, object)
0x3166  stelem.ref
0x3167  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x316c  ldarg.0
0x316d  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3172  ldc.i4.s 0xD
0x3174  stloc.3
0x3175  ldloca.s 3
0x3177  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x317d  callvirt instance string [mscorlib]System.Object::ToString()
0x3182  call     string [mscorlib]System.String::Concat(string, string)
0x3187  ldc.i4   0xA00000
0x318c  box      [mscorlib]System.Int32
0x3191  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x3196  stloc.0
0x3197  ldloc.0
0x3198  brfalse.s loc_31B8
0x319a  ldloc.0
0x319b  isinst   [mscorlib]System.Int32
0x31a0  brfalse.s loc_31B8
0x31a2  ldloc.0
0x31a3  unbox.any [mscorlib]System.Int32
0x31a8  ldc.i4.0
0x31a9  ble.s    loc_31B8
0x31ab  ldarg.1
0x31ac  ldloc.0
0x31ad  unbox.any [mscorlib]System.Int32
0x31b2  conv.i8
0x31b3  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_MaxReceivedMessageSize(int64)
0x31b8  ldarg.0
0x31b9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x31be  ldc.i4.s 0x2F
0x31c0  ldstr    a0// "{0}"
0x31c5  ldc.i4.1
0x31c6  newarr   [mscorlib]System.Object
0x31cb  dup
0x31cc  ldc.i4.0
0x31cd  ldstr    aBindingMaxrece// "binding.MaxReceivedMessageSize:"
0x31d2  ldarg.1
0x31d3  callvirt instance int64 [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_MaxReceivedMessageSize()
0x31d8  box      [mscorlib]System.Int64
0x31dd  call     string [mscorlib]System.String::Concat(object, object)
0x31e2  stelem.ref
0x31e3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x31e8  ldarg.0
0x31e9  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x31ee  ldc.i4.s 0xE
0x31f0  stloc.3
0x31f1  ldloca.s 3
0x31f3  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x31f9  callvirt instance string [mscorlib]System.Object::ToString()
0x31fe  call     string [mscorlib]System.String::Concat(string, string)
0x3203  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3208  stloc.0
0x3209  ldloc.0
0x320a  isinst   [mscorlib]System.String
0x320f  stloc.1
0x3210  ldloc.0
0x3211  brfalse.s loc_326E
0x3213  ldloc.1
0x3214  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3219  brtrue.s loc_326E
0x321b  ldarg.1
0x321c  ldtoken  [System.ServiceModel]System.ServiceModel.TransferMode
0x3221  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3226  ldloc.1
0x3227  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x322c  unbox.any [System.ServiceModel]System.ServiceModel.TransferMode
0x3231  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_TransferMode(valuetype [System.ServiceModel]System.ServiceModel.TransferMode)
0x3236  leave.s  loc_326E
0x3238  stloc.s  4
0x323a  ldarg.0
0x323b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3240  ldc.i4.s 0x2F
0x3242  ldstr    a0// "{0}"
0x3247  ldc.i4.1
0x3248  newarr   [mscorlib]System.Object
0x324d  dup
0x324e  ldc.i4.0
0x324f  ldarg.0
0x3250  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3255  ldstr    aTransfermode// "TransferMode:"
0x325a  ldloc.s  4
0x325c  callvirt instance string [mscorlib]System.Exception::get_Message()
0x3261  call     string [mscorlib]System.String::Concat(string, string, string)
0x3266  stelem.ref
0x3267  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x326c  leave.s  loc_326E
0x326e  ldarg.0
0x326f  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3274  ldc.i4.s 0x2F
0x3276  ldstr    a0// "{0}"
0x327b  ldc.i4.1
0x327c  newarr   [mscorlib]System.Object
0x3281  dup
0x3282  ldc.i4.0
0x3283  ldstr    aBindingTransfe// "binding.TransferMode:"
0x3288  ldarg.1
0x3289  callvirt instance valuetype [System.ServiceModel]System.ServiceModel.TransferMode [System.ServiceModel]System.ServiceModel.NetTcpBinding::get_TransferMode()
0x328e  box      [System.ServiceModel]System.ServiceModel.TransferMode
0x3293  call     string [mscorlib]System.String::Concat(object, object)
0x3298  stelem.ref
0x3299  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x329e  ldarg.0
0x329f  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x32a4  ldc.i4.s 0xF
0x32a6  stloc.3
0x32a7  ldloca.s 3
0x32a9  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x32af  callvirt instance string [mscorlib]System.Object::ToString()
0x32b4  call     string [mscorlib]System.String::Concat(string, string)
0x32b9  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x32be  stloc.0
0x32bf  ldloc.0
0x32c0  isinst   [mscorlib]System.String
0x32c5  stloc.1
0x32c6  ldloc.0
0x32c7  brfalse.s loc_3324
0x32c9  ldloc.1
0x32ca  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32cf  brtrue.s loc_3324
0x32d1  ldarg.1
0x32d2  ldtoken  [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x32d7  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x32dc  ldloc.1
0x32dd  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x32e2  unbox.any [System.ServiceModel]System.ServiceModel.HostNameComparisonMode
0x32e7  callvirt instance void [System.ServiceModel]System.ServiceModel.NetTcpBinding::set_HostNameComparisonMode(valuetype [System.ServiceModel]System.ServiceModel.HostNameComparisonMode)
0x32ec  leave.s  loc_3324
0x32ee  stloc.s  5
0x32f0  ldarg.0
0x32f1  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x32f6  ldc.i4.s 0x2F
0x32f8  ldstr    a0// "{0}"
0x32fd  ldc.i4.1
0x32fe  newarr   [mscorlib]System.Object
0x3303  dup
0x3304  ldc.i4.0
0x3305  ldarg.0
0x3306  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x330b  ldstr    aHostnamecompar// "HostNameComparisonMode:"
  ... truncated ...
```
