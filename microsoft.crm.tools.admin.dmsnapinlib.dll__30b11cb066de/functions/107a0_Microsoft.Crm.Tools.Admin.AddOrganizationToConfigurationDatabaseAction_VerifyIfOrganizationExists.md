# Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::VerifyIfOrganizationExists

- ea: `0x107a0`
- end: `0x10813`
- name: `Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::VerifyIfOrganizationExists`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x105a0`

## callees

- `0x22e0`
- `0x107a0`

## string_xrefs

- `0x107bd`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Organization\DatabaseConfiguration.cs`
- `0x107e8`: `AddOrganization.Error.OrganizationAlreadyExists`

## pseudocode

```c

```

## disassembly

```asm
0x107a0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0x107a5  stloc.0
0x107a6  ldloc.0
0x107a7  ldstr    aOrganization// "Organization"
0x107ac  ldarg.1
0x107ad  box      [mscorlib]System.Guid
0x107b2  ldnull
0x107b3  ldc.i4   0xE1
0x107b8  ldstr    aVerifyiforgani_0// "VerifyIfOrganizationExists"
0x107bd  ldstr    aDDbsShDccm2110_9// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x107c2  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.DatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x107c7  stloc.1
0x107c8  ldloc.1
0x107c9  brtrue.s loc_107CF
0x107cb  ldc.i4.0
0x107cc  stloc.3
0x107cd  leave.s  loc_10811
0x107cf  ldloc.1
0x107d0  ldstr    aState// "State"
0x107d5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x107da  unbox.any [mscorlib]System.Int32
0x107df  stloc.2
0x107e0  ldc.i4.2
0x107e1  ldloc.2
0x107e2  beq.s    loc_10803
0x107e4  ldc.i4.3
0x107e5  ldloc.2
0x107e6  beq.s    loc_10803
0x107e8  ldstr    aAddorganizatio// "AddOrganization.Error.OrganizationAlrea"...
0x107ed  ldc.i4.0
0x107ee  newarr   [mscorlib]System.Object
0x107f3  call     string Microsoft.Crm.Tools.Admin.DMSnapInLibResource::GetString(string name, object[] args)
0x107f8  ldc.i4   0x8004B001
0x107fd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x10802  throw
0x10803  ldc.i4.1
0x10804  stloc.3
0x10805  leave.s  loc_10811
0x10807  ldloc.0
0x10808  brfalse.s loc_10810
0x1080a  ldloc.0
0x1080b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10810  endfinally
0x10811  ldloc.3
0x10812  ret
```
