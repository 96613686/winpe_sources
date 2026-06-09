# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::UpdateUserPurchaseCount

- ea: `0x131c0`
- end: `0x132e3`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::UpdateUserPurchaseCount`
- size: `291`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x12a20`

## callees

- `0x131c0`
- `0x19fc0`

## string_xrefs

- `0x1320f`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x132cb`: `D:\a\1\s\src\CrmLive\Admin\Subscription\ServiceInstanceService.cs`
- `0x1320a`: `UpdateUserPurchaseCount`
- `0x132c6`: `UpdateUserPurchaseCount`

## pseudocode

```c

```

## disassembly

```asm
0x131c0  ldarg.2
0x131c1  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmDatacenterService::get_OnlinePubServiceComponentId()
0x131c6  stloc.0
0x131c7  ldloca.s 0
0x131c9  constrained. [mscorlib]System.Guid
0x131cf  callvirt instance string [mscorlib]System.Object::ToString()
0x131d4  ldc.i4.5
0x131d5  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x131da  brtrue.s loc_131DD
0x131dc  ret
0x131dd  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x131e2  stloc.1
0x131e3  ldloc.1
0x131e4  ldstr    aOrganization// "Organization"
0x131e9  ldarg.3
0x131ea  box      [mscorlib]System.Guid
0x131ef  ldc.i4.2
0x131f0  newarr   [mscorlib]System.String
0x131f5  dup
0x131f6  ldc.i4.0
0x131f7  ldstr    aOfferconversio// "OfferConversionInProgress"
0x131fc  stelem.ref
0x131fd  dup
0x131fe  ldc.i4.1
0x131ff  ldstr    aUserlicensespu// "UserLicensesPurchased"
0x13204  stelem.ref
0x13205  ldc.i4   0x1B8
0x1320a  ldstr    aUpdateuserpurc// "UpdateUserPurchaseCount"
0x1320f  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x13214  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveById(string, object, string[], int32, string, string)
0x13219  stloc.2
0x1321a  ldc.i4.0
0x1321b  stloc.3
0x1321c  ldc.i4.0
0x1321d  stloc.s  4
0x1321f  ldloc.2
0x13220  ldstr    aOfferconversio// "OfferConversionInProgress"
0x13225  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1322a  brfalse.s loc_1323D
0x1322c  ldloc.2
0x1322d  ldstr    aOfferconversio// "OfferConversionInProgress"
0x13232  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13237  unbox.any [mscorlib]System.Boolean
0x1323c  stloc.3
0x1323d  ldloc.2
0x1323e  ldstr    aUserlicensespu// "UserLicensesPurchased"
0x13243  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13248  brfalse.s loc_1325C
0x1324a  ldloc.2
0x1324b  ldstr    aUserlicensespu// "UserLicensesPurchased"
0x13250  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x13255  unbox.any [mscorlib]System.Int32
0x1325a  stloc.s  4
0x1325c  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x13261  ldstr    aDefaultsku// "DefaultSku"
0x13266  ldc.i4.0
0x13267  callvirt T0x2B000001
0x1326c  stloc.s  5
0x1326e  ldloc.s  5
0x13270  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13275  brfalse.s loc_1327E
0x13277  ldstr    aCrmotrial// "crmoTrial"
0x1327c  stloc.s  5
0x1327e  ldarg.0
0x1327f  ldc.i4.0
0x13280  bge.s    loc_132D6
0x13282  ldloc.3
0x13283  brtrue.s loc_132D6
0x13285  ldloc.s  4
0x13287  ldarg.0
0x13288  add
0x13289  ldarg.1
0x1328a  bne.un.s loc_132D6
0x1328c  ldarg.s  4
0x1328e  ldloc.s  5
0x13290  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x13295  brfalse.s loc_132D6
0x13297  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1329c  stloc.s  6
0x1329e  ldloc.s  6
0x132a0  ldstr    aUserlicensespu// "UserLicensesPurchased"
0x132a5  ldloc.s  4
0x132a7  ldarg.0
0x132a8  add
0x132a9  box      [mscorlib]System.Int32
0x132ae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x132b3  ldloc.1
0x132b4  ldstr    aOrganization// "Organization"
0x132b9  ldarg.3
0x132ba  box      [mscorlib]System.Guid
0x132bf  ldloc.s  6
0x132c1  ldc.i4   0x1D3
0x132c6  ldstr    aUpdateuserpurc// "UpdateUserPurchaseCount"
0x132cb  ldstr    aDA1SSrcCrmlive_25// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Subsc"...
0x132d0  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x132d5  pop
0x132d6  leave.s  loc_132E2
0x132d8  ldloc.1
0x132d9  brfalse.s loc_132E1
0x132db  ldloc.1
0x132dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x132e1  endfinally
0x132e2  ret
```
