# <>c__DisplayClass39_0::<CreateInternal>b__0

- ea: `0x23ab50`
- end: `0x23b104`
- name: `<>c__DisplayClass39_0::<CreateInternal>b__0`
- size: `1460`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0xceeb0`
- `0xde0a0`
- `0xe1960`
- `0xe1e70`
- `0x1f4780`
- `0x23ab50`

## string_xrefs

- `0x23ac68`: `accessmode`
- `0x23ac7b`: `accessmode`
- `0x23ac99`: `accessmode`
- `0x23acc9`: `accessmode`
- `0x23afbe`: `accessmode`
- `0x23afd1`: `accessmode`
- `0x23afe9`: `accessmode`
- `0x23b0bd`: `accessmode`
- `0x23b0c8`: `accessmode`
- `0x23af11`: `NewUserCreate`
- `0x23ade4`: `issyncwithdirectory`
- `0x23adf6`: `issyncwithdirectory`
- `0x23acdf`: `Unable to validate user count because accessmode is not set.`

## pseudocode

```c

```

## disassembly

```asm
0x23ab50  ldarg.0
0x23ab51  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ab56  ldstr    aDomainname// "domainname"
0x23ab5b  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23ab60  brtrue.s loc_23AB79
0x23ab62  ldarg.0
0x23ab63  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ab68  ldstr    aDomainname// "domainname"
0x23ab6d  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ab72  castclass [mscorlib]System.String
0x23ab77  br.s     loc_23AB7E
0x23ab79  ldstr    aNull_0// "NULL"
0x23ab7e  stloc.0
0x23ab7f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x23ab84  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x23ab89  ldc.i4.2
0x23ab8a  bne.un.s loc_23ABF2
0x23ab8c  ldarg.0
0x23ab8d  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ab92  ldstr    aDomainname// "domainname"
0x23ab97  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23ab9c  brtrue.s loc_23ABBC
0x23ab9e  ldarg.0
0x23ab9f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23aba4  ldstr    aDomainname// "domainname"
0x23aba9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23abae  castclass [mscorlib]System.String
0x23abb3  ldloca.s 8
0x23abb5  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x23abba  brfalse.s loc_23ABF2
0x23abbc  ldarg.0
0x23abbd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23abc2  ldstr    aDomainname// "domainname"
0x23abc7  ldarg.0
0x23abc8  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23abcd  ldstr    aInternalemaila// "internalemailaddress"
0x23abd2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23abd7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x23abdc  ldarg.0
0x23abdd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23abe2  ldstr    aInternalemaila// "internalemailaddress"
0x23abe7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23abec  castclass [mscorlib]System.String
0x23abf1  stloc.0
0x23abf2  ldarg.0
0x23abf3  ldfld    valuetype [mscorlib]System.Guid class <>c__DisplayClass39_0<var<u1>>::organizationId
0x23abf8  ldstr    aOrganizationid_0// "organizationId"
0x23abfd  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x23ac02  ldarg.0
0x23ac03  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac08  ldstr    aBusinessunitid// "businessunitid"
0x23ac0d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23ac12  brfalse.s loc_23AC25
0x23ac14  ldc.i4   0x8004021A
0x23ac19  ldc.i4.0
0x23ac1a  newarr   [mscorlib]System.Object
0x23ac1f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23ac24  throw
0x23ac25  ldarg.0
0x23ac26  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ac2b  ldarg.0
0x23ac2c  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac31  ldstr    aBusinessunitid// "businessunitid"
0x23ac36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ac3b  unbox.any [mscorlib]System.Guid
0x23ac40  ldarg.0
0x23ac41  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ac46  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::ValidateBusinessUnit(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ac4b  ldarg.0
0x23ac4c  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ac51  ldarg.0
0x23ac52  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac57  ldarg.0
0x23ac58  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ac5d  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CreateAccessMode(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ac62  ldarg.0
0x23ac63  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac68  ldstr    aAccessmode// "accessmode"
0x23ac6d  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23ac72  brtrue.s loc_23AC8E
0x23ac74  ldc.i4.1
0x23ac75  ldarg.0
0x23ac76  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac7b  ldstr    aAccessmode// "accessmode"
0x23ac80  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ac85  unbox.any [mscorlib]System.Int32
0x23ac8a  ceq
0x23ac8c  br.s     loc_23AC8F
0x23ac8e  ldc.i4.0
0x23ac8f  stloc.1
0x23ac90  ldloc.1
0x23ac91  brtrue.s loc_23ACEF
0x23ac93  ldarg.0
0x23ac94  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ac99  ldstr    aAccessmode// "accessmode"
0x23ac9e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23aca3  brtrue.s loc_23ACDF
0x23aca5  ldarg.0
0x23aca6  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23acab  ldstr    aApplicationid// "applicationid"
0x23acb0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23acb5  brfalse.s loc_23ACEF
0x23acb7  ldarg.0
0x23acb8  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23acbd  ldarg.0
0x23acbe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23acc3  ldarg.0
0x23acc4  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23acc9  ldstr    aAccessmode// "accessmode"
0x23acce  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23acd3  unbox.any [mscorlib]System.Int32
0x23acd8  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::ValidateUsersCountForUserAdd(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, int32)
0x23acdd  br.s     loc_23ACEF
0x23acdf  ldstr    aUnableToValida// "Unable to validate user count because a"...
0x23ace4  ldc.i4   0x80040216
0x23ace9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x23acee  throw
0x23acef  ldarg.0
0x23acf0  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23acf5  ldstr    aIsdisabled// "isdisabled"
0x23acfa  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23acff  brfalse.s loc_23AD17
0x23ad01  ldarg.0
0x23ad02  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad07  ldstr    aIsdisabled// "isdisabled"
0x23ad0c  ldc.i4.0
0x23ad0d  box      [mscorlib]System.Boolean
0x23ad12  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x23ad17  ldarg.0
0x23ad18  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ad1d  ldarg.0
0x23ad1e  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad23  ldarg.0
0x23ad24  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ad29  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::AddDefaultEmailSettings(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ad2e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::.ctor()
0x23ad33  stloc.2
0x23ad34  ldloc.2
0x23ad35  ldarg.0
0x23ad36  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad3b  ldloc.1
0x23ad3c  ldarg.0
0x23ad3d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ad42  callvirt instance class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::CreateUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, bool, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ad47  stloc.3
0x23ad48  ldloc.3
0x23ad49  ldstr    aUserinformatio// "userInformation"
0x23ad4e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x23ad53  ldarg.0
0x23ad54  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad59  ldstr    aBusinessunitid// "businessunitid"
0x23ad5e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ad63  unbox.any [mscorlib]System.Guid
0x23ad68  stloc.s  4
0x23ad6a  ldarg.0
0x23ad6b  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad70  ldstr    aParentsystemus// "parentsystemuserid"
0x23ad75  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23ad7a  brtrue.s loc_23ADA4
0x23ad7c  ldarg.0
0x23ad7d  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ad82  ldloc.s  4
0x23ad84  ldarg.0
0x23ad85  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ad8a  ldstr    aParentsystemus// "parentsystemuserid"
0x23ad8f  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ad94  unbox.any [mscorlib]System.Guid
0x23ad99  ldarg.0
0x23ad9a  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ad9f  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::ValidateParentUser(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ada4  ldarg.0
0x23ada5  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23adaa  ldstr    aMobileofflinep// "mobileofflineprofileid"
0x23adaf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23adb4  brtrue.s loc_23ADC7
0x23adb6  ldc.i4   0x800609A6
0x23adbb  ldc.i4.0
0x23adbc  newarr   [mscorlib]System.Object
0x23adc1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x23adc6  throw
0x23adc7  ldarg.0
0x23adc8  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23adcd  ldarg.0
0x23adce  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23add3  ldarg.0
0x23add4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23add9  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CheckAssignTerritoryToUserPrivilege(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23adde  ldarg.0
0x23addf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ade4  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x23ade9  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23adee  brtrue.s loc_23AE2D
0x23adf0  ldarg.0
0x23adf1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23adf6  ldstr    aIssyncwithdire// "issyncwithdirectory"
0x23adfb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ae00  unbox.any [mscorlib]System.Boolean
0x23ae05  brfalse.s loc_23AE2D
0x23ae07  ldarg.0
0x23ae08  ldarg.0
0x23ae09  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ae0e  ldarg.0
0x23ae0f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ae14  ldloc.3
0x23ae15  ldloc.2
0x23ae16  ldarg.0
0x23ae17  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ae1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x23ae21  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::HandleSyncUser(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory, valuetype [mscorlib]System.Guid)
0x23ae26  stfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ae2b  br.s     loc_23AE45
0x23ae2d  ldloc.2
0x23ae2e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23ae33  ldloc.3
0x23ae34  ldarg.0
0x23ae35  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23ae3a  ldarg.0
0x23ae3b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23ae40  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Authentication.UserManagementFactory::CheckUserDoesNotExist(valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserAuthenticationInformation, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23ae45  ldarg.0
0x23ae46  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ae4b  ldstr    aSystemuserid// "systemuserid"
0x23ae50  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23ae55  stloc.s  6
0x23ae57  ldloc.s  6
0x23ae59  brfalse.s loc_23AE6E
0x23ae5b  ldloc.s  6
0x23ae5d  unbox.any [mscorlib]System.Guid
0x23ae62  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x23ae67  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x23ae6c  brfalse.s loc_23AE8E
0x23ae6e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x23ae73  stloc.s  5
0x23ae75  ldarg.0
0x23ae76  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ae7b  ldstr    aSystemuserid// "systemuserid"
0x23ae80  ldloc.s  5
0x23ae82  box      [mscorlib]System.Guid
0x23ae87  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x23ae8c  br.s     loc_23AE97
0x23ae8e  ldloc.s  6
0x23ae90  unbox.any [mscorlib]System.Guid
0x23ae95  stloc.s  5
0x23ae97  ldarg.0
0x23ae98  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23ae9d  ldstr    aCalendarid// "calendarid"
0x23aea2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x23aea7  brtrue.s loc_23AED0
0x23aea9  newobj   instance void Microsoft.Crm.ObjectModel.CalendarService::.ctor()
0x23aeae  ldarg.0
0x23aeaf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23aeb4  ldstr    aCalendarid// "calendarid"
0x23aeb9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x23aebe  unbox.any [mscorlib]System.Guid
0x23aec3  ldarg.0
0x23aec4  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23aec9  callvirt instance void Microsoft.Crm.ObjectModel.CalendarService::ThrowExceptionIfCalendarTypeIsCustomerServiceOrHolidaySchedule(valuetype [mscorlib]System.Guid calendarId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x23aece  br.s     loc_23AEEF
0x23aed0  ldarg.0
0x23aed1  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23aed6  ldarg.0
0x23aed7  ldfld    valuetype [mscorlib]System.Guid class <>c__DisplayClass39_0<var<u1>>::organizationId
0x23aedc  ldloc.s  5
0x23aede  ldarg.0
0x23aedf  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23aee4  ldarg.0
0x23aee5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23aeea  call     instance void class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::CreateDefaultCalendarIfNotSpecified(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23aeef  ldarg.0
0x23aef0  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23aef5  ldarg.0
0x23aef6  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23aefb  newobj   instance void class Microsoft.Crm.ObjectModel.SystemUserServiceUpnHandler`1<var<u1>>::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>)
0x23af00  ldarg.0
0x23af01  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23af06  callvirt instance void class Microsoft.Crm.ObjectModel.SystemUserServiceUpnHandler`1<var<u1>>::PreCreate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x23af0b  ldarg.0
0x23af0c  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23af11  ldstr    aNewusercreate// "NewUserCreate"
0x23af16  ldc.i4.1
0x23af17  box      [mscorlib]System.Boolean
0x23af1c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SetVariableInContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, string, object)
0x23af21  stloc.s  9
0x23af23  ldarg.0
0x23af24  ldfld    class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>> class <>c__DisplayClass39_0<var<u1>>::<>4__this
0x23af29  ldarg.0
0x23af2a  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity class <>c__DisplayClass39_0<var<u1>>::systemuser
0x23af2f  ldarg.0
0x23af30  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext class <>c__DisplayClass39_0<var<u1>>::context
0x23af35  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker class Microsoft.Crm.ObjectModel.SystemUserServiceInternal`1<var<u1>>::<>n__1(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x23af3a  stloc.s  7
0x23af3c  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::.ctor()
0x23af41  dup
0x23af42  ldloc.s  5
0x23af44  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::set_PrincipalId(valuetype [mscorlib]System.Guid)
0x23af49  dup
0x23af4a  ldc.i4.8
0x23af4b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityPrincipal::set_Type(int32)
0x23af50  ldloc.s  7
0x23af52  ldarg.0
  ... truncated ...
```
