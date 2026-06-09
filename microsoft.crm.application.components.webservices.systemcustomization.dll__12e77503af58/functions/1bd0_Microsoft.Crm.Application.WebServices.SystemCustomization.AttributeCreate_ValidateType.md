# Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::ValidateType

- ea: `0x1bd0`
- end: `0x1e84`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.AttributeCreate::ValidateType`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x430`

## callees

- `0x1bd0`
- `0xbf70`

## string_xrefs

- `0x1e6b`: `Type is not valid for create`

## pseudocode

```c

```

## disassembly

```asm
0x1bd0  ldarg.0
0x1bd1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x1bd6  stloc.0
0x1bd7  ldloc.0
0x1bd8  ldc.i4   0xB35135FA
0x1bdd  bgt.un   loc_1C71
0x1be2  ldloc.0
0x1be3  ldc.i4   0x63B39A70
0x1be8  bgt.un.s loc_1C28
0x1bea  ldloc.0
0x1beb  ldc.i4   0x5BC874BE
0x1bf0  bgt.un.s loc_1C0D
0x1bf2  ldloc.0
0x1bf3  ldc.i4   0x1F088D4C
0x1bf8  beq      loc_1D86
0x1bfd  ldloc.0
0x1bfe  ldc.i4   0x5BC874BE
0x1c03  beq      loc_1D08
0x1c08  br       loc_1E77
0x1c0d  ldloc.0
0x1c0e  ldc.i4   0x60CAE230
0x1c13  beq      loc_1D47
0x1c18  ldloc.0
0x1c19  ldc.i4   0x63B39A70
0x1c1e  beq      loc_1E10
0x1c23  br       loc_1E77
0x1c28  ldloc.0
0x1c29  ldc.i4   0x95E97E5E
0x1c2e  bgt.un.s loc_1C4B
0x1c30  ldloc.0
0x1c31  ldc.i4   0x783132F6
0x1c36  beq      loc_1E1F
0x1c3b  ldloc.0
0x1c3c  ldc.i4   0x95E97E5E
0x1c41  beq      loc_1D5C
0x1c46  br       loc_1E77
0x1c4b  ldloc.0
0x1c4c  ldc.i4   0xA4BDAA19
0x1c51  beq      loc_1DEF
0x1c56  ldloc.0
0x1c57  ldc.i4   0xA6C45D85
0x1c5c  beq      loc_1D71
0x1c61  ldloc.0
0x1c62  ldc.i4   0xB35135FA
0x1c67  beq      loc_1DDA
0x1c6c  br       loc_1E77
0x1c71  ldloc.0
0x1c72  ldc.i4   0xCCEA6D90
0x1c77  bgt.un.s loc_1CC2
0x1c79  ldloc.0
0x1c7a  ldc.i4   0xBAC37203
0x1c7f  bgt.un.s loc_1C9C
0x1c81  ldloc.0
0x1c82  ldc.i4   0xBA4B77EF
0x1c87  beq      loc_1E2E
0x1c8c  ldloc.0
0x1c8d  ldc.i4   0xBAC37203
0x1c92  beq      loc_1D32
0x1c97  br       loc_1E77
0x1c9c  ldloc.0
0x1c9d  ldc.i4   0xC1C33E1F
0x1ca2  beq      loc_1E4C
0x1ca7  ldloc.0
0x1ca8  ldc.i4   0xCC898375
0x1cad  beq      loc_1E5B
0x1cb2  ldloc.0
0x1cb3  ldc.i4   0xCCEA6D90
0x1cb8  beq      loc_1DC5
0x1cbd  br       loc_1E77
0x1cc2  ldloc.0
0x1cc3  ldc.i4   0xE150C94F
0x1cc8  bgt.un.s loc_1CE2
0x1cca  ldloc.0
0x1ccb  ldc.i4   0xD9844140
0x1cd0  beq.s    loc_1D1D
0x1cd2  ldloc.0
0x1cd3  ldc.i4   0xE150C94F
0x1cd8  beq      loc_1D9B
0x1cdd  br       loc_1E77
0x1ce2  ldloc.0
0x1ce3  ldc.i4   0xE98BD702
0x1ce8  beq      loc_1DB0
0x1ced  ldloc.0
0x1cee  ldc.i4   0xF5674CD4
0x1cf3  beq      loc_1E3D
0x1cf8  ldloc.0
0x1cf9  ldc.i4   0xF758858B
0x1cfe  beq      loc_1E01
0x1d03  br       loc_1E77
0x1d08  ldarg.0
0x1d09  ldstr    aNvarchar// "nvarchar"
0x1d0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d13  brtrue   loc_1E83
0x1d18  br       loc_1E77
0x1d1d  ldarg.0
0x1d1e  ldstr    aPicklist// "picklist"
0x1d23  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d28  brtrue   loc_1E83
0x1d2d  br       loc_1E77
0x1d32  ldarg.0
0x1d33  ldstr    aMultiselectpic// "multiselectpicklist"
0x1d38  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d3d  brtrue   loc_1E83
0x1d42  br       loc_1E77
0x1d47  ldarg.0
0x1d48  ldstr    aBit// "bit"
0x1d4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d52  brtrue   loc_1E83
0x1d57  br       loc_1E77
0x1d5c  ldarg.0
0x1d5d  ldstr    aInt// "int"
0x1d62  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d67  brtrue   loc_1E83
0x1d6c  br       loc_1E77
0x1d71  ldarg.0
0x1d72  ldstr    aFloat// "float"
0x1d77  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d7c  brtrue   loc_1E83
0x1d81  br       loc_1E77
0x1d86  ldarg.0
0x1d87  ldstr    aDecimal// "decimal"
0x1d8c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1d91  brtrue   loc_1E83
0x1d96  br       loc_1E77
0x1d9b  ldarg.0
0x1d9c  ldstr    aMoney// "money"
0x1da1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1da6  brtrue   loc_1E83
0x1dab  br       loc_1E77
0x1db0  ldarg.0
0x1db1  ldstr    aNtext// "ntext"
0x1db6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dbb  brtrue   loc_1E83
0x1dc0  br       loc_1E77
0x1dc5  ldarg.0
0x1dc6  ldstr    aDatetime// "datetime"
0x1dcb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dd0  brtrue   loc_1E83
0x1dd5  br       loc_1E77
0x1dda  ldarg.0
0x1ddb  ldstr    aImage// "image"
0x1de0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1de5  brtrue   loc_1E83
0x1dea  br       loc_1E77
0x1def  ldarg.0
0x1df0  ldstr    aCustomer// "customer"
0x1df5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1dfa  brtrue   loc_1E83
0x1dff  br.s     loc_1E77
0x1e01  ldarg.0
0x1e02  ldstr    aLookup// "lookup"
0x1e07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e0c  brtrue.s loc_1E68
0x1e0e  br.s     loc_1E77
0x1e10  ldarg.0
0x1e11  ldstr    aPrimarykey// "primarykey"
0x1e16  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e1b  brtrue.s loc_1E68
0x1e1d  br.s     loc_1E77
0x1e1f  ldarg.0
0x1e20  ldstr    aState// "state"
0x1e25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e2a  brtrue.s loc_1E68
0x1e2c  br.s     loc_1E77
0x1e2e  ldarg.0
0x1e2f  ldstr    aStatus// "status"
0x1e34  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e39  brtrue.s loc_1E68
0x1e3b  br.s     loc_1E77
0x1e3d  ldarg.0
0x1e3e  ldstr    aOwner// "owner"
0x1e43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e48  brtrue.s loc_1E68
0x1e4a  br.s     loc_1E77
0x1e4c  ldarg.0
0x1e4d  ldstr    aPartylist// "partylist"
0x1e52  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e57  brtrue.s loc_1E68
0x1e59  br.s     loc_1E77
0x1e5b  ldarg.0
0x1e5c  ldstr    aUniqueidentifi// "uniqueidentifier"
0x1e61  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1e66  brfalse.s loc_1E77
0x1e68  ldarg.1
0x1e69  brfalse.s loc_1E83
0x1e6b  ldstr    aTypeIsNotValid// "Type is not valid for create"
0x1e70  ldarg.0
0x1e71  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1e76  throw
0x1e77  ldstr    aUnexpectedType// "Unexpected type"
0x1e7c  ldarg.0
0x1e7d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1e82  throw
0x1e83  ret
```
