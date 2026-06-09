# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::Execute

- ea: `0x9760`
- end: `0x97b6`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::Execute`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1e90`
- `0x1ec0`
- `0x5040`
- `0x9760`

## pseudocode

```c

```

## disassembly

```asm
0x9760  ldarg.2
0x9761  ldstr    aContext// "context"
0x9766  call     void Microsoft.Crm.Sandbox.SandboxFault::ThrowIfNull(object argument, string name)
0x976b  ldarg.0
0x976c  ldfld    class Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_fullTrustFactory
0x9771  ldloca.s 1
0x9773  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x9779  ldloc.1
0x977a  callvirt instance class Microsoft.Crm.Sandbox.ISandboxOrganizationService Microsoft.Crm.Sandbox.ISandboxOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> userId)
0x977f  ldarg.2
0x9780  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin
0x9785  stloc.0
0x9786  ldloc.0
0x9787  brfalse.s loc_9792
0x9789  ldloc.0
0x978a  ldnull
0x978b  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPlugin::Execute(class [mscorlib]System.IServiceProvider)
0x9790  br.s     loc_979D
0x9792  ldarg.2
0x9793  isinst   [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivitySerializationExecution
0x9798  callvirt instance void [Microsoft.Xrm.Sdk.Workflow]Microsoft.Xrm.Sdk.Workflow.ICustomActivitySerializationExecution::Serialize()
0x979d  ldarg.1
0x979e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x97a3  ldarg.1
0x97a4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x97a9  ldarg.2
0x97aa  ldarg.0
0x97ab  ldfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactoryWrapper::_traceSettings
0x97b0  callvirt instance string Microsoft.Crm.Sandbox.ISandboxOrganizationService::Post(string logicaName, valuetype [mscorlib]System.Guid id, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext context, object traceSettings)
0x97b5  ret
```
