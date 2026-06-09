# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_1

- ea: `0x3520`
- end: `0x36bc`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::Apply_1`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x3d00`

## callees

- `0x2b60`
- `0x2db0`
- `0x3520`

## pseudocode

```c

```

## disassembly

```asm
0x3520  ldarg.0
0x3521  ldarg.1
0x3522  call     instance void Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::ApplyBase(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x3527  ldnull
0x3528  stloc.0
0x3529  ldarg.0
0x352a  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x352f  ldc.i4.s 9
0x3531  stloc.2
0x3532  ldloca.s 2
0x3534  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x353a  callvirt instance string [mscorlib]System.Object::ToString()
0x353f  call     string [mscorlib]System.String::Concat(string, string)
0x3544  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3549  stloc.0
0x354a  ldloc.0
0x354b  brfalse.s loc_356D
0x354d  ldloc.0
0x354e  isinst   [mscorlib]System.Int32
0x3553  brfalse.s loc_356D
0x3555  ldloc.0
0x3556  unbox.any [mscorlib]System.Int32
0x355b  ldc.i4.0
0x355c  ble.s    loc_356D
0x355e  ldarg.1
0x355f  ldloc.0
0x3560  unbox.any [mscorlib]System.Int32
0x3565  conv.i8
0x3566  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_MaxBufferPoolSize(int64)
0x356b  br.s     loc_3579
0x356d  ldarg.1
0x356e  ldc.i4   0x100000
0x3573  conv.i8
0x3574  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_MaxBufferPoolSize(int64)
0x3579  ldarg.0
0x357a  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x357f  ldc.i4.s 0x2F
0x3581  ldstr    a0// "{0}"
0x3586  ldc.i4.1
0x3587  newarr   [mscorlib]System.Object
0x358c  dup
0x358d  ldc.i4.0
0x358e  ldstr    aBindingMaxbuff// "binding.MaxBufferPoolSize:"
0x3593  ldarg.1
0x3594  callvirt instance int64 [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::get_MaxBufferPoolSize()
0x3599  box      [mscorlib]System.Int64
0x359e  call     string [mscorlib]System.String::Concat(object, object)
0x35a3  stelem.ref
0x35a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x35a9  ldarg.0
0x35aa  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x35af  ldc.i4.s 0xA
0x35b1  stloc.2
0x35b2  ldloca.s 2
0x35b4  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x35ba  callvirt instance string [mscorlib]System.Object::ToString()
0x35bf  call     string [mscorlib]System.String::Concat(string, string)
0x35c4  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x35c9  stloc.0
0x35ca  ldloc.0
0x35cb  brfalse.s loc_35EA
0x35cd  ldloc.0
0x35ce  isinst   [mscorlib]System.Int32
0x35d3  brfalse.s loc_35EA
0x35d5  ldloc.0
0x35d6  unbox.any [mscorlib]System.Int32
0x35db  ldc.i4.0
0x35dc  ble.s    loc_35EA
0x35de  ldarg.1
0x35df  ldloc.0
0x35e0  unbox.any [mscorlib]System.Int32
0x35e5  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_MaxBufferSize(int32)
0x35ea  ldarg.0
0x35eb  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x35f0  ldc.i4.s 0x2F
0x35f2  ldstr    a0// "{0}"
0x35f7  ldc.i4.1
0x35f8  newarr   [mscorlib]System.Object
0x35fd  dup
0x35fe  ldc.i4.0
0x35ff  ldstr    aBindingMaxbuff_0// "binding.MaxBufferSize:"
0x3604  ldarg.1
0x3605  callvirt instance int32 [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::get_MaxBufferSize()
0x360a  box      [mscorlib]System.Int32
0x360f  call     string [mscorlib]System.String::Concat(object, object)
0x3614  stelem.ref
0x3615  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x361a  ldarg.0
0x361b  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x3620  ldc.i4.s 0xD
0x3622  stloc.2
0x3623  ldloca.s 2
0x3625  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x362b  callvirt instance string [mscorlib]System.Object::ToString()
0x3630  call     string [mscorlib]System.String::Concat(string, string)
0x3635  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x363a  stloc.0
0x363b  ldloc.0
0x363c  brfalse.s loc_365E
0x363e  ldloc.0
0x363f  isinst   [mscorlib]System.Int32
0x3644  brfalse.s loc_365E
0x3646  ldloc.0
0x3647  unbox.any [mscorlib]System.Int32
0x364c  ldc.i4.0
0x364d  ble.s    loc_365E
0x364f  ldarg.1
0x3650  ldloc.0
0x3651  unbox.any [mscorlib]System.Int32
0x3656  conv.i8
0x3657  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_MaxReceivedMessageSize(int64)
0x365c  br.s     loc_366A
0x365e  ldarg.1
0x365f  ldc.i4   0x100000
0x3664  conv.i8
0x3665  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_MaxReceivedMessageSize(int64)
0x366a  ldarg.0
0x366b  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x3670  ldc.i4.s 0x2F
0x3672  ldstr    a0// "{0}"
0x3677  ldc.i4.1
0x3678  newarr   [mscorlib]System.Object
0x367d  dup
0x367e  ldc.i4.0
0x367f  ldstr    aBindingMaxrece// "binding.MaxReceivedMessageSize:"
0x3684  ldarg.1
0x3685  callvirt instance int64 [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::get_MaxReceivedMessageSize()
0x368a  box      [mscorlib]System.Int64
0x368f  call     string [mscorlib]System.String::Concat(object, object)
0x3694  stelem.ref
0x3695  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x369a  ldarg.0
0x369b  ldc.i4   0x100000
0x36a0  call     instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::GetQuotas(int32 maxStringContentLength)
0x36a5  stloc.1
0x36a6  ldloc.1
0x36a7  ldnull
0x36a8  cgt.un
0x36aa  ldstr    aQuotasIsNull// "quotas is null"
0x36af  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x36b4  ldarg.1
0x36b5  ldloc.1
0x36b6  callvirt instance void [Microsoft.ServiceBus]Microsoft.ServiceBus.WebHttpRelayBinding::set_ReaderQuotas(class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas)
0x36bb  ret
```
