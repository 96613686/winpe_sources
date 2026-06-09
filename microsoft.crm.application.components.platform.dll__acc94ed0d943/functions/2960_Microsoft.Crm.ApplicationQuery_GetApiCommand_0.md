# Microsoft.Crm.ApplicationQuery::GetApiCommand_0

- ea: `0x2960`
- end: `0x462c`
- name: `Microsoft.Crm.ApplicationQuery::GetApiCommand_0`
- size: `7372`
- prototype: ``
- caller_count: `1`
- callee_count: `80`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x2810`

## callees

- `0xc30`
- `0x1280`
- `0x1510`
- `0x1690`
- `0x2960`
- `0x5910`
- `0x9ca50`
- `0x9cc70`
- `0x9cd90`
- `0x9cef0`
- `0x9d030`
- `0x9d070`
- `0x9d110`
- `0x9d1d0`
- `0x9d290`
- `0x9d350`
- `0x9d440`
- `0x9d520`
- `0x9d5c0`
- `0x9d670`
- `0x9d6f0`
- `0x9d790`
- `0x9d920`
- `0x9d9d0`
- `0x9daa0`
- `0x9db50`
- `0x9dc10`
- `0x9dc80`
- `0x9dcf0`
- `0x9dd80`
- `0x9de00`
- `0x9de80`
- `0x9def0`
- `0x9df90`
- `0x9e010`
- `0x9e090`
- `0x9e100`
- `0x9e1b0`
- `0x9e4f0`
- `0x9e650`
- `0x9e870`
- `0x9e900`
- `0x9eab0`
- `0x9eca0`
- `0x9ef00`
- `0x9ef80`
- `0x9f020`
- `0x9f130`
- `0x9f1c0`
- `0x9f230`

## string_xrefs

- `0x2960`: `ApplicationQuery: Building API Command.  View Id : {0}.  QueryAPI : {1}.`
- `0x34ae`: `CustomEntityService.RetrieveByObject`
- `0x34c3`: `CustomEntityService.RetrieveRelatedObjects`
- `0x34d8`: `CRMTask.RetrieveByObject`
- `0x35bf`: `SMSite.RetrieveMembers`
- `0x3724`: `CRMCompetitor.RetrieveByObject`
- `0x385f`: `CRMServiceAppointment.RetrieveByUserByParty`
- `0x38c8`: `CRMTask.RetrieveByUserByParty`
- `0x3985`: `CRMEmailTemplate.RetrieveByObject`
- `0x39ee`: `CRMArticleComment.RetrieveByObject`
- `0x3a03`: `Workflow.RetrieveWorkflowTemplate`
- `0x3aab`: `BizMerchant.RetrieveSubsidiaryTeams`
- `0x3ac0`: `BizMerchant.RetrieveSubsidiaryUsers`
- `0x3b68`: `SMResource.RetrieveServices`
- `0x3cf7`: `SystemUser.RetrieveActiveDirectoryUsers`
- `0x3d9f`: `Solution.RetrievePluginTypesCommand`
- `0x3db4`: `Solution.SolutionComponentViewDecorator`
- `0x3e32`: `CRMQueue.RetrieveCustomQueuesCommand`

## pseudocode

```c

```

## disassembly

```asm
0x2960  ldstr    aApplicationque_1// "ApplicationQuery: Building API Command."...
0x2965  ldc.i4.2
0x2966  newarr   [mscorlib]System.Object
0x296b  dup
0x296c  ldc.i4.0
0x296d  ldarg.0
0x296e  ldfld    class Microsoft.Crm.View Microsoft.Crm.ApplicationQuery::_view
0x2973  callvirt instance string Microsoft.Crm.View::get_ViewId()
0x2978  stelem.ref
0x2979  dup
0x297a  ldc.i4.1
0x297b  ldarg.1
0x297c  stelem.ref
0x297d  call     void Microsoft.Crm.Util::TraceVerbose(string message, object[] args)
0x2982  ldarg.1
0x2983  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2988  stloc.0
0x2989  ldloc.0
0x298a  ldc.i4   0x8F6EB55A
0x298f  bgt.un   loc_2E59
0x2994  ldloc.0
0x2995  ldc.i4   0x499E2B94
0x299a  bgt.un   loc_2BFC
0x299f  ldloc.0
0x29a0  ldc.i4   0x2306C078
0x29a5  bgt.un   loc_2AD3
0x29aa  ldloc.0
0x29ab  ldc.i4   0x13E3A499
0x29b0  bgt.un   loc_2A44
0x29b5  ldloc.0
0x29b6  ldc.i4   0x64838BD
0x29bb  bgt.un.s loc_29FB
0x29bd  ldloc.0
0x29be  ldc.i4   0xECDEE4
0x29c3  bgt.un.s loc_29E0
0x29c5  ldloc.0
0x29c6  ldc.i4   0xD6ACC
0x29cb  beq      loc_3A17
0x29d0  ldloc.0
0x29d1  ldc.i4   0xECDEE4
0x29d6  beq      loc_3555
0x29db  br       loc_4616
0x29e0  ldloc.0
0x29e1  ldc.i4   0x3CE05A0
0x29e6  beq      loc_381F
0x29eb  ldloc.0
0x29ec  ldc.i4   0x64838BD
0x29f1  beq      loc_36E4
0x29f6  br       loc_4616
0x29fb  ldloc.0
0x29fc  ldc.i4   0x6EA46E1
0x2a01  bgt.un.s loc_2A1E
0x2a03  ldloc.0
0x2a04  ldc.i4   0x69A6983
0x2a09  beq      loc_3B28
0x2a0e  ldloc.0
0x2a0f  ldc.i4   0x6EA46E1
0x2a14  beq      loc_33DB
0x2a19  br       loc_4616
0x2a1e  ldloc.0
0x2a1f  ldc.i4   0xCF0A228
0x2a24  beq      loc_3A95
0x2a29  ldloc.0
0x2a2a  ldc.i4   0xE3E9AE3
0x2a2f  beq      loc_3C78
0x2a34  ldloc.0
0x2a35  ldc.i4   0x13E3A499
0x2a3a  beq      loc_3AE9
0x2a3f  br       loc_4616
0x2a44  ldloc.0
0x2a45  ldc.i4   0x1CB76A8C
0x2a4a  bgt.un.s loc_2A8A
0x2a4c  ldloc.0
0x2a4d  ldc.i4   0x1A484687
0x2a52  bgt.un.s loc_2A6F
0x2a54  ldloc.0
0x2a55  ldc.i4   0x172071F2
0x2a5a  beq      loc_3E46
0x2a5f  ldloc.0
0x2a60  ldc.i4   0x1A484687
0x2a65  beq      loc_3CE1
0x2a6a  br       loc_4616
0x2a6f  ldloc.0
0x2a70  ldc.i4   0x1BE15229
0x2a75  beq      loc_3E9A
0x2a7a  ldloc.0
0x2a7b  ldc.i4   0x1CB76A8C
0x2a80  beq      loc_396F
0x2a85  br       loc_4616
0x2a8a  ldloc.0
0x2a8b  ldc.i4   0x1E5B937C
0x2a90  bgt.un.s loc_2AAD
0x2a92  ldloc.0
0x2a93  ldc.i4   0x1E2DE7FA
0x2a98  beq      loc_3DF2
0x2a9d  ldloc.0
0x2a9e  ldc.i4   0x1E5B937C
0x2aa3  beq      loc_3333
0x2aa8  br       loc_4616
0x2aad  ldloc.0
0x2aae  ldc.i4   0x220C16B0
0x2ab3  beq      loc_3873
0x2ab8  ldloc.0
0x2ab9  ldc.i4   0x222F318D
0x2abe  beq      loc_37F5
0x2ac3  ldloc.0
0x2ac4  ldc.i4   0x2306C078
0x2ac9  beq      loc_3D35
0x2ace  br       loc_4616
0x2ad3  ldloc.0
0x2ad4  ldc.i4   0x3ABF7C5C
0x2ad9  bgt.un   loc_2B6D
0x2ade  ldloc.0
0x2adf  ldc.i4   0x328F1548
0x2ae4  bgt.un.s loc_2B24
0x2ae6  ldloc.0
0x2ae7  ldc.i4   0x2BD7AB57
0x2aec  bgt.un.s loc_2B09
0x2aee  ldloc.0
0x2aef  ldc.i4   0x23902985
0x2af4  beq      loc_3EAF
0x2af9  ldloc.0
0x2afa  ldc.i4   0x2BD7AB57
0x2aff  beq      loc_35BE
0x2b04  br       loc_4616
0x2b09  ldloc.0
0x2b0a  ldc.i4   0x3128F64C
0x2b0f  beq      loc_3612
0x2b14  ldloc.0
0x2b15  ldc.i4   0x328F1548
0x2b1a  beq      loc_3930
0x2b1f  br       loc_4616
0x2b24  ldloc.0
0x2b25  ldc.i4   0x38C7C011
0x2b2a  bgt.un.s loc_2B47
0x2b2c  ldloc.0
0x2b2d  ldc.i4   0x34A988E8
0x2b32  beq      loc_3B91
0x2b37  ldloc.0
0x2b38  ldc.i4   0x38C7C011
0x2b3d  beq      loc_3EC4
0x2b42  br       loc_4616
0x2b47  ldloc.0
0x2b48  ldc.i4   0x394C39E5
0x2b4d  beq      loc_3444
0x2b52  ldloc.0
0x2b53  ldc.i4   0x3A1826BA
0x2b58  beq      loc_3666
0x2b5d  ldloc.0
0x2b5e  ldc.i4   0x3ABF7C5C
0x2b63  beq      loc_3E31
0x2b68  br       loc_4616
0x2b6d  ldloc.0
0x2b6e  ldc.i4   0x44925A45
0x2b73  bgt.un.s loc_2BB3
0x2b75  ldloc.0
0x2b76  ldc.i4   0x3C3563A5
0x2b7b  bgt.un.s loc_2B98
0x2b7d  ldloc.0
0x2b7e  ldc.i4   0x3C2C9069
0x2b83  beq      loc_35E8
0x2b88  ldloc.0
0x2b89  ldc.i4   0x3C3563A5
0x2b8e  beq      loc_352B
0x2b93  br       loc_4616
0x2b98  ldloc.0
0x2b99  ldc.i4   0x3FCDE5E0
0x2b9e  beq      loc_331E
0x2ba3  ldloc.0
0x2ba4  ldc.i4   0x44925A45
0x2ba9  beq      loc_367B
0x2bae  br       loc_4616
0x2bb3  ldloc.0
0x2bb4  ldc.i4   0x4747BEC2
0x2bb9  bgt.un.s loc_2BD6
0x2bbb  ldloc.0
0x2bbc  ldc.i4   0x44D7B1E2
0x2bc1  beq      loc_33B1
0x2bc6  ldloc.0
0x2bc7  ldc.i4   0x4747BEC2
0x2bcc  beq      loc_38B2
0x2bd1  br       loc_4616
0x2bd6  ldloc.0
0x2bd7  ldc.i4   0x482133AB
0x2bdc  beq      loc_3999
0x2be1  ldloc.0
0x2be2  ldc.i4   0x498CCAD5
0x2be7  beq      loc_3D89
0x2bec  ldloc.0
0x2bed  ldc.i4   0x499E2B94
0x2bf2  beq      loc_3DB3
0x2bf7  br       loc_4616
0x2bfc  ldloc.0
0x2bfd  ldc.i4   0x781C41B1
0x2c02  bgt.un   loc_2D30
0x2c07  ldloc.0
0x2c08  ldc.i4   0x67604827
0x2c0d  bgt.un   loc_2CA1
0x2c12  ldloc.0
0x2c13  ldc.i4   0x53DEF515
0x2c18  bgt.un.s loc_2C58
0x2c1a  ldloc.0
0x2c1b  ldc.i4   0x4DEB3AE4
0x2c20  bgt.un.s loc_2C3D
0x2c22  ldloc.0
0x2c23  ldc.i4   0x4DAA4136
0x2c28  beq      loc_3AD4
0x2c2d  ldloc.0
0x2c2e  ldc.i4   0x4DEB3AE4
0x2c33  beq      loc_357F
0x2c38  br       loc_4616
0x2c3d  ldloc.0
0x2c3e  ldc.i4   0x51C286AA
0x2c43  beq      loc_3834
0x2c48  ldloc.0
0x2c49  ldc.i4   0x53DEF515
0x2c4e  beq      loc_335D
0x2c53  br       loc_4616
0x2c58  ldloc.0
0x2c59  ldc.i4   0x6306236E
0x2c5e  bgt.un.s loc_2C7B
0x2c60  ldloc.0
0x2c61  ldc.i4   0x5ECD09B2
0x2c66  beq      loc_3C39
0x2c6b  ldloc.0
0x2c6c  ldc.i4   0x6306236E
0x2c71  beq      loc_38F1
0x2c76  br       loc_4616
0x2c7b  ldloc.0
0x2c7c  ldc.i4   0x635DB215
0x2c81  beq      loc_3E5B
0x2c86  ldloc.0
0x2c87  ldc.i4   0x66E95EEB
0x2c8c  beq      loc_3ED9
0x2c91  ldloc.0
0x2c92  ldc.i4   0x67604827
0x2c97  beq      loc_37CB
0x2c9c  br       loc_4616
0x2ca1  ldloc.0
0x2ca2  ldc.i4   0x7007858C
0x2ca7  bgt.un.s loc_2CE7
0x2ca9  ldloc.0
0x2caa  ldc.i4   0x6BA8F075
0x2caf  bgt.un.s loc_2CCC
0x2cb1  ldloc.0
0x2cb2  ldc.i4   0x67FBE0B7
0x2cb7  beq      loc_3DDD
0x2cbc  ldloc.0
0x2cbd  ldc.i4   0x6BA8F075
0x2cc2  beq      loc_3C8D
0x2cc7  br       loc_4616
0x2ccc  ldloc.0
0x2ccd  ldc.i4   0x6BB431C3
0x2cd2  beq      loc_346E
0x2cd7  ldloc.0
0x2cd8  ldc.i4   0x7007858C
0x2cdd  beq      loc_3BE5
0x2ce2  br       loc_4616
0x2ce7  ldloc.0
0x2ce8  ldc.i4   0x7306C463
0x2ced  bgt.un.s loc_2D0A
0x2cef  ldloc.0
0x2cf0  ldc.i4   0x727D2242
0x2cf5  beq      loc_3D5F
0x2cfa  ldloc.0
0x2cfb  ldc.i4   0x7306C463
0x2d00  beq      loc_3ABF
0x2d05  br       loc_4616
0x2d0a  ldloc.0
0x2d0b  ldc.i4   0x7560CEF5
0x2d10  beq      loc_3B67
0x2d15  ldloc.0
0x2d16  ldc.i4   0x778EB280
0x2d1b  beq      loc_3C0F
0x2d20  ldloc.0
0x2d21  ldc.i4   0x781C41B1
0x2d26  beq      loc_3A80
0x2d2b  br       loc_4616
0x2d30  ldloc.0
0x2d31  ldc.i4   0x8087DE34
0x2d36  bgt.un   loc_2DCA
0x2d3b  ldloc.0
0x2d3c  ldc.i4   0x79B0CC11
0x2d41  bgt.un.s loc_2D81
0x2d43  ldloc.0
0x2d44  ldc.i4   0x78BCC616
0x2d49  bgt.un.s loc_2D66
0x2d4b  ldloc.0
0x2d4c  ldc.i4   0x78AF6694
0x2d51  beq      loc_374D
0x2d56  ldloc.0
0x2d57  ldc.i4   0x78BCC616
0x2d5c  beq      loc_3B13
0x2d61  br       loc_4616
0x2d66  ldloc.0
0x2d67  ldc.i4   0x792806F2
0x2d6c  beq      loc_36F9
0x2d71  ldloc.0
0x2d72  ldc.i4   0x79B0CC11
0x2d77  beq      loc_33C6
  ... truncated ...
```
