# Microsoft.Crm.Sandbox.Service.TPSServiceProvider::IsValidAssembly

- ea: `0x8210`
- end: `0x8285`
- name: `Microsoft.Crm.Sandbox.Service.TPSServiceProvider::IsValidAssembly`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x8210`
- `0x8290`

## string_xrefs

- `0x821c`: `publicToken`

## pseudocode

```c

```

## disassembly

```asm
0x8210  ldarg.1
0x8211  ldstr    aAssemblyname// "assemblyName"
0x8216  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x821b  ldarg.2
0x821c  ldstr    aPublictoken// "publicToken"
0x8221  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x8226  ldarg.0
0x8227  call     instance class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient Microsoft.Crm.Sandbox.Service.TPSServiceProvider::CreateTpsClient()
0x822c  ldarg.1
0x822d  ldarg.2
0x822e  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>> [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceClient::GetAssemblyReference(string, string)
0x8233  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>>::get_Result()
0x8238  stloc.0
0x8239  ldloc.0
0x823a  brfalse.s loc_8283
0x823c  ldloc.0
0x823d  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x8242  brfalse.s loc_8283
0x8244  ldloc.0
0x8245  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x824a  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_AssemblyName()
0x824f  brfalse.s loc_8283
0x8251  ldloc.0
0x8252  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x8257  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_PublicKeyToken()
0x825c  brfalse.s loc_8283
0x825e  ldloc.0
0x825f  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x8264  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_AssemblyName()
0x8269  ldarg.1
0x826a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x826f  brfalse.s loc_8283
0x8271  ldloc.0
0x8272  callvirt instance var<u1> class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Online.Clients.Tps.TpsServiceResponse`1<class [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference>::get_Value()
0x8277  callvirt instance string [Microsoft.Crm.Online.Tps.TpsServiceClient]Microsoft.Crm.Cloud.Pes.Tps.Service.Resources.AssemblyReference::get_PublicKeyToken()
0x827c  ldarg.2
0x827d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8282  ret
0x8283  ldc.i4.0
0x8284  ret
```
