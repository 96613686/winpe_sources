# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::CreateWorkflowAttributeType

- ea: `0x246d0`
- end: `0x248af`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::CreateWorkflowAttributeType`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x23fa0`

## callees

- `0x246d0`
- `0x24da0`

## string_xrefs

- `0x24722`: `Unexpected type for CreateCrmType`
- `0x247a4`: `Unexpected type for CreateCrmType`
- `0x24829`: `Unexpected type for CreateCrmType`
- `0x2488f`: `Unexpected type for CreateCrmType`
- `0x2489f`: `Unexpected type for CreateCrmType`

## pseudocode

```c

```

## disassembly

```asm
0x246d0  ldarg.1
0x246d1  ldstr    aBoolean// "Boolean"
0x246d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x246db  brfalse.s loc_246DF
0x246dd  ldc.i4.0
0x246de  ret
0x246df  ldarg.1
0x246e0  ldstr    aEntityreferenc// "EntityReference"
0x246e5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x246ea  brfalse.s loc_24732
0x246ec  ldarg.0
0x246ed  ldarg.2
0x246ee  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x246f3  starg.s  2
0x246f5  ldarg.2
0x246f6  ldstr    aLookup_0// "Lookup"
0x246fb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24700  brfalse.s loc_24704
0x24702  ldc.i4.6
0x24703  ret
0x24704  ldarg.2
0x24705  ldstr    aOwner// "Owner"
0x2470a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2470f  brfalse.s loc_24713
0x24711  ldc.i4.8
0x24712  ret
0x24713  ldarg.2
0x24714  ldstr    aCustomer// "Customer"
0x24719  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2471e  brfalse.s loc_24722
0x24720  ldc.i4.1
0x24721  ret
0x24722  ldstr    aUnexpectedType// "Unexpected type for CreateCrmType"
0x24727  ldc.i4   0x80040216
0x2472c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24731  throw
0x24732  ldarg.1
0x24733  ldstr    aDatetime_0// "DateTime"
0x24738  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2473d  brfalse.s loc_24741
0x2473f  ldc.i4.2
0x24740  ret
0x24741  ldarg.1
0x24742  ldstr    aDecimal// "Decimal"
0x24747  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2474c  brfalse.s loc_24750
0x2474e  ldc.i4.3
0x2474f  ret
0x24750  ldarg.1
0x24751  ldstr    aFloat_0// "Float"
0x24756  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2475b  brfalse.s loc_2475F
0x2475d  ldc.i4.4
0x2475e  ret
0x2475f  ldarg.1
0x24760  ldstr    aInteger// "Integer"
0x24765  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2476a  brfalse.s loc_2476E
0x2476c  ldc.i4.5
0x2476d  ret
0x2476e  ldarg.1
0x2476f  ldstr    aString_1// "String"
0x24774  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24779  brfalse.s loc_247B4
0x2477b  ldarg.0
0x2477c  ldarg.2
0x2477d  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x24782  starg.s  2
0x24784  ldarg.2
0x24785  ldstr    aString_1// "String"
0x2478a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2478f  brfalse.s loc_24794
0x24791  ldc.i4.s 0xE
0x24793  ret
0x24794  ldarg.2
0x24795  ldstr    aEntitynamerefe// "EntityNameReference"
0x2479a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2479f  brfalse.s loc_247A4
0x247a1  ldc.i4.s 0x10
0x247a3  ret
0x247a4  ldstr    aUnexpectedType// "Unexpected type for CreateCrmType"
0x247a9  ldc.i4   0x80040216
0x247ae  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x247b3  throw
0x247b4  ldarg.1
0x247b5  ldstr    aMoney// "Money"
0x247ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x247bf  brfalse.s loc_247C3
0x247c1  ldc.i4.7
0x247c2  ret
0x247c3  ldarg.1
0x247c4  ldstr    aPartylist// "PartyList"
0x247c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x247ce  brfalse.s loc_247D3
0x247d0  ldc.i4.s 9
0x247d2  ret
0x247d3  ldarg.1
0x247d4  ldstr    aOptionsetvalue// "OptionSetValue"
0x247d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x247de  brfalse.s loc_24839
0x247e0  ldarg.0
0x247e1  ldarg.2
0x247e2  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x247e7  starg.s  2
0x247e9  ldarg.2
0x247ea  ldstr    aPicklist_0// "Picklist"
0x247ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x247f4  brfalse.s loc_247F9
0x247f6  ldc.i4.s 0xA
0x247f8  ret
0x247f9  ldarg.2
0x247fa  ldstr    aState// "State"
0x247ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24804  brfalse.s loc_24809
0x24806  ldc.i4.s 0xC
0x24808  ret
0x24809  ldarg.2
0x2480a  ldstr    aStatus_0// "Status"
0x2480f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24814  brfalse.s loc_24819
0x24816  ldc.i4.s 0xD
0x24818  ret
0x24819  ldarg.2
0x2481a  ldstr    aBpfstagecatego// "BpfStageCategory"
0x2481f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24824  brfalse.s loc_24829
0x24826  ldc.i4.s 0x14
0x24828  ret
0x24829  ldstr    aUnexpectedType// "Unexpected type for CreateCrmType"
0x2482e  ldc.i4   0x80040216
0x24833  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x24838  throw
0x24839  ldarg.1
0x2483a  ldstr    aGuid// "Guid"
0x2483f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x24844  brfalse.s loc_2489F
0x24846  ldarg.0
0x24847  ldarg.2
0x24848  call     instance string Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::RemoveFirstAndLastChars(string input)
0x2484d  starg.s  2
0x2484f  ldarg.2
0x24850  ldstr    aKey// "Key"
0x24855  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2485a  brfalse.s loc_2485F
0x2485c  ldc.i4.s 0xB
0x2485e  ret
0x2485f  ldarg.2
0x24860  ldstr    aBpfprocess// "BpfProcess"
0x24865  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2486a  brfalse.s loc_2486F
0x2486c  ldc.i4.s 0x13
0x2486e  ret
0x2486f  ldarg.2
0x24870  ldstr    aBpfstage// "BpfStage"
0x24875  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2487a  brfalse.s loc_2487F
0x2487c  ldc.i4.s 0x15
0x2487e  ret
0x2487f  ldarg.2
0x24880  ldstr    aUniqueidentifi// "UniqueIdentifier"
0x24885  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2488a  brfalse.s loc_2488F
0x2488c  ldc.i4.s 0xF
0x2488e  ret
0x2488f  ldstr    aUnexpectedType// "Unexpected type for CreateCrmType"
0x24894  ldc.i4   0x80040216
0x24899  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x2489e  throw
0x2489f  ldstr    aUnexpectedType// "Unexpected type for CreateCrmType"
0x248a4  ldc.i4   0x80040216
0x248a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x248ae  throw
```
