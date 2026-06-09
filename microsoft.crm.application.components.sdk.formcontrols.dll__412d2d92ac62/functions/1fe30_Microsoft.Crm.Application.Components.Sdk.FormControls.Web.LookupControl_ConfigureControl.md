# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::ConfigureControl

- ea: `0x1fe30`
- end: `0x2012e`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::ConfigureControl`
- size: `766`
- prototype: ``
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1a480`
- `0x22c60`
- `0x24700`

## callees

- `0x17cf0`
- `0x182d0`
- `0x18670`
- `0x1f6a0`
- `0x1f8a0`
- `0x1f8b0`
- `0x1f930`
- `0x1fa40`
- `0x1fa50`
- `0x1fe30`
- `0x20130`
- `0x209e0`

## pseudocode

```c

```

## disassembly

```asm
0x1fe30  ldarg.0
0x1fe31  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Lookup Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_innerLookup
0x1fe36  ldarg.0
0x1fe37  call     instance bool [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_AutoRegisterClientComponent()
0x1fe3c  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_AutoRegisterClientComponent(bool)
0x1fe41  ldarg.0
0x1fe42  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::ConfigureControl()
0x1fe47  ldarg.0
0x1fe48  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::SetDisabled()
0x1fe4d  ldsfld   string [mscorlib]System.String::Empty
0x1fe52  stloc.0
0x1fe53  ldsfld   string [mscorlib]System.String::Empty
0x1fe58  stloc.1
0x1fe59  ldsfld   string [mscorlib]System.String::Empty
0x1fe5e  stloc.2
0x1fe5f  ldarg.0
0x1fe60  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1fe65  brfalse  loc_1FF62
0x1fe6a  ldarg.0
0x1fe6b  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1fe70  ldlen
0x1fe71  brfalse  loc_1FF62
0x1fe76  ldc.i4.0
0x1fe77  stloc.3
0x1fe78  br       loc_1FF54
0x1fe7d  ldloc.3
0x1fe7e  ldc.i4.0
0x1fe7f  ble.s    loc_1FEA5
0x1fe81  ldloc.0
0x1fe82  ldstr    asc_36702// ","
0x1fe87  call     string [mscorlib]System.String::Concat(string, string)
0x1fe8c  stloc.0
0x1fe8d  ldloc.1
0x1fe8e  ldstr    asc_36702// ","
0x1fe93  call     string [mscorlib]System.String::Concat(string, string)
0x1fe98  stloc.1
0x1fe99  ldloc.2
0x1fe9a  ldstr    asc_379D0// ":"
0x1fe9f  call     string [mscorlib]System.String::Concat(string, string)
0x1fea4  stloc.2
0x1fea5  ldloc.0
0x1fea6  ldarg.0
0x1fea7  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1feac  ldloc.3
0x1fead  ldelema  [mscorlib]System.Int32
0x1feb2  ldstr    aD// "D"
0x1feb7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1febc  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1fec1  call     string [mscorlib]System.String::Concat(string, string)
0x1fec6  stloc.0
0x1fec7  ldc.i4.6
0x1fec8  newarr   [mscorlib]System.String
0x1fecd  dup
0x1fece  ldc.i4.0
0x1fecf  ldloc.1
0x1fed0  stelem.ref
0x1fed1  dup
0x1fed2  ldc.i4.1
0x1fed3  ldarg.0
0x1fed4  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1fed9  ldloc.3
0x1feda  ldelem.i4
0x1fedb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetObjName(int32)
0x1fee0  stelem.ref
0x1fee1  dup
0x1fee2  ldc.i4.2
0x1fee3  ldstr    asc_379D0// ":"
0x1fee8  stelem.ref
0x1fee9  dup
0x1feea  ldc.i4.3
0x1feeb  ldarg.0
0x1feec  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1fef1  ldloc.3
0x1fef2  ldelema  [mscorlib]System.Int32
0x1fef7  ldstr    aD// "D"
0x1fefc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ff01  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x1ff06  stelem.ref
0x1ff07  dup
0x1ff08  ldc.i4.4
0x1ff09  ldstr    asc_379D0// ":"
0x1ff0e  stelem.ref
0x1ff0f  dup
0x1ff10  ldc.i4.5
0x1ff11  ldarg.0
0x1ff12  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1ff17  ldloc.3
0x1ff18  ldelem.i4
0x1ff19  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ff1e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ff23  ldc.i4.1
0x1ff24  ldnull
0x1ff25  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x1ff2a  stelem.ref
0x1ff2b  call     string [mscorlib]System.String::Concat(string[])
0x1ff30  stloc.1
0x1ff31  ldloc.2
0x1ff32  ldarg.0
0x1ff33  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1ff38  ldloc.3
0x1ff39  ldelem.i4
0x1ff3a  ldc.i4.0
0x1ff3b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ff40  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconUtil::GetIconPath(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.IconType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ff45  callvirt instance string [mscorlib]System.Object::ToString()
0x1ff4a  call     string [mscorlib]System.String::Concat(string, string)
0x1ff4f  stloc.2
0x1ff50  ldloc.3
0x1ff51  ldc.i4.1
0x1ff52  add
0x1ff53  stloc.3
0x1ff54  ldloc.3
0x1ff55  ldarg.0
0x1ff56  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x1ff5b  ldlen
0x1ff5c  conv.i4
0x1ff5d  blt      loc_1FE7D
0x1ff62  ldarg.0
0x1ff63  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1ff68  brfalse  loc_20034
0x1ff6d  ldarg.0
0x1ff6e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1ff73  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1ff78  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_TransactionCurrencyField()
0x1ff7d  brfalse  loc_20034
0x1ff82  ldarg.0
0x1ff83  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1ff88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Entity()
0x1ff8d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_TransactionCurrencyField()
0x1ff92  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1ff97  ldarg.0
0x1ff98  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormDataControlUIWrapper::get_Metadata()
0x1ff9d  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_LogicalName()
0x1ffa2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1ffa7  brfalse  loc_20034
0x1ffac  ldarg.0
0x1ffad  ldstr    aMsCrmLookupTra// "ms-crm-Lookup-TransactionCurrency"
0x1ffb2  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_LookupImageClass(string value)
0x1ffb7  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x1ffbc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ffc1  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1ffc6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ffcb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1ffd0  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1ffd5  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x1ffda  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_CurrencyDisplayOption()
0x1ffdf  stloc.s  4
0x1ffe1  ldarg.0
0x1ffe2  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x1ffe7  ldstr    aCursymclm// "cursymclm"
0x1ffec  ldloc.s  4
0x1ffee  ldc.i4.1
0x1ffef  beq.s    loc_1FFF8
0x1fff1  ldstr    aCurrencysymbol// "currencysymbol"
0x1fff6  br.s     loc_1FFFD
0x1fff8  ldstr    aIsocurrencycod// "isocurrencycode"
0x1fffd  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x20002  ldarg.0
0x20003  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20008  ldstr    aLocidCurrencyC// "LOCID_CURRENCY_CANNOT_BE_NULL"
0x2000d  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x20012  ldstr    aErrorMessage0x// "Error_Message_0x80048cfb"
0x20017  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2001c  ldc.i4.0
0x2001d  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetResource(string, string, bool)
0x20022  ldarg.0
0x20023  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_CurrentHeader()
0x20028  ldstr    aDefaultcurrenc// "DefaultCurrencyPrecision"
0x2002d  ldc.i4.2
0x2002e  conv.i8
0x2002f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string, int64)
0x20034  ldarg.0
0x20035  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultType()
0x2003a  brtrue.s loc_20053
0x2003c  ldarg.0
0x2003d  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x20042  ldlen
0x20043  brfalse.s loc_20053
0x20045  ldarg.0
0x20046  ldarg.0
0x20047  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x2004c  ldc.i4.0
0x2004d  ldelem.i4
0x2004e  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultType(int32 value)
0x20053  ldarg.0
0x20054  ldloc.0
0x20055  ldloc.1
0x20056  ldloc.2
0x20057  ldarg.0
0x20058  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_crmAttributeId
0x2005d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20062  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20067  brtrue.s loc_2007B
0x20069  ldarg.0
0x2006a  ldflda   valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::_crmAttributeId
0x2006f  ldstr    aB// "B"
0x20074  call     instance string [mscorlib]System.Guid::ToString(string)
0x20079  br.s     loc_20080
0x2007b  ldsfld   string [mscorlib]System.String::Empty
0x20080  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::SetExpandos(string typeString, string typeNameString, string typeIconString, string crmAttributeId)
0x20085  ldarg.0
0x20086  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultViewId()
0x2008b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20090  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20095  brfalse.s loc_20100
0x20097  ldarg.0
0x20098  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x2009d  brfalse.s loc_20100
0x2009f  ldarg.0
0x200a0  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x200a5  ldlen
0x200a6  brfalse.s loc_20100
0x200a8  ldarg.0
0x200a9  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultType()
0x200ae  brtrue.s loc_200BA
0x200b0  ldarg.0
0x200b1  call     instance int32[] Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_LookupTypes()
0x200b6  ldc.i4.0
0x200b7  ldelem.i4
0x200b8  br.s     loc_200C0
0x200ba  ldarg.0
0x200bb  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultType()
0x200c0  stloc.s  5
0x200c2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::Instance()
0x200c7  ldloc.s  5
0x200c9  ldc.i4.s 0x40
0x200cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x200d0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::TryLookupEntry(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x200d5  stloc.s  6
0x200d7  ldloc.s  6
0x200d9  brtrue.s loc_200EF
0x200db  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::Instance()
0x200e0  ldloc.s  5
0x200e2  ldc.i4.0
0x200e3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x200e8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.DefaultSavedQueryIdsCache::TryLookupEntry(int32, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x200ed  stloc.s  6
0x200ef  ldloc.s  6
0x200f1  brfalse.s loc_20100
0x200f3  ldarg.0
0x200f4  ldloc.s  6
0x200f6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.QueryIdData::get_QueryId()
0x200fb  call     instance void Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::set_DefaultViewId(valuetype [mscorlib]System.Guid value)
0x20100  ldarg.0
0x20101  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultViewId()
0x20106  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2010b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20110  brfalse.s loc_2012D
0x20112  ldarg.0
0x20113  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmFormUIControl Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlUIWrapper::get_InnerControl()
0x20118  ldstr    aDefaultviewid_0// "defaultViewId"
0x2011d  ldarg.0
0x2011e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.FormControls.Web.LookupControl::get_DefaultViewId()
0x20123  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GuidToString(valuetype [mscorlib]System.Guid)
0x20128  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string, string)
0x2012d  ret
```
