# Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionLabelsForAutoCreatedAttribute

- ea: `0xb0c0`
- end: `0xcb03`
- name: `Microsoft.Crm.Tools.LangProvisioning.LanguageActivation::ProvisionLabelsForAutoCreatedAttribute`
- size: `6723`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x953e0`

## callees

- `0xb0c0`
- `0xcc40`
- `0xd090`
- `0xd140`
- `0x94fa0`
- `0x950e0`

## string_xrefs

- `0xb40d`: `createdby`
- `0xb3f8`: `createdon`
- `0xb44c`: `createdonbehalfby`
- `0xb5db`: `processid`
- `0xb605`: `traversedpath`
- `0xb62f`: `completedon`
- `0xb7d3`: `overriddencreatedon`
- `0xb7e8`: `createdbyexternalparty`
- `0xb812`: `CreatedOnInfoDescription`
- `0xb83a`: `CreatedOnInfoDisplayName`
- `0xb867`: `CreatedByInfoDescription`
- `0xb88f`: `CreatedByInfoDisplayName`
- `0xb966`: `CreatedOnBehalfByInfoDescription`
- `0xb98e`: `CreatedOnBehalfByInfoDisplayName`
- `0xbf37`: `ProcessIdAttributeDescription`
- `0xbf5f`: `ProcessIdAttributeDisplayName`
- `0xbffe`: `TraversedPathInfoDescription`
- `0xc026`: `TraversedPathInfoDisplayName`
- `0xc053`: `TraversedPathAttributeDescription`
- `0xc07b`: `TraversedPathAttributeDescription`
- `0xc0fd`: `CompletedOnInfoDescription`
- `0xc125`: `CompletedOnInfoDisplayName`
- `0xc251`: `BusinessIdInfoDescription`
- `0xc279`: `BusinessIdInfoDisplayName`
- `0xc7a1`: `OverriddenCreatedOnDescription`
- `0xc7c9`: `OverriddenCreatedOnDisplayName`
- `0xc7f6`: `createdby.description`
- `0xc81e`: `createdby.label`
- `0xc98d`: `lastUpdatedOnRollupFieldInfoDescription`
- `0xc9b5`: `lastUpdatedOnRollupFieldInfoDisplayName`

## pseudocode

```c

```

## disassembly

```asm
0xb0c0  ldarg.3
0xb0c1  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::get_Context()
0xb0c6  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xb0cb  ldarga.s 1
0xb0cd  call     instance valuetype [mscorlib]System.Guid LabelData::get_ObjectId()
0xb0d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetAttribute(valuetype [mscorlib]System.Guid)
0xb0d7  stloc.0
0xb0d8  ldloc.0
0xb0d9  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Name()
0xb0de  stloc.1
0xb0df  ldloc.1
0xb0e0  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xb0e5  stloc.2
0xb0e6  ldloc.2
0xb0e7  ldc.i4   0x70D5BFF2
0xb0ec  bgt.un   loc_B274
0xb0f1  ldloc.2
0xb0f2  ldc.i4   0x33008BA0
0xb0f7  bgt.un   loc_B1AC
0xb0fc  ldloc.2
0xb0fd  ldc.i4   0x151A7EF0
0xb102  bgt.un.s loc_B158
0xb104  ldloc.2
0xb105  ldc.i4   0x71B5F94
0xb10a  bgt.un.s loc_B132
0xb10c  ldloc.2
0xb10d  ldc.i4   0x2336E56
0xb112  beq      loc_B4C9
0xb117  ldloc.2
0xb118  ldc.i4   0x37F9C6E
0xb11d  beq      loc_B604
0xb122  ldloc.2
0xb123  ldc.i4   0x71B5F94
0xb128  beq      loc_B682
0xb12d  br       loc_C897
0xb132  ldloc.2
0xb133  ldc.i4   0xAC6C6C6
0xb138  beq      loc_B40C
0xb13d  ldloc.2
0xb13e  ldc.i4   0xF342417
0xb143  beq      loc_B73F
0xb148  ldloc.2
0xb149  ldc.i4   0x151A7EF0
0xb14e  beq      loc_B586
0xb153  br       loc_C897
0xb158  ldloc.2
0xb159  ldc.i4   0x2163A739
0xb15e  bgt.un.s loc_B186
0xb160  ldloc.2
0xb161  ldc.i4   0x1AFB0736
0xb166  beq      loc_B5EF
0xb16b  ldloc.2
0xb16c  ldc.i4   0x1BBA1596
0xb171  beq      loc_B3F7
0xb176  ldloc.2
0xb177  ldc.i4   0x2163A739
0xb17c  beq      loc_B619
0xb181  br       loc_C897
0xb186  ldloc.2
0xb187  ldc.i4   0x26F8DAA8
0xb18c  beq      loc_B508
0xb191  ldloc.2
0xb192  ldc.i4   0x290E5E51
0xb197  beq      loc_B55C
0xb19c  ldloc.2
0xb19d  ldc.i4   0x33008BA0
0xb1a2  beq      loc_B475
0xb1a7  br       loc_C897
0xb1ac  ldloc.2
0xb1ad  ldc.i4   0x4467CF67
0xb1b2  bgt.un.s loc_B208
0xb1b4  ldloc.2
0xb1b5  ldc.i4   0x3AF103F2
0xb1ba  bgt.un.s loc_B1E2
0xb1bc  ldloc.2
0xb1bd  ldc.i4   0x35567429
0xb1c2  beq      loc_B658
0xb1c7  ldloc.2
0xb1c8  ldc.i4   0x3616BC92
0xb1cd  beq      loc_B6AC
0xb1d2  ldloc.2
0xb1d3  ldc.i4   0x3AF103F2
0xb1d8  beq      loc_B547
0xb1dd  br       loc_C897
0xb1e2  ldloc.2
0xb1e3  ldc.i4   0x3C787F0B
0xb1e8  beq      loc_B62E
0xb1ed  ldloc.2
0xb1ee  ldc.i4   0x42454824
0xb1f3  beq      loc_B715
0xb1f8  ldloc.2
0xb1f9  ldc.i4   0x4467CF67
0xb1fe  beq      loc_B571
0xb203  br       loc_C897
0xb208  ldloc.2
0xb209  ldc.i4   0x59603C55
0xb20e  bgt.un.s loc_B236
0xb210  ldloc.2
0xb211  ldc.i4   0x52830303
0xb216  beq      loc_B697
0xb21b  ldloc.2
0xb21c  ldc.i4   0x56299123
0xb221  beq      loc_B700
0xb226  ldloc.2
0xb227  ldc.i4   0x59603C55
0xb22c  beq      loc_B643
0xb231  br       loc_C897
0xb236  ldloc.2
0xb237  ldc.i4   0x66DE6F1A
0xb23c  bgt.un.s loc_B259
0xb23e  ldloc.2
0xb23f  ldc.i4   0x625693D7
0xb244  beq      loc_B66D
0xb249  ldloc.2
0xb24a  ldc.i4   0x66DE6F1A
0xb24f  beq      loc_B769
0xb254  br       loc_C897
0xb259  ldloc.2
0xb25a  ldc.i4   0x6FBBEF43
0xb25f  beq      loc_B6EB
0xb264  ldloc.2
0xb265  ldc.i4   0x70D5BFF2
0xb26a  beq      loc_B77E
0xb26f  br       loc_C897
0xb274  ldloc.2
0xb275  ldc.i4   0xC09344DE
0xb27a  bgt.un   loc_B32F
0xb27f  ldloc.2
0xb280  ldc.i4   0x9A9119F7
0xb285  bgt.un.s loc_B2DB
0xb287  ldloc.2
0xb288  ldc.i4   0x85830766
0xb28d  bgt.un.s loc_B2B5
0xb28f  ldloc.2
0xb290  ldc.i4   0x78A58F04
0xb295  beq      loc_B6C1
0xb29a  ldloc.2
0xb29b  ldc.i4   0x801A40D7
0xb2a0  beq      loc_B7E7
0xb2a5  ldloc.2
0xb2a6  ldc.i4   0x85830766
0xb2ab  beq      loc_B4F3
0xb2b0  br       loc_C897
0xb2b5  ldloc.2
0xb2b6  ldc.i4   0x950FD58B
0xb2bb  beq      loc_B421
0xb2c0  ldloc.2
0xb2c1  ldc.i4   0x95CD8075
0xb2c6  beq      loc_B72A
0xb2cb  ldloc.2
0xb2cc  ldc.i4   0x9A9119F7
0xb2d1  beq      loc_B5DA
0xb2d6  br       loc_C897
0xb2db  ldloc.2
0xb2dc  ldc.i4   0xA7D06A47
0xb2e1  bgt.un.s loc_B309
0xb2e3  ldloc.2
0xb2e4  ldc.i4   0x9DEF900B
0xb2e9  beq      loc_B436
0xb2ee  ldloc.2
0xb2ef  ldc.i4   0x9EE0E262
0xb2f4  beq      loc_B48A
0xb2f9  ldloc.2
0xb2fa  ldc.i4   0xA7D06A47
0xb2ff  beq      loc_B44B
0xb304  br       loc_C897
0xb309  ldloc.2
0xb30a  ldc.i4   0xB148C085
0xb30f  beq      loc_B51D
0xb314  ldloc.2
0xb315  ldc.i4   0xB40BFCA2
0xb31a  beq      loc_B7D2
0xb31f  ldloc.2
0xb320  ldc.i4   0xC09344DE
0xb325  beq      loc_B793
0xb32a  br       loc_C897
0xb32f  ldloc.2
0xb330  ldc.i4   0xD8FAAA7A
0xb335  bgt.un.s loc_B38B
0xb337  ldloc.2
0xb338  ldc.i4   0xCBAA02E4
0xb33d  bgt.un.s loc_B365
0xb33f  ldloc.2
0xb340  ldc.i4   0xC1F52034
0xb345  beq      loc_B7BD
0xb34a  ldloc.2
0xb34b  ldc.i4   0xC3363EB8
0xb350  beq      loc_B6D6
0xb355  ldloc.2
0xb356  ldc.i4   0xCBAA02E4
0xb35b  beq      loc_B5B0
0xb360  br       loc_C897
0xb365  ldloc.2
0xb366  ldc.i4   0xCE2845CD
0xb36b  beq      loc_B4DE
0xb370  ldloc.2
0xb371  ldc.i4   0xD2040CBE
0xb376  beq      loc_B4B4
0xb37b  ldloc.2
0xb37c  ldc.i4   0xD8FAAA7A
0xb381  beq      loc_B5C5
0xb386  br       loc_C897
0xb38b  ldloc.2
0xb38c  ldc.i4   0xE56B1C59
0xb391  bgt.un.s loc_B3B9
0xb393  ldloc.2
0xb394  ldc.i4   0xD9E5D09C
0xb399  beq      loc_B7FC
0xb39e  ldloc.2
0xb39f  ldc.i4   0xE00FF162
0xb3a4  beq      loc_B460
0xb3a9  ldloc.2
0xb3aa  ldc.i4   0xE56B1C59
0xb3af  beq      loc_B532
0xb3b4  br       loc_C897
0xb3b9  ldloc.2
0xb3ba  ldc.i4   0xF4AB8ACB
0xb3bf  bgt.un.s loc_B3DC
0xb3c1  ldloc.2
0xb3c2  ldc.i4   0xEC1A47FE
0xb3c7  beq      loc_B7A8
0xb3cc  ldloc.2
0xb3cd  ldc.i4   0xF4AB8ACB
0xb3d2  beq      loc_B49F
0xb3d7  br       loc_C897
0xb3dc  ldloc.2
0xb3dd  ldc.i4   0xFCE7F464
0xb3e2  beq      loc_B754
0xb3e7  ldloc.2
0xb3e8  ldc.i4   0xFF3E521C
0xb3ed  beq      loc_B59B
0xb3f2  br       loc_C897
0xb3f7  ldloc.1
0xb3f8  ldstr    aCreatedon// "createdon"
0xb3fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb402  brtrue   loc_B811
0xb407  br       loc_C897
0xb40c  ldloc.1
0xb40d  ldstr    aCreatedby// "createdby"
0xb412  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb417  brtrue   loc_B866
0xb41c  br       loc_C897
0xb421  ldloc.1
0xb422  ldstr    aModifiedon// "modifiedon"
0xb427  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb42c  brtrue   loc_B8BB
0xb431  br       loc_C897
0xb436  ldloc.1
0xb437  ldstr    aModifiedby// "modifiedby"
0xb43c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb441  brtrue   loc_B910
0xb446  br       loc_C897
0xb44b  ldloc.1
0xb44c  ldstr    aCreatedonbehal// "createdonbehalfby"
0xb451  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb456  brtrue   loc_B965
0xb45b  br       loc_C897
0xb460  ldloc.1
0xb461  ldstr    aModifiedonbeha// "modifiedonbehalfby"
0xb466  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb46b  brtrue   loc_B9BA
0xb470  br       loc_C897
0xb475  ldloc.1
0xb476  ldstr    aOwneridyominam// "owneridyominame"
0xb47b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb480  brtrue   loc_BA0F
0xb485  br       loc_C897
0xb48a  ldloc.1
0xb48b  ldstr    aExchangerate// "exchangerate"
0xb490  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb495  brtrue   loc_BA3C
0xb49a  br       loc_C897
0xb49f  ldloc.1
0xb4a0  ldstr    aStatecode// "statecode"
0xb4a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb4aa  brtrue   loc_BA69
0xb4af  br       loc_C897
0xb4b4  ldloc.1
0xb4b5  ldstr    aStatuscode// "statuscode"
0xb4ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb4bf  brtrue   loc_BA96
0xb4c4  br       loc_C897
0xb4c9  ldloc.1
0xb4ca  ldstr    aVersionnumber// "versionnumber"
0xb4cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb4d4  brtrue   loc_BAC3
0xb4d9  br       loc_C897
0xb4de  ldloc.1
0xb4df  ldstr    aTransactioncur// "transactioncurrencyid"
0xb4e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb4e9  brtrue   loc_BB18
0xb4ee  br       loc_C897
0xb4f3  ldloc.1
0xb4f4  ldstr    aOwninguser// "owninguser"
0xb4f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb4fe  brtrue   loc_BB6D
0xb503  br       loc_C897
0xb508  ldloc.1
0xb509  ldstr    aOwningteam// "owningteam"
0xb50e  call     bool [mscorlib]System.String::op_Equality(string, string)
  ... truncated ...
```
