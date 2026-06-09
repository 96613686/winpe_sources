# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::CreateOrganizationService

- ea: `0x9740`
- end: `0x975e`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::CreateOrganizationService`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ec0`
- `0x9880`

## pseudocode

```c

```

## disassembly

```asm
0x9740  ldarg.0
0x9741  ldfld    class Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_fullTrustFactory
0x9746  ldarg.1
0x9747  callvirt instance class Microsoft.Crm.Sandbox.ISandboxOrganizationService Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> userId)
0x974c  ldarg.0
0x974d  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_proxyTypesAssembly
0x9752  ldarg.0
0x9753  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_traceSettings
0x9758  newobj   instance void Microsoft.Crm.Sandbox.SandboxOrganizationServiceWrapper::.ctor(class Microsoft.Crm.Sandbox.ISandboxOrganizationService fullTrustService, class [mscorlib]System.Reflection.Assembly proxyTypesAssembly, object traceSettings)
0x975d  ret
```
