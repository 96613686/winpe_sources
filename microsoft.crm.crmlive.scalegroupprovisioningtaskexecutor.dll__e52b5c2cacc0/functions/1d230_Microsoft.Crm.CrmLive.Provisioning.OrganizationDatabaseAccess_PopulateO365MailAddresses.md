# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::PopulateO365MailAddresses

- ea: `0x1d230`
- end: `0x1d3df`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::PopulateO365MailAddresses`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ce60`

## callees

- `0x7130`
- `0x7180`
- `0x1d230`

## string_xrefs

- `0x1d2bc`: `DirectoryObjectId`
- `0x1d2f1`: `DirectoryObjectId`
- `0x1d304`: `DirectoryObjectId`
- `0x1d2ce`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\OrganizationDatabaseAccess.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1d230  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::.ctor()
0x1d235  stloc.0
0x1d236  ldc.i4.0
0x1d237  stloc.1
0x1d238  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x1d23d  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x1d242  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_ProcessWithGraphJustInTime()
0x1d247  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail)
0x1d24c  brfalse.s loc_1D250
0x1d24e  ldc.i4.2
0x1d24f  stloc.1
0x1d250  call     T0x2B000036
0x1d255  ldarg.0
0x1d256  ldloc.1
0x1d257  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.DataProviderType)
0x1d25c  stloc.2
0x1d25d  ldarg.1
0x1d25e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::GetEnumerator()
0x1d263  stloc.3
0x1d264  br       loc_1D3C1
0x1d269  ldloca.s 3
0x1d26b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::get_Current()
0x1d270  stloc.s  4
0x1d272  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1d277  stloc.s  5
0x1d279  ldloc.s  5
0x1d27b  ldstr    aCrmuserid// "CrmUserId"
0x1d280  ldloc.s  4
0x1d282  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::get_SystemUserId()
0x1d287  box      [mscorlib]System.Guid
0x1d28c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1d291  ldloc.s  5
0x1d293  ldstr    aOrganizationid_0// "OrganizationId"
0x1d298  ldarg.0
0x1d299  box      [mscorlib]System.Guid
0x1d29e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1d2a3  ldnull
0x1d2a4  stloc.s  6
0x1d2a6  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1d2ab  stloc.s  7
0x1d2ad  ldloc.s  7
0x1d2af  ldstr    aSystemuserorga// "SystemUserOrganizations"
0x1d2b4  ldc.i4.1
0x1d2b5  newarr   [mscorlib]System.String
0x1d2ba  dup
0x1d2bb  ldc.i4.0
0x1d2bc  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x1d2c1  stelem.ref
0x1d2c2  ldloc.s  5
0x1d2c4  ldc.i4   0x3BB
0x1d2c9  ldstr    aPopulateo365ma// "PopulateO365MailAddresses"
0x1d2ce  ldstr    aDDbsShDccm2110_31// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x1d2d3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1d2d8  stloc.s  6
0x1d2da  leave.s  loc_1D2E8
0x1d2dc  ldloc.s  7
0x1d2de  brfalse.s loc_1D2E7
0x1d2e0  ldloc.s  7
0x1d2e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d2e7  endfinally
0x1d2e8  ldloc.s  6
0x1d2ea  brfalse  loc_1D3B9
0x1d2ef  ldloc.s  6
0x1d2f1  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x1d2f6  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1d2fb  brfalse  loc_1D3B9
0x1d300  ldloc.2
0x1d301  ldarg.0
0x1d302  ldloc.s  6
0x1d304  ldstr    aDirectoryobjec_4// "DirectoryObjectId"
0x1d309  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1d30e  unbox.any [mscorlib]System.Guid
0x1d313  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::RetrieveObject(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d318  stloc.s  8
0x1d31a  ldloc.s  8
0x1d31c  brfalse  loc_1D3B9
0x1d321  ldloc.s  8
0x1d323  ldstr    aData// "Data"
0x1d328  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x1d32d  brfalse  loc_1D3B9
0x1d332  ldloc.2
0x1d333  ldloc.s  8
0x1d335  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0x1d33a  isinst   [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x1d33f  stloc.s  9
0x1d341  ldloc.s  9
0x1d343  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringSingleLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_Mail()
0x1d348  brfalse.s loc_1D37E
0x1d34a  ldloc.s  9
0x1d34c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringSingleLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_Mail()
0x1d351  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d356  brfalse.s loc_1D37E
0x1d358  ldloc.s  9
0x1d35a  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringSingleLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_Mail()
0x1d35f  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d364  ldlen
0x1d365  brfalse.s loc_1D37E
0x1d367  ldloc.s  4
0x1d369  ldloc.s  9
0x1d36b  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringSingleLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_Mail()
0x1d370  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d375  ldc.i4.0
0x1d376  ldelem.ref
0x1d377  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_EmailAddress(string value)
0x1d37c  br.s     loc_1D3B9
0x1d37e  ldloc.s  9
0x1d380  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_OtherMail()
0x1d385  brfalse.s loc_1D3B9
0x1d387  ldloc.s  9
0x1d389  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_OtherMail()
0x1d38e  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d393  brfalse.s loc_1D3B9
0x1d395  ldloc.s  9
0x1d397  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_OtherMail()
0x1d39c  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d3a1  ldlen
0x1d3a2  brfalse.s loc_1D3B9
0x1d3a4  ldloc.s  4
0x1d3a6  ldloc.s  9
0x1d3a8  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyStringLength1To256 [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_OtherMail()
0x1d3ad  callvirt instance string[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyString::get_Value()
0x1d3b2  ldc.i4.0
0x1d3b3  ldelem.ref
0x1d3b4  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo::set_EmailAddress(string value)
0x1d3b9  ldloc.0
0x1d3ba  ldloc.s  4
0x1d3bc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::Add(var<u1>)
0x1d3c1  ldloca.s 3
0x1d3c3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>::MoveNext()
0x1d3c8  brtrue   loc_1D269
0x1d3cd  leave.s  loc_1D3DD
0x1d3cf  ldloca.s 3
0x1d3d1  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.CrmLive.Provisioning.UserEmailInfo>
0x1d3d7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d3dc  endfinally
0x1d3dd  ldloc.0
0x1d3de  ret
```
