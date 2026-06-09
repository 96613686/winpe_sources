# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::UpdateObject_0

- ea: `0x13fd0`
- end: `0x14005`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::UpdateObject_0`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x13fb0`

## callees

- `0x13fd0`
- `0x14010`
- `0x14050`
- `0x14090`
- `0x15070`

## pseudocode

```c

```

## disassembly

```asm
0x13fd0  ldarg.1
0x13fd1  brtrue.s loc_13FDE
0x13fd3  ldstr    aEntity// "entity"
0x13fd8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13fdd  throw
0x13fde  ldarg.0
0x13fdf  ldarg.1
0x13fe0  ldstr    aEntity// "entity"
0x13fe5  call     instance class Microsoft.Xrm.Sdk.EntityDescriptor Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::EnsureTracked(class Microsoft.Xrm.Sdk.Entity entity, string parameterName)
0x13fea  stloc.0
0x13feb  ldarg.2
0x13fec  brtrue.s loc_13FF6
0x13fee  ldarg.0
0x13fef  ldloc.0
0x13ff0  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::InternalUpdate(class Microsoft.Xrm.Sdk.EntityDescriptor existingEntity)
0x13ff5  ret
0x13ff6  ldarg.0
0x13ff7  ldarg.1
0x13ff8  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::ValidateUpdate(class Microsoft.Xrm.Sdk.Entity graph)
0x13ffd  ldarg.0
0x13ffe  ldarg.1
0x13fff  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::UpdateEntityGraph(class Microsoft.Xrm.Sdk.Entity entity)
0x14004  ret
```
