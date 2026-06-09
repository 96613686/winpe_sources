# Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal

- ea: `0x9aa0`
- end: `0x9ae6`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::ExecuteInternal`
- size: `70`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9930`
- `0x99f0`
- `0x9a20`
- `0x9a60`
- `0x9a80`
- `0x9af0`
- `0x9b20`
- `0x9b50`

## callees

- `0x1e80`
- `0x9aa0`

## pseudocode

```c

```

## disassembly

```asm
0x9aa0  ldc.i4.1
0x9aa1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x9aa6  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x9aab  ldarg.1
0x9aac  ldarg.0
0x9aad  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_proxyTypesAssembly
0x9ab2  call     T0x2B000014
0x9ab7  stloc.0
0x9ab8  ldarg.0
0x9ab9  ldfld    class Microsoft.Crm.Sandbox.ISandboxOrganizationService Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_fullTrustService
0x9abe  ldarg.1
0x9abf  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x9ac4  ldloc.0
0x9ac5  ldarg.0
0x9ac6  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_traceSettings
0x9acb  callvirt instance unsigned int8[] Microsoft.Crm.Sandbox.ISandboxOrganizationService::Execute(string operation, unsigned int8[] serializedRequest, object traceSettings)
0x9ad0  ldarg.0
0x9ad1  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::_proxyTypesAssembly
0x9ad6  call     T0x2B000015
0x9adb  stloc.1
0x9adc  leave.s  loc_9AE4
0x9ade  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x9ae3  endfinally
0x9ae4  ldloc.1
0x9ae5  ret
```
