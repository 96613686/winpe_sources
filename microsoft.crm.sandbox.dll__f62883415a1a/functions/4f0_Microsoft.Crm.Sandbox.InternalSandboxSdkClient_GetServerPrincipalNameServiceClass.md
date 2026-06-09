# Microsoft.Crm.Sandbox.InternalSandboxSdkClient::GetServerPrincipalNameServiceClass

- ea: `0x4f0`
- end: `0x53c`
- name: `Microsoft.Crm.Sandbox.InternalSandboxSdkClient::GetServerPrincipalNameServiceClass`
- size: `76`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1e0`

## callees

- `0xa0`
- `0x4f0`

## string_xrefs

- `0x50d`: `MSCRMAsyncService`

## pseudocode

```c

```

## disassembly

```asm
0x4f0  ldarg.0
0x4f1  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_ServerRole()
0x4f6  stloc.0
0x4f7  ldloc.0
0x4f8  ldc.i4.1
0x4f9  beq.s    loc_507
0x4fb  ldloc.0
0x4fc  ldc.i4.2
0x4fd  beq.s    loc_50D
0x4ff  ldloc.0
0x500  ldc.i4   0x8000
0x505  bne.un.s loc_513
0x507  ldstr    aHttp_0// "HTTP"
0x50c  ret
0x50d  ldstr    aMscrmasyncserv// "MSCRMAsyncService"
0x512  ret
0x513  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x518  ldstr    aInvalidServerR_0// "Invalid server role {0} chosen for retr"...
0x51d  ldc.i4.1
0x51e  newarr   [mscorlib]System.Object
0x523  dup
0x524  ldc.i4.0
0x525  ldarg.0
0x526  call     instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Sandbox.InternalSandboxSdkClient::get_ServerRole()
0x52b  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x530  stelem.ref
0x531  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x536  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x53b  throw
```
