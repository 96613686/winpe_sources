# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::.ctor_1

- ea: `0x18640`
- end: `0x186bd`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::.ctor_1`
- size: `125`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18630`
- `0x18d60`
- `0x18dd0`

## callees

- `0x18640`
- `0x186c0`
- `0x18730`
- `0x18910`

## pseudocode

```c

```

## disassembly

```asm
0x18640  ldarg.0
0x18641  newobj   instance void [mscorlib]System.Object::.ctor()
0x18646  stfld    object Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::_lockObject
0x1864b  ldarg.0
0x1864c  call     instance void [mscorlib]System.Object::.ctor()
0x18651  ldarg.0
0x18652  ldarg.1
0x18653  ldc.i4.1
0x18654  newobj   instance void class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<class Microsoft.Xrm.Sdk.IOrganizationService>::.ctor(class [System]System.Uri, bool)
0x18659  stfld    class Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1<class Microsoft.Xrm.Sdk.IOrganizationService> Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::service
0x1865e  ldarg.2
0x1865f  brfalse.s loc_18673
0x18661  ldarg.3
0x18662  ldnull
0x18663  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x18668  brfalse.s loc_18673
0x1866a  ldarg.0
0x1866b  ldarg.3
0x1866c  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes(class [mscorlib]System.Reflection.Assembly assembly)
0x18671  br.s     loc_1867C
0x18673  ldarg.2
0x18674  brfalse.s loc_1867C
0x18676  ldarg.0
0x18677  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::EnableProxyTypes()
0x1867c  leave.s  loc_186BC
0x1867e  ldc.i4.1
0x1867f  stloc.0
0x18680  callvirt instance class [mscorlib]System.Exception [mscorlib]System.Exception::get_InnerException()
0x18685  isinst   [System]System.Net.WebException
0x1868a  stloc.1
0x1868b  ldloc.1
0x1868c  brfalse.s loc_186B5
0x1868e  ldloc.1
0x1868f  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x18694  isinst   [System]System.Net.HttpWebResponse
0x18699  stloc.2
0x1869a  ldloc.2
0x1869b  brfalse.s loc_186B5
0x1869d  ldloc.2
0x1869e  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x186a3  ldc.i4   0x191
0x186a8  bne.un.s loc_186B5
0x186aa  ldarg.0
0x186ab  ldarg.1
0x186ac  call     instance bool Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::AdjustServiceEndpoint(class [System]System.Uri serviceUri)
0x186b1  ldc.i4.0
0x186b2  ceq
0x186b4  stloc.0
0x186b5  ldloc.0
0x186b6  brfalse.s loc_186BA
0x186b8  rethrow
0x186ba  leave.s  loc_186BC
0x186bc  ret
```
