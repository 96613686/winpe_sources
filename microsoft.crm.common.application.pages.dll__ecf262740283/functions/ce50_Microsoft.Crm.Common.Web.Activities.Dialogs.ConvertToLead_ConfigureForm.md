# Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::ConfigureForm

- ea: `0xce50`
- end: `0xd294`
- name: `Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::ConfigureForm`
- size: `1092`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0xccb0`
- `0xccf0`
- `0xcd30`
- `0xce50`

## pseudocode

```c

```

## disassembly

```asm
0xce50  ldarg.0
0xce51  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0xce56  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0xce5b  ldstr    aActivityid_0// "activityId"
0xce60  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0xce65  stloc.0
0xce66  ldloca.s 1
0xce68  ldloc.0
0xce69  call     instance void [mscorlib]System.Guid::.ctor(string)
0xce6e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xce73  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xce78  ldarg.0
0xce79  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::activityType
0xce7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xce83  stloc.3
0xce84  ldc.i4.7
0xce85  newarr   [mscorlib]System.String
0xce8a  dup
0xce8b  ldc.i4.0
0xce8c  ldstr    aSubject// "subject"
0xce91  stelem.ref
0xce92  dup
0xce93  ldc.i4.1
0xce94  ldstr    aDirectioncode// "directioncode"
0xce99  stelem.ref
0xce9a  dup
0xce9b  ldc.i4.2
0xce9c  ldstr    aStatecode// "statecode"
0xcea1  stelem.ref
0xcea2  dup
0xcea3  ldc.i4.3
0xcea4  ldstr    aFrom// "from"
0xcea9  stelem.ref
0xceaa  dup
0xceab  ldc.i4.4
0xceac  ldstr    aTo// "to"
0xceb1  stelem.ref
0xceb2  dup
0xceb3  ldc.i4.5
0xceb4  ldstr    aCc// "cc"
0xceb9  stelem.ref
0xceba  dup
0xcebb  ldc.i4.6
0xcebc  ldstr    aBcc// "bcc"
0xcec1  stelem.ref
0xcec2  stloc.s  4
0xcec4  ldloc.3
0xcec5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0xceca  ldloc.1
0xcecb  ldloc.s  4
0xcecd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xced2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xced7  stloc.s  5
0xced9  ldloc.s  5
0xcedb  ldstr    aSubject// "subject"
0xcee0  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcee5  brfalse.s loc_CF05
0xcee7  ldarg.0
0xcee8  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_Topic()
0xceed  ldloc.s  5
0xceef  ldstr    aSubject// "subject"
0xcef4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcef9  castclass [mscorlib]System.String
0xcefe  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcf03  br.s     loc_CF15
0xcf05  ldarg.0
0xcf06  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.HiddenInputControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_Topic()
0xcf0b  ldsfld   string [mscorlib]System.String::Empty
0xcf10  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcf15  ldsfld   string [mscorlib]System.String::Empty
0xcf1a  stloc.s  6
0xcf1c  ldc.i4.0
0xcf1d  stloc.s  7
0xcf1f  ldloc.s  5
0xcf21  ldstr    aDirectioncode// "directioncode"
0xcf26  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf2b  brfalse.s loc_CF40
0xcf2d  ldloc.s  5
0xcf2f  ldstr    aDirectioncode// "directioncode"
0xcf34  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf39  unbox.any [mscorlib]System.Boolean
0xcf3e  stloc.s  7
0xcf40  ldloc.s  7
0xcf42  brfalse  loc_D0A8
0xcf47  ldloc.s  5
0xcf49  ldstr    aTo// "to"
0xcf4e  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf53  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0xcf58  stloc.s  0xB
0xcf5a  ldloc.s  5
0xcf5c  ldstr    aCc// "cc"
0xcf61  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf66  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0xcf6b  stloc.s  0xC
0xcf6d  ldloc.s  5
0xcf6f  ldstr    aBcc// "bcc"
0xcf74  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf79  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0xcf7e  stloc.s  0xD
0xcf80  ldloc.s  0xB
0xcf82  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xcf87  ldc.i4.0
0xcf88  ble.s    loc_CFFD
0xcf8a  ldloc.s  0xB
0xcf8c  ldc.i4.0
0xcf8d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xcf92  ldstr    aPartyid// "partyid"
0xcf97  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcf9c  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xcfa1  stloc.2
0xcfa2  ldloc.2
0xcfa3  brfalse.s loc_CFAD
0xcfa5  ldloc.2
0xcfa6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xcfab  stloc.s  6
0xcfad  ldloc.s  0xB
0xcfaf  ldc.i4.0
0xcfb0  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xcfb5  ldstr    aAddressused// "addressused"
0xcfba  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcfbf  brfalse.s loc_CFE8
0xcfc1  ldarg.0
0xcfc2  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xcfc7  ldloc.s  0xB
0xcfc9  ldc.i4.0
0xcfca  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xcfcf  ldstr    aAddressused// "addressused"
0xcfd4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xcfd9  callvirt instance string [mscorlib]System.Object::ToString()
0xcfde  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcfe3  br       loc_D1B3
0xcfe8  ldarg.0
0xcfe9  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xcfee  ldstr    asc_1F1DE// ""
0xcff3  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xcff8  br       loc_D1B3
0xcffd  ldloc.s  0xC
0xcfff  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd004  ldc.i4.0
0xd005  ble.s    loc_D051
0xd007  ldloc.s  0xC
0xd009  ldc.i4.0
0xd00a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd00f  ldstr    aPartyid// "partyid"
0xd014  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd019  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd01e  stloc.2
0xd01f  ldloc.2
0xd020  brfalse.s loc_D02A
0xd022  ldloc.2
0xd023  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xd028  stloc.s  6
0xd02a  ldarg.0
0xd02b  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xd030  ldloc.s  0xC
0xd032  ldc.i4.0
0xd033  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd038  ldstr    aAddressused// "addressused"
0xd03d  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd042  callvirt instance string [mscorlib]System.Object::ToString()
0xd047  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd04c  br       loc_D1B3
0xd051  ldloc.s  0xD
0xd053  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd058  ldc.i4.0
0xd059  ble      loc_D1B3
0xd05e  ldloc.s  0xD
0xd060  ldc.i4.0
0xd061  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd066  ldstr    aPartyid// "partyid"
0xd06b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd070  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd075  stloc.2
0xd076  ldloc.2
0xd077  brfalse.s loc_D081
0xd079  ldloc.2
0xd07a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xd07f  stloc.s  6
0xd081  ldarg.0
0xd082  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xd087  ldloc.s  0xD
0xd089  ldc.i4.0
0xd08a  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd08f  ldstr    aAddressused// "addressused"
0xd094  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd099  callvirt instance string [mscorlib]System.Object::ToString()
0xd09e  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd0a3  br       loc_D1B3
0xd0a8  ldloc.s  5
0xd0aa  ldstr    aFrom// "from"
0xd0af  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd0b4  castclass [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection
0xd0b9  stloc.s  0xE
0xd0bb  ldloc.s  0xE
0xd0bd  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0xd0c2  ldc.i4.0
0xd0c3  ble      loc_D1B3
0xd0c8  ldloc.s  0xE
0xd0ca  ldc.i4.0
0xd0cb  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd0d0  ldstr    aPartyid// "partyid"
0xd0d5  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd0da  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0xd0df  stloc.2
0xd0e0  ldloc.2
0xd0e1  brfalse.s loc_D0EB
0xd0e3  ldloc.2
0xd0e4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Name()
0xd0e9  stloc.s  6
0xd0eb  ldloc.s  0xE
0xd0ed  ldc.i4.0
0xd0ee  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd0f3  ldstr    aAddressused// "addressused"
0xd0f8  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd0fd  brfalse.s loc_D126
0xd0ff  ldarg.0
0xd100  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xd105  ldloc.s  0xE
0xd107  ldc.i4.0
0xd108  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd10d  ldstr    aAddressused// "addressused"
0xd112  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd117  callvirt instance string [mscorlib]System.Object::ToString()
0xd11c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd121  br       loc_D1B3
0xd126  ldarg.0
0xd127  ldfld    int32 Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::activityType
0xd12c  ldc.i4   0x1078
0xd131  bne.un.s loc_D1A3
0xd133  ldnull
0xd134  stloc.s  0xF
0xd136  ldloc.s  0xE
0xd138  ldc.i4.0
0xd139  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd13e  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0xd143  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd148  brfalse.s loc_D1B3
0xd14a  ldloc.s  0xE
0xd14c  ldc.i4.0
0xd14d  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Item(!!T0)
0xd152  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0xd157  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd15c  callvirt instance string [mscorlib]System.Object::ToString()
0xd161  ldloc.2
0xd162  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0xd167  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0xd16c  ldc.i4.1
0xd16d  newarr   [mscorlib]System.String
0xd172  dup
0xd173  ldc.i4.0
0xd174  ldstr    aEmailaddress1// "emailaddress1"
0xd179  stelem.ref
0xd17a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd17f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Retrieve(string, valuetype [mscorlib]System.Guid, string[], class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd184  stloc.s  0xF
0xd186  ldloc.s  0xF
0xd188  brfalse.s loc_D1B3
0xd18a  ldarg.0
0xd18b  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xd190  ldloc.s  0xF
0xd192  ldstr    aEmailaddress1// "emailaddress1"
0xd197  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xd19c  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd1a1  br.s     loc_D1B3
0xd1a3  ldarg.0
0xd1a4  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.EmailAddressControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_EmailAddress()
0xd1a9  ldsfld   string [mscorlib]System.String::Empty
0xd1ae  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd1b3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd1b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0xd1bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xd1c2  stloc.s  8
0xd1c4  ldloc.s  8
0xd1c6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd1cb  ldc.i4.4
0xd1cc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0xd1d1  ldstr    aLastname// "lastname"
0xd1d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0xd1db  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StringAttributeMetadata
0xd1e0  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.TextAttributeMetadata::get_MaxLength()
0xd1e5  stloc.s  9
0xd1e7  ldloc.s  6
0xd1e9  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd1ee  ldloc.s  9
0xd1f0  ble.s    loc_D1FE
0xd1f2  ldloc.s  6
0xd1f4  ldc.i4.0
0xd1f5  ldloc.s  9
0xd1f7  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0xd1fc  stloc.s  6
0xd1fe  ldarg.0
0xd1ff  call     instance class [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.TextBoxControl Microsoft.Crm.Common.Web.Activities.Dialogs.ConvertToLead::get_LastName()
0xd204  ldloc.s  6
0xd206  callvirt instance void [Microsoft.Crm.Application.Components.Sdk.FormControls]Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::set_Value(object)
0xd20b  ldarg.0
0xd20c  ldarg.0
0xd20d  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppUIPage::get_CurrentResourceManager()
0xd212  ldstr    aConvertActivit_5// "Convert_Activity_To_Lead_InlineDlg_Titl"...
0xd217  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xd21c  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Pages.DialogPage::set_DialogTitle(string)
  ... truncated ...
```
