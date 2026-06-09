# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::ConfigureEndpoint

- ea: `0x1bc00`
- end: `0x1bcdf`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::ConfigureEndpoint`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x19d50`
- `0x19d90`
- `0x19de0`
- `0x19e00`
- `0x1bc00`

## string_xrefs

- `0x1bc0c`: `serviceProxy`

## pseudocode

```c

```

## disassembly

```asm
0x1bc00  ldarg.0
0x1bc01  ldstr    aEndpoint// "endpoint"
0x1bc06  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1bc0b  ldarg.1
0x1bc0c  ldstr    aServiceproxy// "serviceProxy"
0x1bc11  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1bc16  ldarg.0
0x1bc17  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ContractDescription [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Contract()
0x1bc1c  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.OperationDescriptionCollection [System.ServiceModel]System.ServiceModel.Description.ContractDescription::get_Operations()
0x1bc21  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.OperationDescription>::GetEnumerator()
0x1bc26  stloc.1
0x1bc27  br.s     loc_1BC48
0x1bc29  ldloc.1
0x1bc2a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.ServiceModel]System.ServiceModel.Description.OperationDescription>::get_Current()
0x1bc2f  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IOperationBehavior> [System.ServiceModel]System.ServiceModel.Description.OperationDescription::get_Behaviors()
0x1bc34  callvirt T0x2B000008
0x1bc39  stloc.2
0x1bc3a  ldloc.2
0x1bc3b  brfalse.s loc_1BC48
0x1bc3d  ldloc.2
0x1bc3e  ldc.i4   0x7FFFFFFF
0x1bc43  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.DataContractSerializerOperationBehavior::set_MaxItemsInObjectGraph(int32)
0x1bc48  ldloc.1
0x1bc49  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bc4e  brtrue.s loc_1BC29
0x1bc50  leave.s  loc_1BC5C
0x1bc52  ldloc.1
0x1bc53  brfalse.s loc_1BC5B
0x1bc55  ldloc.1
0x1bc56  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bc5b  endfinally
0x1bc5c  ldarg.0
0x1bc5d  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.Binding [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Binding()
0x1bc62  newobj   instance void Microsoft.Xrm.Sdk.Client.XrmBinding::.ctor(class [System.ServiceModel]System.ServiceModel.Channels.Binding binding)
0x1bc67  stloc.0
0x1bc68  ldarg.0
0x1bc69  ldloc.0
0x1bc6a  callvirt instance void [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::set_Binding(class [System.ServiceModel]System.ServiceModel.Channels.Binding)
0x1bc6f  ldloc.0
0x1bc70  ldc.i4   0x7FFFFFFF
0x1bc75  conv.i8
0x1bc76  callvirt instance void Microsoft.Xrm.Sdk.Client.XrmBinding::set_MaxReceivedMessageSize(int64 value)
0x1bc7b  ldloc.0
0x1bc7c  ldc.i4   0x7FFFFFFF
0x1bc81  callvirt instance void Microsoft.Xrm.Sdk.Client.XrmBinding::set_MaxBufferSize(int32 value)
0x1bc86  ldloc.0
0x1bc87  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Xrm.Sdk.Client.XrmBinding::get_ReaderQuotas()
0x1bc8c  ldc.i4   0x7FFFFFFF
0x1bc91  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxStringContentLength(int32)
0x1bc96  ldloc.0
0x1bc97  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Xrm.Sdk.Client.XrmBinding::get_ReaderQuotas()
0x1bc9c  ldc.i4   0x7FFFFFFF
0x1bca1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxArrayLength(int32)
0x1bca6  ldloc.0
0x1bca7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Xrm.Sdk.Client.XrmBinding::get_ReaderQuotas()
0x1bcac  ldc.i4   0x7FFFFFFF
0x1bcb1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxBytesPerRead(int32)
0x1bcb6  ldloc.0
0x1bcb7  callvirt instance class [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas Microsoft.Xrm.Sdk.Client.XrmBinding::get_ReaderQuotas()
0x1bcbc  ldc.i4   0x7FFFFFFF
0x1bcc1  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxNameTableCharCount(int32)
0x1bcc6  ldloc.0
0x1bcc7  ldarg.1
0x1bcc8  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_Timeout()
0x1bccd  ldarg.1
0x1bcce  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_Timeout()
0x1bcd3  ldarg.1
0x1bcd4  callvirt instance valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::get_Timeout()
0x1bcd9  call     void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::SetBindingTimeout(class [System.ServiceModel]System.ServiceModel.Channels.Binding, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x1bcde  ret
```
