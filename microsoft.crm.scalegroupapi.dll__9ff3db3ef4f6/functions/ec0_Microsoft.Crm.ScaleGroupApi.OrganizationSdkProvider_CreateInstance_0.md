# Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance_0

- ea: `0xec0`
- end: `0xf06`
- name: `Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance_0`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xeb0`
- `0x2ad0`

## callees

- `0xe70`
- `0xe90`
- `0xec0`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldarg.0
0xec1  ldstr    aOrgid// "orgId"
0xec6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0xecb  ldnull
0xecc  stloc.0
0xecd  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::_override
0xed2  brfalse.s loc_EDC
0xed4  ldsfld   class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::_override
0xed9  stloc.0
0xeda  br.s     loc_EF9
0xedc  call     class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory [Microsoft.Crm.Extensibility]Microsoft.Crm.Extensibility.InprocessServiceFactory::get_Instance()
0xee1  ldarg.0
0xee2  ldarg.1
0xee3  newobj   instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::.ctor()
0xee8  call     class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin::get_WebServiceApi()
0xeed  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken::.ctor(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOrigin)
0xef2  ldnull
0xef3  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.IInProcessOrganizationServiceFactory::CreateInstance(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken, class [mscorlib]System.Reflection.Assembly)
0xef8  stloc.0
0xef9  newobj   instance void Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::.ctor()
0xefe  dup
0xeff  ldloc.0
0xf00  callvirt instance void Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::set_Sdk(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService value)
0xf05  ret
```
