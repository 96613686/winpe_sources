# Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::AnalyzeUser

- ea: `0x10290`
- end: `0x105c6`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::AnalyzeUser`
- size: `822`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x10130`

## callees

- `0xff20`
- `0xff30`
- `0xff40`
- `0xff50`
- `0xff60`
- `0xff70`
- `0xff80`
- `0xff90`
- `0xffa0`
- `0xffb0`
- `0xffc0`
- `0xffe0`
- `0x10000`
- `0x10020`
- `0x10060`
- `0x10070`
- `0x10080`
- `0x100a0`
- `0x100c0`
- `0x100e0`
- `0x10110`
- `0x10290`
- `0x10660`
- `0x106c0`
- `0x10700`
- `0x107c0`
- `0x10850`
- `0x10900`
- `0x1a410`
- `0x30ea0`

## string_xrefs

- `0x10318`: `Missing user object in directory object`
- `0x10516`: `User is not member of security group.`

## pseudocode

```c

```

## disassembly

```asm
0x10290  newobj   instance void <>c__DisplayClass2_0::.ctor()
0x10295  stloc.0
0x10296  ldloc.0
0x10297  ldarg.3
0x10298  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x1029d  ldloc.0
0x1029e  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::.ctor()
0x102a3  stfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x102a8  ldloc.0
0x102a9  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x102ae  ldarg.0
0x102af  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_OrganizationId(valuetype [mscorlib]System.Guid value)
0x102b4  ldloc.0
0x102b5  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x102ba  ldarg.2
0x102bb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_GroupId()
0x102c0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_GroupId(valuetype [mscorlib]System.Guid value)
0x102c5  ldloc.0
0x102c6  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x102cb  ldarg.2
0x102cc  callvirt instance string [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_MappedUser()
0x102d1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_MappedUser(string value)
0x102d6  ldloc.0
0x102d7  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x102dc  brtrue.s loc_102F1
0x102de  ldloc.0
0x102df  call     T0x2B000036
0x102e4  ldarg.0
0x102e5  ldarg.s  5
0x102e7  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProviderFactory::GetProvider(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.DataProviderType)
0x102ec  stfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x102f1  ldloc.0
0x102f2  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x102f7  ldloc.0
0x102f8  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x102fd  ldarg.1
0x102fe  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryObject [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::ConvertToDirectoryObject(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0x10303  isinst   [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User
0x10308  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_User(class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User value)
0x1030d  ldloc.0
0x1030e  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10313  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x10318  ldstr    aMissingUserObj// "Missing user object in directory object"
0x1031d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x10322  ldloc.0
0x10323  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10328  ldarg.1
0x10329  ldstr    aObjectid_1// "ObjectId"
0x1032e  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x10333  unbox.any [mscorlib]System.Guid
0x10338  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_DirectoryObjectId(valuetype [mscorlib]System.Guid value)
0x1033d  ldloc.0
0x1033e  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10343  ldloc.0
0x10344  ldftn    instance bool <>c__DisplayClass2_0::<AnalyzeUser>b__0()
0x1034a  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1034f  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x10354  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_IsTenantAdmin(class [mscorlib]System.Lazy`1<bool> value)
0x10359  ldloc.0
0x1035a  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1035f  ldloc.0
0x10360  ldftn    instance bool <>c__DisplayClass2_0::<AnalyzeUser>b__1()
0x10366  newobj   instance void class [mscorlib]System.Func`1<bool>::.ctor(object, native int)
0x1036b  newobj   instance void class [mscorlib]System.Lazy`1<bool>::.ctor(class [mscorlib]System.Func`1<var<u1>>)
0x10370  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_IsCrmServiceAdmin(class [mscorlib]System.Lazy`1<bool> value)
0x10375  ldloc.0
0x10376  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1037b  ldloc.0
0x1037c  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x10381  ldloc.0
0x10382  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10387  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x1038c  ldarg.0
0x1038d  ldarg.s  4
0x1038f  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::IsUserLicensedInOsdp(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user, valuetype [mscorlib]System.Guid organizationId, bool ignoreLicenseChecks)
0x10394  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_IsLicensed(bool value)
0x10399  ldloc.0
0x1039a  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1039f  ldarg.0
0x103a0  ldloc.0
0x103a1  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x103a6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x103ab  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::GetCrmUserId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId)
0x103b0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_CrmUserId(valuetype [mscorlib]System.Guid value)
0x103b5  ldloc.0
0x103b6  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x103bb  ldloca.s 1
0x103bd  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>
0x103c3  ldloc.1
0x103c4  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_AdminState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState> value)
0x103c9  ldloc.0
0x103ca  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x103cf  ldc.i4.0
0x103d0  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_PublishRequired(bool value)
0x103d5  ldloc.0
0x103d6  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x103db  ldloc.0
0x103dc  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x103e1  ldloc.0
0x103e2  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x103e7  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_User()
0x103ec  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::IsUserSoftDeleted(class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider directoryProvider, class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User user)
0x103f1  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_IsSoftDelete(bool value)
0x103f6  ldarg.2
0x103f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUser::get_GroupId()
0x103fc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x10401  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10406  brfalse.s loc_1043A
0x10408  ldloc.0
0x10409  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1040e  ldloc.0
0x1040f  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x10414  ldarg.0
0x10415  ldloc.0
0x10416  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1041b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_GroupId()
0x10420  ldloc.0
0x10421  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10426  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1042b  callvirt instance valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::IsMember(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x10430  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::.ctor(var<u1>)
0x10435  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_AdminState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState> value)
0x1043a  ldarg.s  5
0x1043c  ldc.i4.2
0x1043d  bne.un.s loc_10474
0x1043f  ldloc.0
0x10440  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10445  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x1044a  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x1044f  brtrue.s loc_10463
0x10451  ldloc.0
0x10452  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10457  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsCrmServiceAdmin()
0x1045c  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x10461  brfalse.s loc_10474
0x10463  ldloc.0
0x10464  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10469  ldc.i4.0
0x1046a  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::.ctor(var<u1>)
0x1046f  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_AdminState(valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState> value)
0x10474  ldloc.0
0x10475  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1047a  callvirt instance class [mscorlib]System.Lazy`1<bool> Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_IsTenantAdmin()
0x1047f  callvirt instance var<u1> class [mscorlib]System.Lazy`1<bool>::get_Value()
0x10484  brfalse.s loc_10497
0x10486  ldloc.0
0x10487  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1048c  ldc.i4.1
0x1048d  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x10492  br       loc_10520
0x10497  ldloca.s 2
0x10499  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>
0x1049f  ldarg.0
0x104a0  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.Organization::GetOrganizationSecurityGroup(valuetype [mscorlib]System.Guid organizationId)
0x104a5  stloc.3
0x104a6  ldloc.3
0x104a7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x104ac  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x104b1  brfalse.s loc_104D2
0x104b3  ldloca.s 2
0x104b5  ldloc.0
0x104b6  ldfld    class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider <>c__DisplayClass2_0::directoryProvider
0x104bb  ldarg.0
0x104bc  ldloc.3
0x104bd  ldloc.0
0x104be  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x104c3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x104c8  callvirt instance valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.IMainDirectoryDataProvider::IsMember(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x104cd  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::.ctor(var<u1>)
0x104d2  ldloc.0
0x104d3  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x104d8  ldloca.s 2
0x104da  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::get_HasValue()
0x104df  brfalse.s loc_104FD
0x104e1  ldloc.2
0x104e2  stloc.1
0x104e3  ldc.i4.0
0x104e4  stloc.s  4
0x104e6  ldloca.s 1
0x104e8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::GetValueOrDefault()
0x104ed  ldloc.s  4
0x104ef  beq.s    loc_104F4
0x104f1  ldc.i4.0
0x104f2  br.s     loc_104FE
0x104f4  ldloca.s 1
0x104f6  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.SyncApi.MemberGroupState>::get_HasValue()
0x104fb  br.s     loc_104FE
0x104fd  ldc.i4.1
0x104fe  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x10503  ldloc.0
0x10504  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10509  callvirt instance bool Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_ShouldSync()
0x1050e  brtrue.s loc_10520
0x10510  ldloc.0
0x10511  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10516  ldstr    aUserIsNotMembe// "User is not member of security group."
0x1051b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_SkippedUserSyncDetail(string value)
0x10520  ldarg.0
0x10521  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.OrganizationType [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CrmOrganizationService::GetOrganizationType(valuetype [mscorlib]System.Guid)
0x10526  dup
0x10527  ldc.i4.s 0xB
0x10529  bne.un.s loc_1057E
0x1052b  ldarg.0
0x1052c  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::IsOrgExemptFromApproval(valuetype [mscorlib]System.Guid organizationId)
0x10531  brfalse.s loc_10541
0x10533  ldloc.0
0x10534  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10539  ldc.i4.1
0x1053a  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x1053f  br.s     loc_1057E
0x10541  ldloc.0
0x10542  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10547  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1054c  ldarg.0
0x1054d  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::IsUserEmailTrialApproved(valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid organizationId)
0x10552  brfalse.s loc_10562
0x10554  ldloc.0
0x10555  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1055a  ldc.i4.1
0x1055b  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x10560  br.s     loc_1057E
0x10562  ldloc.0
0x10563  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10568  ldc.i4.0
0x10569  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x1056e  ldloc.0
0x1056f  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10574  ldstr    aEmailtrialinst// "EmailTrialInstanceType: User is neither"...
0x10579  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_SkippedUserSyncDetail(string value)
0x1057e  ldc.i4.s 0xD
0x10580  bne.un.s loc_105BF
0x10582  ldloc.0
0x10583  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x10588  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::get_DirectoryObjectId()
0x1058d  ldarg.0
0x1058e  call     bool Microsoft.Crm.CrmLive.Provisioning.SyncUserAction::IsUserInitialUser(valuetype [mscorlib]System.Guid userObjectId, valuetype [mscorlib]System.Guid organizationId)
0x10593  brfalse.s loc_105A3
0x10595  ldloc.0
0x10596  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x1059b  ldc.i4.1
0x1059c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x105a1  br.s     loc_105BF
0x105a3  ldloc.0
0x105a4  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x105a9  ldc.i4.0
0x105aa  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_ShouldSync(bool value)
0x105af  ldloc.0
0x105b0  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x105b5  ldstr    aDeveloperinsta// "DeveloperInstanceType: User is not the "...
0x105ba  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SyncUserDto::set_SkippedUserSyncDetail(string value)
0x105bf  ldloc.0
0x105c0  ldfld    class Microsoft.Crm.CrmLive.Provisioning.SyncUserDto <>c__DisplayClass2_0::dto
0x105c5  ret
```
