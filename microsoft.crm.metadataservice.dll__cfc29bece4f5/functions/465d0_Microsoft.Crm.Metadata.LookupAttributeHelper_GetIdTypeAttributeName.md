# Microsoft.Crm.Metadata.LookupAttributeHelper::GetIdTypeAttributeName

- ea: `0x465d0`
- end: `0x4670d`
- name: `Microsoft.Crm.Metadata.LookupAttributeHelper::GetIdTypeAttributeName`
- size: `317`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x46040`
- `0x46210`
- `0x541f0`

## callees

- `0x465d0`
- `0x46780`
- `0x75380`

## string_xrefs

- `0x46687`: `CreatedObjectId`
- `0x466dc`: `CreatedObjectIdTypeCode`

## pseudocode

```c

```

## disassembly

```asm
0x465d0  ldarg.0
0x465d1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x465d6  stloc.0
0x465d7  ldloc.0
0x465d8  ldc.i4   0xBF7FB1CA
0x465dd  bgt.un.s loc_46602
0x465df  ldloc.0
0x465e0  ldc.i4   0x64DFC5D6
0x465e5  beq      loc_46677
0x465ea  ldloc.0
0x465eb  ldc.i4   0x7C8F05D8
0x465f0  beq      loc_46695
0x465f5  ldloc.0
0x465f6  ldc.i4   0xBF7FB1CA
0x465fb  beq.s    loc_46668
0x465fd  br       loc_466E8
0x46602  ldloc.0
0x46603  ldc.i4   0xF06E9C90
0x46608  bgt.un.s loc_4661F
0x4660a  ldloc.0
0x4660b  ldc.i4   0xEABB9EAD
0x46610  beq.s    loc_46686
0x46612  ldloc.0
0x46613  ldc.i4   0xF06E9C90
0x46618  beq.s    loc_46656
0x4661a  br       loc_466E8
0x4661f  ldloc.0
0x46620  ldc.i4   0xF0BE4E70
0x46625  beq.s    loc_46644
0x46627  ldloc.0
0x46628  ldc.i4   0xF93751D6
0x4662d  bne.un   loc_466E8
0x46632  ldarg.0
0x46633  ldstr    aRegarding_0// "Regarding"
0x46638  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4663d  brtrue.s loc_466A4
0x4663f  br       loc_466E8
0x46644  ldarg.0
0x46645  ldstr    aRegardingobjec_1// "RegardingObjectId"
0x4664a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4664f  brtrue.s loc_466A4
0x46651  br       loc_466E8
0x46656  ldarg.0
0x46657  ldstr    aRegardingobjec_2// "RegardingObjectid"
0x4665c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46661  brtrue.s loc_466A4
0x46663  br       loc_466E8
0x46668  ldarg.0
0x46669  ldstr    aEmailsender// "EmailSender"
0x4666e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46673  brtrue.s loc_466D0
0x46675  br.s     loc_466E8
0x46677  ldarg.0
0x46678  ldstr    aOriginatingact// "OriginatingActivityId"
0x4667d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46682  brtrue.s loc_466D6
0x46684  br.s     loc_466E8
0x46686  ldarg.0
0x46687  ldstr    aCreatedobjecti// "CreatedObjectId"
0x4668c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x46691  brtrue.s loc_466DC
0x46693  br.s     loc_466E8
0x46695  ldarg.0
0x46696  ldstr    aBaserecordid_0// "BaseRecordId"
0x4669b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x466a0  brtrue.s loc_466E2
0x466a2  br.s     loc_466E8
0x466a4  ldarg.1
0x466a5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LookupAttributeHelper::BulkOperationId
0x466aa  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x466af  brfalse.s loc_466B7
0x466b1  ldstr    aRegardingobjec_3// "RegardingObjectIdTypeCode"
0x466b6  ret
0x466b7  ldarg.1
0x466b8  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.LookupAttributeHelper::DynamicPropertyInstanceEntityId
0x466bd  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x466c2  brfalse.s loc_466CA
0x466c4  ldstr    aRegardingobjec_4// "RegardingObjectIdType"
0x466c9  ret
0x466ca  ldstr    aRegardingobjec_5// "RegardingObjectTypeCode"
0x466cf  ret
0x466d0  ldstr    aEmailsenderobj// "EmailSenderObjectTypeCode"
0x466d5  ret
0x466d6  ldstr    aOriginatingact_0// "OriginatingActivityIdTypeCode"
0x466db  ret
0x466dc  ldstr    aCreatedobjecti_0// "CreatedObjectIdTypeCode"
0x466e1  ret
0x466e2  ldstr    aBaserecordidty// "BaseRecordIdTypeCode"
0x466e7  ret
0x466e8  ldarg.0
0x466e9  ldstr    aId_0// "Id"
0x466ee  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x466f3  brfalse.s loc_46701
0x466f5  ldarg.0
0x466f6  ldstr    aType_0// "Type"
0x466fb  call     string Microsoft.Crm.Metadata.LookupAttributeHelper::PopulateSuffix(string attributeName, string suffix)
0x46700  ret
0x46701  ldarg.0
0x46702  ldstr    aIdtype// "IdType"
0x46707  call     string Microsoft.Crm.Metadata.LookupAttributeHelper::PopulateSuffix(string attributeName, string suffix)
0x4670c  ret
```
