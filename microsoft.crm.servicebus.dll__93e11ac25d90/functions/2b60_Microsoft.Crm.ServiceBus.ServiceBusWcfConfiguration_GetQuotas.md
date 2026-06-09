# Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::GetQuotas

- ea: `0x2b60`
- end: `0x2da3`
- name: `Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::GetQuotas`
- size: `579`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2f90`
- `0x33f0`
- `0x3520`

## callees

- `0x2b60`

## string_xrefs

- `0x2c2d`: `quotas.MaxBytesPerRead:`

## pseudocode

```c

```

## disassembly

```asm
0x2b60  newobj   instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::.ctor()
0x2b65  stloc.0
0x2b66  ldnull
0x2b67  stloc.1
0x2b68  ldarg.0
0x2b69  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2b6e  ldc.i4.0
0x2b6f  stloc.2
0x2b70  ldloca.s 2
0x2b72  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2b78  callvirt instance string [mscorlib]System.Object::ToString()
0x2b7d  call     string [mscorlib]System.String::Concat(string, string)
0x2b82  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2b87  stloc.1
0x2b88  ldloc.1
0x2b89  brfalse.s loc_2BA8
0x2b8b  ldloc.1
0x2b8c  isinst   [mscorlib]System.Int32
0x2b91  brfalse.s loc_2BA8
0x2b93  ldloc.1
0x2b94  unbox.any [mscorlib]System.Int32
0x2b99  ldc.i4.0
0x2b9a  ble.s    loc_2BA8
0x2b9c  ldloc.0
0x2b9d  ldloc.1
0x2b9e  unbox.any [mscorlib]System.Int32
0x2ba3  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxArrayLength(int32)
0x2ba8  ldarg.0
0x2ba9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2bae  ldc.i4.s 0x2F
0x2bb0  ldstr    a0// "{0}"
0x2bb5  ldc.i4.1
0x2bb6  newarr   [mscorlib]System.Object
0x2bbb  dup
0x2bbc  ldc.i4.0
0x2bbd  ldstr    aQuotasMaxarray// "quotas.MaxArrayLength:"
0x2bc2  ldloc.0
0x2bc3  callvirt instance int32 [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_MaxArrayLength()
0x2bc8  box      [mscorlib]System.Int32
0x2bcd  call     string [mscorlib]System.String::Concat(object, object)
0x2bd2  stelem.ref
0x2bd3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2bd8  ldarg.0
0x2bd9  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2bde  ldc.i4.1
0x2bdf  stloc.2
0x2be0  ldloca.s 2
0x2be2  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2be8  callvirt instance string [mscorlib]System.Object::ToString()
0x2bed  call     string [mscorlib]System.String::Concat(string, string)
0x2bf2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2bf7  stloc.1
0x2bf8  ldloc.1
0x2bf9  brfalse.s loc_2C18
0x2bfb  ldloc.1
0x2bfc  isinst   [mscorlib]System.Int32
0x2c01  brfalse.s loc_2C18
0x2c03  ldloc.1
0x2c04  unbox.any [mscorlib]System.Int32
0x2c09  ldc.i4.0
0x2c0a  ble.s    loc_2C18
0x2c0c  ldloc.0
0x2c0d  ldloc.1
0x2c0e  unbox.any [mscorlib]System.Int32
0x2c13  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxBytesPerRead(int32)
0x2c18  ldarg.0
0x2c19  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2c1e  ldc.i4.s 0x2F
0x2c20  ldstr    a0// "{0}"
0x2c25  ldc.i4.1
0x2c26  newarr   [mscorlib]System.Object
0x2c2b  dup
0x2c2c  ldc.i4.0
0x2c2d  ldstr    aQuotasMaxbytes// "quotas.MaxBytesPerRead:"
0x2c32  ldloc.0
0x2c33  callvirt instance int32 [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_MaxBytesPerRead()
0x2c38  box      [mscorlib]System.Int32
0x2c3d  call     string [mscorlib]System.String::Concat(object, object)
0x2c42  stelem.ref
0x2c43  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2c48  ldarg.0
0x2c49  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2c4e  ldc.i4.2
0x2c4f  stloc.2
0x2c50  ldloca.s 2
0x2c52  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2c58  callvirt instance string [mscorlib]System.Object::ToString()
0x2c5d  call     string [mscorlib]System.String::Concat(string, string)
0x2c62  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2c67  stloc.1
0x2c68  ldloc.1
0x2c69  brfalse.s loc_2C88
0x2c6b  ldloc.1
0x2c6c  isinst   [mscorlib]System.Int32
0x2c71  brfalse.s loc_2C88
0x2c73  ldloc.1
0x2c74  unbox.any [mscorlib]System.Int32
0x2c79  ldc.i4.0
0x2c7a  ble.s    loc_2C88
0x2c7c  ldloc.0
0x2c7d  ldloc.1
0x2c7e  unbox.any [mscorlib]System.Int32
0x2c83  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxDepth(int32)
0x2c88  ldarg.0
0x2c89  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2c8e  ldc.i4.s 0x2F
0x2c90  ldstr    a0// "{0}"
0x2c95  ldc.i4.1
0x2c96  newarr   [mscorlib]System.Object
0x2c9b  dup
0x2c9c  ldc.i4.0
0x2c9d  ldstr    aQuotasMaxdepth// "quotas.MaxDepth:"
0x2ca2  ldloc.0
0x2ca3  callvirt instance int32 [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_MaxDepth()
0x2ca8  box      [mscorlib]System.Int32
0x2cad  call     string [mscorlib]System.String::Concat(object, object)
0x2cb2  stelem.ref
0x2cb3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2cb8  ldarg.0
0x2cb9  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2cbe  ldc.i4.3
0x2cbf  stloc.2
0x2cc0  ldloca.s 2
0x2cc2  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2cc8  callvirt instance string [mscorlib]System.Object::ToString()
0x2ccd  call     string [mscorlib]System.String::Concat(string, string)
0x2cd2  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2cd7  stloc.1
0x2cd8  ldloc.1
0x2cd9  brfalse.s loc_2CF8
0x2cdb  ldloc.1
0x2cdc  isinst   [mscorlib]System.Int32
0x2ce1  brfalse.s loc_2CF8
0x2ce3  ldloc.1
0x2ce4  unbox.any [mscorlib]System.Int32
0x2ce9  ldc.i4.0
0x2cea  ble.s    loc_2CF8
0x2cec  ldloc.0
0x2ced  ldloc.1
0x2cee  unbox.any [mscorlib]System.Int32
0x2cf3  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxNameTableCharCount(int32)
0x2cf8  ldarg.0
0x2cf9  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2cfe  ldc.i4.s 0x2F
0x2d00  ldstr    a0// "{0}"
0x2d05  ldc.i4.1
0x2d06  newarr   [mscorlib]System.Object
0x2d0b  dup
0x2d0c  ldc.i4.0
0x2d0d  ldstr    aQuotasMaxnamet// "quotas.MaxNameTableCharCount:"
0x2d12  ldloc.0
0x2d13  callvirt instance int32 [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_MaxNameTableCharCount()
0x2d18  box      [mscorlib]System.Int32
0x2d1d  call     string [mscorlib]System.String::Concat(object, object)
0x2d22  stelem.ref
0x2d23  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2d28  ldarg.0
0x2d29  ldfld    string Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_propertyPrefix
0x2d2e  ldc.i4.4
0x2d2f  stloc.2
0x2d30  ldloca.s 2
0x2d32  constrained. Microsoft.Crm.ServiceBus.ServiceBusWcfProperty
0x2d38  callvirt instance string [mscorlib]System.Object::ToString()
0x2d3d  call     string [mscorlib]System.String::Concat(string, string)
0x2d42  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x2d47  stloc.1
0x2d48  ldloc.1
0x2d49  brfalse.s loc_2D6A
0x2d4b  ldloc.1
0x2d4c  isinst   [mscorlib]System.Int32
0x2d51  brfalse.s loc_2D6A
0x2d53  ldloc.1
0x2d54  unbox.any [mscorlib]System.Int32
0x2d59  ldc.i4.0
0x2d5a  ble.s    loc_2D6A
0x2d5c  ldloc.0
0x2d5d  ldloc.1
0x2d5e  unbox.any [mscorlib]System.Int32
0x2d63  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxStringContentLength(int32)
0x2d68  br.s     loc_2D71
0x2d6a  ldloc.0
0x2d6b  ldarg.1
0x2d6c  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxStringContentLength(int32)
0x2d71  ldarg.0
0x2d72  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.ServiceBusWcfConfiguration::_orgId
0x2d77  ldc.i4.s 0x2F
0x2d79  ldstr    a0// "{0}"
0x2d7e  ldc.i4.1
0x2d7f  newarr   [mscorlib]System.Object
0x2d84  dup
0x2d85  ldc.i4.0
0x2d86  ldstr    aQuotasMaxstrin// "quotas.MaxStringContentLength:"
0x2d8b  ldloc.0
0x2d8c  callvirt instance int32 [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::get_MaxStringContentLength()
0x2d91  box      [mscorlib]System.Int32
0x2d96  call     string [mscorlib]System.String::Concat(object, object)
0x2d9b  stelem.ref
0x2d9c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2da1  ldloc.0
0x2da2  ret
```
