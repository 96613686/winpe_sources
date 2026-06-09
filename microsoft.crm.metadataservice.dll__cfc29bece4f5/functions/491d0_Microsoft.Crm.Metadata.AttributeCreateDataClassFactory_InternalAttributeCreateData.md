# Microsoft.Crm.Metadata.AttributeCreateDataClassFactory::InternalAttributeCreateData

- ea: `0x491d0`
- end: `0x4934c`
- name: `Microsoft.Crm.Metadata.AttributeCreateDataClassFactory::InternalAttributeCreateData`
- size: `380`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x49130`
- `0x49180`

## callees

- `0x48d20`
- `0x48d70`
- `0x48e60`
- `0x48ef0`
- `0x48fa0`
- `0x491d0`
- `0x75380`

## string_xrefs

- `0x4932e`: `You cannot create an AttributeCreateData object for status data - status attributes cannot be created independently of an entity`
- `0x49339`: `You cannot create an AttributeCreateData object for state data - state attributes cannot be created independently of an entity`

## pseudocode

```c

```

## disassembly

```asm
0x491d0  ldarg.1
0x491d1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x491d6  stloc.0
0x491d7  ldloc.0
0x491d8  ldc.i4   0xBA4B77EF
0x491dd  bgt.un.s loc_49225
0x491df  ldloc.0
0x491e0  ldc.i4   0x60CAE230
0x491e5  bgt.un.s loc_49202
0x491e7  ldloc.0
0x491e8  ldc.i4   0x5BC874BE
0x491ed  beq      loc_492B1
0x491f2  ldloc.0
0x491f3  ldc.i4   0x60CAE230
0x491f8  beq      loc_492C3
0x491fd  br       loc_49344
0x49202  ldloc.0
0x49203  ldc.i4   0x783132F6
0x49208  beq      loc_492FF
0x4920d  ldloc.0
0x4920e  ldc.i4   0xA4BDAA19
0x49213  beq.s    loc_4928D
0x49215  ldloc.0
0x49216  ldc.i4   0xBA4B77EF
0x4921b  beq      loc_492F0
0x49220  br       loc_49344
0x49225  ldloc.0
0x49226  ldc.i4   0xC1C33E1F
0x4922b  bgt.un.s loc_49245
0x4922d  ldloc.0
0x4922e  ldc.i4   0xBAC37203
0x49233  beq      loc_492E1
0x49238  ldloc.0
0x49239  ldc.i4   0xC1C33E1F
0x4923e  beq.s    loc_4929F
0x49240  br       loc_49344
0x49245  ldloc.0
0x49246  ldc.i4   0xD9844140
0x4924b  beq      loc_492D2
0x49250  ldloc.0
0x49251  ldc.i4   0xF5674CD4
0x49256  beq.s    loc_49278
0x49258  ldloc.0
0x49259  ldc.i4   0xF758858B
0x4925e  bne.un   loc_49344
0x49263  ldarg.1
0x49264  ldstr    aLookup// "lookup"
0x49269  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4926e  brtrue   loc_4930E
0x49273  br       loc_49344
0x49278  ldarg.1
0x49279  ldstr    aOwner// "owner"
0x4927e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x49283  brtrue   loc_4930E
0x49288  br       loc_49344
0x4928d  ldarg.1
0x4928e  ldstr    aCustomer// "customer"
0x49293  call     bool [mscorlib]System.String::op_Equality(string, string)
0x49298  brtrue.s loc_4930E
0x4929a  br       loc_49344
0x4929f  ldarg.1
0x492a0  ldstr    aPartylist// "partylist"
0x492a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492aa  brtrue.s loc_4930E
0x492ac  br       loc_49344
0x492b1  ldarg.1
0x492b2  ldstr    aNvarchar// "nvarchar"
0x492b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492bc  brtrue.s loc_49316
0x492be  br       loc_49344
0x492c3  ldarg.1
0x492c4  ldstr    aBit// "bit"
0x492c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492ce  brtrue.s loc_4931E
0x492d0  br.s     loc_49344
0x492d2  ldarg.1
0x492d3  ldstr    aPicklist// "picklist"
0x492d8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492dd  brtrue.s loc_49326
0x492df  br.s     loc_49344
0x492e1  ldarg.1
0x492e2  ldstr    aMultiselectpic// "multiselectpicklist"
0x492e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492ec  brtrue.s loc_49326
0x492ee  br.s     loc_49344
0x492f0  ldarg.1
0x492f1  ldstr    aStatus// "status"
0x492f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x492fb  brtrue.s loc_4932E
0x492fd  br.s     loc_49344
0x492ff  ldarg.1
0x49300  ldstr    aState// "state"
0x49305  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4930a  brtrue.s loc_49339
0x4930c  br.s     loc_49344
0x4930e  ldarg.0
0x4930f  ldarg.2
0x49310  newobj   instance void Microsoft.Crm.Metadata.LookupAttributeCreateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x49315  ret
0x49316  ldarg.0
0x49317  ldarg.2
0x49318  newobj   instance void Microsoft.Crm.Metadata.StringAttributeCreateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x4931d  ret
0x4931e  ldarg.0
0x4931f  ldarg.2
0x49320  newobj   instance void Microsoft.Crm.Metadata.BooleanAttributeCreateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x49325  ret
0x49326  ldarg.0
0x49327  ldarg.2
0x49328  newobj   instance void Microsoft.Crm.Metadata.PicklistAttributeCreateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x4932d  ret
0x4932e  ldstr    aYouCannotCreat_2// "You cannot create an AttributeCreateDat"...
0x49333  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x49338  throw
0x49339  ldstr    aYouCannotCreat_3// "You cannot create an AttributeCreateDat"...
0x4933e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x49343  throw
0x49344  ldarg.0
0x49345  ldarg.2
0x49346  newobj   instance void Microsoft.Crm.Metadata.AttributeCreateData::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity attributeDescription, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext orgContext)
0x4934b  ret
```
