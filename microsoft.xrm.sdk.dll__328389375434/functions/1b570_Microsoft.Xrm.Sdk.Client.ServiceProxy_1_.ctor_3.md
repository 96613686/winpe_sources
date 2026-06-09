# Microsoft.Xrm.Sdk.Client.ServiceProxy`1::.ctor_3

- ea: `0x1b570`
- end: `0x1b5b8`
- name: `Microsoft.Xrm.Sdk.Client.ServiceProxy`1::.ctor_3`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x7ca0`

## string_xrefs

- `0x1b582`: `serviceConfiguration`
- `0x1b592`: `serviceConfiguration.CurrentServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x1b570  ldarg.0
0x1b571  ldsfld   valuetype [mscorlib]System.TimeSpan Microsoft.Xrm.Sdk.Client.ServiceDefaults::DefaultTimeout
0x1b576  stfld    valuetype [mscorlib]System.TimeSpan class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::_timeout
0x1b57b  ldarg.0
0x1b57c  call     instance void [mscorlib]System.Object::.ctor()
0x1b581  ldarg.1
0x1b582  ldstr    aServiceconfigu// "serviceConfiguration"
0x1b587  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b58c  ldarg.1
0x1b58d  callvirt instance class [System.ServiceModel]System.ServiceModel.Description.ServiceEndpoint class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>::get_CurrentServiceEndpoint()
0x1b592  ldstr    aServiceconfigu_1// "serviceConfiguration.CurrentServiceEndp"...
0x1b597  call     void Microsoft.Xrm.Sdk.ClientExceptionHelper::ThrowIfNull(object parameter, string name)
0x1b59c  ldarg.0
0x1b59d  ldarg.1
0x1b59e  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_ServiceConfiguration(class Microsoft.Xrm.Sdk.Client.IServiceConfiguration`1<var<u1>>)
0x1b5a3  ldarg.0
0x1b5a4  ldarg.2
0x1b5a5  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::SetClientCredentials(class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials)
0x1b5aa  ldarg.0
0x1b5ab  ldc.i4.1
0x1b5ac  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::set_IsAuthenticated(bool)
0x1b5b1  ldarg.0
0x1b5b2  call     instance void class Microsoft.Xrm.Sdk.Client.ServiceProxy`1<var<u1>>::SetDefaultEndpointSwitchBehavior()
0x1b5b7  ret
```
