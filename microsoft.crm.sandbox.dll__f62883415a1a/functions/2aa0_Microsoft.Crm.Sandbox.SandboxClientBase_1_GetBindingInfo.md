# Microsoft.Crm.Sandbox.SandboxClientBase`1::GetBindingInfo

- ea: `0x2aa0`
- end: `0x2b1b`
- name: `Microsoft.Crm.Sandbox.SandboxClientBase`1::GetBindingInfo`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x2ac6`: `OpenTimeout`

## pseudocode

```c

```

## disassembly

```asm
0x2aa0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2aa5  stloc.0
0x2aa6  ldstr    a01// "{0}: {1}, "
0x2aab  stloc.1
0x2aac  ldloc.0
0x2aad  ldloc.1
0x2aae  ldstr    aClosetimeout// "CloseTimeout"
0x2ab3  ldarg.1
0x2ab4  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_CloseTimeout()
0x2ab9  box      [mscorlib]System.TimeSpan
0x2abe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2ac3  pop
0x2ac4  ldloc.0
0x2ac5  ldloc.1
0x2ac6  ldstr    aOpentimeout// "OpenTimeout"
0x2acb  ldarg.1
0x2acc  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_OpenTimeout()
0x2ad1  box      [mscorlib]System.TimeSpan
0x2ad6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2adb  pop
0x2adc  ldloc.0
0x2add  ldloc.1
0x2ade  ldstr    aReceivetimeout// "ReceiveTimeout"
0x2ae3  ldarg.1
0x2ae4  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_ReceiveTimeout()
0x2ae9  box      [mscorlib]System.TimeSpan
0x2aee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2af3  pop
0x2af4  ldloc.0
0x2af5  ldloc.1
0x2af6  ldstr    aSendtimeout// "SendTimeout"
0x2afb  ldarg.1
0x2afc  callvirt instance valuetype [mscorlib]System.TimeSpan [System.ServiceModel]System.ServiceModel.Channels.Binding::get_SendTimeout()
0x2b01  box      [mscorlib]System.TimeSpan
0x2b06  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object)
0x2b0b  pop
0x2b0c  ldarg.0
0x2b0d  ldarg.1
0x2b0e  castclass [System.ServiceModel]System.ServiceModel.NetTcpBinding
0x2b13  ldloc.0
0x2b14  ldloc.1
0x2b15  call     instance string class Microsoft.Crm.Sandbox.SandboxClientBase`1<var<u1>>::GetTcpBindingSettings(class [System.ServiceModel]System.ServiceModel.NetTcpBinding, class [mscorlib]System.Text.StringBuilder, string)
0x2b1a  ret
```
