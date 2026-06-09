# Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLogging::IsActivityRequest

- ea: `0x22a960`
- end: `0x22ae78`
- name: `Microsoft.Crm.ObjectModel.ActivityLogging.ActivityLogging::IsActivityRequest`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2298d0`

## callees

- `0x22a960`
- `0x22be40`

## string_xrefs

- `0x22abf8`: `TriggerServiceEndpointCheck`
- `0x22acf4`: `RetrievePrincipalAccess`
- `0x22ae68`: `RetrieveEntityXml`
- `0x22adb1`: `ConfigureReportingDataConnector`
- `0x22ac0d`: `QueryExpressionToFetchXml`
- `0x22ac22`: `FetchXmlToQueryExpression`
- `0x22ac8b`: `RetrieveInstalledLanguagePackVersion`
- `0x22acdf`: `RetrieveInstalledLanguagePacks`
- `0x22ad33`: `IsReportingDataConnectorInstalled`
- `0x22ad5d`: `IsBackOfficeInstalled`
- `0x22ad9c`: `IsComponentCustomizable`
- `0x22adc6`: `CheckClientCompatibility`

## pseudocode

```c

```

## disassembly

```asm
0x22a960  ldarg.0
0x22a961  ldstr    aRequest// "request"
0x22a966  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x22a96b  ldc.i4.1
0x22a96c  stloc.0
0x22a96d  ldarg.0
0x22a96e  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::get_RequestName()
0x22a973  stloc.1
0x22a974  ldloc.1
0x22a975  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x22a97a  stloc.2
0x22a97b  ldloc.2
0x22a97c  ldc.i4   0x801C149D
0x22a981  bgt.un   loc_22AAA4
0x22a986  ldloc.2
0x22a987  ldc.i4   0x5119FF38
0x22a98c  bgt.un   loc_22AA15
0x22a991  ldloc.2
0x22a992  ldc.i4   0x1E1709E3
0x22a997  bgt.un.s loc_22A9D7
0x22a999  ldloc.2
0x22a99a  ldc.i4   0x944A3A9
0x22a99f  bgt.un.s loc_22A9BC
0x22a9a1  ldloc.2
0x22a9a2  ldc.i4   0x3ED292E
0x22a9a7  beq      loc_22AC36
0x22a9ac  ldloc.2
0x22a9ad  ldc.i4   0x944A3A9
0x22a9b2  beq      loc_22AC21
0x22a9b7  br       loc_22AE76
0x22a9bc  ldloc.2
0x22a9bd  ldc.i4   0x1547CFDA
0x22a9c2  beq      loc_22AD1D
0x22a9c7  ldloc.2
0x22a9c8  ldc.i4   0x1E1709E3
0x22a9cd  beq      loc_22AD08
0x22a9d2  br       loc_22AE76
0x22a9d7  ldloc.2
0x22a9d8  ldc.i4   0x3D2D1908
0x22a9dd  bgt.un.s loc_22A9FA
0x22a9df  ldloc.2
0x22a9e0  ldc.i4   0x34D78BC3
0x22a9e5  beq      loc_22ADDA
0x22a9ea  ldloc.2
0x22a9eb  ldc.i4   0x3D2D1908
0x22a9f0  beq      loc_22ADC5
0x22a9f5  br       loc_22AE76
0x22a9fa  ldloc.2
0x22a9fb  ldc.i4   0x42E3C87D
0x22aa00  beq      loc_22AC4B
0x22aa05  ldloc.2
0x22aa06  ldc.i4   0x5119FF38
0x22aa0b  beq      loc_22AD5C
0x22aa10  br       loc_22AE76
0x22aa15  ldloc.2
0x22aa16  ldc.i4   0x59D9C072
0x22aa1b  bgt.un.s loc_22AA5B
0x22aa1d  ldloc.2
0x22aa1e  ldc.i4   0x58AC0B8D
0x22aa23  bgt.un.s loc_22AA40
0x22aa25  ldloc.2
0x22aa26  ldc.i4   0x56F09D8D
0x22aa2b  beq      loc_22AE2B
0x22aa30  ldloc.2
0x22aa31  ldc.i4   0x58AC0B8D
0x22aa36  beq      loc_22ABE2
0x22aa3b  br       loc_22AE76
0x22aa40  ldloc.2
0x22aa41  ldc.i4   0x59286E53
0x22aa46  beq      loc_22AE67
0x22aa4b  ldloc.2
0x22aa4c  ldc.i4   0x59D9C072
0x22aa51  beq      loc_22AC8A
0x22aa56  br       loc_22AE76
0x22aa5b  ldloc.2
0x22aa5c  ldc.i4   0x6562A41B
0x22aa61  bgt.un.s loc_22AA7E
0x22aa63  ldloc.2
0x22aa64  ldc.i4   0x63641717
0x22aa69  beq      loc_22ACB4
0x22aa6e  ldloc.2
0x22aa6f  ldc.i4   0x6562A41B
0x22aa74  beq      loc_22AC60
0x22aa79  br       loc_22AE76
0x22aa7e  ldloc.2
0x22aa7f  ldc.i4   0x6E3A33CC
0x22aa84  beq      loc_22AD9B
0x22aa89  ldloc.2
0x22aa8a  ldc.i4   0x7F14EC0A
0x22aa8f  beq      loc_22AD32
0x22aa94  ldloc.2
0x22aa95  ldc.i4   0x801C149D
0x22aa9a  beq      loc_22ABF7
0x22aa9f  br       loc_22AE76
0x22aaa4  ldloc.2
0x22aaa5  ldc.i4   0xAA707564
0x22aaaa  bgt.un   loc_22AB3E
0x22aaaf  ldloc.2
0x22aab0  ldc.i4   0x909E0913
0x22aab5  bgt.un.s loc_22AAF5
0x22aab7  ldloc.2
0x22aab8  ldc.i4   0x86903830
0x22aabd  bgt.un.s loc_22AADA
0x22aabf  ldloc.2
0x22aac0  ldc.i4   0x8331481E
0x22aac5  beq      loc_22ADB0
0x22aaca  ldloc.2
0x22aacb  ldc.i4   0x86903830
0x22aad0  beq      loc_22ADEF
0x22aad5  br       loc_22AE76
0x22aada  ldloc.2
0x22aadb  ldc.i4   0x8E3EBF60
0x22aae0  beq      loc_22AD47
0x22aae5  ldloc.2
0x22aae6  ldc.i4   0x909E0913
0x22aaeb  beq      loc_22AE1C
0x22aaf0  br       loc_22AE76
0x22aaf5  ldloc.2
0x22aaf6  ldc.i4   0x984AC6BF
0x22aafb  bgt.un.s loc_22AB18
0x22aafd  ldloc.2
0x22aafe  ldc.i4   0x9595C91D
0x22ab03  beq      loc_22AC0C
0x22ab08  ldloc.2
0x22ab09  ldc.i4   0x984AC6BF
0x22ab0e  beq      loc_22AD86
0x22ab13  br       loc_22AE76
0x22ab18  ldloc.2
0x22ab19  ldc.i4   0xA7AC161B
0x22ab1e  beq      loc_22AE58
0x22ab23  ldloc.2
0x22ab24  ldc.i4   0xAA439C79
0x22ab29  beq      loc_22AE3A
0x22ab2e  ldloc.2
0x22ab2f  ldc.i4   0xAA707564
0x22ab34  beq      loc_22ABCD
0x22ab39  br       loc_22AE76
0x22ab3e  ldloc.2
0x22ab3f  ldc.i4   0xC5008070
0x22ab44  bgt.un.s loc_22AB84
0x22ab46  ldloc.2
0x22ab47  ldc.i4   0xBF32E99B
0x22ab4c  bgt.un.s loc_22AB69
0x22ab4e  ldloc.2
0x22ab4f  ldc.i4   0xAC9B8E27
0x22ab54  beq      loc_22ACDE
0x22ab59  ldloc.2
0x22ab5a  ldc.i4   0xBF32E99B
0x22ab5f  beq      loc_22ACF3
0x22ab64  br       loc_22AE76
0x22ab69  ldloc.2
0x22ab6a  ldc.i4   0xC382898D
0x22ab6f  beq      loc_22ADFE
0x22ab74  ldloc.2
0x22ab75  ldc.i4   0xC5008070
0x22ab7a  beq      loc_22AC9F
0x22ab7f  br       loc_22AE76
0x22ab84  ldloc.2
0x22ab85  ldc.i4   0xE039EB62
0x22ab8a  bgt.un.s loc_22ABA7
0x22ab8c  ldloc.2
0x22ab8d  ldc.i4   0xDC00C611
0x22ab92  beq      loc_22AE49
0x22ab97  ldloc.2
0x22ab98  ldc.i4   0xE039EB62
0x22ab9d  beq      loc_22AC75
0x22aba2  br       loc_22AE76
0x22aba7  ldloc.2
0x22aba8  ldc.i4   0xE072EFC3
0x22abad  beq      loc_22ACC9
0x22abb2  ldloc.2
0x22abb3  ldc.i4   0xE3E7D4FA
0x22abb8  beq      loc_22AD71
0x22abbd  ldloc.2
0x22abbe  ldc.i4   0xFCE5CD50
0x22abc3  beq      loc_22AE0D
0x22abc8  br       loc_22AE76
0x22abcd  ldloc.1
0x22abce  ldstr    aWhoami// "WhoAmI"
0x22abd3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22abd8  brtrue   loc_22AE74
0x22abdd  br       loc_22AE76
0x22abe2  ldloc.1
0x22abe3  ldstr    aRetrievefilter_0// "RetrieveFilteredForms"
0x22abe8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22abed  brtrue   loc_22AE74
0x22abf2  br       loc_22AE76
0x22abf7  ldloc.1
0x22abf8  ldstr    aTriggerservice// "TriggerServiceEndpointCheck"
0x22abfd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac02  brtrue   loc_22AE74
0x22ac07  br       loc_22AE76
0x22ac0c  ldloc.1
0x22ac0d  ldstr    aQueryexpressio_1// "QueryExpressionToFetchXml"
0x22ac12  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac17  brtrue   loc_22AE74
0x22ac1c  br       loc_22AE76
0x22ac21  ldloc.1
0x22ac22  ldstr    aFetchxmltoquer// "FetchXmlToQueryExpression"
0x22ac27  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac2c  brtrue   loc_22AE74
0x22ac31  br       loc_22AE76
0x22ac36  ldloc.1
0x22ac37  ldstr    aFirenotificati// "FireNotificationEvent"
0x22ac3c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac41  brtrue   loc_22AE74
0x22ac46  br       loc_22AE76
0x22ac4b  ldloc.1
0x22ac4c  ldstr    aRetrievemetada// "RetrieveMetadataChanges"
0x22ac51  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac56  brtrue   loc_22AE74
0x22ac5b  br       loc_22AE76
0x22ac60  ldloc.1
0x22ac61  ldstr    aRetrieveentity_4// "RetrieveEntityChanges"
0x22ac66  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac6b  brtrue   loc_22AE74
0x22ac70  br       loc_22AE76
0x22ac75  ldloc.1
0x22ac76  ldstr    aRetrieveprovis_0// "RetrieveProvisionedLanguagePackVersion"
0x22ac7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac80  brtrue   loc_22AE74
0x22ac85  br       loc_22AE76
0x22ac8a  ldloc.1
0x22ac8b  ldstr    aRetrieveinstal// "RetrieveInstalledLanguagePackVersion"
0x22ac90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ac95  brtrue   loc_22AE74
0x22ac9a  br       loc_22AE76
0x22ac9f  ldloc.1
0x22aca0  ldstr    aRetrieveprovis// "RetrieveProvisionedLanguages"
0x22aca5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22acaa  brtrue   loc_22AE74
0x22acaf  br       loc_22AE76
0x22acb4  ldloc.1
0x22acb5  ldstr    aRetrieveavaila// "RetrieveAvailableLanguages"
0x22acba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22acbf  brtrue   loc_22AE74
0x22acc4  br       loc_22AE76
0x22acc9  ldloc.1
0x22acca  ldstr    aRetrievedeprov// "RetrieveDeprovisionedLanguages"
0x22accf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22acd4  brtrue   loc_22AE74
0x22acd9  br       loc_22AE76
0x22acde  ldloc.1
0x22acdf  ldstr    aRetrieveinstal_0// "RetrieveInstalledLanguagePacks"
0x22ace4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ace9  brtrue   loc_22AE74
0x22acee  br       loc_22AE76
0x22acf3  ldloc.1
0x22acf4  ldstr    aRetrieveprinci// "RetrievePrincipalAccess"
0x22acf9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22acfe  brtrue   loc_22AE74
0x22ad03  br       loc_22AE76
0x22ad08  ldloc.1
0x22ad09  ldstr    aGetalltimezone// "GetAllTimeZonesWithDisplayName"
0x22ad0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad13  brtrue   loc_22AE74
0x22ad18  br       loc_22AE76
0x22ad1d  ldloc.1
0x22ad1e  ldstr    aGettimezonecod// "GetTimeZoneCodeByLocalizedName"
0x22ad23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad28  brtrue   loc_22AE74
0x22ad2d  br       loc_22AE76
0x22ad32  ldloc.1
0x22ad33  ldstr    aIsreportingdat// "IsReportingDataConnectorInstalled"
0x22ad38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad3d  brtrue   loc_22AE74
0x22ad42  br       loc_22AE76
0x22ad47  ldloc.1
0x22ad48  ldstr    aLocaltimefromu// "LocalTimeFromUtcTime"
0x22ad4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad52  brtrue   loc_22AE74
0x22ad57  br       loc_22AE76
0x22ad5c  ldloc.1
0x22ad5d  ldstr    aIsbackofficein// "IsBackOfficeInstalled"
0x22ad62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad67  brtrue   loc_22AE74
0x22ad6c  br       loc_22AE76
0x22ad71  ldloc.1
0x22ad72  ldstr    aFormataddress// "FormatAddress"
0x22ad77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad7c  brtrue   loc_22AE74
0x22ad81  br       loc_22AE76
0x22ad86  ldloc.1
0x22ad87  ldstr    aIssupportuserr// "IsSupportUserRole"
0x22ad8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ad91  brtrue   loc_22AE74
0x22ad96  br       loc_22AE76
0x22ad9b  ldloc.1
0x22ad9c  ldstr    aIscomponentcus// "IsComponentCustomizable"
0x22ada1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22ada6  brtrue   loc_22AE74
0x22adab  br       loc_22AE76
0x22adb0  ldloc.1
0x22adb1  ldstr    aConfigurerepor// "ConfigureReportingDataConnector"
0x22adb6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22adbb  brtrue   loc_22AE74
0x22adc0  br       loc_22AE76
0x22adc5  ldloc.1
0x22adc6  ldstr    aCheckclientcom// "CheckClientCompatibility"
0x22adcb  call     bool [mscorlib]System.String::op_Equality(string, string)
  ... truncated ...
```
