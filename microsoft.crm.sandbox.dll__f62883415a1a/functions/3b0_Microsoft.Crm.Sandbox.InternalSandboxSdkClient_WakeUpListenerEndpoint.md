# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::WakeUpListenerEndpoint

- ea: `0x3b0`
- end: `0x440`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::WakeUpListenerEndpoint`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x260`

## callees

- `0x80`
- `0x3b0`
- `0x14d0`

## string_xrefs

- `0x3b7`: `InternalSandboxSdkClient.WakeUpListenerEndpoint: Attempting to wake up Listener endpoint for server: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x3b0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b5  ldc.i4.s 0x21
0x3b7  ldstr    aInternalsandbo_1// "InternalSandboxSdkClient.WakeUpListener"...
0x3bc  ldc.i4.1
0x3bd  newarr   [mscorlib]System.Object
0x3c2  dup
0x3c3  ldc.i4.0
0x3c4  ldarg.0
0x3c5  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_Server()
0x3ca  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x3cf  stelem.ref
0x3d0  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3d5  ldstr    aHttp// "http"
0x3da  ldarg.0
0x3db  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_Server()
0x3e0  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x3e5  newobj   instance void [System]System.UriBuilder::.ctor(string, string)
0x3ea  dup
0x3eb  ldstr    aDefaultAspx// "default.aspx"
0x3f0  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x3f5  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x3fa  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x3ff  castclass [System]System.Net.HttpWebRequest
0x404  stloc.0
0x405  ldloc.0
0x406  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebRequest::GetResponse()
0x40b  pop
0x40c  leave.s  loc_43F
0x40e  stloc.1
0x40f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x414  ldc.i4.s 0x21
0x416  ldstr    aInternalsandbo_2// "InternalSandboxSdkClient.WakeUpListener"...
0x41b  ldc.i4.2
0x41c  newarr   [mscorlib]System.Object
0x421  dup
0x422  ldc.i4.0
0x423  ldarg.0
0x424  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_Server()
0x429  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.ServerData::get_Name()
0x42e  stelem.ref
0x42f  dup
0x430  ldc.i4.1
0x431  ldloc.1
0x432  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x437  stelem.ref
0x438  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x43d  leave.s  loc_43F
0x43f  ret
```
