# Microsoft.Crm.Tools.Admin.OrganizationDatabaseNotDeployedValidator::InternalCheck

- ea: `0xcab0`
- end: `0xcb61`
- name: `Microsoft.Crm.Tools.Admin.OrganizationDatabaseNotDeployedValidator::InternalCheck`
- size: `177`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x22e0`
- `0x7640`
- `0x76c0`
- `0x84f0`
- `0x8720`
- `0x89f0`
- `0x8bf0`
- `0xcab0`
- `0x19750`

## string_xrefs

- `0xcac3`: `InstallInfo.CreateDatabase`
- `0xcad7`: `Cannot call this OrganizationDatabaseNotDeployedValidator if CreateDatabase property is set to true`
- `0xcb3b`: `OrganizationDatabaseNotAlreadyImportedValidator.Failure`

## pseudocode

```c

```

## disassembly

```asm
0xcab0  newobj   instance void <>c__DisplayClass1_0::.ctor()
0xcab5  stloc.0
0xcab6  ldarg.1
0xcab7  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationInfo::.ctor(class [mscorlib]System.Collections.IDictionary data)
0xcabc  stloc.1
0xcabd  ldloc.1
0xcabe  callvirt instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0xcac3  ldstr    aInstallinfoCre// "InstallInfo.CreateDatabase"
0xcac8  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0xcacd  brfalse.s loc_CAE2
0xcacf  ldloc.1
0xcad0  callvirt instance bool Microsoft.Crm.Tools.Admin.OrganizationInfo::get_CreateDatabase()
0xcad5  brfalse.s loc_CAE2
0xcad7  ldstr    aCannotCallThis_0// "Cannot call this OrganizationDatabaseNo"...
0xcadc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0xcae1  throw
0xcae2  ldloc.0
0xcae3  ldloc.1
0xcae4  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_SqlServerName()
0xcae9  stfld    string <>c__DisplayClass1_0::sqlServerName
0xcaee  ldloc.0
0xcaef  ldloc.1
0xcaf0  callvirt instance string Microsoft.Crm.Tools.Admin.OrganizationInfo::get_DatabaseName()
0xcaf5  stfld    string <>c__DisplayClass1_0::databaseName
0xcafa  call     class Microsoft.Crm.Tools.Admin.OrganizationController Microsoft.Crm.Tools.Admin.OrganizationController::get_Instance()
0xcaff  ldc.i4.3
0xcb00  newarr   [mscorlib]System.String
0xcb05  dup
0xcb06  ldc.i4.0
0xcb07  ldstr    aId// "Id"
0xcb0c  stelem.ref
0xcb0d  dup
0xcb0e  ldc.i4.1
0xcb0f  ldstr    aSqlservername// "SqlServerName"
0xcb14  stelem.ref
0xcb15  dup
0xcb16  ldc.i4.2
0xcb17  ldstr    aDatabasename// "DatabaseName"
0xcb1c  stelem.ref
0xcb1d  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData[] Microsoft.Crm.Tools.Admin.OrganizationController::RetrieveAll(string[] columns)
0xcb22  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0xcb27  ldloc.0
0xcb28  ldftn    instance bool <>c__DisplayClass1_0::<InternalCheck>b__0(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData organization)
0xcb2e  newobj   instance void class [mscorlib]System.Predicate`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData>::.ctor(object, native int)
0xcb33  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData>::Exists(class [mscorlib]System.Predicate`1<var<u1>>)
0xcb38  brfalse.s loc_CB5A
0xcb3a  ldc.i4.2
0xcb3b  ldstr    aOrganizationda_1// "OrganizationDatabaseNotAlreadyImportedV"...
0xcb40  ldc.i4.1
0xcb41  newarr   [mscorlib]System.Object
0xcb46  dup
0xcb47  ldc.i4.0
0xcb48  ldloc.0
0xcb49  ldfld    string <>c__DisplayClass1_0::databaseName
0xcb4e  stelem.ref
0xcb4f  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0xcb54  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult, string)
0xcb59  ret
0xcb5a  ldc.i4.0
0xcb5b  newobj   instance void [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResultInfo::.ctor(valuetype [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.CheckResult)
0xcb60  ret
```
