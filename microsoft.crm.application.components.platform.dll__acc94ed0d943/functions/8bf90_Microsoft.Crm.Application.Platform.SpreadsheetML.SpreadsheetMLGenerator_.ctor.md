# Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::.ctor

- ea: `0x8bf90`
- end: `0x8c1ef`
- name: `Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::.ctor`
- size: `607`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x66d0`
- `0x11760`
- `0x2fb90`
- `0x2fbc0`
- `0x30260`
- `0x3a980`
- `0x8bf20`
- `0x8bf90`

## string_xrefs

- `0x8bf96`: `IW_ExportTemplate_RequiredField`
- `0x8bfab`: `IW_ExportTemplate_TextField`
- `0x8bfc0`: `IW_ExportTemplate_DecimalField`
- `0x8bfd5`: `IW_ExportTemplate_IntegerField`
- `0x8bfea`: `IW_ExportTemplate_DateField`
- `0x8bfff`: `IW_ExportTemplate_DateTimeField`
- `0x8c014`: `IW_ExportTemplate_PicklistField`
- `0x8c029`: `IW_ExportTemplate_LookupField`
- `0x8c03e`: `IW_ExportTemplate_MaxLength`
- `0x8c053`: `IW_ExportTemplate_MinValue`
- `0x8c068`: `IW_ExportTemplate_MaxValue`
- `0x8c07d`: `IW_ExportTemplate_PicklistValue`
- `0x8c092`: `IW_ExportTemplate_LengthExceeded_Title`
- `0x8c0a7`: `IW_ExportTemplate_DecimalRange_Title`
- `0x8c0bc`: `IW_ExportTemplate_InvalidInteger_Title`
- `0x8c0d1`: `IW_ExportTemplate_InvalidDate_Title`
- `0x8c0e6`: `IW_ExportTemplate_InvalidDateTime_Title`
- `0x8c0fb`: `IW_ExportTemplate_InvalidListValue_Title`
- `0x8c110`: `IW_ExportTemplate_LengthExceeded_Message`
- `0x8c125`: `IW_ExportTemplate_DecimalRange_Message`
- `0x8c13a`: `IW_ExportTemplate_InvalidInteger_Message`
- `0x8c14f`: `IW_ExportTemplate_InvalidDate_Message`
- `0x8c164`: `IW_ExportTemplate_InvalidDateTime_Message`
- `0x8c179`: `IW_ExportTemplate_InvalidListValue_Message`

## pseudocode

```c

```

## disassembly

```asm
0x8bf90  ldarg.0
0x8bf91  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bf96  ldstr    aIwExporttempla// "IW_ExportTemplate_RequiredField"
0x8bf9b  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8bfa0  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::requiredFieldInputTitle
0x8bfa5  ldarg.0
0x8bfa6  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bfab  ldstr    aIwExporttempla_0// "IW_ExportTemplate_TextField"
0x8bfb0  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8bfb5  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::textFieldInputTitle
0x8bfba  ldarg.0
0x8bfbb  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bfc0  ldstr    aIwExporttempla_1// "IW_ExportTemplate_DecimalField"
0x8bfc5  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8bfca  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldInputTitle
0x8bfcf  ldarg.0
0x8bfd0  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bfd5  ldstr    aIwExporttempla_2// "IW_ExportTemplate_IntegerField"
0x8bfda  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8bfdf  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldInputTitle
0x8bfe4  ldarg.0
0x8bfe5  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bfea  ldstr    aIwExporttempla_3// "IW_ExportTemplate_DateField"
0x8bfef  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8bff4  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldInputTitle
0x8bff9  ldarg.0
0x8bffa  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8bfff  ldstr    aIwExporttempla_4// "IW_ExportTemplate_DateTimeField"
0x8c004  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c009  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateTimeFieldInputTitle
0x8c00e  ldarg.0
0x8c00f  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c014  ldstr    aIwExporttempla_5// "IW_ExportTemplate_PicklistField"
0x8c019  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c01e  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::picklistFieldInputTitle
0x8c023  ldarg.0
0x8c024  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c029  ldstr    aIwExporttempla_6// "IW_ExportTemplate_LookupField"
0x8c02e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c033  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::lookupFieldInputTitle
0x8c038  ldarg.0
0x8c039  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c03e  ldstr    aIwExporttempla_7// "IW_ExportTemplate_MaxLength"
0x8c043  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c048  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxLengthInputMessageFormat
0x8c04d  ldarg.0
0x8c04e  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c053  ldstr    aIwExporttempla_8// "IW_ExportTemplate_MinValue"
0x8c058  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c05d  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::minValueInputMessageFormat
0x8c062  ldarg.0
0x8c063  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c068  ldstr    aIwExporttempla_9// "IW_ExportTemplate_MaxValue"
0x8c06d  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c072  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxValueInputMessageFormat
0x8c077  ldarg.0
0x8c078  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c07d  ldstr    aIwExporttempla_10// "IW_ExportTemplate_PicklistValue"
0x8c082  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c087  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::picklistFieldInputMessage
0x8c08c  ldarg.0
0x8c08d  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c092  ldstr    aIwExporttempla_11// "IW_ExportTemplate_LengthExceeded_Title"
0x8c097  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c09c  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::textFieldErrorTitle
0x8c0a1  ldarg.0
0x8c0a2  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c0a7  ldstr    aIwExporttempla_12// "IW_ExportTemplate_DecimalRange_Title"
0x8c0ac  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c0b1  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldErrorTitle
0x8c0b6  ldarg.0
0x8c0b7  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c0bc  ldstr    aIwExporttempla_13// "IW_ExportTemplate_InvalidInteger_Title"
0x8c0c1  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c0c6  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldErrorTitle
0x8c0cb  ldarg.0
0x8c0cc  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c0d1  ldstr    aIwExporttempla_14// "IW_ExportTemplate_InvalidDate_Title"
0x8c0d6  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c0db  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldErrorTitle
0x8c0e0  ldarg.0
0x8c0e1  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c0e6  ldstr    aIwExporttempla_15// "IW_ExportTemplate_InvalidDateTime_Title"
0x8c0eb  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c0f0  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateTimeFieldErrorTitle
0x8c0f5  ldarg.0
0x8c0f6  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c0fb  ldstr    aIwExporttempla_16// "IW_ExportTemplate_InvalidListValue_Titl"...
0x8c100  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c105  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::picklistFieldErrorTitle
0x8c10a  ldarg.0
0x8c10b  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c110  ldstr    aIwExporttempla_17// "IW_ExportTemplate_LengthExceeded_Messag"...
0x8c115  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c11a  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxLengthErrorMessageFormat
0x8c11f  ldarg.0
0x8c120  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c125  ldstr    aIwExporttempla_18// "IW_ExportTemplate_DecimalRange_Message"
0x8c12a  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c12f  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::decimalFieldErrorMessageFormat
0x8c134  ldarg.0
0x8c135  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c13a  ldstr    aIwExporttempla_19// "IW_ExportTemplate_InvalidInteger_Messag"...
0x8c13f  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c144  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::integerFieldErrorMessageFormat
0x8c149  ldarg.0
0x8c14a  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c14f  ldstr    aIwExporttempla_20// "IW_ExportTemplate_InvalidDate_Message"
0x8c154  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c159  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateFieldErrorMessageFormat
0x8c15e  ldarg.0
0x8c15f  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c164  ldstr    aIwExporttempla_21// "IW_ExportTemplate_InvalidDateTime_Messa"...
0x8c169  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c16e  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::dateTimeFieldErrorMessageFormat
0x8c173  ldarg.0
0x8c174  call     class Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x8c179  ldstr    aIwExporttempla_22// "IW_ExportTemplate_InvalidListValue_Mess"...
0x8c17e  callvirt instance string Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string name)
0x8c183  stfld    string Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::picklistFieldErrorMessage
0x8c188  ldarg.0
0x8c189  call     instance void [mscorlib]System.Object::.ctor()
0x8c18e  ldarg.1
0x8c18f  brfalse.s loc_8C194
0x8c191  ldarg.2
0x8c192  brtrue.s loc_8C19F
0x8c194  ldstr    aNeedNonNullShe// "need non-null sheetProperties and attri"...
0x8c199  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x8c19e  throw
0x8c19f  ldarg.0
0x8c1a0  ldarg.1
0x8c1a1  stfld    class Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetProperties Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_sheetProperties
0x8c1a6  ldarg.0
0x8c1a7  ldarg.2
0x8c1a8  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Platform.SpreadsheetML.AttributeProperties> Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::_attributePropertiesList
0x8c1ad  ldarg.0
0x8c1ae  call     int32 Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::get_MaximumPrecisionAcrossCurrencies()
0x8c1b3  stfld    int32 Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::maxPrecisionAcrossCurrencies
0x8c1b8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationCache::Instance()
0x8c1bd  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c1c2  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x8c1c7  call     class Microsoft.Crm.Application.Security.UserInformation Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x8c1cc  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings>::LookupEntry(void, var<u1>)
0x8c1d1  stloc.0
0x8c1d2  ldarg.0
0x8c1d3  ldloc.0
0x8c1d4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_PricingDecimalPrecision()
0x8c1d9  stfld    int32 Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::pricingDecimalPrecision
0x8c1de  ldarg.0
0x8c1df  call     class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x8c1e4  newobj   instance void Microsoft.Crm.ExcelNumberFormats::.ctor(class [mscorlib]System.Globalization.CultureInfo cultureInfo)
0x8c1e9  stfld    class Microsoft.Crm.ExcelNumberFormats Microsoft.Crm.Application.Platform.SpreadsheetML.SpreadsheetMLGenerator::excelFormats
0x8c1ee  ret
```
