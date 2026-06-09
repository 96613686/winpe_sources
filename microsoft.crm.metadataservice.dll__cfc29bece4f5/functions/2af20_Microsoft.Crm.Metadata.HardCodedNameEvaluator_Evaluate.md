# Microsoft.Crm.Metadata.HardCodedNameEvaluator::Evaluate

- ea: `0x2af20`
- end: `0x2b036`
- name: `Microsoft.Crm.Metadata.HardCodedNameEvaluator::Evaluate`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2ac70`

## string_xrefs

- `0x2af69`: `overwritetime`
- `0x2af72`: `componentstate`
- `0x2af84`: `createdon`
- `0x2af96`: `createdby`
- `0x2afa8`: `overriddencreatedon`
- `0x2afba`: `createdonbehalfby`

## pseudocode

```c

```

## disassembly

```asm
0x2af20  ldc.i4.s 0x1E
0x2af22  newarr   [mscorlib]System.String
0x2af27  dup
0x2af28  ldc.i4.0
0x2af29  ldstr    aOwninguser// "owninguser"
0x2af2e  stelem.ref
0x2af2f  dup
0x2af30  ldc.i4.1
0x2af31  ldstr    aOwningteam// "owningteam"
0x2af36  stelem.ref
0x2af37  dup
0x2af38  ldc.i4.2
0x2af39  ldstr    aOwnerid// "ownerid"
0x2af3e  stelem.ref
0x2af3f  dup
0x2af40  ldc.i4.3
0x2af41  ldstr    aOwningbusiness// "owningbusinessunit"
0x2af46  stelem.ref
0x2af47  dup
0x2af48  ldc.i4.4
0x2af49  ldstr    aBusinessunitid// "businessunitid"
0x2af4e  stelem.ref
0x2af4f  dup
0x2af50  ldc.i4.5
0x2af51  ldstr    aOrganizationid// "organizationid"
0x2af56  stelem.ref
0x2af57  dup
0x2af58  ldc.i4.6
0x2af59  ldstr    aSolutionid// "solutionid"
0x2af5e  stelem.ref
0x2af5f  dup
0x2af60  ldc.i4.7
0x2af61  ldstr    aSupportingsolu// "supportingsolutionid"
0x2af66  stelem.ref
0x2af67  dup
0x2af68  ldc.i4.8
0x2af69  ldstr    aOverwritetime// "overwritetime"
0x2af6e  stelem.ref
0x2af6f  dup
0x2af70  ldc.i4.s 9
0x2af72  ldstr    aComponentstate// "componentstate"
0x2af77  stelem.ref
0x2af78  dup
0x2af79  ldc.i4.s 0xA
0x2af7b  ldstr    aTransactioncur_4// "transactioncurrencyid"
0x2af80  stelem.ref
0x2af81  dup
0x2af82  ldc.i4.s 0xB
0x2af84  ldstr    aCreatedon// "createdon"
0x2af89  stelem.ref
0x2af8a  dup
0x2af8b  ldc.i4.s 0xC
0x2af8d  ldstr    aModifiedon// "modifiedon"
0x2af92  stelem.ref
0x2af93  dup
0x2af94  ldc.i4.s 0xD
0x2af96  ldstr    aCreatedby_0// "createdby"
0x2af9b  stelem.ref
0x2af9c  dup
0x2af9d  ldc.i4.s 0xE
0x2af9f  ldstr    aModifiedby// "modifiedby"
0x2afa4  stelem.ref
0x2afa5  dup
0x2afa6  ldc.i4.s 0xF
0x2afa8  ldstr    aOverriddencrea// "overriddencreatedon"
0x2afad  stelem.ref
0x2afae  dup
0x2afaf  ldc.i4.s 0x10
0x2afb1  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0x2afb6  stelem.ref
0x2afb7  dup
0x2afb8  ldc.i4.s 0x11
0x2afba  ldstr    aCreatedonbehal// "createdonbehalfby"
0x2afbf  stelem.ref
0x2afc0  dup
0x2afc1  ldc.i4.s 0x12
0x2afc3  ldstr    aTimezoneruleve// "timezoneruleversionnumber"
0x2afc8  stelem.ref
0x2afc9  dup
0x2afca  ldc.i4.s 0x13
0x2afcc  ldstr    aStatecode_1// "statecode"
0x2afd1  stelem.ref
0x2afd2  dup
0x2afd3  ldc.i4.s 0x14
0x2afd5  ldstr    aStatuscode// "statuscode"
0x2afda  stelem.ref
0x2afdb  dup
0x2afdc  ldc.i4.s 0x15
0x2afde  ldstr    aImportsequence// "importsequencenumber"
0x2afe3  stelem.ref
0x2afe4  dup
0x2afe5  ldc.i4.s 0x16
0x2afe7  ldstr    aExchangerate_1// "exchangerate"
0x2afec  stelem.ref
0x2afed  dup
0x2afee  ldc.i4.s 0x17
0x2aff0  ldstr    aUtcconversiont// "utcconversiontimezonecode"
0x2aff5  stelem.ref
0x2aff6  dup
0x2aff7  ldc.i4.s 0x18
0x2aff9  ldstr    aSubscriptionid// "subscriptionid"
0x2affe  stelem.ref
0x2afff  dup
0x2b000  ldc.i4.s 0x19
0x2b002  ldstr    aFullname// "fullname"
0x2b007  stelem.ref
0x2b008  dup
0x2b009  ldc.i4.s 0x1A
0x2b00b  ldstr    aFirstname// "firstname"
0x2b010  stelem.ref
0x2b011  dup
0x2b012  ldc.i4.s 0x1B
0x2b014  ldstr    aMiddlename// "middlename"
0x2b019  stelem.ref
0x2b01a  dup
0x2b01b  ldc.i4.s 0x1C
0x2b01d  ldstr    aLastname// "lastname"
0x2b022  stelem.ref
0x2b023  dup
0x2b024  ldc.i4.s 0x1D
0x2b026  ldstr    aGoalownerid// "GoalOwnerId"
0x2b02b  stelem.ref
0x2b02c  stloc.0
0x2b02d  ldarg.0
0x2b02e  ldarg.1
0x2b02f  ldloc.0
0x2b030  call     instance bool Microsoft.Crm.Metadata.CanBeSecuredEvaluator::AttributeNameCompare(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeDescription attribute, string[] HardCodedAttributeNames)
0x2b035  ret
```
