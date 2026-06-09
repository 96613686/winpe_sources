# Microsoft.Crm.Reporting.ReportProvisioningPublisher::RetrieveLatestVersionOfMuiInstalledAtSrs

- ea: `0x3890`
- end: `0x3978`
- name: `Microsoft.Crm.Reporting.ReportProvisioningPublisher::RetrieveLatestVersionOfMuiInstalledAtSrs`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3800`

## callees

- `0x3f0`
- `0x3770`
- `0x3890`
- `0x56b0`
- `0x66c0`

## pseudocode

```c

```

## disassembly

```asm
0x3890  ldarg.0
0x3891  call     instance class Microsoft.Crm.Reporting.RuntimeReportServer Microsoft.Crm.Reporting.ReportProvisioningPublisher::get_ReportServer()
0x3896  callvirt instance class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::get_OrganizationContext()
0x389b  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_CommonFolderPath()
0x38a0  stloc.0
0x38a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x38a6  ldc.i4.s 0x20
0x38a8  ldstr    aReProvisioning// "Re-provisioning reports: Retrieving Ver"...
0x38ad  ldc.i4.2
0x38ae  newarr   [mscorlib]System.Object
0x38b3  dup
0x38b4  ldc.i4.0
0x38b5  ldloc.0
0x38b6  stelem.ref
0x38b7  dup
0x38b8  ldc.i4.1
0x38b9  ldarg.0
0x38ba  ldfld    class Microsoft.Crm.Reporting.IReportProvisioningContext Microsoft.Crm.Reporting.ReportProvisioningPublisher::_context
0x38bf  callvirt instance int32 Microsoft.Crm.Reporting.IReportProvisioningContext::get_Language()
0x38c4  box      [mscorlib]System.Int32
0x38c9  stelem.ref
0x38ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38cf  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::.ctor()
0x38d4  stloc.1
0x38d5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38da  ldstr    aMuiversion0// "MUIVERSION_{0}"
0x38df  ldc.i4.1
0x38e0  newarr   [mscorlib]System.Object
0x38e5  dup
0x38e6  ldc.i4.0
0x38e7  ldarg.0
0x38e8  ldfld    class Microsoft.Crm.Reporting.IReportProvisioningContext Microsoft.Crm.Reporting.ReportProvisioningPublisher::_context
0x38ed  callvirt instance int32 Microsoft.Crm.Reporting.IReportProvisioningContext::get_Language()
0x38f2  stloc.3
0x38f3  ldloca.s 3
0x38f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38fa  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x38ff  stelem.ref
0x3900  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3905  stloc.2
0x3906  ldloc.1
0x3907  ldloc.2
0x3908  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::set_Name(string)
0x390d  ldarg.0
0x390e  call     instance class Microsoft.Crm.Reporting.RuntimeReportServer Microsoft.Crm.Reporting.ReportProvisioningPublisher::get_ReportServer()
0x3913  ldloc.0
0x3914  ldc.i4.1
0x3915  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property
0x391a  dup
0x391b  ldc.i4.0
0x391c  ldloc.1
0x391d  stelem.ref
0x391e  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Microsoft.Crm.Reporting.RuntimeReportServer::GetProperties(string Item, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property[] Properties)
0x3923  stloc.s  4
0x3925  ldc.i4.0
0x3926  stloc.3
0x3927  br.s     loc_396F
0x3929  ldloc.s  4
0x392b  ldloc.3
0x392c  ldelem.ref
0x392d  stloc.s  5
0x392f  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x3934  ldc.i4.s 0x20
0x3936  ldstr    aReProvisioning_0// "Re-provisioning reports: Report folder "...
0x393b  ldc.i4.2
0x393c  newarr   [mscorlib]System.Object
0x3941  dup
0x3942  ldc.i4.0
0x3943  ldloc.0
0x3944  stelem.ref
0x3945  dup
0x3946  ldc.i4.1
0x3947  ldloc.s  5
0x3949  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::get_Value()
0x394e  stelem.ref
0x394f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3954  ldloc.s  5
0x3956  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::get_Name()
0x395b  ldloc.2
0x395c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3961  brfalse.s loc_396B
0x3963  ldloc.s  5
0x3965  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Property::get_Value()
0x396a  ret
0x396b  ldloc.3
0x396c  ldc.i4.1
0x396d  add
0x396e  stloc.3
0x396f  ldloc.3
0x3970  ldloc.s  4
0x3972  ldlen
0x3973  conv.i4
0x3974  blt.s    loc_3929
0x3976  ldnull
0x3977  ret
```
