# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes_0

- ea: `0x18730`
- end: `0x187a5`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes_0`
- size: `117`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18640`
- `0x1a4b0`

## callees

- `0x7ca0`
- `0x15360`
- `0x18730`
- `0x187b0`

## string_xrefs

- `0x18741`: `CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x18730  ldarg.1
0x18731  ldstr    aAssembly// "assembly"
0x18736  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1873b  ldarg.0
0x1873c  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x18741  ldstr    aCurrentservice// "CurrentServiceEndpoint"
0x18746  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1874b  ldarg.0
0x1874c  ldfld    object Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::_lockObject
0x18751  stloc.0
0x18752  ldc.i4.0
0x18753  stloc.1
0x18754  ldloc.0
0x18755  ldloca.s 1
0x18757  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1875c  ldarg.0
0x1875d  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x18762  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x18767  callvirt T0x2B000014
0x1876c  stloc.2
0x1876d  ldloc.2
0x1876e  brfalse.s loc_18782
0x18770  ldarg.0
0x18771  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x18776  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x1877b  ldloc.2
0x1877c  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Remove(var<u1>)
0x18781  pop
0x18782  ldarg.0
0x18783  call     instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::get_CurrentServiceEndpoint()
0x18788  callvirt instance class [System.ServiceModel]System.Collections.Generic.KeyedByTypeCollection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior> [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint::get_Behaviors()
0x1878d  ldarg.1
0x1878e  newobj   instance void Microsoft.Xrm.Sdk.Client.ProxyTypesBehavior::.ctor(class [mscorlib]System.Reflection.Assembly proxyTypesAssembly)
0x18793  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.ServiceModel]System.ServiceModel.Description.IEndpointBehavior>::Add(var<u1>)
0x18798  leave.s  loc_187A4
0x1879a  ldloc.1
0x1879b  brfalse.s loc_187A3
0x1879d  ldloc.0
0x1879e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x187a3  endfinally
0x187a4  ret
```
