# Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::CreateFieldTemplate

- ea: `0xd6690`
- end: `0xd6c83`
- name: `Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::CreateFieldTemplate`
- size: `1523`
- prototype: ``
- caller_count: `1`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0xd61f0`

## callees

- `0xd6650`
- `0xd6670`
- `0xd6690`
- `0xd9750`
- `0xd9770`
- `0xdb360`
- `0xdb3e0`
- `0xdbc60`
- `0xdbce0`
- `0xdbd40`
- `0xdbdf0`
- `0xdbe60`
- `0xdc080`
- `0xdc3e0`
- `0xdc450`
- `0xdc5a0`
- `0xdc600`
- `0xdc640`
- `0xdc680`
- `0xdca10`
- `0xdcbc0`
- `0xdcc10`
- `0xdd2e0`
- `0xde090`
- `0xf0f70`
- `0xf4470`
- `0xf4540`
- `0xf46e0`
- `0xf4840`

## string_xrefs

- `0xd699e`: `Crm.EmailTemplateGlobal`
- `0xd6a4e`: `Crm.ServiceTimeCode`

## pseudocode

```c

```

## disassembly

```asm
0xd6690  ldnull
0xd6691  stloc.0
0xd6692  ldnull
0xd6693  stloc.1
0xd6694  ldarg.1
0xd6695  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_EntityName()
0xd669a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xd669f  brtrue.s loc_D66C4
0xd66a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0xd66a6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xd66ab  ldarg.1
0xd66ac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_EntityName()
0xd66b1  ldc.i4.1
0xd66b2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xd66b7  ldarg.1
0xd66b8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_FieldName()
0xd66bd  ldc.i4.1
0xd66be  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0xd66c3  stloc.1
0xd66c4  ldarg.0
0xd66c5  ldloc.1
0xd66c6  call     instance int32 Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::GetPrecision(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attrMetadata)
0xd66cb  stloc.2
0xd66cc  ldarg.0
0xd66cd  ldloc.1
0xd66ce  call     instance string Microsoft.Crm.Application.Controls.Grid.UI.LayoutProviderExportToExcelGridList::GetFormat(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attrMetadata)
0xd66d3  stloc.3
0xd66d4  ldarg.1
0xd66d5  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.Column::get_UIInfo()
0xd66da  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Grid.ColumnUIInfo::get_RendererType()
0xd66df  stloc.s  4
0xd66e1  ldloc.s  4
0xd66e3  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xd66e8  stloc.s  5
0xd66ea  ldloc.s  5
0xd66ec  ldc.i4   0x95241A3A
0xd66f1  bgt.un   loc_D67E9
0xd66f6  ldloc.s  5
0xd66f8  ldc.i4   0x3DF5F53A
0xd66fd  bgt.un.s loc_D6774
0xd66ff  ldloc.s  5
0xd6701  ldc.i4   0x1F088D4C
0xd6706  bgt.un.s loc_D6731
0xd6708  ldloc.s  5
0xd670a  ldc.i4   0x12860A02
0xd670f  beq      loc_D6AA4
0xd6714  ldloc.s  5
0xd6716  ldc.i4   0x1BE34ABF
0xd671b  beq      loc_D69F4
0xd6720  ldloc.s  5
0xd6722  ldc.i4   0x1F088D4C
0xd6727  beq      loc_D6B12
0xd672c  br       loc_D6C2E
0xd6731  ldloc.s  5
0xd6733  ldc.i4   0x37F9F65B
0xd6738  bgt.un.s loc_D6757
0xd673a  ldloc.s  5
0xd673c  ldc.i4   0x223B3F22
0xd6741  beq      loc_D6A36
0xd6746  ldloc.s  5
0xd6748  ldc.i4   0x37F9F65B
0xd674d  beq      loc_D6A78
0xd6752  br       loc_D6C2E
0xd6757  ldloc.s  5
0xd6759  ldc.i4   0x3902F19C
0xd675e  beq      loc_D69C8
0xd6763  ldloc.s  5
0xd6765  ldc.i4   0x3DF5F53A
0xd676a  beq      loc_D6986
0xd676f  br       loc_D6C2E
0xd6774  ldloc.s  5
0xd6776  ldc.i4   0x7E0C3808
0xd677b  bgt.un.s loc_D67A6
0xd677d  ldloc.s  5
0xd677f  ldc.i4   0x65BAC4B6
0xd6784  beq      loc_D6A4C
0xd6789  ldloc.s  5
0xd678b  ldc.i4   0x7415F11E
0xd6790  beq      loc_D695A
0xd6795  ldloc.s  5
0xd6797  ldc.i4   0x7E0C3808
0xd679c  beq      loc_D69DE
0xd67a1  br       loc_D6C2E
0xd67a6  ldloc.s  5
0xd67a8  ldc.i4   0x8B9FE088
0xd67ad  bgt.un.s loc_D67CC
0xd67af  ldloc.s  5
0xd67b1  ldc.i4   0x8AB0F193
0xd67b6  beq      loc_D692E
0xd67bb  ldloc.s  5
0xd67bd  ldc.i4   0x8B9FE088
0xd67c2  beq      loc_D6970
0xd67c7  br       loc_D6C2E
0xd67cc  ldloc.s  5
0xd67ce  ldc.i4   0x94861273
0xd67d3  beq      loc_D6944
0xd67d8  ldloc.s  5
0xd67da  ldc.i4   0x95241A3A
0xd67df  beq      loc_D6A8E
0xd67e4  br       loc_D6C2E
0xd67e9  ldloc.s  5
0xd67eb  ldc.i4   0xC5BD6133
0xd67f0  bgt.un.s loc_D6867
0xd67f2  ldloc.s  5
0xd67f4  ldc.i4   0xA6C45D85
0xd67f9  bgt.un.s loc_D6824
0xd67fb  ldloc.s  5
0xd67fd  ldc.i4   0x95E97E5E
0xd6802  beq      loc_D6AE6
0xd6807  ldloc.s  5
0xd6809  ldc.i4   0xA4BDAA19
0xd680e  beq      loc_D6918
0xd6813  ldloc.s  5
0xd6815  ldc.i4   0xA6C45D85
0xd681a  beq      loc_D6AFC
0xd681f  br       loc_D6C2E
0xd6824  ldloc.s  5
0xd6826  ldc.i4   0xC1C33E1F
0xd682b  bgt.un.s loc_D684A
0xd682d  ldloc.s  5
0xd682f  ldc.i4   0xC1374E85
0xd6834  beq      loc_D6AD0
0xd6839  ldloc.s  5
0xd683b  ldc.i4   0xC1C33E1F
0xd6840  beq      loc_D68D6
0xd6845  br       loc_D6C2E
0xd684a  ldloc.s  5
0xd684c  ldc.i4   0xC40B0CF7
0xd6851  beq      loc_D6A20
0xd6856  ldloc.s  5
0xd6858  ldc.i4   0xC5BD6133
0xd685d  beq      loc_D6A62
0xd6862  br       loc_D6C2E
0xd6867  ldloc.s  5
0xd6869  ldc.i4   0xDA35889F
0xd686e  bgt.un.s loc_D6899
0xd6870  ldloc.s  5
0xd6872  ldc.i4   0xCCEA6D90
0xd6877  beq      loc_D6ABA
0xd687c  ldloc.s  5
0xd687e  ldc.i4   0xD1631704
0xd6883  beq      loc_D699C
0xd6888  ldloc.s  5
0xd688a  ldc.i4   0xDA35889F
0xd688f  beq      loc_D69B2
0xd6894  br       loc_D6C2E
0xd6899  ldloc.s  5
0xd689b  ldc.i4   0xF4293B18
0xd68a0  bgt.un.s loc_D68BF
0xd68a2  ldloc.s  5
0xd68a4  ldc.i4   0xE150C94F
0xd68a9  beq      loc_D6B28
0xd68ae  ldloc.s  5
0xd68b0  ldc.i4   0xF4293B18
0xd68b5  beq      loc_D6A0A
0xd68ba  br       loc_D6C2E
0xd68bf  ldloc.s  5
0xd68c1  ldc.i4   0xF5674CD4
0xd68c6  beq.s    loc_D6902
0xd68c8  ldloc.s  5
0xd68ca  ldc.i4   0xF758858B
0xd68cf  beq.s    loc_D68EC
0xd68d1  br       loc_D6C2E
0xd68d6  ldloc.s  4
0xd68d8  ldstr    aPartylist// "partylist"
0xd68dd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd68e2  brtrue   loc_D6B3E
0xd68e7  br       loc_D6C2E
0xd68ec  ldloc.s  4
0xd68ee  ldstr    aLookup// "lookup"
0xd68f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd68f8  brtrue   loc_D6B49
0xd68fd  br       loc_D6C2E
0xd6902  ldloc.s  4
0xd6904  ldstr    aOwner// "owner"
0xd6909  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd690e  brtrue   loc_D6B49
0xd6913  br       loc_D6C2E
0xd6918  ldloc.s  4
0xd691a  ldstr    aCustomer// "customer"
0xd691f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6924  brtrue   loc_D6B49
0xd6929  br       loc_D6C2E
0xd692e  ldloc.s  4
0xd6930  ldstr    aCrmDisablelook// "Crm.DisableLookup"
0xd6935  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd693a  brtrue   loc_D6B49
0xd693f  br       loc_D6C2E
0xd6944  ldloc.s  4
0xd6946  ldstr    aCrmStarttimefo// "Crm.StartTimeFormat"
0xd694b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6950  brtrue   loc_D6B54
0xd6955  br       loc_D6C2E
0xd695a  ldloc.s  4
0xd695c  ldstr    aCrmEndtimeform// "Crm.EndTimeFormat"
0xd6961  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6966  brtrue   loc_D6B5F
0xd696b  br       loc_D6C2E
0xd6970  ldloc.s  4
0xd6972  ldstr    aCrmReturnedtyp// "Crm.ReturnedType"
0xd6977  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd697c  brtrue   loc_D6B6A
0xd6981  br       loc_D6C2E
0xd6986  ldloc.s  4
0xd6988  ldstr    aCrmUserdatetim// "Crm.UserDateTimeFormat"
0xd698d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6992  brtrue   loc_D6B75
0xd6997  br       loc_D6C2E
0xd699c  ldloc.s  4
0xd699e  ldstr    aCrmEmailtempla// "Crm.EmailTemplateGlobal"
0xd69a3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd69a8  brtrue   loc_D6B80
0xd69ad  br       loc_D6C2E
0xd69b2  ldloc.s  4
0xd69b4  ldstr    aCrmLanguagecod// "Crm.LanguageCodeFormat"
0xd69b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd69be  brtrue   loc_D6B8B
0xd69c3  br       loc_D6C2E
0xd69c8  ldloc.s  4
0xd69ca  ldstr    aCrmPercentagef// "Crm.PercentageFormat"
0xd69cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd69d4  brtrue   loc_D6B96
0xd69d9  br       loc_D6C2E
0xd69de  ldloc.s  4
0xd69e0  ldstr    aCrmDurationfor// "Crm.DurationFormat"
0xd69e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd69ea  brtrue   loc_D6BA1
0xd69ef  br       loc_D6C2E
0xd69f4  ldloc.s  4
0xd69f6  ldstr    aCrmTimezonefor// "Crm.TimezoneFormat"
0xd69fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a00  brtrue   loc_D6BAC
0xd6a05  br       loc_D6C2E
0xd6a0a  ldloc.s  4
0xd6a0c  ldstr    aCrmSystemregar// "Crm.SystemRegardingObject"
0xd6a11  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a16  brtrue   loc_D6BB7
0xd6a1b  br       loc_D6C2E
0xd6a20  ldloc.s  4
0xd6a22  ldstr    aCrmErrordescri// "Crm.ErrorDescription"
0xd6a27  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a2c  brtrue   loc_D6BC2
0xd6a31  br       loc_D6C2E
0xd6a36  ldloc.s  4
0xd6a38  ldstr    aCrmErrornumber// "Crm.ErrorNumber"
0xd6a3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a42  brtrue   loc_D6BCD
0xd6a47  br       loc_D6C2E
0xd6a4c  ldloc.s  4
0xd6a4e  ldstr    aCrmServicetime// "Crm.ServiceTimeCode"
0xd6a53  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a58  brtrue   loc_D6BD8
0xd6a5d  br       loc_D6C2E
0xd6a62  ldloc.s  4
0xd6a64  ldstr    aCrmSdkmessagef// "Crm.SdkMessageFilterTypeCode"
0xd6a69  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a6e  brtrue   loc_D6BE3
0xd6a73  br       loc_D6C2E
0xd6a78  ldloc.s  4
0xd6a7a  ldstr    aCrmSolutionimp// "Crm.SolutionImportStatus"
0xd6a7f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a84  brtrue   loc_D6BEE
0xd6a89  br       loc_D6C2E
0xd6a8e  ldloc.s  4
0xd6a90  ldstr    aCrmHolidaysdur// "Crm.HolidaysDuration"
0xd6a95  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6a9a  brtrue   loc_D6BF6
0xd6a9f  br       loc_D6C2E
0xd6aa4  ldloc.s  4
0xd6aa6  ldstr    aCrmEmptycolumn// "Crm.EmptyColumn"
0xd6aab  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6ab0  brtrue   loc_D6BFE
0xd6ab5  br       loc_D6C2E
0xd6aba  ldloc.s  4
0xd6abc  ldstr    aDatetime// "datetime"
0xd6ac1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6ac6  brtrue   loc_D6C06
0xd6acb  br       loc_D6C2E
0xd6ad0  ldloc.s  4
0xd6ad2  ldstr    aCrmHtmltext// "Crm.HtmlText"
0xd6ad7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6adc  brtrue   loc_D6C0F
0xd6ae1  br       loc_D6C2E
0xd6ae6  ldloc.s  4
0xd6ae8  ldstr    aInt// "int"
0xd6aed  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6af2  brtrue   loc_D6C17
0xd6af7  br       loc_D6C2E
0xd6afc  ldloc.s  4
0xd6afe  ldstr    aFloat// "float"
0xd6b03  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6b08  brtrue   loc_D6C17
0xd6b0d  br       loc_D6C2E
0xd6b12  ldloc.s  4
0xd6b14  ldstr    aDecimal// "decimal"
0xd6b19  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6b1e  brtrue   loc_D6C17
0xd6b23  br       loc_D6C2E
0xd6b28  ldloc.s  4
0xd6b2a  ldstr    aMoney// "money"
  ... truncated ...
```
