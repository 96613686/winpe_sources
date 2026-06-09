# Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::.ctor

- ea: `0x2920`
- end: `0x297e`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::.ctor`
- size: `94`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3470`

## callees

- `0x2310`

## string_xrefs

- `0x295e`: `SandboxOrganizationServiceFactory ctor`

## pseudocode

```c

```

## disassembly

```asm
0x2920  ldarg.0
0x2921  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService>::.ctor()
0x2926  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Sandbox.SandboxOrganizationService> Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServices
0x292b  ldarg.0
0x292c  newobj   instance void [mscorlib]System.Object::.ctor()
0x2931  stfld    object Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_xrmServicesLock
0x2936  ldarg.0
0x2937  call     instance void Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::.ctor()
0x293c  ldarg.1
0x293d  ldstr    aCallinfo// "callInfo"
0x2942  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2947  ldarg.2
0x2948  ldstr    aContext// "context"
0x294d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2952  ldarg.3
0x2953  ldstr    aAssemblyname// "assemblyName"
0x2958  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x295d  ldarg.1
0x295e  ldstr    aSandboxorganiz_16// "SandboxOrganizationServiceFactory ctor"
0x2963  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::Trace(string)
0x2968  ldarg.0
0x2969  ldarg.3
0x296a  stfld    string Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_assemblyName
0x296f  ldarg.0
0x2970  ldarg.1
0x2971  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_callInfo
0x2976  ldarg.0
0x2977  ldarg.2
0x2978  stfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext Microsoft.Crm.Sandbox.SandboxOrganizationServiceFactory::_context
0x297d  ret
```
