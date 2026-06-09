# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService

- ea: `0x2980`
- end: `0x29c8`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2980`
- `0x29d0`
- `0x2b80`

## pseudocode

```c

```

## disassembly

```asm
0x2980  ldarga.s 1
0x2982  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x2987  brfalse.s loc_29BC
0x2989  ldarga.s 1
0x298b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x2990  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2995  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x299a  brfalse.s loc_29AE
0x299c  ldarga.s 1
0x299e  ldarg.0
0x299f  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::get_Context()
0x29a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_UserId()
0x29a9  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::.ctor(var<u1>)
0x29ae  ldarg.0
0x29af  ldarga.s 1
0x29b1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x29b6  call     instance class Microsoft.Crm.Sandbox.SandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Guid userId)
0x29bb  ret
0x29bc  ldarg.0
0x29bd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x29c2  call     instance class Microsoft.Crm.Sandbox.SandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Guid userId)
0x29c7  ret
```
