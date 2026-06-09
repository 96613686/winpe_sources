# Microsoft.Crm.BusinessEntities.RibbonUtility::IsEntityUsingRibbon

- ea: `0x70b30`
- end: `0x7215e`
- name: `Microsoft.Crm.BusinessEntities.RibbonUtility::IsEntityUsingRibbon`
- size: `5678`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x72160`

## callees

- `0x70b30`
- `0x85d00`

## string_xrefs

- `0x715ad`: `azureserviceconnection`
- `0x716fd`: `competitor`
- `0x71712`: `channelaccessprofile`
- `0x7177b`: `contracttemplate`
- `0x71862`: `entitlementtemplate`
- `0x718a1`: `entitlementtemplatechannel`
- `0x719f1`: `kbarticlecomment`
- `0x71b17`: `personaldocumenttemplate`
- `0x71baa`: `channelaccessprofilerule`
- `0x71bbf`: `channelaccessprofileruleitem`
- `0x71c91`: `recommendationmodel`
- `0x71ca6`: `recommendationmodelmapping`
- `0x71cbb`: `recommendationmodelversion`
- `0x71cd0`: `recommendationmodelversionhistory`
- `0x71d78`: `service`
- `0x71d8d`: `serviceappointment`
- `0x71e89`: `teamtemplate`
- `0x71ef2`: `topicmodelconfiguration`
- `0x7206c`: `documenttemplate`

## pseudocode

```c

```

## disassembly

```asm
0x70b30  ldarg.0
0x70b31  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x70b36  stloc.0
0x70b37  ldloc.0
0x70b38  ldc.i4   0x7A894EAD
0x70b3d  bgt.un   loc_71028
0x70b42  ldloc.0
0x70b43  ldc.i4   0x3A91EE5D
0x70b48  bgt.un   loc_70DB5
0x70b4d  ldloc.0
0x70b4e  ldc.i4   0x202D8E44
0x70b53  bgt.un   loc_70C81
0x70b58  ldloc.0
0x70b59  ldc.i4   0xDE2124B
0x70b5e  bgt.un   loc_70BF2
0x70b63  ldloc.0
0x70b64  ldc.i4   0x69DB403
0x70b69  bgt.un.s loc_70BA9
0x70b6b  ldloc.0
0x70b6c  ldc.i4   0xD63684
0x70b71  bgt.un.s loc_70B8E
0x70b73  ldloc.0
0x70b74  ldc.i4   0xB4717
0x70b79  beq      loc_7163F
0x70b7e  ldloc.0
0x70b7f  ldc.i4   0xD63684
0x70b84  beq      loc_715C1
0x70b89  br       loc_72146
0x70b8e  ldloc.0
0x70b8f  ldc.i4   0x23A4D5E
0x70b94  beq      loc_71669
0x70b99  ldloc.0
0x70b9a  ldc.i4   0x69DB403
0x70b9f  beq      loc_720FB
0x70ba4  br       loc_72146
0x70ba9  ldloc.0
0x70baa  ldc.i4   0x964BC5D
0x70baf  bgt.un.s loc_70BCC
0x70bb1  ldloc.0
0x70bb2  ldc.i4   0x6B75FD1
0x70bb7  beq      loc_7177A
0x70bbc  ldloc.0
0x70bbd  ldc.i4   0x964BC5D
0x70bc2  beq      loc_71A44
0x70bc7  br       loc_72146
0x70bcc  ldloc.0
0x70bcd  ldc.i4   0xAAE7816
0x70bd2  beq      loc_71C51
0x70bd7  ldloc.0
0x70bd8  ldc.i4   0xCFB5881
0x70bdd  beq      loc_71A59
0x70be2  ldloc.0
0x70be3  ldc.i4   0xDE2124B
0x70be8  beq      loc_71FAE
0x70bed  br       loc_72146
0x70bf2  ldloc.0
0x70bf3  ldc.i4   0x19BB34EB
0x70bf8  bgt.un.s loc_70C38
0x70bfa  ldloc.0
0x70bfb  ldc.i4   0x127E5C5E
0x70c00  bgt.un.s loc_70C1D
0x70c02  ldloc.0
0x70c03  ldc.i4   0x11FB040B
0x70c08  beq      loc_716FC
0x70c0d  ldloc.0
0x70c0e  ldc.i4   0x127E5C5E
0x70c13  beq      loc_717CE
0x70c18  br       loc_72146
0x70c1d  ldloc.0
0x70c1e  ldc.i4   0x166F6876
0x70c23  beq      loc_71933
0x70c28  ldloc.0
0x70c29  ldc.i4   0x19BB34EB
0x70c2e  beq      loc_71CF9
0x70c33  br       loc_72146
0x70c38  ldloc.0
0x70c39  ldc.i4   0x1AC51E81
0x70c3e  bgt.un.s loc_70C5B
0x70c40  ldloc.0
0x70c41  ldc.i4   0x19F244C8
0x70c46  beq      loc_71F1B
0x70c4b  ldloc.0
0x70c4c  ldc.i4   0x1AC51E81
0x70c51  beq      loc_7162A
0x70c56  br       loc_72146
0x70c5b  ldloc.0
0x70c5c  ldc.i4   0x1AFFA305
0x70c61  beq      loc_72017
0x70c66  ldloc.0
0x70c67  ldc.i4   0x1B12602B
0x70c6c  beq      loc_720CE
0x70c71  ldloc.0
0x70c72  ldc.i4   0x202D8E44
0x70c77  beq      loc_71DA1
0x70c7c  br       loc_72146
0x70c81  ldloc.0
0x70c82  ldc.i4   0x2D065ED2
0x70c87  bgt.un   loc_70D1B
0x70c8c  ldloc.0
0x70c8d  ldc.i4   0x28C2619F
0x70c92  bgt.un.s loc_70CD2
0x70c94  ldloc.0
0x70c95  ldc.i4   0x260D185E
0x70c9a  bgt.un.s loc_70CB7
0x70c9c  ldloc.0
0x70c9d  ldc.i4   0x2448CA2F
0x70ca2  beq      loc_71A2F
0x70ca7  ldloc.0
0x70ca8  ldc.i4   0x260D185E
0x70cad  beq      loc_715EB
0x70cb2  br       loc_72146
0x70cb7  ldloc.0
0x70cb8  ldc.i4   0x28AEA025
0x70cbd  beq      loc_71972
0x70cc2  ldloc.0
0x70cc3  ldc.i4   0x28C2619F
0x70cc8  beq      loc_720AA
0x70ccd  br       loc_72146
0x70cd2  ldloc.0
0x70cd3  ldc.i4   0x29DF7FF5
0x70cd8  bgt.un.s loc_70CF5
0x70cda  ldloc.0
0x70cdb  ldc.i4   0x294FC75C
0x70ce0  beq      loc_71519
0x70ce5  ldloc.0
0x70ce6  ldc.i4   0x29DF7FF5
0x70ceb  beq      loc_71D0E
0x70cf0  br       loc_72146
0x70cf5  ldloc.0
0x70cf6  ldc.i4   0x2A5E5203
0x70cfb  beq      loc_71750
0x70d00  ldloc.0
0x70d01  ldc.i4   0x2B7081CB
0x70d06  beq      loc_71A83
0x70d0b  ldloc.0
0x70d0c  ldc.i4   0x2D065ED2
0x70d11  beq      loc_71654
0x70d16  br       loc_72146
0x70d1b  ldloc.0
0x70d1c  ldc.i4   0x3684A602
0x70d21  bgt.un.s loc_70D6C
0x70d23  ldloc.0
0x70d24  ldc.i4   0x31C00640
0x70d29  bgt.un.s loc_70D46
0x70d2b  ldloc.0
0x70d2c  ldc.i4   0x2FD6AA80
0x70d31  beq      loc_71F30
0x70d36  ldloc.0
0x70d37  ldc.i4   0x31C00640
0x70d3c  beq      loc_716BD
0x70d41  br       loc_72146
0x70d46  ldloc.0
0x70d47  ldc.i4   0x358A4E9E
0x70d4c  beq      loc_717E3
0x70d51  ldloc.0
0x70d52  ldc.i4   0x358B1F11
0x70d57  beq      loc_71D8C
0x70d5c  ldloc.0
0x70d5d  ldc.i4   0x3684A602
0x70d62  beq      loc_7191E
0x70d67  br       loc_72146
0x70d6c  ldloc.0
0x70d6d  ldc.i4   0x387405D8
0x70d72  bgt.un.s loc_70D8F
0x70d74  ldloc.0
0x70d75  ldc.i4   0x3791EE4E
0x70d7a  beq      loc_71E0A
0x70d7f  ldloc.0
0x70d80  ldc.i4   0x387405D8
0x70d85  beq      loc_71D62
0x70d8a  br       loc_72146
0x70d8f  ldloc.0
0x70d90  ldc.i4   0x38B99ED9
0x70d95  beq      loc_71726
0x70d9a  ldloc.0
0x70d9b  ldc.i4   0x391C1186
0x70da0  beq      loc_7178F
0x70da5  ldloc.0
0x70da6  ldc.i4   0x3A91EE5D
0x70dab  beq      loc_71C66
0x70db0  br       loc_72146
0x70db5  ldloc.0
0x70db6  ldc.i4   0x5D5DEB01
0x70dbb  bgt.un   loc_70EF4
0x70dc0  ldloc.0
0x70dc1  ldc.i4   0x4B3072ED
0x70dc6  bgt.un   loc_70E5A
0x70dcb  ldloc.0
0x70dcc  ldc.i4   0x43799776
0x70dd1  bgt.un.s loc_70E11
0x70dd3  ldloc.0
0x70dd4  ldc.i4   0x4173B5F6
0x70dd9  bgt.un.s loc_70DF6
0x70ddb  ldloc.0
0x70ddc  ldc.i4   0x3BE6679C
0x70de1  beq      loc_716E7
0x70de6  ldloc.0
0x70de7  ldc.i4   0x4173B5F6
0x70dec  beq      loc_718CA
0x70df1  br       loc_72146
0x70df6  ldloc.0
0x70df7  ldc.i4   0x4303B923
0x70dfc  beq      loc_7173B
0x70e01  ldloc.0
0x70e02  ldc.i4   0x43799776
0x70e07  beq      loc_71B16
0x70e0c  br       loc_72146
0x70e11  ldloc.0
0x70e12  ldc.i4   0x446D9721
0x70e17  bgt.un.s loc_70E34
0x70e19  ldloc.0
0x70e1a  ldc.i4   0x4433F178
0x70e1f  beq      loc_71948
0x70e24  ldloc.0
0x70e25  ldc.i4   0x446D9721
0x70e2a  beq      loc_720DD
0x70e2f  br       loc_72146
0x70e34  ldloc.0
0x70e35  ldc.i4   0x4477CD19
0x70e3a  beq      loc_71AD7
0x70e3f  ldloc.0
0x70e40  ldc.i4   0x478D44D5
0x70e45  beq      loc_71CBA
0x70e4a  ldloc.0
0x70e4b  ldc.i4   0x4B3072ED
0x70e50  beq      loc_71F45
0x70e55  br       loc_72146
0x70e5a  ldloc.0
0x70e5b  ldc.i4   0x5AEC13B9
0x70e60  bgt.un.s loc_70EAB
0x70e62  ldloc.0
0x70e63  ldc.i4   0x56DFDE64
0x70e68  bgt.un.s loc_70E85
0x70e6a  ldloc.0
0x70e6b  ldc.i4   0x553629DE
0x70e70  beq      loc_71BBE
0x70e75  ldloc.0
0x70e76  ldc.i4   0x56DFDE64
0x70e7b  beq      loc_71D77
0x70e80  br       loc_72146
0x70e85  ldloc.0
0x70e86  ldc.i4   0x57766D0F
0x70e8b  beq      loc_71CCF
0x70e90  ldloc.0
0x70e91  ldc.i4   0x5A906110
0x70e96  beq      loc_719B1
0x70e9b  ldloc.0
0x70e9c  ldc.i4   0x5AEC13B9
0x70ea1  beq      loc_71FC3
0x70ea6  br       loc_72146
0x70eab  ldloc.0
0x70eac  ldc.i4   0x5D0007E8
0x70eb1  bgt.un.s loc_70ECE
0x70eb3  ldloc.0
0x70eb4  ldc.i4   0x5C78D68F
0x70eb9  beq      loc_71E49
0x70ebe  ldloc.0
0x70ebf  ldc.i4   0x5D0007E8
0x70ec4  beq      loc_71B94
0x70ec9  br       loc_72146
0x70ece  ldloc.0
0x70ecf  ldc.i4   0x5D2A07F2
0x70ed4  beq      loc_719DB
0x70ed9  ldloc.0
0x70eda  ldc.i4   0x5D473C96
0x70edf  beq      loc_71E88
0x70ee4  ldloc.0
0x70ee5  ldc.i4   0x5D5DEB01
0x70eea  beq      loc_71543
0x70eef  br       loc_72146
0x70ef4  ldloc.0
0x70ef5  ldc.i4   0x7332EF8F
0x70efa  bgt.un   loc_70F8E
0x70eff  ldloc.0
0x70f00  ldc.i4   0x6399A267
0x70f05  bgt.un.s loc_70F45
0x70f07  ldloc.0
0x70f08  ldc.i4   0x61CE40F0
0x70f0d  bgt.un.s loc_70F2A
0x70f0f  ldloc.0
0x70f10  ldc.i4   0x5FF9A401
0x70f15  beq      loc_71C7B
0x70f1a  ldloc.0
0x70f1b  ldc.i4   0x61CE40F0
0x70f20  beq      loc_71A05
0x70f25  br       loc_72146
0x70f2a  ldloc.0
0x70f2b  ldc.i4   0x6217EC3D
0x70f30  beq      loc_71A1A
0x70f35  ldloc.0
0x70f36  ldc.i4   0x6399A267
0x70f3b  beq      loc_7195D
0x70f40  br       loc_72146
0x70f45  ldloc.0
0x70f46  ldc.i4   0x6BE5AA1A
0x70f4b  bgt.un.s loc_70F68
0x70f4d  ldloc.0
0x70f4e  ldc.i4   0x6B84688A
0x70f53  beq      loc_71861
0x70f58  ldloc.0
  ... truncated ...
```
