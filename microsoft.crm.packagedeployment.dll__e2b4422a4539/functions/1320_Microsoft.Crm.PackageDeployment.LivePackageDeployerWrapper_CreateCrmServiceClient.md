# Microsoft.Crm.PackageDeployment.LivePackageDeployerWrapper::CreateCrmServiceClient

- ea: `0x1320`
- end: `0x1396`
- name: `Microsoft.Crm.PackageDeployment.LivePackageDeployerWrapper::CreateCrmServiceClient`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x580`
- `0x5c0`
- `0x7d0`
- `0x1320`

## string_xrefs

- `0x1380`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x1320  ldarg.0
0x1321  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1326  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::UserId
0x132b  stloc.0
0x132c  ldarg.0
0x132d  call     instance class Microsoft.Crm.PackageDeployment.PackageDeployerArguments Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_Arguments()
0x1332  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.PackageDeployment.PackageDeployerArguments::OrganizationId
0x1337  stloc.1
0x1338  ldnull
0x1339  stloc.2
0x133a  ldarg.0
0x133b  call     instance string Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::get_FullyQualifiedPathToAssembly()
0x1340  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x1345  stloc.2
0x1346  leave.s  loc_1358
0x1348  stloc.3
0x1349  ldarg.0
0x134a  ldc.i4.1
0x134b  ldloc.3
0x134c  callvirt instance string [mscorlib]System.Object::ToString()
0x1351  call     instance void Microsoft.Crm.PackageDeployment.PackageDeployerWrapperBase::LogMessage(valuetype [System]System.Diagnostics.TraceLevel level, string message)
0x1356  leave.s  loc_1358
0x1358  ldarg.0
0x1359  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0x135e  ldloc.1
0x135f  ldloc.0
0x1360  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0x1365  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0x136a  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0x136f  ldloc.2
0x1370  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0x1375  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.PackageDeployment.LivePackageDeployerWrapper::_service
0x137a  ldarg.0
0x137b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.PackageDeployment.LivePackageDeployerWrapper::_service
0x1380  ldstr    aService// "service"
0x1385  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x138a  ldarg.0
0x138b  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy Microsoft.Crm.PackageDeployment.LivePackageDeployerWrapper::_service
0x1390  newobj   instance void [Microsoft.Xrm.Tooling.Connector]Microsoft.Xrm.Tooling.Connector.CrmServiceClient::.ctor(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy)
0x1395  ret
```
