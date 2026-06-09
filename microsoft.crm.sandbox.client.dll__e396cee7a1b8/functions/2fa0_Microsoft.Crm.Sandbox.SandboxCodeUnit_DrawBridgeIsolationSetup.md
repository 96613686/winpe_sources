# Microsoft.Crm.Sandbox.SandboxCodeUnit::DrawBridgeIsolationSetup

- ea: `0x2fa0`
- end: `0x2fd7`
- name: `Microsoft.Crm.Sandbox.SandboxCodeUnit::DrawBridgeIsolationSetup`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x34a0`

## callees

- `0x2fa0`

## string_xrefs

- `0x2fbd`: `Service Bus Issuer Certificate`

## pseudocode

```c

```

## disassembly

```asm
0x2fa0  ldarg.1
0x2fa1  call     bool [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::IsDrawbridgeIsolationEnabled(valuetype [mscorlib]System.Guid)
0x2fa6  stloc.0
0x2fa7  ldarg.0
0x2fa8  ldloc.0
0x2fa9  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_UseDrawBridgeIsolation(bool)
0x2fae  ldloc.0
0x2faf  brfalse.s loc_2FD5
0x2fb1  ldstr    aAppfabricissue// "AppFabricIssuer"
0x2fb6  call     class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificate(string)
0x2fbb  stloc.1
0x2fbc  ldloc.1
0x2fbd  ldstr    aServiceBusIssu// "Service Bus Issuer Certificate"
0x2fc2  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2fc7  ldarg.0
0x2fc8  ldloc.1
0x2fc9  ldc.i4.3
0x2fca  ldc.i4.0
0x2fcb  callvirt instance string [System]System.Security.Cryptography.X509Certificates.X509Certificate2::GetNameInfo(valuetype [System]System.Security.Cryptography.X509Certificates.X509NameType, bool)
0x2fd0  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::set_ServiceCertificateDNSName(string)
0x2fd5  ldloc.0
0x2fd6  ret
```
