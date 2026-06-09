# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo_0

- ea: `0x430`
- end: `0xae7`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetAttributeInfo_0`
- size: `1719`
- prototype: ``
- caller_count: `3`
- callee_count: `29`
- tags: `service_task, broker_com_uri`

## callers

- `0x420`
- `0x20e0`
- `0x2b70`

## callees

- `0x190`
- `0x1a0`
- `0x200`
- `0x220`
- `0x270`
- `0x2b0`
- `0x360`
- `0x430`
- `0xaf0`
- `0xbe0`
- `0x1000`
- `0x13e0`
- `0x1400`
- `0x14e0`
- `0x1580`
- `0x1650`
- `0x1740`
- `0x17d0`
- `0x18b0`
- `0x18e0`
- `0x1900`
- `0x1920`
- `0x1a10`
- `0x1b30`
- `0x1b50`
- `0x1b70`
- `0x1bd0`
- `0x1e90`
- `0xbf70`

## string_xrefs

- `0x9a4`: `isfieldsecurityenabled`
- `0x9b2`: `isfieldsecurityenabled`
- `0xa68`: `linkedattributeid`
- `0xa99`: `linkedattributeid`

## pseudocode

```c

```

## disassembly

```asm
0x430  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x435  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x43a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x43f  stloc.0
0x440  ldnull
0x441  stloc.1
0x442  ldarg.0
0x443  ldstr    aType// "type"
0x448  callvirt instance class Microsoft.Crm.Application.WebServices.ParameterBag Microsoft.Crm.Application.WebServices.ParameterBag::GetBag(string name)
0x44d  stloc.2
0x44e  ldarg.1
0x44f  brtrue.s loc_45E
0x451  ldloc.2
0x452  ldstr    aName// "name"
0x457  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name)
0x45c  br.s     loc_469
0x45e  ldarg.1
0x45f  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x464  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x469  stloc.3
0x46a  ldloc.3
0x46b  ldarg.1
0x46c  ldnull
0x46d  ceq
0x46f  call     void Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::ValidateType(string typeName, bool forCreate)
0x474  ldloc.3
0x475  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x47a  stloc.s  4
0x47c  ldloc.s  4
0x47e  ldc.i4   0xB35135FA
0x483  bgt.un   loc_523
0x488  ldloc.s  4
0x48a  ldc.i4   0x63B39A70
0x48f  bgt.un.s loc_4D4
0x491  ldloc.s  4
0x493  ldc.i4   0x5BC874BE
0x498  bgt.un.s loc_4B7
0x49a  ldloc.s  4
0x49c  ldc.i4   0x1F088D4C
0x4a1  beq      loc_645
0x4a6  ldloc.s  4
0x4a8  ldc.i4   0x5BC874BE
0x4ad  beq      loc_5C7
0x4b2  br       loc_812
0x4b7  ldloc.s  4
0x4b9  ldc.i4   0x60CAE230
0x4be  beq      loc_606
0x4c3  ldloc.s  4
0x4c5  ldc.i4   0x63B39A70
0x4ca  beq      loc_6AE
0x4cf  br       loc_812
0x4d4  ldloc.s  4
0x4d6  ldc.i4   0x95E97E5E
0x4db  bgt.un.s loc_4FA
0x4dd  ldloc.s  4
0x4df  ldc.i4   0x783132F6
0x4e4  beq      loc_6C3
0x4e9  ldloc.s  4
0x4eb  ldc.i4   0x95E97E5E
0x4f0  beq      loc_61B
0x4f5  br       loc_812
0x4fa  ldloc.s  4
0x4fc  ldc.i4   0xA4BDAA19
0x501  beq      loc_72C
0x506  ldloc.s  4
0x508  ldc.i4   0xA6C45D85
0x50d  beq      loc_630
0x512  ldloc.s  4
0x514  ldc.i4   0xB35135FA
0x519  beq      loc_741
0x51e  br       loc_812
0x523  ldloc.s  4
0x525  ldc.i4   0xCCEA6D90
0x52a  bgt.un.s loc_57B
0x52c  ldloc.s  4
0x52e  ldc.i4   0xBAC37203
0x533  bgt.un.s loc_552
0x535  ldloc.s  4
0x537  ldc.i4   0xBA4B77EF
0x53c  beq      loc_6D8
0x541  ldloc.s  4
0x543  ldc.i4   0xBAC37203
0x548  beq      loc_5F1
0x54d  br       loc_812
0x552  ldloc.s  4
0x554  ldc.i4   0xC1C33E1F
0x559  beq      loc_702
0x55e  ldloc.s  4
0x560  ldc.i4   0xCC898375
0x565  beq      loc_717
0x56a  ldloc.s  4
0x56c  ldc.i4   0xCCEA6D90
0x571  beq      loc_684
0x576  br       loc_812
0x57b  ldloc.s  4
0x57d  ldc.i4   0xE150C94F
0x582  bgt.un.s loc_59E
0x584  ldloc.s  4
0x586  ldc.i4   0xD9844140
0x58b  beq.s    loc_5DC
0x58d  ldloc.s  4
0x58f  ldc.i4   0xE150C94F
0x594  beq      loc_65A
0x599  br       loc_812
0x59e  ldloc.s  4
0x5a0  ldc.i4   0xE98BD702
0x5a5  beq      loc_66F
0x5aa  ldloc.s  4
0x5ac  ldc.i4   0xF5674CD4
0x5b1  beq      loc_6ED
0x5b6  ldloc.s  4
0x5b8  ldc.i4   0xF758858B
0x5bd  beq      loc_699
0x5c2  br       loc_812
0x5c7  ldloc.3
0x5c8  ldstr    aNvarchar// "nvarchar"
0x5cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5d2  brtrue   loc_756
0x5d7  br       loc_812
0x5dc  ldloc.3
0x5dd  ldstr    aPicklist// "picklist"
0x5e2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5e7  brtrue   loc_763
0x5ec  br       loc_812
0x5f1  ldloc.3
0x5f2  ldstr    aMultiselectpic// "multiselectpicklist"
0x5f7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5fc  brtrue   loc_771
0x601  br       loc_812
0x606  ldloc.3
0x607  ldstr    aBit// "bit"
0x60c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x611  brtrue   loc_77F
0x616  br       loc_812
0x61b  ldloc.3
0x61c  ldstr    aInt// "int"
0x621  call     bool [mscorlib]System.String::op_Equality(string, string)
0x626  brtrue   loc_78C
0x62b  br       loc_812
0x630  ldloc.3
0x631  ldstr    aFloat// "float"
0x636  call     bool [mscorlib]System.String::op_Equality(string, string)
0x63b  brtrue   loc_796
0x640  br       loc_812
0x645  ldloc.3
0x646  ldstr    aDecimal// "decimal"
0x64b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x650  brtrue   loc_7A0
0x655  br       loc_812
0x65a  ldloc.3
0x65b  ldstr    aMoney// "money"
0x660  call     bool [mscorlib]System.String::op_Equality(string, string)
0x665  brtrue   loc_7AA
0x66a  br       loc_812
0x66f  ldloc.3
0x670  ldstr    aNtext// "ntext"
0x675  call     bool [mscorlib]System.String::op_Equality(string, string)
0x67a  brtrue   loc_7B4
0x67f  br       loc_812
0x684  ldloc.3
0x685  ldstr    aDatetime// "datetime"
0x68a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x68f  brtrue   loc_7BE
0x694  br       loc_812
0x699  ldloc.3
0x69a  ldstr    aLookup// "lookup"
0x69f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6a4  brtrue   loc_7C8
0x6a9  br       loc_812
0x6ae  ldloc.3
0x6af  ldstr    aPrimarykey// "primarykey"
0x6b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6b9  brtrue   loc_7D1
0x6be  br       loc_812
0x6c3  ldloc.3
0x6c4  ldstr    aState// "state"
0x6c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6ce  brtrue   loc_7D9
0x6d3  br       loc_812
0x6d8  ldloc.3
0x6d9  ldstr    aStatus// "status"
0x6de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6e3  brtrue   loc_7E2
0x6e8  br       loc_812
0x6ed  ldloc.3
0x6ee  ldstr    aOwner// "owner"
0x6f3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6f8  brtrue   loc_7EB
0x6fd  br       loc_812
0x702  ldloc.3
0x703  ldstr    aPartylist// "partylist"
0x708  call     bool [mscorlib]System.String::op_Equality(string, string)
0x70d  brtrue   loc_7F3
0x712  br       loc_812
0x717  ldloc.3
0x718  ldstr    aUniqueidentifi// "uniqueidentifier"
0x71d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x722  brtrue   loc_7FC
0x727  br       loc_812
0x72c  ldloc.3
0x72d  ldstr    aCustomer// "customer"
0x732  call     bool [mscorlib]System.String::op_Equality(string, string)
0x737  brtrue   loc_804
0x73c  br       loc_812
0x741  ldloc.3
0x742  ldstr    aImage// "image"
0x747  call     bool [mscorlib]System.String::op_Equality(string, string)
0x74c  brtrue   loc_80C
0x751  br       loc_812
0x756  ldloc.2
0x757  ldarg.1
0x758  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStringInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x75d  stloc.1
0x75e  br       loc_812
0x763  ldloc.2
0x764  ldloc.3
0x765  ldarg.1
0x766  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPicklistInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, string typeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x76b  stloc.1
0x76c  br       loc_812
0x771  ldloc.2
0x772  ldloc.3
0x773  ldarg.1
0x774  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPicklistInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, string typeName, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x779  stloc.1
0x77a  br       loc_812
0x77f  ldloc.2
0x780  ldarg.1
0x781  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetBooleanInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x786  stloc.1
0x787  br       loc_812
0x78c  ldloc.2
0x78d  ldarg.1
0x78e  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetIntegerInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x793  stloc.1
0x794  br.s     loc_812
0x796  ldloc.2
0x797  ldarg.1
0x798  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetFloatInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x79d  stloc.1
0x79e  br.s     loc_812
0x7a0  ldloc.2
0x7a1  ldarg.1
0x7a2  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDecimalInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7a7  stloc.1
0x7a8  br.s     loc_812
0x7aa  ldloc.2
0x7ab  ldarg.1
0x7ac  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMoneyInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7b1  stloc.1
0x7b2  br.s     loc_812
0x7b4  ldloc.2
0x7b5  ldarg.1
0x7b6  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetMemoInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7bb  stloc.1
0x7bc  br.s     loc_812
0x7be  ldloc.2
0x7bf  ldarg.1
0x7c0  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetDateTimeInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7c5  stloc.1
0x7c6  br.s     loc_812
0x7c8  ldarg.1
0x7c9  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetLookupInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7ce  stloc.1
0x7cf  br.s     loc_812
0x7d1  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPrimaryKeyInfo()
0x7d6  stloc.1
0x7d7  br.s     loc_812
0x7d9  ldarg.1
0x7da  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStateInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7df  stloc.1
0x7e0  br.s     loc_812
0x7e2  ldloc.2
0x7e3  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetStatusInfo(class Microsoft.Crm.Application.WebServices.ParameterBag typeBag)
0x7e8  stloc.1
0x7e9  br.s     loc_812
0x7eb  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetOwnerInfo()
0x7f0  stloc.1
0x7f1  br.s     loc_812
0x7f3  ldarg.1
0x7f4  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetPartyListInfo(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata attributeMD)
0x7f9  stloc.1
0x7fa  br.s     loc_812
0x7fc  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetUniqueIdentifierInfo()
0x801  stloc.1
0x802  br.s     loc_812
0x804  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetCustomerInfo()
0x809  stloc.1
0x80a  br.s     loc_812
0x80c  call     class [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::GetImageInfo()
0x811  stloc.1
0x812  ldarg.1
0x813  brfalse.s loc_875
0x815  ldloc.1
0x816  ldarg.1
0x817  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PhysicalName()
0x81c  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.AttributeInfo::set_Name(string)
0x821  ldloc.1
0x822  ldarg.1
0x823  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Locked()
  ... truncated ...
```
