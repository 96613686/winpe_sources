# Microsoft.Crm.ObjectModel.CrmSecurityExtensionFactory::Get

- ea: `0x174a00`
- end: `0x175542`
- name: `Microsoft.Crm.ObjectModel.CrmSecurityExtensionFactory::Get`
- size: `2882`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xc6640`

## callees

- `0x804a0`
- `0x804f0`
- `0x8d7c0`
- `0xc2490`
- `0xc6630`
- `0xc9d20`
- `0xcf550`
- `0xe1190`
- `0xe1610`
- `0xf8ef0`
- `0x11e220`
- `0x11e580`
- `0x11e750`
- `0x11e920`
- `0x11ed50`
- `0x11ef20`
- `0x11f1f0`
- `0x11f460`
- `0x11f4c0`
- `0x11f730`
- `0x140fa0`
- `0x158f30`
- `0x1733f0`
- `0x174a00`
- `0x175550`
- `0x1755d0`
- `0x1b30f0`
- `0x1b4ab0`
- `0x1b5b80`
- `0x1b5f90`
- `0x1b9d10`
- `0x1beda0`
- `0x1c5ae0`
- `0x1e58d0`
- `0x1e7550`
- `0x22be40`

## string_xrefs

- `0x17542f`: `SavedOrgInsightsConfiguration`
- `0x175054`: `Template`
- `0x17548a`: `ActivityPartyServicebaseFactory`
- `0x1751a4`: `PrincipalObjectAttributeAccess`
- `0x174eda`: `CompetitorAddress`
- `0x174f58`: `PostComment`

## pseudocode

```c

```

## disassembly

```asm
0x174a00  ldarg.2
0x174a01  castclass Microsoft.Crm.ObjectModel.IActivityPartyServicebaseFactory
0x174a06  stloc.0
0x174a07  ldarg.1
0x174a08  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x174a0d  stloc.1
0x174a0e  ldloc.1
0x174a0f  ldc.i4   0x807A6AA9
0x174a14  bgt.un   loc_174C60
0x174a19  ldloc.1
0x174a1a  ldc.i4   0x445CB1D1
0x174a1f  bgt.un   loc_174B42
0x174a24  ldloc.1
0x174a25  ldc.i4   0x242FAA23
0x174a2a  bgt.un   loc_174AB3
0x174a2f  ldloc.1
0x174a30  ldc.i4   0x14635B23
0x174a35  bgt.un.s loc_174A75
0x174a37  ldloc.1
0x174a38  ldc.i4   0xB01B6F5
0x174a3d  bgt.un.s loc_174A5A
0x174a3f  ldloc.1
0x174a40  ldc.i4   0xA46C77D
0x174a45  beq      loc_174F2D
0x174a4a  ldloc.1
0x174a4b  ldc.i4   0xB01B6F5
0x174a50  beq      loc_174EC4
0x174a55  br       loc_17553C
0x174a5a  ldloc.1
0x174a5b  ldc.i4   0x13E5BC70
0x174a60  beq      loc_174EAF
0x174a65  ldloc.1
0x174a66  ldc.i4   0x14635B23
0x174a6b  beq      loc_17513A
0x174a70  br       loc_17553C
0x174a75  ldloc.1
0x174a76  ldc.i4   0x22CC4A33
0x174a7b  bgt.un.s loc_174A98
0x174a7d  ldloc.1
0x174a7e  ldc.i4   0x1BA2F42D
0x174a83  beq      loc_17535C
0x174a88  ldloc.1
0x174a89  ldc.i4   0x22CC4A33
0x174a8e  beq      loc_175068
0x174a93  br       loc_17553C
0x174a98  ldloc.1
0x174a99  ldc.i4   0x23B0D815
0x174a9e  beq      loc_175029
0x174aa3  ldloc.1
0x174aa4  ldc.i4   0x242FAA23
0x174aa9  beq      loc_1752F3
0x174aae  br       loc_17553C
0x174ab3  ldloc.1
0x174ab4  ldc.i4   0x3B6DFA92
0x174ab9  bgt.un.s loc_174AF9
0x174abb  ldloc.1
0x174abc  ldc.i4   0x29A46B54
0x174ac1  bgt.un.s loc_174ADE
0x174ac3  ldloc.1
0x174ac4  ldc.i4   0x29617E96
0x174ac9  beq      loc_175221
0x174ace  ldloc.1
0x174acf  ldc.i4   0x29A46B54
0x174ad4  beq      loc_1751A3
0x174ad9  br       loc_17553C
0x174ade  ldloc.1
0x174adf  ldc.i4   0x351B9C62
0x174ae4  beq      loc_1750A7
0x174ae9  ldloc.1
0x174aea  ldc.i4   0x3B6DFA92
0x174aef  beq      loc_1750FB
0x174af4  br       loc_17553C
0x174af9  ldloc.1
0x174afa  ldc.i4   0x3F43BB84
0x174aff  bgt.un.s loc_174B1C
0x174b01  ldloc.1
0x174b02  ldc.i4   0x3C00740E
0x174b07  beq      loc_17507D
0x174b0c  ldloc.1
0x174b0d  ldc.i4   0x3F43BB84
0x174b12  beq      loc_174FEA
0x174b17  br       loc_17553C
0x174b1c  ldloc.1
0x174b1d  ldc.i4   0x3FA484BE
0x174b22  beq      loc_175125
0x174b27  ldloc.1
0x174b28  ldc.i4   0x421E0F5D
0x174b2d  beq      loc_175419
0x174b32  ldloc.1
0x174b33  ldc.i4   0x445CB1D1
0x174b38  beq      loc_17524B
0x174b3d  br       loc_17553C
0x174b42  ldloc.1
0x174b43  ldc.i4   0x65966B2B
0x174b48  bgt.un   loc_174BD1
0x174b4d  ldloc.1
0x174b4e  ldc.i4   0x59F8A2FC
0x174b53  bgt.un.s loc_174B93
0x174b55  ldloc.1
0x174b56  ldc.i4   0x529C60CC
0x174b5b  bgt.un.s loc_174B78
0x174b5d  ldloc.1
0x174b5e  ldc.i4   0x4F943A64
0x174b63  beq      loc_1753B0
0x174b68  ldloc.1
0x174b69  ldc.i4   0x529C60CC
0x174b6e  beq      loc_175371
0x174b73  br       loc_17553C
0x174b78  ldloc.1
0x174b79  ldc.i4   0x59CA5C18
0x174b7e  beq      loc_175404
0x174b83  ldloc.1
0x174b84  ldc.i4   0x59F8A2FC
0x174b89  beq      loc_175260
0x174b8e  br       loc_17553C
0x174b93  ldloc.1
0x174b94  ldc.i4   0x5BE82FBE
0x174b99  bgt.un.s loc_174BB6
0x174b9b  ldloc.1
0x174b9c  ldc.i4   0x5ABE5677
0x174ba1  beq      loc_1751CD
0x174ba6  ldloc.1
0x174ba7  ldc.i4   0x5BE82FBE
0x174bac  beq      loc_175347
0x174bb1  br       loc_17553C
0x174bb6  ldloc.1
0x174bb7  ldc.i4   0x6179841C
0x174bbc  beq      loc_1753EF
0x174bc1  ldloc.1
0x174bc2  ldc.i4   0x65966B2B
0x174bc7  beq      loc_175053
0x174bcc  br       loc_17553C
0x174bd1  ldloc.1
0x174bd2  ldc.i4   0x73AC94C3
0x174bd7  bgt.un.s loc_174C17
0x174bd9  ldloc.1
0x174bda  ldc.i4   0x683C933C
0x174bdf  bgt.un.s loc_174BFC
0x174be1  ldloc.1
0x174be2  ldc.i4   0x6604212A
0x174be7  beq      loc_174F81
0x174bec  ldloc.1
0x174bed  ldc.i4   0x683C933C
0x174bf2  beq      loc_17503E
0x174bf7  br       loc_17553C
0x174bfc  ldloc.1
0x174bfd  ldc.i4   0x71EC87B0
0x174c02  beq      loc_1751F7
0x174c07  ldloc.1
0x174c08  ldc.i4   0x73AC94C3
0x174c0d  beq      loc_175275
0x174c12  br       loc_17553C
0x174c17  ldloc.1
0x174c18  ldc.i4   0x779662AF
0x174c1d  bgt.un.s loc_174C3A
0x174c1f  ldloc.1
0x174c20  ldc.i4   0x76EF3D8C
0x174c25  beq      loc_1752DE
0x174c2a  ldloc.1
0x174c2b  ldc.i4   0x779662AF
0x174c30  beq      loc_175164
0x174c35  br       loc_17553C
0x174c3a  ldloc.1
0x174c3b  ldc.i4   0x7864DEF4
0x174c40  beq      loc_174F6C
0x174c45  ldloc.1
0x174c46  ldc.i4   0x7BA4F807
0x174c4b  beq      loc_175110
0x174c50  ldloc.1
0x174c51  ldc.i4   0x807A6AA9
0x174c56  beq      loc_1751E2
0x174c5b  br       loc_17553C
0x174c60  ldloc.1
0x174c61  ldc.i4   0xB7577C6F
0x174c66  bgt.un   loc_174D89
0x174c6b  ldloc.1
0x174c6c  ldc.i4   0x9D973548
0x174c71  bgt.un   loc_174CFA
0x174c76  ldloc.1
0x174c77  ldc.i4   0x9643522E
0x174c7c  bgt.un.s loc_174CBC
0x174c7e  ldloc.1
0x174c7f  ldc.i4   0x91ADCEBC
0x174c84  bgt.un.s loc_174CA1
0x174c86  ldloc.1
0x174c87  ldc.i4   0x8D2937A1
0x174c8c  beq      loc_17531D
0x174c91  ldloc.1
0x174c92  ldc.i4   0x91ADCEBC
0x174c97  beq      loc_1750D1
0x174c9c  br       loc_17553C
0x174ca1  ldloc.1
0x174ca2  ldc.i4   0x9456C141
0x174ca7  beq      loc_174FAB
0x174cac  ldloc.1
0x174cad  ldc.i4   0x9643522E
0x174cb2  beq      loc_174FFF
0x174cb7  br       loc_17553C
0x174cbc  ldloc.1
0x174cbd  ldc.i4   0x99486786
0x174cc2  bgt.un.s loc_174CDF
0x174cc4  ldloc.1
0x174cc5  ldc.i4   0x969BB496
0x174cca  beq      loc_17539B
0x174ccf  ldloc.1
0x174cd0  ldc.i4   0x99486786
0x174cd5  beq      loc_1750BC
0x174cda  br       loc_17553C
0x174cdf  ldloc.1
0x174ce0  ldc.i4   0x9C52B721
0x174ce5  beq      loc_17518E
0x174cea  ldloc.1
0x174ceb  ldc.i4   0x9D973548
0x174cf0  beq      loc_17514F
0x174cf5  br       loc_17553C
0x174cfa  ldloc.1
0x174cfb  ldc.i4   0xA29A7232
0x174d00  bgt.un.s loc_174D40
0x174d02  ldloc.1
0x174d03  ldc.i4   0x9E52653F
0x174d08  bgt.un.s loc_174D25
0x174d0a  ldloc.1
0x174d0b  ldc.i4   0x9DEC979B
0x174d10  beq      loc_175332
0x174d15  ldloc.1
0x174d16  ldc.i4   0x9E52653F
0x174d1b  beq      loc_174FD5
0x174d20  br       loc_17553C
0x174d25  ldloc.1
0x174d26  ldc.i4   0xA1CF2FD3
0x174d2b  beq      loc_17528A
0x174d30  ldloc.1
0x174d31  ldc.i4   0xA29A7232
0x174d36  beq      loc_175308
0x174d3b  br       loc_17553C
0x174d40  ldloc.1
0x174d41  ldc.i4   0xAF7C29A7
0x174d46  bgt.un.s loc_174D63
0x174d48  ldloc.1
0x174d49  ldc.i4   0xA94E5C80
0x174d4e  beq      loc_1752B4
0x174d53  ldloc.1
0x174d54  ldc.i4   0xAF7C29A7
0x174d59  beq      loc_174EEE
0x174d5e  br       loc_17553C
0x174d63  ldloc.1
0x174d64  ldc.i4   0xAFB3E591
0x174d69  beq      loc_1752C9
0x174d6e  ldloc.1
0x174d6f  ldc.i4   0xB26DA2F2
0x174d74  beq      loc_175014
0x174d79  ldloc.1
0x174d7a  ldc.i4   0xB7577C6F
0x174d7f  beq      loc_1750E6
0x174d84  br       loc_17553C
0x174d89  ldloc.1
0x174d8a  ldc.i4   0xD79E2A53
0x174d8f  bgt.un   loc_174E23
0x174d94  ldloc.1
0x174d95  ldc.i4   0xC7AC09C9
0x174d9a  bgt.un.s loc_174DDA
0x174d9c  ldloc.1
0x174d9d  ldc.i4   0xC54502BA
0x174da2  bgt.un.s loc_174DBF
0x174da4  ldloc.1
0x174da5  ldc.i4   0xBDAA4E80
0x174daa  beq      loc_174F57
0x174daf  ldloc.1
0x174db0  ldc.i4   0xC54502BA
0x174db5  beq      loc_17520C
0x174dba  br       loc_17553C
0x174dbf  ldloc.1
0x174dc0  ldc.i4   0xC79BAA2F
0x174dc5  beq      loc_174F96
0x174dca  ldloc.1
0x174dcb  ldc.i4   0xC7AC09C9
0x174dd0  beq      loc_174ED9
0x174dd5  br       loc_17553C
0x174dda  ldloc.1
0x174ddb  ldc.i4   0xCF3EA3AA
0x174de0  bgt.un.s loc_174DFD
0x174de2  ldloc.1
0x174de3  ldc.i4   0xCA6A85AE
0x174de8  beq      loc_175179
0x174ded  ldloc.1
0x174dee  ldc.i4   0xCF3EA3AA
0x174df3  beq      loc_17529F
0x174df8  br       loc_17553C
0x174dfd  ldloc.1
0x174dfe  ldc.i4   0xD3D7036D
0x174e03  beq      loc_174F18
0x174e08  ldloc.1
0x174e09  ldc.i4   0xD5060070
0x174e0e  beq      loc_175443
0x174e13  ldloc.1
0x174e14  ldc.i4   0xD79E2A53
0x174e19  beq      loc_175386
0x174e1e  br       loc_17553C
0x174e23  ldloc.1
0x174e24  ldc.i4   0xF0C79167
  ... truncated ...
```
