# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes

- ea: `0x186c0`
- end: `0x18729`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18640`
- `0x1a480`

## callees

- `0x7ca0`
- `0x15340`
- `0x186c0`
- `0x187b0`

## string_xrefs

- `0x186c6`: `CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x186c0  ldarg.0
0x186c1  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x186c6  ldstr    aCurrentservice// "CurrentServiceEndpoint"
0x186cb  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x186d0  ldarg.0
0x186d1  ldfld    object Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::_lockObject
0x186d6  stloc.0
0x186d7  ldc.i4.0
0x186d8  stloc.1
0x186d9  ldloc.0
0x186da  ldloca.s 1
0x186dc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x186e1  ldarg.0
0x186e2  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x186e7  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x186ec  callvirt T0x2B000014
0x186f1  stloc.2
0x186f2  ldloc.2
0x186f3  brfalse.s loc_18707
0x186f5  ldarg.0
0x186f6  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x186fb  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x18700  ldloc.2
0x18701  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Remove(var<u1>)
0x18706  pop
0x18707  ldarg.0
0x18708  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x1870d  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x18712  newobj   instance void Microsoft.Xrm.Sdk.Client.ProxyTypesBehavior::.ctor()
0x18717  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x1871c  leave.s  loc_18728
0x1871e  ldloc.1
0x1871f  brfalse.s loc_18727
0x18721  ldloc.0
0x18722  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x18727  endfinally
0x18728  ret
```
