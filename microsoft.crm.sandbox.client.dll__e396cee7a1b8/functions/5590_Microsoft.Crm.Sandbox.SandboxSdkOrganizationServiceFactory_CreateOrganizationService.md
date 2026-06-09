# Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::CreateOrganizationService

- ea: `0x5590`
- end: `0x55f1`
- name: `Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::CreateOrganizationService`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3630`

## string_xrefs

- `0x55b1`: `SandboxSdkListener.CreateOrganizationService: _sdkContext.UserId: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5590  ldarga.s 1
0x5592  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x5597  ldc.i4.0
0x5598  ceq
0x559a  ldstr    aUserid// "userId"
0x559f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x55a4  ldarg.0
0x55a5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_context
0x55aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OrganizationId()
0x55af  ldc.i4.s 0x21
0x55b1  ldstr    aSandboxsdklist_25// "SandboxSdkListener.CreateOrganizationSe"...
0x55b6  ldc.i4.1
0x55b7  newarr   [mscorlib]System.Object
0x55bc  dup
0x55bd  ldc.i4.0
0x55be  ldarg.0
0x55bf  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_sdkContext
0x55c4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x55c9  box      [mscorlib]System.Guid
0x55ce  stelem.ref
0x55cf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x55d4  ldarg.0
0x55d5  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_context
0x55da  ldarg.0
0x55db  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_sdkContext
0x55e0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkContext::get_UserId()
0x55e5  ldarg.0
0x55e6  ldfld    bool Microsoft.Crm.Sandbox.SandboxSdkOrganizationServiceFactory::_forReports
0x55eb  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Sandbox.SandboxPluginHelper::GetOrganizationService(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, valuetype [mscorlib]System.Guid userId, bool forReports)
0x55f0  ret
```
