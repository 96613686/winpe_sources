# Microsoft.Crm.Tools.Admin.RSConfigAction::Do

- ea: `0x11490`
- end: `0x11513`
- name: `Microsoft.Crm.Tools.Admin.RSConfigAction::Do`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x22e0`
- `0x71d0`
- `0x8670`
- `0x8ab0`
- `0x11490`
- `0x11520`

## string_xrefs

- `0x114f4`: `RSConfigAction.Failure`

## pseudocode

```c

```

## disassembly

```asm
0x11490  ldarg.0
0x11491  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x11496  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x1149b  newobj   instance void [System]System.Uri::.ctor(string)
0x114a0  stloc.0
0x114a1  ldarg.0
0x114a2  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x114a7  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_ReportingUrl()
0x114ac  call     bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.IIsUtility::IsLocalUrl(string)
0x114b1  stloc.1
0x114b2  ldarg.0
0x114b3  ldloc.0
0x114b4  ldarg.0
0x114b5  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x114ba  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x114bf  ldloc.1
0x114c0  call     instance void Microsoft.Crm.Tools.Admin.RSConfigAction::ConfigureReports(class [System]System.Uri reportingUrl, string organizationUniqueName, bool isLocalUrl)
0x114c5  leave.s  loc_114EB
0x114c7  pop
0x114c8  ldc.i4.0
0x114c9  ldc.i4.0
0x114ca  ldc.i4.s 0x1E
0x114cc  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int32, int32, int32)
0x114d1  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x114d6  ldarg.0
0x114d7  ldloc.0
0x114d8  ldarg.0
0x114d9  call     instance class Microsoft.Crm.Tools.Admin.OrganizationInfo Microsoft.Crm.Tools.Admin.OrganizationAction::get_OrganizationInfo()
0x114de  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationUniqueName()
0x114e3  ldloc.1
0x114e4  call     instance void Microsoft.Crm.Tools.Admin.RSConfigAction::ConfigureReports(class [System]System.Uri reportingUrl, string organizationUniqueName, bool isLocalUrl)
0x114e9  leave.s  loc_114EB
0x114eb  leave.s  loc_11512
0x114ed  pop
0x114ee  ldarg.0
0x114ef  call     instance class [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::get_Description()
0x114f4  ldstr    aRsconfigaction// "RSConfigAction.Failure"
0x114f9  ldc.i4.0
0x114fa  newarr   [mscorlib]System.Object
0x114ff  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x11504  callvirt instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction/ActionDescription::set_FailureMessage(string)
0x11509  ldarg.0
0x1150a  ldc.i4.1
0x1150b  stfld    bool [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CrmAction::CriticalFailure
0x11510  rethrow
0x11512  ret
```
