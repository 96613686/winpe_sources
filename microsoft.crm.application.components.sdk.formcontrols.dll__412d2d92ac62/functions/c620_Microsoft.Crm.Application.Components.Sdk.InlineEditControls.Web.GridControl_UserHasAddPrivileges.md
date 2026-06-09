# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasAddPrivileges

- ea: `0xc620`
- end: `0xc7ae`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::UserHasAddPrivileges`
- size: `398`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0xbee0`
- `0xc7d0`

## callees

- `0xc620`
- `0xe480`
- `0x1cb30`
- `0x1e6e0`
- `0x1e700`
- `0x1e720`
- `0x1e760`

## pseudocode

```c

```

## disassembly

```asm
0xc620  ldarg.0
0xc621  callvirt instance class [System.Web]System.Web.UI.Page [System.Web]System.Web.UI.Control::get_Page()
0xc626  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xc62b  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xc630  ldstr    aEtc// "etc"
0xc635  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xc63a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc63f  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0xc644  stloc.0
0xc645  ldarg.0
0xc646  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc64b  ldc.i4.6
0xc64c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc651  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc656  stloc.1
0xc657  ldarg.0
0xc658  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_TargetEntityType()
0xc65d  ldc.i4.1
0xc65e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc663  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc668  stloc.2
0xc669  ldarg.0
0xc66a  call     instance bool Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid()
0xc66f  brfalse.s loc_C675
0xc671  ldloc.1
0xc672  ldloc.2
0xc673  and
0xc674  ret
0xc675  ldc.i4   0xCA2
0xc67a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc67f  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc684  ldc.i4.2
0xc685  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc68a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc68f  stloc.3
0xc690  ldc.i4.8
0xc691  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc696  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc69b  stloc.s  4
0xc69d  ldloc.0
0xc69e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6a3  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6a8  stloc.s  5
0xc6aa  dup
0xc6ab  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc6b0  ldc.i4.0
0xc6b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6b6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6bb  stloc.s  6
0xc6bd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc6c2  ldc.i4.7
0xc6c3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6c8  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6cd  stloc.s  7
0xc6cf  ldloc.3
0xc6d0  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc6d5  ldc.i4.1
0xc6d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6db  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6e0  stloc.s  8
0xc6e2  ldloc.s  4
0xc6e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc6e9  ldc.i4.1
0xc6ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc6ef  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc6f4  stloc.s  9
0xc6f6  ldloc.s  5
0xc6f8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc6fd  ldc.i4.7
0xc6fe  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc703  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc708  stloc.s  0xA
0xc70a  ldarg.0
0xc70b  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsStakeholdersGrid()
0xc710  brfalse.s loc_C71E
0xc712  ldloc.s  6
0xc714  ldloc.s  7
0xc716  and
0xc717  ldloc.s  0xA
0xc719  and
0xc71a  ldloc.s  8
0xc71c  and
0xc71d  ret
0xc71e  ldarg.0
0xc71f  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsSalesTeamGrid()
0xc724  brfalse.s loc_C73B
0xc726  ldloc.s  6
0xc728  ldloc.s  7
0xc72a  and
0xc72b  ldloc.s  0xA
0xc72d  and
0xc72e  ldloc.s  9
0xc730  and
0xc731  brfalse.s loc_C739
0xc733  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xc738  ret
0xc739  ldc.i4.0
0xc73a  ret
0xc73b  ldarg.0
0xc73c  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsCompetitorsGrid()
0xc741  brfalse.s loc_C77D
0xc743  ldc.i4.s 0x7B
0xc745  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc74a  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc74f  dup
0xc750  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc755  ldc.i4.6
0xc756  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc75b  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc760  stloc.s  0xB
0xc762  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc767  ldc.i4.1
0xc768  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc76d  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc772  stloc.s  0xC
0xc774  ldloc.s  0xB
0xc776  ldloc.s  0xA
0xc778  and
0xc779  ldloc.s  0xC
0xc77b  and
0xc77c  ret
0xc77d  ldarg.0
0xc77e  call     instance bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_IsRecordAssociatedSalesTeamGrid()
0xc783  brfalse.s loc_C7A7
0xc785  ldloc.s  5
0xc787  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0xc78c  ldc.i4.5
0xc78d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xc792  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.PrivilegeType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xc797  ldloc.s  9
0xc799  and
0xc79a  ldloc.s  0xA
0xc79c  and
0xc79d  brfalse.s loc_C7A5
0xc79f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0xc7a4  ret
0xc7a5  ldc.i4.0
0xc7a6  ret
0xc7a7  ldloc.1
0xc7a8  ldloc.s  0xA
0xc7aa  and
0xc7ab  ldloc.2
0xc7ac  and
0xc7ad  ret
```
