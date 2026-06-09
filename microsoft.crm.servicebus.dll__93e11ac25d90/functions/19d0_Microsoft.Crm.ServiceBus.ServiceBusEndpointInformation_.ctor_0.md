# Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor_0

- ea: `0x19d0`
- end: `0x1a61`
- name: `Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::.ctor_0`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0xf50`

## callees

- `0x19d0`
- `0x1a80`
- `0x1b40`
- `0x1bc0`
- `0x1be0`
- `0x1ca0`
- `0x1db0`
- `0x22e0`
- `0x2320`

## string_xrefs

- `0x19ee`: `orgServiceFactory`
- `0x1a2d`: `orgService`

## pseudocode

```c

```

## disassembly

```asm
0x19d0  ldarg.0
0x19d1  call     instance void [mscorlib]System.Object::.ctor()
0x19d6  ldarg.1
0x19d7  ldstr    aAssemblyname// "assemblyName"
0x19dc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x19e1  ldarg.2
0x19e2  ldstr    aOrganizationid// "organizationId"
0x19e7  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x19ec  ldarg.s  6
0x19ee  ldstr    aOrgservicefact// "orgServiceFactory"
0x19f3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x19f8  ldarg.0
0x19f9  ldc.i4.0
0x19fa  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ValidateOnly(bool value)
0x19ff  ldarg.0
0x1a00  ldarg.1
0x1a01  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_AssemblyName(string value)
0x1a06  ldarg.0
0x1a07  ldnull
0x1a08  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_ClaimCollection(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x1a0d  ldarg.0
0x1a0e  ldarg.2
0x1a0f  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x1a14  ldarg.0
0x1a15  ldc.i4.1
0x1a16  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::set_UserClaim(valuetype UserClaimType value)
0x1a1b  ldarg.s  6
0x1a1d  ldloca.s 1
0x1a1f  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x1a25  ldloc.1
0x1a26  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationServiceFactory::CreateOrganizationService(valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>)
0x1a2b  stloc.0
0x1a2c  ldloc.0
0x1a2d  ldstr    aOrgservice// "orgService"
0x1a32  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1a37  ldarg.s  5
0x1a39  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1a3e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1a43  brfalse.s loc_1A4E
0x1a45  ldarg.0
0x1a46  ldarg.s  5
0x1a48  ldarg.2
0x1a49  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::LoadFromDatabase(valuetype [mscorlib]System.Guid configurationId, valuetype [mscorlib]System.Guid organizationId)
0x1a4e  ldarg.0
0x1a4f  ldarg.2
0x1a50  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetOrganizationName(valuetype [mscorlib]System.Guid organizationId)
0x1a55  ldarg.0
0x1a56  ldarg.3
0x1a57  ldarg.s  4
0x1a59  ldarg.2
0x1a5a  ldloc.0
0x1a5b  call     instance void Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation::SetUserInfo(valuetype [mscorlib]System.Guid userId, valuetype [mscorlib]System.Guid intiatingUserId, valuetype [mscorlib]System.Guid organizationId, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService orgService)
0x1a60  ret
```
