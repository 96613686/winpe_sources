# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CanSwitch

- ea: `0x160b0`
- end: `0x160f0`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CanSwitch`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`
- `0x160b0`

## string_xrefs

- `0x160b1`: `currentUri`

## pseudocode

```c

```

## disassembly

```asm
0x160b0  ldarg.1
0x160b1  ldstr    aCurrenturi// "currentUri"
0x160b6  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x160bb  ldsfld   object class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::_lockObject
0x160c0  stloc.0
0x160c1  ldc.i4.0
0x160c2  stloc.1
0x160c3  ldloc.0
0x160c4  ldloca.s 1
0x160c6  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x160cb  ldarg.1
0x160cc  ldarg.0
0x160cd  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x160d2  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Address()
0x160d7  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x160dc  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x160e1  stloc.2
0x160e2  leave.s  loc_160EE
0x160e4  ldloc.1
0x160e5  brfalse.s loc_160ED
0x160e7  ldloc.0
0x160e8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x160ed  endfinally
0x160ee  ldloc.2
0x160ef  ret
```
