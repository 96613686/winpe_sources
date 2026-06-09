# Microsoft.Xrm.Sdk.CallerImpersonationScope::.ctor

- ea: `0x2880`
- end: `0x28c0`
- name: `Microsoft.Xrm.Sdk.CallerImpersonationScope::.ctor`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x288b`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x2880  ldarg.0
0x2881  call     instance void [mscorlib]System.Object::.ctor()
0x2886  ldstr    aCallerid// "CallerId"
0x288b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x2890  ldarg.2
0x2891  box      [mscorlib]System.Guid
0x2896  call     class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader [System.ServiceModel]System.ServiceModel.Channels.MessageHeader::CreateHeader(string, string, object)
0x289b  stloc.0
0x289c  ldarg.1
0x289d  castclass [System.ServiceModel]System.ServiceModel.IContextChannel
0x28a2  stloc.1
0x28a3  ldarg.0
0x28a4  ldloc.1
0x28a5  newobj   instance void [System.ServiceModel]System.ServiceModel.OperationContextScope::.ctor(class [System.ServiceModel]System.ServiceModel.IContextChannel)
0x28aa  stfld    class [System.ServiceModel]System.ServiceModel.OperationContextScope Microsoft.Xrm.Sdk.CallerImpersonationScope::scope
0x28af  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x28b4  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x28b9  ldloc.0
0x28ba  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::Add(class [System.ServiceModel]System.ServiceModel.Channels.MessageHeader)
0x28bf  ret
```
