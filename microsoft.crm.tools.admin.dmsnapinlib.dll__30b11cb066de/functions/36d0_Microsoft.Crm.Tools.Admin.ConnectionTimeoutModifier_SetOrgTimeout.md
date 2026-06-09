# Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::SetOrgTimeout

- ea: `0x36d0`
- end: `0x3798`
- name: `Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::SetOrgTimeout`
- size: `200`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3680`
- `0x3990`

## callees

- `0x36d0`
- `0x37a0`

## string_xrefs

- `0x36ea`: `SqlCommandTimeout`
- `0x373a`: `SqlCommandTimeout`
- `0x36f7`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Common\ConnectionTimeoutModifier.cs`
- `0x375e`: `d:\dbs\sh\dccm2\1101_190851\cmd\44\src\Tools2\DMSnapin\lib\Common\ConnectionTimeoutModifier.cs`
- `0x3778`: `Unable to update the command timeout for organization: {0} Exception {1}`

## pseudocode

```c

```

## disassembly

```asm
0x36d0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x36d5  stloc.0
0x36d6  ldloc.0
0x36d7  ldstr    aOrganization// "Organization"
0x36dc  ldarg.2
0x36dd  box      [mscorlib]System.Guid
0x36e2  ldc.i4.1
0x36e3  newarr   [mscorlib]System.String
0x36e8  dup
0x36e9  ldc.i4.0
0x36ea  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0x36ef  stelem.ref
0x36f0  ldc.i4.s 0x3C
0x36f2  ldstr    aSetorgtimeout// "SetOrgTimeout"
0x36f7  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x36fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x3701  call     int32 Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::ReadSqlCommandTimeout(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag bag)
0x3706  stloc.1
0x3707  ldarg.0
0x3708  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x370d  ldstr    aConnectionstri_0// "ConnectionStringTimeout"
0x3712  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::ContainsKey(var<u1>)
0x3717  brtrue.s loc_372F
0x3719  ldarg.0
0x371a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>> Microsoft.Crm.Tools.Admin.ConnectionTimeoutModifier::oldValues
0x371f  ldstr    aConnectionstri_0// "ConnectionStringTimeout"
0x3724  ldloc.1
0x3725  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x372a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Nullable`1<int32>>::Add(var<u1>, !!T0)
0x372f  ldloc.1
0x3730  ldarg.1
0x3731  beq.s    loc_3769
0x3733  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x3738  stloc.2
0x3739  ldloc.2
0x373a  ldstr    aSqlcommandtime// "SqlCommandTimeout"
0x373f  ldarg.1
0x3740  box      [mscorlib]System.Int32
0x3745  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x374a  ldloc.0
0x374b  ldstr    aOrganization// "Organization"
0x3750  ldarg.2
0x3751  box      [mscorlib]System.Guid
0x3756  ldloc.2
0x3757  ldc.i4.s 0x48
0x3759  ldstr    aSetorgtimeout// "SetOrgTimeout"
0x375e  ldstr    aDDbsShDccm2110_1// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\4"...
0x3763  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x3768  pop
0x3769  leave.s  loc_3775
0x376b  ldloc.0
0x376c  brfalse.s loc_3774
0x376e  ldloc.0
0x376f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3774  endfinally
0x3775  leave.s  loc_3797
0x3777  stloc.3
0x3778  ldstr    aUnableToUpdate// "Unable to update the command timeout fo"...
0x377d  ldc.i4.2
0x377e  newarr   [mscorlib]System.Object
0x3783  dup
0x3784  ldc.i4.0
0x3785  ldarg.2
0x3786  box      [mscorlib]System.Guid
0x378b  stelem.ref
0x378c  dup
0x378d  ldc.i4.1
0x378e  ldloc.3
0x378f  stelem.ref
0x3790  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteWarning(string, object[])
0x3795  leave.s  loc_3797
0x3797  ret
```
