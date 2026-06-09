# Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::HandleUserLicenseAndCalType

- ea: `0xcd40`
- end: `0xcff0`
- name: `Microsoft.Crm.CrmLive.Provisioning.DirectoryObjectUtility::HandleUserLicenseAndCalType`
- size: `688`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xc940`

## callees

- `0xcd40`
- `0x30890`

## string_xrefs

- `0xcee1`: `accessmode`
- `0xceee`: `accessmode`
- `0xcf01`: `accessmode`
- `0xcf2c`: `accessmode`
- `0xcf3f`: `accessmode`
- `0xcf8a`: `accessmode`
- `0xcf9c`: `accessmode`
- `0xcfbf`: `accessmode`
- `0xcfcc`: `accessmode`
- `0xcfdf`: `accessmode`

## pseudocode

```c

```

## disassembly

```asm
0xcd40  ldarg.1
0xcd41  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AssignedPlan()
0xcd46  brfalse  loc_CF61
0xcd4b  ldarg.1
0xcd4c  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AssignedPlan()
0xcd51  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan::get_Value()
0xcd56  brfalse  loc_CF61
0xcd5b  ldc.i4.0
0xcd5c  stloc.0
0xcd5d  ldarg.0
0xcd5e  ldstr    aUserlicensetyp// "userlicensetype"
0xcd63  ldc.i4.m1
0xcd64  box      [mscorlib]System.Int32
0xcd69  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcd6e  ldarg.0
0xcd6f  ldstr    aCaltype// "caltype"
0xcd74  ldc.i4.0
0xcd75  box      [mscorlib]System.Int32
0xcd7a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcd7f  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xcd84  ldstr    aEmailtrialcapa// "EmailTrialCapability"
0xcd89  ldc.i4.1
0xcd8a  callvirt T0x2B000011
0xcd8f  stloc.1
0xcd90  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xcd95  ldstr    aDevelopercapab// "DeveloperCapability"
0xcd9a  ldc.i4.1
0xcd9b  callvirt T0x2B000011
0xcda0  stloc.2
0xcda1  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0xcda6  ldstr    aMarketingcapab// "MarketingCapability"
0xcdab  ldc.i4.1
0xcdac  callvirt T0x2B000011
0xcdb1  stloc.3
0xcdb2  ldstr    a012// "{0},{1},{2}"
0xcdb7  ldloc.1
0xcdb8  ldloc.2
0xcdb9  ldloc.3
0xcdba  call     string [mscorlib]System.String::Format(string, object, object, object)
0xcdbf  stloc.s  4
0xcdc1  ldarg.1
0xcdc2  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.User::get_AssignedPlan()
0xcdc7  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan[] [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.DirectoryPropertyXmlAssignedPlan::get_Value()
0xcdcc  stloc.s  5
0xcdce  ldc.i4.0
0xcdcf  stloc.s  6
0xcdd1  br       loc_CF55
0xcdd6  ldloc.s  5
0xcdd8  ldloc.s  6
0xcdda  ldelem.ref
0xcddb  stloc.s  7
0xcddd  newobj   instance void <>c__DisplayClass11_0::.ctor()
0xcde2  stloc.s  8
0xcde4  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserLicenseService::.ctor()
0xcde9  ldloc.s  7
0xcdeb  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xcdf0  callvirt instance class [System.Xml]System.Xml.XmlElement [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_Capability()
0xcdf5  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xcdfa  ldstr    aPlan// "Plan"
0xcdff  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xce04  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xce09  callvirt instance class [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserLicense [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserLicenseService::RetrieveByCapability(string)
0xce0e  stloc.s  9
0xce10  ldloc.s  9
0xce12  brfalse.s loc_CE61
0xce14  ldloc.s  7
0xce16  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xce1b  callvirt instance valuetype [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedCapabilityStatus [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_CapabilityStatus()
0xce20  brfalse.s loc_CE31
0xce22  ldloc.s  7
0xce24  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xce29  callvirt instance valuetype [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedCapabilityStatus [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_CapabilityStatus()
0xce2e  ldc.i4.1
0xce2f  bne.un.s loc_CE61
0xce31  ldc.i4.1
0xce32  stloc.0
0xce33  ldarg.0
0xce34  ldstr    aUserlicensetyp// "userlicensetype"
0xce39  ldloc.s  9
0xce3b  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserLicense::get_OrgUserLicenseType()
0xce40  box      [mscorlib]System.Int32
0xce45  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xce4a  ldarg.0
0xce4b  ldstr    aCaltype// "caltype"
0xce50  ldloc.s  9
0xce52  callvirt instance int32 [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.UserLicense::get_EffectiveOrgCalType()
0xce57  box      [mscorlib]System.Int32
0xce5c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xce61  ldloc.s  8
0xce63  ldloc.s  7
0xce65  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xce6a  callvirt instance class [System.Xml]System.Xml.XmlElement [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_Capability()
0xce6f  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0xce74  ldstr    aPlan// "Plan"
0xce79  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0xce7e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0xce83  stfld    string <>c__DisplayClass11_0::capabilityName
0xce88  ldloc.s  8
0xce8a  ldfld    string <>c__DisplayClass11_0::capabilityName
0xce8f  brfalse.s loc_CEE0
0xce91  ldloc.1
0xce92  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xce97  brtrue.s loc_CEE0
0xce99  ldloc.s  4
0xce9b  ldc.i4.1
0xce9c  newarr   [mscorlib]System.Char
0xcea1  dup
0xcea2  ldc.i4.0
0xcea3  ldc.i4.s 0x2C
0xcea5  stelem.i2
0xcea6  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xceab  stloc.s  0xA
0xcead  ldloc.s  7
0xceaf  brfalse.s loc_CEE0
0xceb1  ldloc.s  7
0xceb3  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xceb8  brfalse.s loc_CEE0
0xceba  ldloc.s  7
0xcebc  callvirt instance class [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.XmlValueAssignedPlan::get_Plan()
0xcec1  callvirt instance valuetype [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedCapabilityStatus [Microsoft.Crm.CrmLive.MicrosoftOnline.Client]Microsoft.Crm.CrmLive.MicrosoftOnline.Client.AssignedPlanValue::get_CapabilityStatus()
0xcec6  brtrue.s loc_CEE0
0xcec8  ldloc.s  0xA
0xceca  ldloc.s  8
0xcecc  ldftn    instance bool <>c__DisplayClass11_0::<HandleUserLicenseAndCalType>b__0(string x)
0xced2  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0xced7  call     T0x2B000040
0xcedc  brfalse.s loc_CEE0
0xcede  ldc.i4.1
0xcedf  stloc.0
0xcee0  ldarg.0
0xcee1  ldstr    aAccessmode// "accessmode"
0xcee6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xceeb  brtrue.s loc_CF00
0xceed  ldarg.0
0xceee  ldstr    aAccessmode// "accessmode"
0xcef3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcef8  unbox.any [mscorlib]System.Int32
0xcefd  ldc.i4.4
0xcefe  beq.s    loc_CF11
0xcf00  ldarg.0
0xcf01  ldstr    aAccessmode// "accessmode"
0xcf06  ldc.i4.0
0xcf07  box      [mscorlib]System.Int32
0xcf0c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf11  ldarg.2
0xcf12  brfalse.s loc_CF4F
0xcf14  ldloc.0
0xcf15  brtrue.s loc_CF4F
0xcf17  ldarg.0
0xcf18  ldstr    aCaltype// "caltype"
0xcf1d  ldc.i4.1
0xcf1e  box      [mscorlib]System.Int32
0xcf23  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf28  ldarg.3
0xcf29  brfalse.s loc_CF3E
0xcf2b  ldarg.0
0xcf2c  ldstr    aAccessmode// "accessmode"
0xcf31  ldc.i4.0
0xcf32  box      [mscorlib]System.Int32
0xcf37  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf3c  br.s     loc_CF4F
0xcf3e  ldarg.0
0xcf3f  ldstr    aAccessmode// "accessmode"
0xcf44  ldc.i4.1
0xcf45  box      [mscorlib]System.Int32
0xcf4a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf4f  ldloc.s  6
0xcf51  ldc.i4.1
0xcf52  add
0xcf53  stloc.s  6
0xcf55  ldloc.s  6
0xcf57  ldloc.s  5
0xcf59  ldlen
0xcf5a  conv.i4
0xcf5b  blt      loc_CDD6
0xcf60  ret
0xcf61  ldarg.0
0xcf62  ldstr    aUserlicensetyp// "userlicensetype"
0xcf67  ldc.i4.m1
0xcf68  box      [mscorlib]System.Int32
0xcf6d  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf72  ldarg.2
0xcf73  brfalse.s loc_CFAD
0xcf75  ldarg.0
0xcf76  ldstr    aCaltype// "caltype"
0xcf7b  ldc.i4.1
0xcf7c  box      [mscorlib]System.Int32
0xcf81  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf86  ldarg.3
0xcf87  brfalse.s loc_CF9B
0xcf89  ldarg.0
0xcf8a  ldstr    aAccessmode// "accessmode"
0xcf8f  ldc.i4.0
0xcf90  box      [mscorlib]System.Int32
0xcf95  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcf9a  ret
0xcf9b  ldarg.0
0xcf9c  ldstr    aAccessmode// "accessmode"
0xcfa1  ldc.i4.1
0xcfa2  box      [mscorlib]System.Int32
0xcfa7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcfac  ret
0xcfad  ldarg.0
0xcfae  ldstr    aCaltype// "caltype"
0xcfb3  ldc.i4.0
0xcfb4  box      [mscorlib]System.Int32
0xcfb9  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcfbe  ldarg.0
0xcfbf  ldstr    aAccessmode// "accessmode"
0xcfc4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0xcfc9  brtrue.s loc_CFDE
0xcfcb  ldarg.0
0xcfcc  ldstr    aAccessmode// "accessmode"
0xcfd1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0xcfd6  unbox.any [mscorlib]System.Int32
0xcfdb  ldc.i4.4
0xcfdc  beq.s    loc_CFEF
0xcfde  ldarg.0
0xcfdf  ldstr    aAccessmode// "accessmode"
0xcfe4  ldc.i4.0
0xcfe5  box      [mscorlib]System.Int32
0xcfea  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0xcfef  ret
```
