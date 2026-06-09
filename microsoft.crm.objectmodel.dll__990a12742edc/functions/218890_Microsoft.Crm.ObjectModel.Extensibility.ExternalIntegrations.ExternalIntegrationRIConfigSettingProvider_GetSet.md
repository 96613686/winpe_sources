# Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::GetSettingsForFeature

- ea: `0x218890`
- end: `0x218a98`
- name: `Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::GetSettingsForFeature`
- size: `520`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x218460`

## callees

- `0x218520`
- `0x218540`
- `0x218560`
- `0x218580`
- `0x2185a0`
- `0x2185b0`
- `0x218620`
- `0x218790`
- `0x218890`
- `0x218aa0`
- `0x218ad0`
- `0x218b20`

## string_xrefs

- `0x2188e9`: `AppIdUri`
- `0x2188ef`: `AppIdUri`
- `0x218903`: `AppIdUri`
- `0x218913`: `ActivityAnalysisServiceEndpoint`
- `0x218a57`: `ActivityAnalysisServiceEndpoint`
- `0x218a6b`: `ActivityAnalysisServiceEndpoint`

## pseudocode

```c

```

## disassembly

```asm
0x218890  ldarg.0
0x218891  ldarg.1
0x218892  call     instance class [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::GetSettingsForFeature(string featureKeyName)
0x218897  stloc.0
0x218898  ldarg.0
0x218899  ldc.i4.s 0xE
0x21889b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::RetrievePropertiesFromAzureApplicationTableInGeoDb(int32 applicationServiceType)
0x2188a0  stloc.1
0x2188a1  ldloc.1
0x2188a2  brfalse.s loc_218912
0x2188a4  ldloc.0
0x2188a5  brfalse.s loc_218912
0x2188a7  ldarg.0
0x2188a8  ldloc.0
0x2188a9  callvirt instance string [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings::get_ApplicationId()
0x2188ae  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::set_ApplicationId(string value)
0x2188b3  ldarg.0
0x2188b4  ldloc.0
0x2188b5  callvirt instance string [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings::get_SubscriptionId()
0x2188ba  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::set_SubscriptionId(string value)
0x2188bf  ldarg.0
0x2188c0  ldloc.0
0x2188c1  callvirt instance string [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings::get_ApplicationSecret()
0x2188c6  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::set_ApplicationSecret(string value)
0x2188cb  ldarg.0
0x2188cc  ldloc.0
0x2188cd  callvirt instance string [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings::get_ApplicationSecretSecondary()
0x2188d2  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::set_ApplicationSecretSecondary(string value)
0x2188d7  ldarg.0
0x2188d8  ldloc.0
0x2188d9  callvirt instance string [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.ExternalIntegration.IExternalIntegrationConfigSettings::get_ApplicationInfo()
0x2188de  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::set_ApplicationInfo(string value)
0x2188e3  ldarg.0
0x2188e4  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x2188e9  ldstr    aAppiduri// "AppIdUri"
0x2188ee  ldloc.1
0x2188ef  ldstr    aAppiduri// "AppIdUri"
0x2188f4  call     T0x2B000357
0x2188f9  dup
0x2188fa  brtrue.s loc_21890D
0x2188fc  pop
0x2188fd  ldarg.0
0x2188fe  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218903  ldstr    aAppiduri// "AppIdUri"
0x218908  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x21890d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218912  ldarg.0
0x218913  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x218918  ldc.i4.s 0x10
0x21891a  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::SetValueFromAzureApplicationTable(string key, int32 applicationServiceType)
0x21891f  ldarg.0
0x218920  ldstr    aNotesanalysise// "NotesAnalysisEndpoint"
0x218925  ldc.i4.s 0x1C
0x218927  call     instance void Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::SetValueFromAzureApplicationTable(string key, int32 applicationServiceType)
0x21892c  ldarg.0
0x21892d  ldarg.1
0x21892e  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationRIConfigSettingProvider::RetrievePropertiesFromOrgApplicationMapTableInGeoDb(string featureKey)
0x218933  stloc.1
0x218934  ldloc.1
0x218935  brfalse  loc_218A96
0x21893a  ldarg.0
0x21893b  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218940  ldstr    aConnectionstri_0// "ConnectionString"
0x218945  ldloc.1
0x218946  ldstr    aConnectionstri_0// "ConnectionString"
0x21894b  call     T0x2B000357
0x218950  dup
0x218951  brtrue.s loc_218964
0x218953  pop
0x218954  ldarg.0
0x218955  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x21895a  ldstr    aConnectionstri_0// "ConnectionString"
0x21895f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x218964  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218969  ldarg.0
0x21896a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x21896f  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0x218974  ldloc.1
0x218975  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0x21897a  call     T0x2B000359
0x21897f  box      [mscorlib]System.Int32
0x218984  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218989  ldarg.0
0x21898a  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x21898f  ldstr    aOrgprovisionin// "OrgProvisioningType"
0x218994  ldloc.1
0x218995  ldstr    aOrgprovisionin// "OrgProvisioningType"
0x21899a  call     T0x2B000357
0x21899f  dup
0x2189a0  brtrue.s loc_2189B3
0x2189a2  pop
0x2189a3  ldarg.0
0x2189a4  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x2189a9  ldstr    aOrgprovisionin// "OrgProvisioningType"
0x2189ae  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2189b3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2189b8  ldarg.0
0x2189b9  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x2189be  ldstr    aRelationshipan_0// "RelationshipAnalyticsDCIHubPlanType"
0x2189c3  ldloc.1
0x2189c4  ldstr    aRelationshipan_0// "RelationshipAnalyticsDCIHubPlanType"
0x2189c9  call     T0x2B000357
0x2189ce  dup
0x2189cf  brtrue.s loc_2189E2
0x2189d1  pop
0x2189d2  ldarg.0
0x2189d3  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x2189d8  ldstr    aRelationshipan_0// "RelationshipAnalyticsDCIHubPlanType"
0x2189dd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x2189e2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x2189e7  ldarg.0
0x2189e8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x2189ed  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x2189f2  ldloc.1
0x2189f3  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x2189f8  call     string Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::GetDecryptedPropertyValueAsString(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propBag, string propertyName)
0x2189fd  dup
0x2189fe  brtrue.s loc_218A11
0x218a00  pop
0x218a01  ldarg.0
0x218a02  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218a07  ldstr    aTenantprimaryk// "TenantPrimaryKey"
0x218a0c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x218a11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218a16  ldarg.0
0x218a17  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218a1c  ldstr    aEmailengagemen_5// "EmailEngagementProvisioningStatus"
0x218a21  ldloc.1
0x218a22  ldstr    aEmailengagemen_5// "EmailEngagementProvisioningStatus"
0x218a27  call     T0x2B000359
0x218a2c  box      [mscorlib]System.Int32
0x218a31  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218a36  ldarg.0
0x218a37  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218a3c  ldstr    aActivityanalys_0// "ActivityAnalysisProvisioningStatus"
0x218a41  ldloc.1
0x218a42  ldstr    aActivityanalys_0// "ActivityAnalysisProvisioningStatus"
0x218a47  call     T0x2B000359
0x218a4c  box      [mscorlib]System.Int32
0x218a51  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218a56  ldloc.1
0x218a57  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x218a5c  call     T0x2B000357
0x218a61  stloc.2
0x218a62  ldloc.2
0x218a63  brfalse.s loc_218A76
0x218a65  ldarg.0
0x218a66  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218a6b  ldstr    aActivityanalys// "ActivityAnalysisServiceEndpoint"
0x218a70  ldloc.2
0x218a71  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218a76  ldloc.1
0x218a77  ldstr    aNotesanalysise// "NotesAnalysisEndpoint"
0x218a7c  call     T0x2B000357
0x218a81  stloc.3
0x218a82  ldloc.3
0x218a83  brfalse.s loc_218A96
0x218a85  ldarg.0
0x218a86  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.ObjectModel.Extensibility.ExternalIntegrations.ExternalIntegrationGeoDbConfigSettingProvider::get_ApplicationData()
0x218a8b  ldstr    aNotesanalysise// "NotesAnalysisEndpoint"
0x218a90  ldloc.3
0x218a91  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x218a96  ldarg.0
0x218a97  ret
```
