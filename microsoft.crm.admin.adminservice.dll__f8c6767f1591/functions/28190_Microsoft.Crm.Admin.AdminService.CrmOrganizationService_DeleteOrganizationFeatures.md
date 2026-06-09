# Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationFeatures

- ea: `0x28190`
- end: `0x28202`
- name: `Microsoft.Crm.Admin.AdminService.CrmOrganizationService::DeleteOrganizationFeatures`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x25e50`

## callees

- `0x28190`

## string_xrefs

- `0x281d4`: `D:\a\1\s\src\CrmLive\Admin\Organization\CrmOrganizationService.cs`
- `0x28193`: `DeleteOrganizationFeatures`
- `0x281cf`: `DeleteOrganizationFeatures`
- `0x281e6`: `Exception in DeleteOrganizationFeatures {0}`

## pseudocode

```c

```

## disassembly

```asm
0x28190  ldarg.0
0x28191  ldc.i4.s 0x14
0x28193  ldstr    aDeleteorganiza_1// "DeleteOrganizationFeatures"
0x28198  ldc.i4.0
0x28199  newarr   [mscorlib]System.Object
0x2819e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x281a3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x281a8  stloc.0
0x281a9  ldloc.0
0x281aa  ldstr    aOrganizationid_0// "OrganizationId"
0x281af  ldarg.0
0x281b0  box      [mscorlib]System.Guid
0x281b5  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x281ba  ldarg.1
0x281bb  ldstr    aOrganizationfe_0// "OrganizationFeatureMap"
0x281c0  ldc.i4.1
0x281c1  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x281c6  dup
0x281c7  ldc.i4.0
0x281c8  ldloc.0
0x281c9  stelem.ref
0x281ca  ldc.i4   0x6C5
0x281cf  ldstr    aDeleteorganiza_1// "DeleteOrganizationFeatures"
0x281d4  ldstr    aDA1SSrcCrmlive_50// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x281d9  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::Delete(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x281de  pop
0x281df  leave.s  loc_28201
0x281e1  stloc.1
0x281e2  ldloc.1
0x281e3  ldarg.0
0x281e4  ldc.i4.s 0x14
0x281e6  ldstr    aExceptionInDel_0// "Exception in DeleteOrganizationFeatures"...
0x281eb  ldc.i4.1
0x281ec  newarr   [mscorlib]System.Object
0x281f1  dup
0x281f2  ldc.i4.0
0x281f3  ldloc.1
0x281f4  callvirt instance string [mscorlib]System.Exception::get_Message()
0x281f9  stelem.ref
0x281fa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x281ff  rethrow
0x28201  ret
```
