# Microsoft.Crm.Tools.Admin.OrganizationDatabaseExistsValidator::InternalCheck

- ea: `0xc600`
- end: `0xc68b`
- name: `Microsoft.Crm.Tools.Admin.OrganizationDatabaseExistsValidator::InternalCheck`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x84f0`
- `0x8720`
- `0x89f0`
- `0x8bf0`
- `0xc600`

## string_xrefs

- `0xc60d`: `InstallInfo.CreateDatabase`
- `0xc625`: `Cannot call this OrganizationDatabaseExistsValidator if CreateDatabase property is set to true`

## pseudocode

```c

```

## disassembly

```asm
0xc600  ldarg.1
0xc601  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xc606  stloc.0
0xc607  ldloc.0
0xc608  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xc60d  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xc612  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xc617  brfalse.s loc_C624
0xc619  ldloc.0
0xc61a  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xc61f  ldc.i4.0
0xc620  ceq
0xc622  br.s     loc_C625
0xc624  ldc.i4.1
0xc625  ldstr    aCannotCallThis// "Cannot call this OrganizationDatabaseEx"...
0xc62a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xc62f  ldloc.0
0xc630  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0xc635  stloc.1
0xc636  ldloc.0
0xc637  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xc63c  ldloc.1
0xc63d  call     bool [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.SqlUtility::DatabaseExists(string, string)
0xc642  brtrue.s loc_C661
0xc644  ldc.i4.2
0xc645  ldstr    aOrganizationda// "OrganizationDatabaseExistsValidator.Dat"...
0xc64a  ldc.i4.1
0xc64b  newarr   [mscorlib]System.Object
0xc650  dup
0xc651  ldc.i4.0
0xc652  ldloc.1
0xc653  stelem.ref
0xc654  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xc659  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xc65e  stloc.2
0xc65f  leave.s  loc_C689
0xc661  leave.s  loc_C682
0xc663  pop
0xc664  ldc.i4.2
0xc665  ldarg.0
0xc666  ldstr    aOrganizationda// "OrganizationDatabaseExistsValidator.Dat"...
0xc66b  ldc.i4.1
0xc66c  newarr   [mscorlib]System.Object
0xc671  dup
0xc672  ldc.i4.0
0xc673  ldloc.1
0xc674  stelem.ref
0xc675  call     instance string [Microsoft.Crm.Setup.Common]Microsoft.Crm.Setup.Common.Validator::GetResourceString(string, object[])
0xc67a  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xc67f  stloc.2
0xc680  leave.s  loc_C689
0xc682  ldc.i4.0
0xc683  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xc688  ret
0xc689  ldloc.2
0xc68a  ret
```
