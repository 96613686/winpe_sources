# Microsoft.Crm.Sandbox.Service.TPSServiceProvider::GetAssemblyKeyVaultAddress

- ea: `0x8170`
- end: `0x8210`
- name: `Microsoft.Crm.Sandbox.Service.TPSServiceProvider::GetAssemblyKeyVaultAddress`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8170`
- `0x8290`

## string_xrefs

- `0x817c`: `publicToken`
- `0x81b8`: `TPSServiceProvider.GetAssemblyKeyVaultAddress - KeyVaultUri: {0}`
- `0x81e2`: `Assembly {0} with PublicToken {1} does not have KeyVault configured`
- `0x81f9`: `Assembly {0} with PublicToken {1} is unknown`

## pseudocode

```c

```

## disassembly

```asm
0x8170  ldarg.1
0x8171  ldstr    aAssemblyname// "assemblyName"
0x8176  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x817b  ldarg.2
0x817c  ldstr    aPublictoken// "publicToken"
0x8181  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8186  ldarg.0
0x8187  call     instance class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient Microsoft.Crm.Sandbox.Service.TPSServiceProvider::CreateTpsClient()
0x818c  ldarg.1
0x818d  ldarg.2
0x818e  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>> [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient::GetAssemblyReference(string, string)
0x8193  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>>::get_Result()
0x8198  stloc.0
0x8199  ldloc.0
0x819a  brfalse.s loc_81F9
0x819c  ldloc.0
0x819d  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x81a2  brfalse.s loc_81F9
0x81a4  ldloc.0
0x81a5  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x81aa  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_KeyVaultUri()
0x81af  brfalse.s loc_81E2
0x81b1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x81b6  ldc.i4.s 0x1F
0x81b8  ldstr    aTpsserviceprov// "TPSServiceProvider.GetAssemblyKeyVaultA"...
0x81bd  ldc.i4.1
0x81be  newarr   [mscorlib]System.Object
0x81c3  dup
0x81c4  ldc.i4.0
0x81c5  ldloc.0
0x81c6  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x81cb  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_KeyVaultUri()
0x81d0  stelem.ref
0x81d1  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x81d6  ldloc.0
0x81d7  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x81dc  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_KeyVaultUri()
0x81e1  ret
0x81e2  ldstr    aAssembly0WithP// "Assembly {0} with PublicToken {1} does "...
0x81e7  ldarg.1
0x81e8  ldarg.2
0x81e9  call     string [mscorlib]System.String::Format(string, object, object)
0x81ee  ldc.i4   0x80091006
0x81f3  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x81f8  throw
0x81f9  ldstr    aAssembly0WithP_0// "Assembly {0} with PublicToken {1} is un"...
0x81fe  ldarg.1
0x81ff  ldarg.2
0x8200  call     string [mscorlib]System.String::Format(string, object, object)
0x8205  ldc.i4   0x80091007
0x820a  newobj   instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.CrmExceptions.CrmTPSException::.ctor(string, int32)
0x820f  throw
```
