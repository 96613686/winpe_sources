# Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Update_0

- ea: `0x1f040`
- end: `0x1f1a8`
- name: `Microsoft.Crm.Admin.AdminService.CrmScaleGroupService::Update_0`
- size: `360`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1eff0`
- `0x1f020`

## callees

- `0x18790`
- `0x1f040`
- `0x20310`
- `0x203d0`
- `0x25a40`
- `0x260a0`
- `0x27750`
- `0x28560`
- `0x285a0`
- `0x285c0`
- `0x29690`
- `0x296d0`
- `0x29880`
- `0x29920`
- `0x29950`

## string_xrefs

- `0x1f0a5`: `Update`
- `0x1f0aa`: `D:\a\1\s\src\CrmLive\Admin\ScaleGroup\CrmScaleGroupService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1f040  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1f045  ldc.i4.s 9
0x1f047  ldstr    aUpdatingScaleg// "Updating ScaleGroup state, Id=({0}))"
0x1f04c  ldc.i4.1
0x1f04d  newarr   [mscorlib]System.Object
0x1f052  dup
0x1f053  ldc.i4.0
0x1f054  ldarg.1
0x1f055  box      [mscorlib]System.Guid
0x1f05a  stelem.ref
0x1f05b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f060  ldarg.1
0x1f061  ldstr    aScalegroupIden// "ScaleGroup identifier"
0x1f066  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1f06b  ldarg.2
0x1f06c  ldstr    aScalegroupdata// "ScaleGroupData"
0x1f071  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1f076  ldarg.3
0x1f077  ldstr    aDatacenterid_1// "DatacenterId"
0x1f07c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1f081  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1f086  stloc.0
0x1f087  ldloc.0
0x1f088  ldarg.3
0x1f089  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::set_DatacenterId(valuetype [mscorlib]System.Guid)
0x1f08e  ldloc.0
0x1f08f  ldstr    aScalegroup// "ScaleGroup"
0x1f094  ldarg.1
0x1f095  box      [mscorlib]System.Guid
0x1f09a  ldarg.2
0x1f09b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1f0a0  ldc.i4   0x16F
0x1f0a5  ldstr    aUpdate// "Update"
0x1f0aa  ldstr    aDA1SSrcCrmlive_42// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Scale"...
0x1f0af  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1f0b4  pop
0x1f0b5  leave.s  loc_1F0C1
0x1f0b7  ldloc.0
0x1f0b8  brfalse.s loc_1F0C0
0x1f0ba  ldloc.0
0x1f0bb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f0c0  endfinally
0x1f0c1  ldarg.2
0x1f0c2  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x1f0c7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f0cc  brfalse.s loc_1F0DE
0x1f0ce  ldarg.2
0x1f0cf  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_HelpContentServer()
0x1f0d4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f0d9  brtrue   loc_1F177
0x1f0de  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::.ctor()
0x1f0e3  stloc.1
0x1f0e4  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::.ctor()
0x1f0e9  stloc.2
0x1f0ea  ldloc.2
0x1f0eb  ldarg.1
0x1f0ec  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x1f0f1  ldloc.2
0x1f0f2  ldarg.3
0x1f0f3  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationFilter::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x1f0f8  ldloc.1
0x1f0f9  ldc.i4.1
0x1f0fa  newarr   [mscorlib]System.String
0x1f0ff  dup
0x1f100  ldc.i4.0
0x1f101  ldstr    aId// "Id"
0x1f106  stelem.ref
0x1f107  ldloc.2
0x1f108  callvirt instance class Microsoft.Crm.Admin.AdminService.OrganizationData[] Microsoft.Crm.Admin.AdminService.CrmOrganizationService::RetrieveMultiple(string[] columns, class Microsoft.Crm.Admin.AdminService.OrganizationFilter filter)
0x1f10d  stloc.3
0x1f10e  ldc.i4.0
0x1f10f  stloc.s  4
0x1f111  br.s     loc_1F170
0x1f113  ldloc.3
0x1f114  ldloc.s  4
0x1f116  ldelem.ref
0x1f117  stloc.s  5
0x1f119  newobj   instance void Microsoft.Crm.Admin.AdminService.OrganizationData::.ctor()
0x1f11e  stloc.s  6
0x1f120  ldarg.2
0x1f121  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x1f126  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f12b  brtrue.s loc_1F13A
0x1f12d  ldloc.s  6
0x1f12f  ldarg.2
0x1f130  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_ReportServer()
0x1f135  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_SrsUrl(string value)
0x1f13a  ldarg.2
0x1f13b  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_HelpContentServer()
0x1f140  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1f145  brtrue.s loc_1F154
0x1f147  ldloc.s  6
0x1f149  ldarg.2
0x1f14a  callvirt instance string Microsoft.Crm.Admin.AdminService.ScaleGroupData::get_HelpContentServer()
0x1f14f  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_HelpContentServerUrl(string value)
0x1f154  ldloc.s  6
0x1f156  ldloc.s  5
0x1f158  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.OrganizationData::get_Id()
0x1f15d  callvirt instance void Microsoft.Crm.Admin.AdminService.OrganizationData::set_Id(valuetype [mscorlib]System.Guid value)
0x1f162  ldloc.1
0x1f163  ldloc.s  6
0x1f165  callvirt instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationService::UpdateWithoutCheckStatus(class Microsoft.Crm.Admin.AdminService.OrganizationData organizationData)
0x1f16a  ldloc.s  4
0x1f16c  ldc.i4.1
0x1f16d  add
0x1f16e  stloc.s  4
0x1f170  ldloc.s  4
0x1f172  ldloc.3
0x1f173  ldlen
0x1f174  conv.i4
0x1f175  blt.s    loc_1F113
0x1f177  leave.s  loc_1F1A7
0x1f179  stloc.s  7
0x1f17b  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1f180  ldc.i4.s 9
0x1f182  ldstr    aExceptionInUpd_1// "Exception in updating scalegroup Id=({0"...
0x1f187  ldc.i4.2
0x1f188  newarr   [mscorlib]System.Object
0x1f18d  dup
0x1f18e  ldc.i4.0
0x1f18f  ldarg.1
0x1f190  box      [mscorlib]System.Guid
0x1f195  stelem.ref
0x1f196  dup
0x1f197  ldc.i4.1
0x1f198  ldloc.s  7
0x1f19a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1f19f  stelem.ref
0x1f1a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1f1a5  rethrow
0x1f1a7  ret
```
