# Microsoft.Crm.Tools.Admin.LicenseController::GetMultipleTenancy

- ea: `0x17bf0`
- end: `0x17c6c`
- name: `Microsoft.Crm.Tools.Admin.LicenseController::GetMultipleTenancy`
- size: `124`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8ef0`
- `0x14630`
- `0x14d30`

## callees

- `0x7640`
- `0x76c0`
- `0x17ae0`
- `0x17bf0`
- `0x17cb0`
- `0x17cd0`

## string_xrefs

- `0x17c4b`: `License type that is installed does not support multiple tenancy.You cannot have more than one organization. Now there are ({0}) organizations.`

## pseudocode

```c

```

## disassembly

```asm
0x17bf0  ldarg.0
0x17bf1  call     instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.StoredLicenseData Microsoft.Crm.Tools.Admin.LicenseController::ReadLicense()
0x17bf6  callvirt instance bool [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.LicenseData::get_IsMultipleTenancy()
0x17bfb  brfalse.s loc_17C03
0x17bfd  newobj   instance void Microsoft.Crm.Tools.Admin.MultipleTenancyTrue::.ctor()
0x17c02  ret
0x17c03  call     class Microsoft.Crm.Tools.Admin.OrganizationController Microsoft.Crm.Tools.Admin.OrganizationController::get_Instance()
0x17c08  ldc.i4.2
0x17c09  newarr   [mscorlib]System.String
0x17c0e  dup
0x17c0f  ldc.i4.0
0x17c10  ldstr    aId// "Id"
0x17c15  stelem.ref
0x17c16  dup
0x17c17  ldc.i4.1
0x17c18  ldstr    aUniquename// "UniqueName"
0x17c1d  stelem.ref
0x17c1e  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData[] Microsoft.Crm.Tools.Admin.OrganizationController::RetrieveAll(string[] columns)
0x17c23  stloc.0
0x17c24  ldloc.0
0x17c25  ldlen
0x17c26  conv.i4
0x17c27  stloc.1
0x17c28  ldloc.1
0x17c29  brfalse.s loc_17C31
0x17c2b  ldloc.1
0x17c2c  ldc.i4.1
0x17c2d  beq.s    loc_17C38
0x17c2f  br.s     loc_17C46
0x17c31  ldnull
0x17c32  newobj   instance void Microsoft.Crm.Tools.Admin.MultipleTenancyFalse::.ctor(string organizationName)
0x17c37  ret
0x17c38  ldloc.0
0x17c39  ldc.i4.0
0x17c3a  ldelem.ref
0x17c3b  callvirt instance string [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.OrganizationData::get_UniqueName()
0x17c40  newobj   instance void Microsoft.Crm.Tools.Admin.MultipleTenancyFalse::.ctor(string organizationName)
0x17c45  ret
0x17c46  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17c4b  ldstr    aLicenseTypeTha// "License type that is installed does not"...
0x17c50  ldc.i4.1
0x17c51  newarr   [mscorlib]System.Object
0x17c56  dup
0x17c57  ldc.i4.0
0x17c58  ldloc.0
0x17c59  ldlen
0x17c5a  conv.i4
0x17c5b  box      [mscorlib]System.Int32
0x17c60  stelem.ref
0x17c61  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17c66  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x17c6b  throw
```
