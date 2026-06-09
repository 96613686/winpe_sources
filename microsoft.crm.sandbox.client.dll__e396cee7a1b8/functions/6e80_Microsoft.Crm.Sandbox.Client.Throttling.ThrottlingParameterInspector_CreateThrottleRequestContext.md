# Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::CreateThrottleRequestContext

- ea: `0x6e80`
- end: `0x6eba`
- name: `Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::CreateThrottleRequestContext`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x6df0`

## callees

- `0x6e80`
- `0x70b0`
- `0x93a0`

## pseudocode

```c

```

## disassembly

```asm
0x6e80  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e85  stloc.0
0x6e86  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6e8b  stloc.1
0x6e8c  ldarg.1
0x6e8d  brfalse.s loc_6E9D
0x6e8f  ldarg.1
0x6e90  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x6e95  stloc.0
0x6e96  ldarg.1
0x6e97  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_OrganizationId()
0x6e9c  stloc.1
0x6e9d  ldloc.0
0x6e9e  ldloc.1
0x6e9f  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.UserAndOrganizationContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x6ea4  stloc.2
0x6ea5  ldloc.1
0x6ea6  ldloc.0
0x6ea7  ldarg.0
0x6ea8  ldloc.2
0x6ea9  call     instance bool Microsoft.Crm.Sandbox.Client.Throttling.ThrottlingParameterInspector::IsFcbEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext context)
0x6eae  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x6eb3  ldarg.2
0x6eb4  newobj   instance void ThrottleRequestContext::.ctor(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid userId, bool fcbOn, valuetype [mscorlib]System.DateTime startTime, string operationName)
0x6eb9  ret
```
