# Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::CreateCrmServiceClient

- ea: `0x1b30`
- end: `0x1ba6`
- name: `Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::CreateCrmServiceClient`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0xcf0`
- `0xd30`
- `0xf40`
- `0x1b30`

## string_xrefs

- `0x1b90`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x1b30  ldarg.0
0x1b31  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1b36  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::UserId
0x1b3b  stloc.0
0x1b3c  ldarg.0
0x1b3d  call     instance class Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1b42  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerArguments::OrganizationId
0x1b47  stloc.1
0x1b48  ldnull
0x1b49  stloc.2
0x1b4a  ldarg.0
0x1b4b  call     instance string Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x1b50  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x1b55  stloc.2
0x1b56  leave.s  loc_1B68
0x1b58  stloc.3
0x1b59  ldarg.0
0x1b5a  ldc.i4.1
0x1b5b  ldloc.3
0x1b5c  callvirt instance string [mscorlib]System.Object::ToString()
0x1b61  call     instance void Microsoft.Crm.MultiTenantPackageDeployment.PackageDeployerWrapperBase::LogMessage(valuetype [System]System.Diagnostics.TraceLevel level, string message)
0x1b66  leave.s  loc_1B68
0x1b68  ldarg.0
0x1b69  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x1b6e  ldloc.1
0x1b6f  ldloc.0
0x1b70  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x1b75  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x1b7a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x1b7f  ldloc.2
0x1b80  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x1b85  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::_service
0x1b8a  ldarg.0
0x1b8b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::_service
0x1b90  ldstr    aService// "service"
0x1b95  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b9a  ldarg.0
0x1b9b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.MultiTenantPackageDeployment.LivePackageDeployerWrapper::_service
0x1ba0  newobj   instance void [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy)
0x1ba5  ret
```
