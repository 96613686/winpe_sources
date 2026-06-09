# Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeUpdateData

- ea: `0x19760`
- end: `0x19a5c`
- name: `Microsoft.Crm.Metadata.AttributeInfo::CreateAttributeInfoFromAttributeUpdateData`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1abc0`

## callees

- `0x18250`
- `0x19760`
- `0x19b20`
- `0x1a490`
- `0x2bf00`
- `0x2c1d0`
- `0x432a0`
- `0x43950`
- `0x44080`
- `0x44640`
- `0x4a3e0`
- `0x58be0`
- `0x58f50`
- `0x59130`
- `0x75380`

## string_xrefs

- `0x19761`: `updateData`

## pseudocode

```c

```

## disassembly

```asm
0x19760  ldarg.0
0x19761  ldstr    aUpdatedata// "updateData"
0x19766  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1976b  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypes::get_AttributeTypesById()
0x19770  ldarg.1
0x19771  box      [mscorlib]System.Guid
0x19776  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeDictionary::get_Item(object)
0x1977b  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_Name()
0x19780  stloc.0
0x19781  ldloc.0
0x19782  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x19787  stloc.2
0x19788  ldloc.2
0x19789  ldc.i4   0xBA4B77EF
0x1978e  bgt.un   loc_19817
0x19793  ldloc.2
0x19794  ldc.i4   0x783132F6
0x19799  bgt.un.s loc_197D9
0x1979b  ldloc.2
0x1979c  ldc.i4   0x5BC874BE
0x197a1  bgt.un.s loc_197BE
0x197a3  ldloc.2
0x197a4  ldc.i4   0x1F088D4C
0x197a9  beq      loc_19911
0x197ae  ldloc.2
0x197af  ldc.i4   0x5BC874BE
0x197b4  beq      loc_1993B
0x197b9  br       loc_19A47
0x197be  ldloc.2
0x197bf  ldc.i4   0x60CAE230
0x197c4  beq      loc_1998F
0x197c9  ldloc.2
0x197ca  ldc.i4   0x783132F6
0x197cf  beq      loc_1997A
0x197d4  br       loc_19A47
0x197d9  ldloc.2
0x197da  ldc.i4   0xA4BDAA19
0x197df  bgt.un.s loc_197FC
0x197e1  ldloc.2
0x197e2  ldc.i4   0x95E97E5E
0x197e7  beq      loc_198E7
0x197ec  ldloc.2
0x197ed  ldc.i4   0xA4BDAA19
0x197f2  beq      loc_198BD
0x197f7  br       loc_19A47
0x197fc  ldloc.2
0x197fd  ldc.i4   0xA6C45D85
0x19802  beq      loc_19926
0x19807  ldloc.2
0x19808  ldc.i4   0xBA4B77EF
0x1980d  beq      loc_19965
0x19812  br       loc_19A47
0x19817  ldloc.2
0x19818  ldc.i4   0xD9844140
0x1981d  bgt.un.s loc_1985D
0x1981f  ldloc.2
0x19820  ldc.i4   0xC1C33E1F
0x19825  bgt.un.s loc_19842
0x19827  ldloc.2
0x19828  ldc.i4   0xBAC37203
0x1982d  beq      loc_199B9
0x19832  ldloc.2
0x19833  ldc.i4   0xC1C33E1F
0x19838  beq      loc_198D2
0x1983d  br       loc_19A47
0x19842  ldloc.2
0x19843  ldc.i4   0xCCEA6D90
0x19848  beq      loc_199C8
0x1984d  ldloc.2
0x1984e  ldc.i4   0xD9844140
0x19853  beq      loc_199A4
0x19858  br       loc_19A47
0x1985d  ldloc.2
0x1985e  ldc.i4   0xE98BD702
0x19863  bgt.un.s loc_19880
0x19865  ldloc.2
0x19866  ldc.i4   0xE150C94F
0x1986b  beq      loc_198FC
0x19870  ldloc.2
0x19871  ldc.i4   0xE98BD702
0x19876  beq      loc_19950
0x1987b  br       loc_19A47
0x19880  ldloc.2
0x19881  ldc.i4   0xF5674CD4
0x19886  beq.s    loc_198A8
0x19888  ldloc.2
0x19889  ldc.i4   0xF758858B
0x1988e  bne.un   loc_19A47
0x19893  ldloc.0
0x19894  ldstr    aLookup// "lookup"
0x19899  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1989e  brtrue   loc_199D7
0x198a3  br       loc_19A47
0x198a8  ldloc.0
0x198a9  ldstr    aOwner// "owner"
0x198ae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198b3  brtrue   loc_199D7
0x198b8  br       loc_19A47
0x198bd  ldloc.0
0x198be  ldstr    aCustomer// "customer"
0x198c3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198c8  brtrue   loc_199D7
0x198cd  br       loc_19A47
0x198d2  ldloc.0
0x198d3  ldstr    aPartylist// "partylist"
0x198d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198dd  brtrue   loc_199D7
0x198e2  br       loc_19A47
0x198e7  ldloc.0
0x198e8  ldstr    aInt// "int"
0x198ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198f2  brtrue   loc_199E0
0x198f7  br       loc_19A47
0x198fc  ldloc.0
0x198fd  ldstr    aMoney// "money"
0x19902  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19907  brtrue   loc_199E9
0x1990c  br       loc_19A47
0x19911  ldloc.0
0x19912  ldstr    aDecimal// "decimal"
0x19917  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1991c  brtrue   loc_199F2
0x19921  br       loc_19A47
0x19926  ldloc.0
0x19927  ldstr    aFloat// "float"
0x1992c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19931  brtrue   loc_199FB
0x19936  br       loc_19A47
0x1993b  ldloc.0
0x1993c  ldstr    aNvarchar// "nvarchar"
0x19941  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19946  brtrue   loc_19A04
0x1994b  br       loc_19A47
0x19950  ldloc.0
0x19951  ldstr    aNtext// "ntext"
0x19956  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1995b  brtrue   loc_19A0D
0x19960  br       loc_19A47
0x19965  ldloc.0
0x19966  ldstr    aStatus// "status"
0x1996b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19970  brtrue   loc_19A16
0x19975  br       loc_19A47
0x1997a  ldloc.0
0x1997b  ldstr    aState// "state"
0x19980  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19985  brtrue   loc_19A20
0x1998a  br       loc_19A47
0x1998f  ldloc.0
0x19990  ldstr    aBit// "bit"
0x19995  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1999a  brtrue   loc_19A2A
0x1999f  br       loc_19A47
0x199a4  ldloc.0
0x199a5  ldstr    aPicklist// "picklist"
0x199aa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x199af  brtrue   loc_19A34
0x199b4  br       loc_19A47
0x199b9  ldloc.0
0x199ba  ldstr    aMultiselectpic// "multiselectpicklist"
0x199bf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x199c4  brtrue.s loc_19A34
0x199c6  br.s     loc_19A47
0x199c8  ldloc.0
0x199c9  ldstr    aDatetime// "datetime"
0x199ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x199d3  brtrue.s loc_19A3E
0x199d5  br.s     loc_19A47
0x199d7  ldarg.0
0x199d8  newobj   instance void Microsoft.Crm.Metadata.LookupAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x199dd  stloc.1
0x199de  br.s     loc_19A4E
0x199e0  ldarg.0
0x199e1  newobj   instance void Microsoft.Crm.Metadata.IntAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x199e6  stloc.1
0x199e7  br.s     loc_19A4E
0x199e9  ldarg.0
0x199ea  newobj   instance void Microsoft.Crm.Metadata.MoneyAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x199ef  stloc.1
0x199f0  br.s     loc_19A4E
0x199f2  ldarg.0
0x199f3  newobj   instance void Microsoft.Crm.Metadata.DecimalAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x199f8  stloc.1
0x199f9  br.s     loc_19A4E
0x199fb  ldarg.0
0x199fc  newobj   instance void Microsoft.Crm.Metadata.FloatAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x19a01  stloc.1
0x19a02  br.s     loc_19A4E
0x19a04  ldarg.0
0x19a05  newobj   instance void Microsoft.Crm.Metadata.StringAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x19a0a  stloc.1
0x19a0b  br.s     loc_19A4E
0x19a0d  ldarg.0
0x19a0e  newobj   instance void Microsoft.Crm.Metadata.MemoAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x19a13  stloc.1
0x19a14  br.s     loc_19A4E
0x19a16  ldarg.0
0x19a17  ldarg.2
0x19a18  newobj   instance void Microsoft.Crm.Metadata.StatusAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x19a1d  stloc.1
0x19a1e  br.s     loc_19A4E
0x19a20  ldarg.0
0x19a21  ldarg.2
0x19a22  newobj   instance void Microsoft.Crm.Metadata.StateAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x19a27  stloc.1
0x19a28  br.s     loc_19A4E
0x19a2a  ldarg.0
0x19a2b  ldarg.2
0x19a2c  newobj   instance void Microsoft.Crm.Metadata.BooleanAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x19a31  stloc.1
0x19a32  br.s     loc_19A4E
0x19a34  ldarg.0
0x19a35  ldarg.2
0x19a36  newobj   instance void Microsoft.Crm.Metadata.PicklistAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x19a3b  stloc.1
0x19a3c  br.s     loc_19A4E
0x19a3e  ldarg.0
0x19a3f  newobj   instance void Microsoft.Crm.Metadata.DateTimeAttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x19a44  stloc.1
0x19a45  br.s     loc_19A4E
0x19a47  ldarg.0
0x19a48  newobj   instance void Microsoft.Crm.Metadata.AttributeInfo::.ctor(class Microsoft.Crm.Metadata.AttributeUpdateData updateData)
0x19a4d  stloc.1
0x19a4e  ldloc.1
0x19a4f  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescriptionPropertyBag Microsoft.Crm.Metadata.AttributeInfo::attributeData
0x19a54  ldarg.1
0x19a55  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeDescription::set_AttributeTypeId(valuetype [mscorlib]System.Guid)
0x19a5a  ldloc.1
0x19a5b  ret
```
