# Microsoft.Crm.Core.Security.Identity.ClaimTypes::.cctor

- ea: `0x4f890`
- end: `0x4f90b`
- name: `Microsoft.Crm.Core.Security.Identity.ClaimTypes::.cctor`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x4f890`: `http://schemas.microsoft.com/xrm/2011/Claims/OrganizationId`
- `0x4f89a`: `http://schemas.microsoft.com/xrm/2011/Claims/Organization`
- `0x4f8a4`: `http://schemas.microsoft.com/xrm/2011/Claims/CrmUser`
- `0x4f8ae`: `http://schemas.microsoft.com/xrm/2011/Claims/Crm`
- `0x4f8e6`: `http://schemas.microsoft.com/xrm/2011/Claims/CustomSessionTokenValidTo`
- `0x4f8f0`: `http://schemas.microsoft.com/xrm/2011/Claims/CustomSessionTokenReminderInMins`

## pseudocode

```c

```

## disassembly

```asm
0x4f890  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f895  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::OrganizationId
0x4f89a  ldstr    aHttpSchemasMic_8// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f89f  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::Organization
0x4f8a4  ldstr    aHttpSchemasMic_9// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f8a9  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CrmUser
0x4f8ae  ldstr    aHttpSchemasMic_10// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f8b3  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CrmIssuer
0x4f8b8  ldstr    aCallerid// "callerId"
0x4f8bd  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CallerId
0x4f8c2  ldstr    aCallerregardin// "callerRegardingObjectId"
0x4f8c7  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CallerRegardingObjectId
0x4f8cc  ldstr    aUsertype// "userType"
0x4f8d1  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::UserType
0x4f8d6  ldstr    aPuid// "puid"
0x4f8db  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::_headerIdentityClaimType
0x4f8e0  ldc.i4.0
0x4f8e1  stsfld   bool Microsoft.Crm.Core.Security.Identity.ClaimTypes::_headerIdentityClaimTypeSet
0x4f8e6  ldstr    aHttpSchemasMic_11// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f8eb  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CustomSessionTokenValidTo
0x4f8f0  ldstr    aHttpSchemasMic_12// "http://schemas.microsoft.com/xrm/2011/C"...
0x4f8f5  stsfld   string Microsoft.Crm.Core.Security.Identity.ClaimTypes::CustomSessionTokenReminderInMins
0x4f8fa  newobj   instance void [mscorlib]System.Object::.ctor()
0x4f8ff  stsfld   object Microsoft.Crm.Core.Security.Identity.ClaimTypes::_lockObject
0x4f904  ldc.i4.0
0x4f905  stsfld   bool Microsoft.Crm.Core.Security.Identity.ClaimTypes::_identityClaimTypeSet
0x4f90a  ret
```
