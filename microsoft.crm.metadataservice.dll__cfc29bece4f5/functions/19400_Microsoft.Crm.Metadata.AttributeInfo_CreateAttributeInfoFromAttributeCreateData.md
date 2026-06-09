# Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeCreateData

- ea: `0x19400`
- end: `0x1975a`
- name: `Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeCreateData`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0xded0`
- `0x1a6e0`

## callees

- `0x18100`
- `0x19400`
- `0x19af0`
- `0x1a440`
- `0x2bef0`
- `0x2c190`
- `0x43260`
- `0x43580`
- `0x43920`
- `0x44000`
- `0x44550`
- `0x48b90`
- `0x4a3a0`
- `0x58b50`
- `0x75380`

## string_xrefs

- `0x19401`: `createData`
- `0x19411`: `createData.AttributeDescription`
- `0x1942d`: `The AttributeCreateData provided must have the attribute type id set on it`
- `0x19717`: `You cannot create a StatusAttributeInfo object from an AttributeCreateData object - status attributes cannot be created independently of an entity`
- `0x19722`: `You cannot create a StateAttributeInfo object from an AttributeCreateData object - state attributes cannot be created independently of an entity`

## pseudocode

```c

```

## disassembly

```asm
0x19400  ldarg.0
0x19401  ldstr    aCreatedata// "createData"
0x19406  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1940b  ldarg.0
0x1940c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x19411  ldstr    aCreatedataAttr// "createData.AttributeDescription"
0x19416  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1941b  ldarg.0
0x1941c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x19421  ldstr    aAttributetypei// "attributetypeid"
0x19426  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x1942b  brfalse.s loc_19438
0x1942d  ldstr    aTheAttributecr// "The AttributeCreateData provided must h"...
0x19432  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x19437  throw
0x19438  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x1943d  ldarg.0
0x1943e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity Microsoft.Crm.Metadata.AttributeData::get_AttributeDescription()
0x19443  ldstr    aAttributetypei// "attributetypeid"
0x19448  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x1944d  unbox.any [mscorlib]System.Guid
0x19452  box      [mscorlib]System.Guid
0x19457  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1945c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x19461  stloc.0
0x19462  ldloc.0
0x19463  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x19468  stloc.1
0x19469  ldloc.1
0x1946a  ldc.i4   0xB35135FA
0x1946f  bgt.un   loc_194F8
0x19474  ldloc.1
0x19475  ldc.i4   0x783132F6
0x1947a  bgt.un.s loc_194BA
0x1947c  ldloc.1
0x1947d  ldc.i4   0x5BC874BE
0x19482  bgt.un.s loc_1949F
0x19484  ldloc.1
0x19485  ldc.i4   0x1F088D4C
0x1948a  beq      loc_195FD
0x1948f  ldloc.1
0x19490  ldc.i4   0x5BC874BE
0x19495  beq      loc_19627
0x1949a  br       loc_19753
0x1949f  ldloc.1
0x194a0  ldc.i4   0x60CAE230
0x194a5  beq      loc_1967B
0x194aa  ldloc.1
0x194ab  ldc.i4   0x783132F6
0x194b0  beq      loc_19666
0x194b5  br       loc_19753
0x194ba  ldloc.1
0x194bb  ldc.i4   0xA4BDAA19
0x194c0  bgt.un.s loc_194DD
0x194c2  ldloc.1
0x194c3  ldc.i4   0x95E97E5E
0x194c8  beq      loc_195D3
0x194cd  ldloc.1
0x194ce  ldc.i4   0xA4BDAA19
0x194d3  beq      loc_195A9
0x194d8  br       loc_19753
0x194dd  ldloc.1
0x194de  ldc.i4   0xA6C45D85
0x194e3  beq      loc_19612
0x194e8  ldloc.1
0x194e9  ldc.i4   0xB35135FA
0x194ee  beq      loc_196CC
0x194f3  br       loc_19753
0x194f8  ldloc.1
0x194f9  ldc.i4   0xCCEA6D90
0x194fe  bgt.un.s loc_1953E
0x19500  ldloc.1
0x19501  ldc.i4   0xBAC37203
0x19506  bgt.un.s loc_19523
0x19508  ldloc.1
0x19509  ldc.i4   0xBA4B77EF
0x1950e  beq      loc_19651
0x19513  ldloc.1
0x19514  ldc.i4   0xBAC37203
0x19519  beq      loc_196A5
0x1951e  br       loc_19753
0x19523  ldloc.1
0x19524  ldc.i4   0xC1C33E1F
0x19529  beq      loc_195BE
0x1952e  ldloc.1
0x1952f  ldc.i4   0xCCEA6D90
0x19534  beq      loc_196BA
0x19539  br       loc_19753
0x1953e  ldloc.1
0x1953f  ldc.i4   0xE150C94F
0x19544  bgt.un.s loc_19561
0x19546  ldloc.1
0x19547  ldc.i4   0xD9844140
0x1954c  beq      loc_19690
0x19551  ldloc.1
0x19552  ldc.i4   0xE150C94F
0x19557  beq      loc_195E8
0x1955c  br       loc_19753
0x19561  ldloc.1
0x19562  ldc.i4   0xE98BD702
0x19567  beq      loc_1963C
0x1956c  ldloc.1
0x1956d  ldc.i4   0xF5674CD4
0x19572  beq.s    loc_19594
0x19574  ldloc.1
0x19575  ldc.i4   0xF758858B
0x1957a  bne.un   loc_19753
0x1957f  ldloc.0
0x19580  ldstr    aLookup// "lookup"
0x19585  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1958a  brtrue   loc_196DB
0x1958f  br       loc_19753
0x19594  ldloc.0
0x19595  ldstr    aOwner// "owner"
0x1959a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1959f  brtrue   loc_196DB
0x195a4  br       loc_19753
0x195a9  ldloc.0
0x195aa  ldstr    aCustomer// "customer"
0x195af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x195b4  brtrue   loc_196DB
0x195b9  br       loc_19753
0x195be  ldloc.0
0x195bf  ldstr    aPartylist// "partylist"
0x195c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x195c9  brtrue   loc_196DB
0x195ce  br       loc_19753
0x195d3  ldloc.0
0x195d4  ldstr    aInt// "int"
0x195d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x195de  brtrue   loc_196E8
0x195e3  br       loc_19753
0x195e8  ldloc.0
0x195e9  ldstr    aMoney// "money"
0x195ee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x195f3  brtrue   loc_196EF
0x195f8  br       loc_19753
0x195fd  ldloc.0
0x195fe  ldstr    aDecimal// "decimal"
0x19603  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19608  brtrue   loc_196F6
0x1960d  br       loc_19753
0x19612  ldloc.0
0x19613  ldstr    aFloat// "float"
0x19618  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1961d  brtrue   loc_196FD
0x19622  br       loc_19753
0x19627  ldloc.0
0x19628  ldstr    aNvarchar// "nvarchar"
0x1962d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19632  brtrue   loc_19704
0x19637  br       loc_19753
0x1963c  ldloc.0
0x1963d  ldstr    aNtext// "ntext"
0x19642  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19647  brtrue   loc_19710
0x1964c  br       loc_19753
0x19651  ldloc.0
0x19652  ldstr    aStatus// "status"
0x19657  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1965c  brtrue   loc_19717
0x19661  br       loc_19753
0x19666  ldloc.0
0x19667  ldstr    aState// "state"
0x1966c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19671  brtrue   loc_19722
0x19676  br       loc_19753
0x1967b  ldloc.0
0x1967c  ldstr    aBit// "bit"
0x19681  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19686  brtrue   loc_1972D
0x1968b  br       loc_19753
0x19690  ldloc.0
0x19691  ldstr    aPicklist// "picklist"
0x19696  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1969b  brtrue   loc_19739
0x196a0  br       loc_19753
0x196a5  ldloc.0
0x196a6  ldstr    aMultiselectpic// "multiselectpicklist"
0x196ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x196b0  brtrue   loc_19739
0x196b5  br       loc_19753
0x196ba  ldloc.0
0x196bb  ldstr    aDatetime// "datetime"
0x196c0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x196c5  brtrue.s loc_19745
0x196c7  br       loc_19753
0x196cc  ldloc.0
0x196cd  ldstr    aImage// "image"
0x196d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x196d7  brtrue.s loc_1974C
0x196d9  br.s     loc_19753
0x196db  ldarg.0
0x196dc  castclass Microsoft.Crm.Metadata.LookupAttributeCreateData
0x196e1  ldarg.1
0x196e2  newobj   instance void Microsoft.Crm.Metadata.LookupAttributeInfo::.ctor(class Microsoft.Crm.Metadata.LookupAttributeCreateData createData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x196e7  ret
0x196e8  ldarg.0
0x196e9  newobj   instance void Microsoft.Crm.Metadata.IntAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x196ee  ret
0x196ef  ldarg.0
0x196f0  newobj   instance void Microsoft.Crm.Metadata.MoneyAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x196f5  ret
0x196f6  ldarg.0
0x196f7  newobj   instance void Microsoft.Crm.Metadata.DecimalAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x196fc  ret
0x196fd  ldarg.0
0x196fe  newobj   instance void Microsoft.Crm.Metadata.FloatAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x19703  ret
0x19704  ldarg.0
0x19705  castclass Microsoft.Crm.Metadata.StringAttributeCreateData
0x1970a  newobj   instance void Microsoft.Crm.Metadata.StringAttributeInfo::.ctor(class Microsoft.Crm.Metadata.StringAttributeCreateData createData)
0x1970f  ret
0x19710  ldarg.0
0x19711  newobj   instance void Microsoft.Crm.Metadata.MemoAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x19716  ret
0x19717  ldstr    aYouCannotCreat_0// "You cannot create a StatusAttributeInfo"...
0x1971c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x19721  throw
0x19722  ldstr    aYouCannotCreat_1// "You cannot create a StateAttributeInfo "...
0x19727  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x1972c  throw
0x1972d  ldarg.0
0x1972e  castclass Microsoft.Crm.Metadata.BooleanAttributeCreateData
0x19733  newobj   instance void Microsoft.Crm.Metadata.BooleanAttributeInfo::.ctor(class Microsoft.Crm.Metadata.BooleanAttributeCreateData createData)
0x19738  ret
0x19739  ldarg.0
0x1973a  castclass Microsoft.Crm.Metadata.PicklistAttributeCreateData
0x1973f  newobj   instance void Microsoft.Crm.Metadata.PicklistAttributeInfo::.ctor(class Microsoft.Crm.Metadata.PicklistAttributeCreateData createData)
0x19744  ret
0x19745  ldarg.0
0x19746  newobj   instance void Microsoft.Crm.Metadata.DateTimeAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x1974b  ret
0x1974c  ldarg.0
0x1974d  newobj   instance void Microsoft.Crm.Metadata.ImageAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x19752  ret
0x19753  ldarg.0
0x19754  newobj   instance void Microsoft.Crm.Metadata.AttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeCreateData createData)
0x19759  ret
```
