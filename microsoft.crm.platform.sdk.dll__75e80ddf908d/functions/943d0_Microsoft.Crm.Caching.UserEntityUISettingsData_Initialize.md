# Microsoft.Crm.Caching.UserEntityUISettingsData::Initialize

- ea: `0x943d0`
- end: `0x9450c`
- name: `Microsoft.Crm.Caching.UserEntityUISettingsData::Initialize`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x81f50`
- `0x81f60`
- `0x94290`
- `0x942b0`
- `0x942d0`
- `0x942f0`
- `0x94310`
- `0x94350`
- `0x943b0`
- `0x943d0`
- `0x94510`

## string_xrefs

- `0x943f4`: `userentityuisettingsid`
- `0x94402`: `userentityuisettingsid`
- `0x9445d`: `taborderxml`
- `0x9446b`: `taborderxml`
- `0x94480`: `readingpanexml`
- `0x9448e`: `readingpanexml`
- `0x944a3`: `lastviewedformxml`
- `0x944b1`: `lastviewedformxml`
- `0x944e9`: `recentlyviewedxml`
- `0x944f7`: `recentlyviewedxml`

## pseudocode

```c

```

## disassembly

```asm
0x943d0  ldarg.1
0x943d1  ldstr    aOwnerid// "ownerid"
0x943d6  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x943db  brtrue.s loc_943F3
0x943dd  ldarg.0
0x943de  ldarg.1
0x943df  ldstr    aOwnerid// "ownerid"
0x943e4  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x943e9  unbox.any [mscorlib]System.Guid
0x943ee  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_OwnerId(valuetype [mscorlib]System.Guid value)
0x943f3  ldarg.1
0x943f4  ldstr    aUserentityuise// "userentityuisettingsid"
0x943f9  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x943fe  brtrue.s loc_94416
0x94400  ldarg.0
0x94401  ldarg.1
0x94402  ldstr    aUserentityuise// "userentityuisettingsid"
0x94407  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9440c  unbox.any [mscorlib]System.Guid
0x94411  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_UserEntityUISettingsId(valuetype [mscorlib]System.Guid value)
0x94416  ldarg.1
0x94417  ldstr    aOwningbusiness// "owningbusinessunit"
0x9441c  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x94421  brtrue.s loc_94439
0x94423  ldarg.0
0x94424  ldarg.1
0x94425  ldstr    aOwningbusiness// "owningbusinessunit"
0x9442a  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x9442f  unbox.any [mscorlib]System.Guid
0x94434  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_OwningBusinessUnit(valuetype [mscorlib]System.Guid value)
0x94439  ldarg.1
0x9443a  ldstr    aObjecttypecode_0// "objecttypecode"
0x9443f  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x94444  brtrue.s loc_9445C
0x94446  ldarg.0
0x94447  ldarg.1
0x94448  ldstr    aObjecttypecode_0// "objecttypecode"
0x9444d  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x94452  unbox.any [mscorlib]System.Int32
0x94457  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_ObjectTypeCode(int32 value)
0x9445c  ldarg.1
0x9445d  ldstr    aTaborderxml// "taborderxml"
0x94462  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x94467  brtrue.s loc_9447F
0x94469  ldarg.0
0x9446a  ldarg.1
0x9446b  ldstr    aTaborderxml// "taborderxml"
0x94470  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x94475  castclass [mscorlib]System.String
0x9447a  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_TabOrderXml(string value)
0x9447f  ldarg.1
0x94480  ldstr    aReadingpanexml// "readingpanexml"
0x94485  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x9448a  brtrue.s loc_944A2
0x9448c  ldarg.0
0x9448d  ldarg.1
0x9448e  ldstr    aReadingpanexml// "readingpanexml"
0x94493  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x94498  castclass [mscorlib]System.String
0x9449d  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::InitializeReadingPane(string readingPaneXml)
0x944a2  ldarg.1
0x944a3  ldstr    aLastviewedform// "lastviewedformxml"
0x944a8  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x944ad  brtrue.s loc_944C5
0x944af  ldarg.0
0x944b0  ldarg.1
0x944b1  ldstr    aLastviewedform// "lastviewedformxml"
0x944b6  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x944bb  castclass [mscorlib]System.String
0x944c0  stfld    string Microsoft.Crm.Caching.UserEntityUISettingsData::_lastViewedFormXml
0x944c5  ldarg.1
0x944c6  ldstr    aShowinaddressb// "showinaddressbook"
0x944cb  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x944d0  brtrue.s loc_944E8
0x944d2  ldarg.0
0x944d3  ldarg.1
0x944d4  ldstr    aShowinaddressb// "showinaddressbook"
0x944d9  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x944de  unbox.any [mscorlib]System.Boolean
0x944e3  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_ShowInAddressBook(bool value)
0x944e8  ldarg.1
0x944e9  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x944ee  callvirt instance bool Microsoft.Crm.Caching.ICacheEntityWrapper::IsAttributeNull(string attributeName)
0x944f3  brtrue.s loc_9450B
0x944f5  ldarg.0
0x944f6  ldarg.1
0x944f7  ldstr    aRecentlyviewed// "recentlyviewedxml"
0x944fc  callvirt instance object Microsoft.Crm.Caching.ICacheEntityWrapper::GetAttributeValue(string attributeName)
0x94501  isinst   [mscorlib]System.String
0x94506  call     instance void Microsoft.Crm.Caching.UserEntityUISettingsData::set_RecentlyViewedXml(string value)
0x9450b  ret
```
