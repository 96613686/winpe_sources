# Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::RetrieveUniqueFriendlyNameForContext

- ea: `0xc3a0`
- end: `0xc46b`
- name: `Microsoft.Crm.CrmLive.Provisioning.OsdpCompanyHandler::RetrieveUniqueFriendlyNameForContext`
- size: `203`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0xc130`

## callees

- `0xc3a0`
- `0x306c0`

## string_xrefs

- `0xc3f4`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\CompanyHandler\OsdpCompanyHandler.cs`

## pseudocode

```c

```

## disassembly

```asm
0xc3a0  newobj   instance void <>c__DisplayClass9_0::.ctor()
0xc3a5  stloc.0
0xc3a6  ldloc.0
0xc3a7  ldarg.1
0xc3a8  stfld    string <>c__DisplayClass9_0::newFriendlyName
0xc3ad  ldc.i4.1
0xc3ae  stloc.1
0xc3af  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xc3b4  stloc.2
0xc3b5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xc3ba  stloc.3
0xc3bb  ldloc.3
0xc3bc  ldstr    aContextid// "ContextId"
0xc3c1  ldarg.0
0xc3c2  box      [mscorlib]System.Guid
0xc3c7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xc3cc  ldloc.2
0xc3cd  ldstr    aOrganizationli// "OrganizationLifecycle"
0xc3d2  ldc.i4.1
0xc3d3  newarr   [mscorlib]System.String
0xc3d8  dup
0xc3d9  ldc.i4.0
0xc3da  ldstr    aOrganizationfr// "OrganizationFriendlyName"
0xc3df  stelem.ref
0xc3e0  ldc.i4.1
0xc3e1  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xc3e6  dup
0xc3e7  ldc.i4.0
0xc3e8  ldloc.3
0xc3e9  stelem.ref
0xc3ea  ldc.i4   0x135
0xc3ef  ldstr    aRetrieveunique// "RetrieveUniqueFriendlyNameForContext"
0xc3f4  ldstr    aDDbsShDccm2110_13// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xc3f9  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xc3fe  stloc.s  4
0xc400  ldloc.s  4
0xc402  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0xc407  brtrue.s loc_C458
0xc409  ldloc.s  4
0xc40b  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0xc410  ldloc.0
0xc411  ldfld    class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c__DisplayClass9_0::<>9__0
0xc416  dup
0xc417  brtrue.s loc_C431
0xc419  pop
0xc41a  ldloc.0
0xc41b  ldloc.0
0xc41c  ldftn    instance bool <>c__DisplayClass9_0::<RetrieveUniqueFriendlyNameForContext>b__0(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag x)
0xc422  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool>::.ctor(object, native int)
0xc427  dup
0xc428  stloc.s  5
0xc42a  stfld    class [mscorlib]System.Func`2<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, bool> <>c__DisplayClass9_0::<>9__0
0xc42f  ldloc.s  5
0xc431  call     T0x2B00003D
0xc436  brtrue.s loc_C43A
0xc438  leave.s  loc_C464
0xc43a  ldloc.0
0xc43b  ldarg.1
0xc43c  ldloca.s 1
0xc43e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xc443  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xc448  call     string [mscorlib]System.String::Concat(string, string)
0xc44d  stfld    string <>c__DisplayClass9_0::newFriendlyName
0xc452  ldloc.1
0xc453  ldc.i4.1
0xc454  add
0xc455  stloc.1
0xc456  br.s     loc_C409
0xc458  leave.s  loc_C464
0xc45a  ldloc.2
0xc45b  brfalse.s loc_C463
0xc45d  ldloc.2
0xc45e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc463  endfinally
0xc464  ldloc.0
0xc465  ldfld    string <>c__DisplayClass9_0::newFriendlyName
0xc46a  ret
```
