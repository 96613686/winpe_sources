# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_0

- ea: `0x33f0`
- end: `0x351b`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_0`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3c90`

## callees

- `0x2b60`
- `0x2db0`
- `0x33f0`

## pseudocode

```c

```

## disassembly

```asm
0x33f0  ldarg.0
0x33f1  ldarg.1
0x33f2  call     instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::ApplyBase(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x33f7  ldnull
0x33f8  stloc.0
0x33f9  ldarg.0
0x33fa  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x33ff  ldc.i4.s 9
0x3401  stloc.2
0x3402  ldloca.s 2
0x3404  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x340a  callvirt instance string [mscorlib]System.Object::ToString()
0x340f  call     string [mscorlib]System.String::Concat(string, string)
0x3414  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3419  stloc.0
0x341a  ldloc.0
0x341b  brfalse.s loc_343D
0x341d  ldloc.0
0x341e  isinst   [mscorlib]System.Int32
0x3423  brfalse.s loc_343D
0x3425  ldloc.0
0x3426  unbox.any [mscorlib]System.Int32
0x342b  ldc.i4.0
0x342c  ble.s    loc_343D
0x342e  ldarg.1
0x342f  ldloc.0
0x3430  unbox.any [mscorlib]System.Int32
0x3435  conv.i8
0x3436  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::set_MaxBufferPoolSize(int64)
0x343b  br.s     loc_3449
0x343d  ldarg.1
0x343e  ldc.i4   0x100000
0x3443  conv.i8
0x3444  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::set_MaxBufferPoolSize(int64)
0x3449  ldarg.0
0x344a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x344f  ldc.i4.s 0x2F
0x3451  ldstr    a0// "{0}"
0x3456  ldc.i4.1
0x3457  newarr   [mscorlib]System.Object
0x345c  dup
0x345d  ldc.i4.0
0x345e  ldstr    aBindingMaxbuff// "binding.MaxBufferPoolSize:"
0x3463  ldarg.1
0x3464  callvirt instance int64 [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::get_MaxBufferPoolSize()
0x3469  box      [mscorlib]System.Int64
0x346e  call     string [mscorlib]System.String::Concat(object, object)
0x3473  stelem.ref
0x3474  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3479  ldarg.0
0x347a  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x347f  ldc.i4.s 0xD
0x3481  stloc.2
0x3482  ldloca.s 2
0x3484  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x348a  callvirt instance string [mscorlib]System.Object::ToString()
0x348f  call     string [mscorlib]System.String::Concat(string, string)
0x3494  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3499  stloc.0
0x349a  ldloc.0
0x349b  brfalse.s loc_34BD
0x349d  ldloc.0
0x349e  isinst   [mscorlib]System.Int32
0x34a3  brfalse.s loc_34BD
0x34a5  ldloc.0
0x34a6  unbox.any [mscorlib]System.Int32
0x34ab  ldc.i4.0
0x34ac  ble.s    loc_34BD
0x34ae  ldarg.1
0x34af  ldloc.0
0x34b0  unbox.any [mscorlib]System.Int32
0x34b5  conv.i8
0x34b6  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::set_MaxReceivedMessageSize(int64)
0x34bb  br.s     loc_34C9
0x34bd  ldarg.1
0x34be  ldc.i4   0x100000
0x34c3  conv.i8
0x34c4  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::set_MaxReceivedMessageSize(int64)
0x34c9  ldarg.0
0x34ca  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x34cf  ldc.i4.s 0x2F
0x34d1  ldstr    a0// "{0}"
0x34d6  ldc.i4.1
0x34d7  newarr   [mscorlib]System.Object
0x34dc  dup
0x34dd  ldc.i4.0
0x34de  ldstr    aBindingMaxrece// "binding.MaxReceivedMessageSize:"
0x34e3  ldarg.1
0x34e4  callvirt instance int64 [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::get_MaxReceivedMessageSize()
0x34e9  box      [mscorlib]System.Int64
0x34ee  call     string [mscorlib]System.String::Concat(object, object)
0x34f3  stelem.ref
0x34f4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x34f9  ldarg.0
0x34fa  ldc.i4   0x100000
0x34ff  call     instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::GetQuotas(int32 maxStringContentLength)
0x3504  stloc.1
0x3505  ldloc.1
0x3506  ldnull
0x3507  cgt.un
0x3509  ldstr    aQuotasIsNull// "quotas is null"
0x350e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x3513  ldarg.1
0x3514  ldloc.1
0x3515  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WSHttpRelayBindingBase::set_ReaderQuotas(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x351a  ret
```
