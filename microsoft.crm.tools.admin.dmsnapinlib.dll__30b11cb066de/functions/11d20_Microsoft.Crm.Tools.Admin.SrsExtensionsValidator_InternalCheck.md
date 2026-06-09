# Microsoft.Crm.Tools.Admin.SrsExtensionsValidator::InternalCheck

- ea: `0x11d20`
- end: `0x11d77`
- name: `Microsoft.Crm.Tools.Admin.SrsExtensionsValidator::InternalCheck`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x84f0`
- `0x8ab0`
- `0x11d20`

## string_xrefs

- `0x11d4a`: `SrsExtensionsValidator.Failure`

## pseudocode

```c

```

## disassembly

```asm
0x11d20  ldarg.1
0x11d21  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0x11d26  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x11d2b  newobj   instance void [System]System.Uri::.ctor(string)
0x11d30  call     class [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SetupReportServer [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.SetupReportServer::GetSetupReportServer(class [System]System.Uri)
0x11d35  stloc.0
0x11d36  ldloc.0
0x11d37  ldc.i4.1
0x11d38  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.DataProviderType)
0x11d3d  brfalse.s loc_11D48
0x11d3f  ldloc.0
0x11d40  ldc.i4.0
0x11d41  callvirt instance bool [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype [Microsoft.Crm.Reporting]Microsoft.Crm.Reporting.DataProviderType)
0x11d46  brtrue.s loc_11D62
0x11d48  ldc.i4.2
0x11d49  ldarg.0
0x11d4a  ldstr    aSrsextensionsv// "SrsExtensionsValidator.Failure"
0x11d4f  ldc.i4.0
0x11d50  newarr   [mscorlib]System.Object
0x11d55  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0x11d5a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0x11d5f  stloc.1
0x11d60  leave.s  loc_11D75
0x11d62  leave.s  loc_11D6E
0x11d64  ldloc.0
0x11d65  brfalse.s loc_11D6D
0x11d67  ldloc.0
0x11d68  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11d6d  endfinally
0x11d6e  ldc.i4.0
0x11d6f  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0x11d74  ret
0x11d75  ldloc.1
0x11d76  ret
```
