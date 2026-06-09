# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanCreatePostRelationships

- ea: `0x4e9c0`
- end: `0x4edd7`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanCreatePostRelationships`
- size: `1047`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3bf10`

## callees

- `0x4e9c0`
- `0x75380`

## string_xrefs

- `0x4ebff`: `competitor`
- `0x4ed9a`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0x4e9c0  ldarg.1
0x4e9c1  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x4e9c6  stloc.0
0x4e9c7  ldloc.0
0x4e9c8  ldc.i4   0x6BE5AA1A
0x4e9cd  bgt.un   loc_4EAB2
0x4e9d2  ldloc.0
0x4e9d3  ldc.i4   0x2A5E5203
0x4e9d8  bgt.un.s loc_4EA46
0x4e9da  ldloc.0
0x4e9db  ldc.i4   0x11FB040B
0x4e9e0  bgt.un.s loc_4EA08
0x4e9e2  ldloc.0
0x4e9e3  ldc.i4   0x964BC5D
0x4e9e8  beq      loc_4ECD0
0x4e9ed  ldloc.0
0x4e9ee  ldc.i4   0xCFB5881
0x4e9f3  beq      loc_4ECE5
0x4e9f8  ldloc.0
0x4e9f9  ldc.i4   0x11FB040B
0x4e9fe  beq      loc_4EBFE
0x4ea03  br       loc_4EDD5
0x4ea08  ldloc.0
0x4ea09  ldc.i4   0x2448CA2F
0x4ea0e  bgt.un.s loc_4EA2B
0x4ea10  ldloc.0
0x4ea11  ldc.i4   0x166F6876
0x4ea16  beq      loc_4EC67
0x4ea1b  ldloc.0
0x4ea1c  ldc.i4   0x2448CA2F
0x4ea21  beq      loc_4ECBB
0x4ea26  br       loc_4EDD5
0x4ea2b  ldloc.0
0x4ea2c  ldc.i4   0x294FC75C
0x4ea31  beq      loc_4EBAA
0x4ea36  ldloc.0
0x4ea37  ldc.i4   0x2A5E5203
0x4ea3c  beq      loc_4EC28
0x4ea41  br       loc_4EDD5
0x4ea46  ldloc.0
0x4ea47  ldc.i4   0x4303B923
0x4ea4c  bgt.un.s loc_4EA74
0x4ea4e  ldloc.0
0x4ea4f  ldc.i4   0x31C00640
0x4ea54  beq      loc_4EBE9
0x4ea59  ldloc.0
0x4ea5a  ldc.i4   0x358B1F11
0x4ea5f  beq      loc_4ED99
0x4ea64  ldloc.0
0x4ea65  ldc.i4   0x4303B923
0x4ea6a  beq      loc_4EC13
0x4ea6f  br       loc_4EDD5
0x4ea74  ldloc.0
0x4ea75  ldc.i4   0x5D2A07F2
0x4ea7a  bgt.un.s loc_4EA97
0x4ea7c  ldloc.0
0x4ea7d  ldc.i4   0x5A906110
0x4ea82  beq      loc_4EC91
0x4ea87  ldloc.0
0x4ea88  ldc.i4   0x5D2A07F2
0x4ea8d  beq      loc_4ECA6
0x4ea92  br       loc_4EDD5
0x4ea97  ldloc.0
0x4ea98  ldc.i4   0x6399A267
0x4ea9d  beq      loc_4EC7C
0x4eaa2  ldloc.0
0x4eaa3  ldc.i4   0x6BE5AA1A
0x4eaa8  beq      loc_4ECFA
0x4eaad  br       loc_4EDD5
0x4eab2  ldloc.0
0x4eab3  ldc.i4   0xB2887BD7
0x4eab8  bgt.un.s loc_4EB26
0x4eaba  ldloc.0
0x4eabb  ldc.i4   0x8A8753C7
0x4eac0  bgt.un.s loc_4EAE8
0x4eac2  ldloc.0
0x4eac3  ldc.i4   0x771D3B4C
0x4eac8  beq      loc_4ED7B
0x4eacd  ldloc.0
0x4eace  ldc.i4   0x82EBAD3A
0x4ead3  beq      loc_4EBBF
0x4ead8  ldloc.0
0x4ead9  ldc.i4   0x8A8753C7
0x4eade  beq      loc_4EC3D
0x4eae3  br       loc_4EDD5
0x4eae8  ldloc.0
0x4eae9  ldc.i4   0x98689BE9
0x4eaee  bgt.un.s loc_4EB0B
0x4eaf0  ldloc.0
0x4eaf1  ldc.i4   0x9144976A
0x4eaf6  beq      loc_4EBD4
0x4eafb  ldloc.0
0x4eafc  ldc.i4   0x98689BE9
0x4eb01  beq      loc_4ED8A
0x4eb06  br       loc_4EDD5
0x4eb0b  ldloc.0
0x4eb0c  ldc.i4   0xA08FA0FE
0x4eb11  beq      loc_4ED39
0x4eb16  ldloc.0
0x4eb17  ldc.i4   0xB2887BD7
0x4eb1c  beq      loc_4ED5D
0x4eb21  br       loc_4EDD5
0x4eb26  ldloc.0
0x4eb27  ldc.i4   0xE548412C
0x4eb2c  bgt.un.s loc_4EB6C
0x4eb2e  ldloc.0
0x4eb2f  ldc.i4   0xD0F6891F
0x4eb34  bgt.un.s loc_4EB51
0x4eb36  ldloc.0
0x4eb37  ldc.i4   0xB2F80A30
0x4eb3c  beq      loc_4EC52
0x4eb41  ldloc.0
0x4eb42  ldc.i4   0xD0F6891F
0x4eb47  beq      loc_4EDA8
0x4eb4c  br       loc_4EDD5
0x4eb51  ldloc.0
0x4eb52  ldc.i4   0xD6FABDD3
0x4eb57  beq      loc_4ED6C
0x4eb5c  ldloc.0
0x4eb5d  ldc.i4   0xE548412C
0x4eb62  beq      loc_4ED24
0x4eb67  br       loc_4EDD5
0x4eb6c  ldloc.0
0x4eb6d  ldc.i4   0xF448886C
0x4eb72  bgt.un.s loc_4EB8F
0x4eb74  ldloc.0
0x4eb75  ldc.i4   0xEC10F909
0x4eb7a  beq      loc_4EDC6
0x4eb7f  ldloc.0
0x4eb80  ldc.i4   0xF448886C
0x4eb85  beq      loc_4EDB7
0x4eb8a  br       loc_4EDD5
0x4eb8f  ldloc.0
0x4eb90  ldc.i4   0xF4DFB8B8
0x4eb95  beq      loc_4ED4E
0x4eb9a  ldloc.0
0x4eb9b  ldc.i4   0xF8963A7F
0x4eba0  beq      loc_4ED0F
0x4eba5  br       loc_4EDD5
0x4ebaa  ldarg.1
0x4ebab  ldstr    aAccount_0// "account"
0x4ebb0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ebb5  brtrue   loc_4EDD3
0x4ebba  br       loc_4EDD5
0x4ebbf  ldarg.1
0x4ebc0  ldstr    aAppointment// "appointment"
0x4ebc5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ebca  brtrue   loc_4EDD3
0x4ebcf  br       loc_4EDD5
0x4ebd4  ldarg.1
0x4ebd5  ldstr    aCampaignactivi// "campaignactivity"
0x4ebda  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ebdf  brtrue   loc_4EDD3
0x4ebe4  br       loc_4EDD5
0x4ebe9  ldarg.1
0x4ebea  ldstr    aCampaignrespon// "campaignresponse"
0x4ebef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ebf4  brtrue   loc_4EDD3
0x4ebf9  br       loc_4EDD5
0x4ebfe  ldarg.1
0x4ebff  ldstr    aCompetitor// "competitor"
0x4ec04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec09  brtrue   loc_4EDD3
0x4ec0e  br       loc_4EDD5
0x4ec13  ldarg.1
0x4ec14  ldstr    aContact_0// "contact"
0x4ec19  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec1e  brtrue   loc_4EDD3
0x4ec23  br       loc_4EDD5
0x4ec28  ldarg.1
0x4ec29  ldstr    aContract// "contract"
0x4ec2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec33  brtrue   loc_4EDD3
0x4ec38  br       loc_4EDD5
0x4ec3d  ldarg.1
0x4ec3e  ldstr    aEmail// "email"
0x4ec43  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec48  brtrue   loc_4EDD3
0x4ec4d  br       loc_4EDD5
0x4ec52  ldarg.1
0x4ec53  ldstr    aFax// "fax"
0x4ec58  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec5d  brtrue   loc_4EDD3
0x4ec62  br       loc_4EDD5
0x4ec67  ldarg.1
0x4ec68  ldstr    aGoal// "goal"
0x4ec6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec72  brtrue   loc_4EDD3
0x4ec77  br       loc_4EDD5
0x4ec7c  ldarg.1
0x4ec7d  ldstr    aIncident// "incident"
0x4ec82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec87  brtrue   loc_4EDD3
0x4ec8c  br       loc_4EDD5
0x4ec91  ldarg.1
0x4ec92  ldstr    aInvoice// "invoice"
0x4ec97  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ec9c  brtrue   loc_4EDD3
0x4eca1  br       loc_4EDD5
0x4eca6  ldarg.1
0x4eca7  ldstr    aKbarticle// "kbarticle"
0x4ecac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ecb1  brtrue   loc_4EDD3
0x4ecb6  br       loc_4EDD5
0x4ecbb  ldarg.1
0x4ecbc  ldstr    aLead_0// "lead"
0x4ecc1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ecc6  brtrue   loc_4EDD3
0x4eccb  br       loc_4EDD5
0x4ecd0  ldarg.1
0x4ecd1  ldstr    aLetter// "letter"
0x4ecd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ecdb  brtrue   loc_4EDD3
0x4ece0  br       loc_4EDD5
0x4ece5  ldarg.1
0x4ece6  ldstr    aList// "list"
0x4eceb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ecf0  brtrue   loc_4EDD3
0x4ecf5  br       loc_4EDD5
0x4ecfa  ldarg.1
0x4ecfb  ldstr    aOpportunity// "opportunity"
0x4ed00  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed05  brtrue   loc_4EDD3
0x4ed0a  br       loc_4EDD5
0x4ed0f  ldarg.1
0x4ed10  ldstr    aPhonecall// "phonecall"
0x4ed15  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed1a  brtrue   loc_4EDD3
0x4ed1f  br       loc_4EDD5
0x4ed24  ldarg.1
0x4ed25  ldstr    aProduct// "product"
0x4ed2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed2f  brtrue   loc_4EDD3
0x4ed34  br       loc_4EDD5
0x4ed39  ldarg.1
0x4ed3a  ldstr    aProcesssession// "processsession"
0x4ed3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed44  brtrue   loc_4EDD3
0x4ed49  br       loc_4EDD5
0x4ed4e  ldarg.1
0x4ed4f  ldstr    aQueue// "queue"
0x4ed54  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed59  brtrue.s loc_4EDD3
0x4ed5b  br.s     loc_4EDD5
0x4ed5d  ldarg.1
0x4ed5e  ldstr    aQuote// "quote"
0x4ed63  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed68  brtrue.s loc_4EDD3
0x4ed6a  br.s     loc_4EDD5
0x4ed6c  ldarg.1
0x4ed6d  ldstr    aRecurringappoi// "recurringappointmentmaster"
0x4ed72  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed77  brtrue.s loc_4EDD3
0x4ed79  br.s     loc_4EDD5
0x4ed7b  ldarg.1
0x4ed7c  ldstr    aSalesliteratur_0// "salesliterature"
0x4ed81  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed86  brtrue.s loc_4EDD3
0x4ed88  br.s     loc_4EDD5
0x4ed8a  ldarg.1
0x4ed8b  ldstr    aSalesorder// "salesorder"
0x4ed90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4ed95  brtrue.s loc_4EDD3
0x4ed97  br.s     loc_4EDD5
0x4ed99  ldarg.1
0x4ed9a  ldstr    aServiceappoint// "serviceappointment"
0x4ed9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4eda4  brtrue.s loc_4EDD3
0x4eda6  br.s     loc_4EDD5
0x4eda8  ldarg.1
0x4eda9  ldstr    aSystemuser_0// "systemuser"
0x4edae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4edb3  brtrue.s loc_4EDD3
0x4edb5  br.s     loc_4EDD5
0x4edb7  ldarg.1
0x4edb8  ldstr    aTask// "task"
0x4edbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4edc2  brtrue.s loc_4EDD3
0x4edc4  br.s     loc_4EDD5
0x4edc6  ldarg.1
0x4edc7  ldstr    aTerritory// "territory"
0x4edcc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4edd1  brfalse.s loc_4EDD5
0x4edd3  ldc.i4.1
0x4edd4  ret
0x4edd5  ldc.i4.0
0x4edd6  ret
```
