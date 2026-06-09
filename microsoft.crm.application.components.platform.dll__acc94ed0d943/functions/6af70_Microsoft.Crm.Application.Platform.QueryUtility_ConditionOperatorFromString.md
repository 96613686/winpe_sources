# Microsoft.Crm.Application.Platform.QueryUtility::ConditionOperatorFromString

- ea: `0x6af70`
- end: `0x6b993`
- name: `Microsoft.Crm.Application.Platform.QueryUtility::ConditionOperatorFromString`
- size: `2595`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x6ad50`

## callees

- `0x6af70`
- `0x9ca50`

## string_xrefs

- `0x6b832`: `eq-businessid`
- `0x6b847`: `ne-businessid`

## pseudocode

```c

```

## disassembly

```asm
0x6af70  ldarg.0
0x6af71  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6af76  stloc.0
0x6af77  ldloc.0
0x6af78  ldc.i4   0x77074BA4
0x6af7d  bgt.un   loc_6B198
0x6af82  ldloc.0
0x6af83  ldc.i4   0x3C206DD9
0x6af88  bgt.un   loc_6B085
0x6af8d  ldloc.0
0x6af8e  ldc.i4   0x13E4B180
0x6af93  bgt.un.s loc_6B001
0x6af95  ldloc.0
0x6af96  ldc.i4   0xBE7CF36
0x6af9b  bgt.un.s loc_6AFC3
0x6af9d  ldloc.0
0x6af9e  ldc.i4   0x7A3AC7
0x6afa3  beq      loc_6B663
0x6afa8  ldloc.0
0x6afa9  ldc.i4   0x6BE8DBE
0x6afae  beq      loc_6B480
0x6afb3  ldloc.0
0x6afb4  ldc.i4   0xBE7CF36
0x6afb9  beq      loc_6B441
0x6afbe  br       loc_6B974
0x6afc3  ldloc.0
0x6afc4  ldc.i4   0x10A4A95A
0x6afc9  bgt.un.s loc_6AFE6
0x6afcb  ldloc.0
0x6afcc  ldc.i4   0xF81E1B5
0x6afd1  beq      loc_6B624
0x6afd6  ldloc.0
0x6afd7  ldc.i4   0x10A4A95A
0x6afdc  beq      loc_6B5A6
0x6afe1  br       loc_6B974
0x6afe6  ldloc.0
0x6afe7  ldc.i4   0x111C2E9D
0x6afec  beq      loc_6B831
0x6aff1  ldloc.0
0x6aff2  ldc.i4   0x13E4B180
0x6aff7  beq      loc_6B6A2
0x6affc  br       loc_6B974
0x6b001  ldloc.0
0x6b002  ldc.i4   0x2A999937
0x6b007  bgt.un.s loc_6B047
0x6b009  ldloc.0
0x6b00a  ldc.i4   0x1B0EF6FD
0x6b00f  bgt.un.s loc_6B02C
0x6b011  ldloc.0
0x6b012  ldc.i4   0x1AA3E856
0x6b017  beq      loc_6B456
0x6b01c  ldloc.0
0x6b01d  ldc.i4   0x1B0EF6FD
0x6b022  beq      loc_6B60F
0x6b027  br       loc_6B974
0x6b02c  ldloc.0
0x6b02d  ldc.i4   0x20F60A0B
0x6b032  beq      loc_6B807
0x6b037  ldloc.0
0x6b038  ldc.i4   0x2A999937
0x6b03d  beq      loc_6B3C3
0x6b042  br       loc_6B974
0x6b047  ldloc.0
0x6b048  ldc.i4   0x35A5CDE2
0x6b04d  bgt.un.s loc_6B06A
0x6b04f  ldloc.0
0x6b050  ldc.i4   0x2DED9EC2
0x6b055  beq      loc_6B5E5
0x6b05a  ldloc.0
0x6b05b  ldc.i4   0x35A5CDE2
0x6b060  beq      loc_6B591
0x6b065  br       loc_6B974
0x6b06a  ldloc.0
0x6b06b  ldc.i4   0x3773E1DF
0x6b070  beq      loc_6B528
0x6b075  ldloc.0
0x6b076  ldc.i4   0x3C206DD9
0x6b07b  beq      loc_6B3ED
0x6b080  br       loc_6B974
0x6b085  ldloc.0
0x6b086  ldc.i4   0x5D31EAED
0x6b08b  bgt.un   loc_6B114
0x6b090  ldloc.0
0x6b091  ldc.i4   0x4B208576
0x6b096  bgt.un.s loc_6B0D6
0x6b098  ldloc.0
0x6b099  ldc.i4   0x420372BE
0x6b09e  bgt.un.s loc_6B0BB
0x6b0a0  ldloc.0
0x6b0a1  ldc.i4   0x41387A9E
0x6b0a6  beq      loc_6B46B
0x6b0ab  ldloc.0
0x6b0ac  ldc.i4   0x420372BE
0x6b0b1  beq      loc_6B4FE
0x6b0b6  br       loc_6B974
0x6b0bb  ldloc.0
0x6b0bc  ldc.i4   0x441A6A43
0x6b0c1  beq      loc_6B3AE
0x6b0c6  ldloc.0
0x6b0c7  ldc.i4   0x4B208576
0x6b0cc  beq      loc_6B402
0x6b0d1  br       loc_6B974
0x6b0d6  ldloc.0
0x6b0d7  ldc.i4   0x5836603C
0x6b0dc  bgt.un.s loc_6B0F9
0x6b0de  ldloc.0
0x6b0df  ldc.i4   0x4C31D02A
0x6b0e4  beq      loc_6B417
0x6b0e9  ldloc.0
0x6b0ea  ldc.i4   0x5836603C
0x6b0ef  beq      loc_6B3D8
0x6b0f4  br       loc_6B974
0x6b0f9  ldloc.0
0x6b0fa  ldc.i4   0x5CE75A29
0x6b0ff  beq      loc_6B74A
0x6b104  ldloc.0
0x6b105  ldc.i4   0x5D31EAED
0x6b10a  beq      loc_6B42C
0x6b10f  br       loc_6B974
0x6b114  ldloc.0
0x6b115  ldc.i4   0x63FE3327
0x6b11a  bgt.un.s loc_6B15A
0x6b11c  ldloc.0
0x6b11d  ldc.i4   0x5F3B1A83
0x6b122  bgt.un.s loc_6B13F
0x6b124  ldloc.0
0x6b125  ldc.i4   0x5D6BD25F
0x6b12a  beq      loc_6B774
0x6b12f  ldloc.0
0x6b130  ldc.i4   0x5F3B1A83
0x6b135  beq      loc_6B81C
0x6b13a  br       loc_6B974
0x6b13f  ldloc.0
0x6b140  ldc.i4   0x61342FD0
0x6b145  beq      loc_6B5D0
0x6b14a  ldloc.0
0x6b14b  ldc.i4   0x63FE3327
0x6b150  beq      loc_6B4E9
0x6b155  br       loc_6B974
0x6b15a  ldloc.0
0x6b15b  ldc.i4   0x71B4B0FF
0x6b160  bgt.un.s loc_6B17D
0x6b162  ldloc.0
0x6b163  ldc.i4   0x6DCDE80F
0x6b168  beq      loc_6B75F
0x6b16d  ldloc.0
0x6b16e  ldc.i4   0x71B4B0FF
0x6b173  beq      loc_6B6E1
0x6b178  br       loc_6B974
0x6b17d  ldloc.0
0x6b17e  ldc.i4   0x746BD140
0x6b183  beq      loc_6B53D
0x6b188  ldloc.0
0x6b189  ldc.i4   0x77074BA4
0x6b18e  beq      loc_6B4BF
0x6b193  br       loc_6B974
0x6b198  ldloc.0
0x6b199  ldc.i4   0xA4213C0A
0x6b19e  bgt.un   loc_6B29B
0x6b1a3  ldloc.0
0x6b1a4  ldc.i4   0x8BDB1AFD
0x6b1a9  bgt.un.s loc_6B217
0x6b1ab  ldloc.0
0x6b1ac  ldc.i4   0x7BFF8395
0x6b1b1  bgt.un.s loc_6B1D9
0x6b1b3  ldloc.0
0x6b1b4  ldc.i4   0x7791A0C5
0x6b1b9  beq      loc_6B6B7
0x6b1be  ldloc.0
0x6b1bf  ldc.i4   0x7881ACA4
0x6b1c4  beq      loc_6B678
0x6b1c9  ldloc.0
0x6b1ca  ldc.i4   0x7BFF8395
0x6b1cf  beq      loc_6B7C8
0x6b1d4  br       loc_6B974
0x6b1d9  ldloc.0
0x6b1da  ldc.i4   0x85C364C4
0x6b1df  bgt.un.s loc_6B1FC
0x6b1e1  ldloc.0
0x6b1e2  ldc.i4   0x827D4A3D
0x6b1e7  beq      loc_6B5FA
0x6b1ec  ldloc.0
0x6b1ed  ldc.i4   0x85C364C4
0x6b1f2  beq      loc_6B4D4
0x6b1f7  br       loc_6B974
0x6b1fc  ldloc.0
0x6b1fd  ldc.i4   0x89193ACD
0x6b202  beq      loc_6B85B
0x6b207  ldloc.0
0x6b208  ldc.i4   0x8BDB1AFD
0x6b20d  beq      loc_6B7B3
0x6b212  br       loc_6B974
0x6b217  ldloc.0
0x6b218  ldc.i4   0x9B35F66D
0x6b21d  bgt.un.s loc_6B25D
0x6b21f  ldloc.0
0x6b220  ldc.i4   0x92DACA6A
0x6b225  bgt.un.s loc_6B242
0x6b227  ldloc.0
0x6b228  ldc.i4   0x91396775
0x6b22d  beq      loc_6B6F6
0x6b232  ldloc.0
0x6b233  ldc.i4   0x92DACA6A
0x6b238  beq      loc_6B639
0x6b23d  br       loc_6B974
0x6b242  ldloc.0
0x6b243  ldc.i4   0x93349F0F
0x6b248  beq      loc_6B4AA
0x6b24d  ldloc.0
0x6b24e  ldc.i4   0x9B35F66D
0x6b253  beq      loc_6B870
0x6b258  br       loc_6B974
0x6b25d  ldloc.0
0x6b25e  ldc.i4   0x9F3E505A
0x6b263  bgt.un.s loc_6B280
0x6b265  ldloc.0
0x6b266  ldc.i4   0x9CEDD7E7
0x6b26b  beq      loc_6B720
0x6b270  ldloc.0
0x6b271  ldc.i4   0x9F3E505A
0x6b276  beq      loc_6B64E
0x6b27b  br       loc_6B974
0x6b280  ldloc.0
0x6b281  ldc.i4   0xA04FA089
0x6b286  beq      loc_6B735
0x6b28b  ldloc.0
0x6b28c  ldc.i4   0xA4213C0A
0x6b291  beq      loc_6B89A
0x6b296  br       loc_6B974
0x6b29b  ldloc.0
0x6b29c  ldc.i4   0xCA495058
0x6b2a1  bgt.un   loc_6B32A
0x6b2a6  ldloc.0
0x6b2a7  ldc.i4   0xAFDD2ECB
0x6b2ac  bgt.un.s loc_6B2EC
0x6b2ae  ldloc.0
0x6b2af  ldc.i4   0xA537E030
0x6b2b4  bgt.un.s loc_6B2D1
0x6b2b6  ldloc.0
0x6b2b7  ldc.i4   0xA4EE076F
0x6b2bc  beq      loc_6B495
0x6b2c1  ldloc.0
0x6b2c2  ldc.i4   0xA537E030
0x6b2c7  beq      loc_6B846
0x6b2cc  br       loc_6B974
0x6b2d1  ldloc.0
0x6b2d2  ldc.i4   0xAC3C2A26
0x6b2d7  beq      loc_6B513
0x6b2dc  ldloc.0
0x6b2dd  ldc.i4   0xAFDD2ECB
0x6b2e2  beq      loc_6B5BB
0x6b2e7  br       loc_6B974
0x6b2ec  ldloc.0
0x6b2ed  ldc.i4   0xB5DE77B7
0x6b2f2  bgt.un.s loc_6B30F
0x6b2f4  ldloc.0
0x6b2f5  ldc.i4   0xB55BE2E3
0x6b2fa  beq      loc_6B68D
0x6b2ff  ldloc.0
0x6b300  ldc.i4   0xB5DE77B7
0x6b305  beq      loc_6B57C
0x6b30a  br       loc_6B974
0x6b30f  ldloc.0
0x6b310  ldc.i4   0xBB8A3F98
0x6b315  beq      loc_6B79E
0x6b31a  ldloc.0
0x6b31b  ldc.i4   0xCA495058
0x6b320  beq      loc_6B885
0x6b325  br       loc_6B974
0x6b32a  ldloc.0
0x6b32b  ldc.i4   0xDE5F18C6
0x6b330  bgt.un.s loc_6B370
0x6b332  ldloc.0
0x6b333  ldc.i4   0xDD04E037
0x6b338  bgt.un.s loc_6B355
0x6b33a  ldloc.0
0x6b33b  ldc.i4   0xCC9961C8
0x6b340  beq      loc_6B567
0x6b345  ldloc.0
0x6b346  ldc.i4   0xDD04E037
0x6b34b  beq      loc_6B7DD
0x6b350  br       loc_6B974
0x6b355  ldloc.0
0x6b356  ldc.i4   0xDE44F050
0x6b35b  beq      loc_6B552
0x6b360  ldloc.0
0x6b361  ldc.i4   0xDE5F18C6
0x6b366  beq      loc_6B789
0x6b36b  br       loc_6B974
0x6b370  ldloc.0
0x6b371  ldc.i4   0xEE38B3F2
0x6b376  bgt.un.s loc_6B393
0x6b378  ldloc.0
0x6b379  ldc.i4   0xEC58020C
0x6b37e  beq      loc_6B6CC
0x6b383  ldloc.0
0x6b384  ldc.i4   0xEE38B3F2
0x6b389  beq      loc_6B7F2
0x6b38e  br       loc_6B974
0x6b393  ldloc.0
  ... truncated ...
```
