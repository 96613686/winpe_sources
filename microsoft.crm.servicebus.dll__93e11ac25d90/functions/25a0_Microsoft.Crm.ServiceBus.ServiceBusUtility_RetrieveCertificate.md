# Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveCertificate

- ea: `0x25a0`
- end: `0x25f5`
- name: `Microsoft.Crm.ServiceBus.ServiceBusUtility::RetrieveCertificate`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x5750`

## callees

- `0x25a0`

## string_xrefs

- `0x25b4`: `Invalid service integration issuer public certificate data.`
- `0x25c6`: `Invalid service integration issuer public certificate data.`
- `0x25e3`: `Service integration issuer certificate not found.`

## pseudocode

```c

```

## disassembly

```asm
0x25a0  ldarg.0
0x25a1  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::get_Certificate()
0x25a6  call     unsigned int8[] [mscorlib]System.Convert::FromBase64String(string)
0x25ab  newobj   instance void [System]System.Security.Cryptography.X509Certificates.X509Certificate2::.ctor(unsigned int8[])
0x25b0  pop
0x25b1  leave.s  loc_25D7
0x25b3  stloc.1
0x25b4  ldstr    aInvalidService// "Invalid service integration issuer publ"...
0x25b9  ldloc.1
0x25ba  ldc.i4   0x80044177
0x25bf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x25c4  throw
0x25c5  stloc.2
0x25c6  ldstr    aInvalidService// "Invalid service integration issuer publ"...
0x25cb  ldloc.2
0x25cc  ldc.i4   0x80044177
0x25d1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x25d6  throw
0x25d7  ldnull
0x25d8  stloc.0
0x25d9  ldarg.0
0x25da  ldloca.s 0
0x25dc  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.CertificateUtility::TryRetrieveCertificate(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData, class [System]System.Security.Cryptography.X509Certificates.X509Certificate2&)
0x25e1  brtrue.s loc_25F3
0x25e3  ldstr    aServiceIntegra// "Service integration issuer certificate "...
0x25e8  ldc.i4   0x80044177
0x25ed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x25f2  throw
0x25f3  ldloc.0
0x25f4  ret
```
