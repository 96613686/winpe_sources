# Microsoft.Crm.Sandbox.SandboxClient::Start

- ea: `0x590`
- end: `0x5f9`
- name: `Microsoft.Crm.Sandbox.SandboxClient::Start`
- size: `105`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1160`
- `0x8950`

## callees

- `0x520`
- `0x540`
- `0x590`

## string_xrefs

- `0x5d0`: `MSCRMSandboxService`

## pseudocode

```c

```

## disassembly

```asm
0x590  newobj   instance void [System]System.UriBuilder::.ctor()
0x595  stloc.0
0x596  ldarg.0
0x597  call     instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x59c  ldnull
0x59d  cgt.un
0x59f  ldstr    aRemotemachinen// "RemoteMachineName is null"
0x5a4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x5a9  ldloc.0
0x5aa  ldarg.0
0x5ab  call     instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x5b0  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x5b5  ldloc.0
0x5b6  ldstr    aCrmsandboxhost// "CrmSandboxHost"
0x5bb  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x5c0  ldarg.0
0x5c1  call     instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteFullMachineName()
0x5c6  dup
0x5c7  brtrue.s loc_5D0
0x5c9  pop
0x5ca  ldarg.0
0x5cb  call     instance string Microsoft.Crm.Sandbox.SandboxClient::get_RemoteMachineName()
0x5d0  ldstr    aMscrmsandboxse// "MSCRMSandboxService"
0x5d5  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::GetSpnIdentityString(string, string)
0x5da  stloc.1
0x5db  ldloc.1
0x5dc  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5e1  brtrue.s loc_5EB
0x5e3  ldloc.1
0x5e4  call     class [System.ServiceModel]System.ServiceModel.EndpointIdentity [System.ServiceModel]System.ServiceModel.EndpointIdentity::CreateSpnIdentity(string)
0x5e9  br.s     loc_5EC
0x5eb  ldnull
0x5ec  stloc.2
0x5ed  ldarg.0
0x5ee  ldloc.0
0x5ef  ldc.i4.1
0x5f0  ldnull
0x5f1  ldc.i4.4
0x5f2  ldloc.2
0x5f3  call     instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::Start(class [System]System.UriBuilder, valuetype [System.ServiceModel]System.ServiceModel.TcpClientCredentialType, class [System.ServiceModel]System.ServiceModel.Description.ClientCredentials, valuetype [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPropertyPrefix, class [System.ServiceModel]System.ServiceModel.EndpointIdentity)
0x5f8  ret
```
