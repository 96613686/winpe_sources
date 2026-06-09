# Microsoft.Crm.Application.Controls.PageManager::isCALICOPage

- ea: `0xa9f90`
- end: `0xab4e1`
- name: `Microsoft.Crm.Application.Controls.PageManager::isCALICOPage`
- size: `5457`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0xa9a50`
- `0xab5c0`

## callees

- `0xa9f90`
- `0xab4f0`
- `0xf0f70`

## string_xrefs

- `0xaa778`: `COMPS`
- `0xaa907`: `SERVICES`
- `0xaa946`: `SERVICEAPPOINTMENT`
- `0xaa9ee`: `CHANNELACCESSPROFILERULE`
- `0xaaa03`: `CHANNELACCESSPROFILERULEITEM`
- `0xaaaab`: `ENTITLEMENTTEMPLATE`

## pseudocode

```c

```

## disassembly

```asm
0xa9f90  ldsfld   string [mscorlib]System.String::Empty
0xa9f95  stloc.0
0xa9f96  ldnull
0xa9f97  stloc.1
0xa9f98  ldarg.0
0xa9f99  ldloca.s 0
0xa9f9b  ldloca.s 1
0xa9f9d  call     void Microsoft.Crm.Application.Controls.PageManager::getPathAndUri(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.UIPage page, [out] string& path, [out] class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri& uri)
0xa9fa2  ldarg.1
0xa9fa3  ldc.i4.0
0xa9fa4  stind.i4
0xa9fa5  ldarg.0
0xa9fa6  isinst   Microsoft.Crm.Application.Controls.EntityPage
0xa9fab  brfalse  loc_AAFB7
0xa9fb0  ldloc.0
0xa9fb1  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xa9fb6  ldstr    aEditAspx_0// "/EDIT.ASPX"
0xa9fbb  ldc.i4.5
0xa9fbc  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0xa9fc1  brfalse  loc_AAFB7
0xa9fc6  ldloc.0
0xa9fc7  ldc.i4.1
0xa9fc8  newarr   [mscorlib]System.Char
0xa9fcd  dup
0xa9fce  ldc.i4.0
0xa9fcf  ldc.i4.s 0x2F
0xa9fd1  stelem.i2
0xa9fd2  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xa9fd7  dup
0xa9fd8  ldlen
0xa9fd9  conv.i4
0xa9fda  ldc.i4.2
0xa9fdb  sub
0xa9fdc  ldelem.ref
0xa9fdd  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0xa9fe2  stloc.2
0xa9fe3  ldloc.2
0xa9fe4  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xa9fe9  stloc.3
0xa9fea  ldloc.3
0xa9feb  ldc.i4   0x63B61CC0
0xa9ff0  bgt.un   loc_AA2AA
0xa9ff5  ldloc.3
0xa9ff6  ldc.i4   0x3934191A
0xa9ffb  bgt.un   loc_AA155
0xaa000  ldloc.3
0xaa001  ldc.i4   0x21CA76B1
0xaa006  bgt.un   loc_AA0B0
0xaa00b  ldloc.3
0xaa00c  ldc.i4   0xEB1608F
0xaa011  bgt.un.s loc_AA05C
0xaa013  ldloc.3
0xaa014  ldc.i4   0x75F510C
0xaa019  bgt.un.s loc_AA036
0xaa01b  ldloc.3
0xaa01c  ldc.i4   0x16C8525
0xaa021  beq      loc_AA8DC
0xaa026  ldloc.3
0xaa027  ldc.i4   0x75F510C
0xaa02c  beq      loc_AA723
0xaa031  br       loc_AAFB5
0xaa036  ldloc.3
0xaa037  ldc.i4   0x8C2FEB3
0xaa03c  beq      loc_AA8F1
0xaa041  ldloc.3
0xaa042  ldc.i4   0xCF493FB
0xaa047  beq      loc_AA6BA
0xaa04c  ldloc.3
0xaa04d  ldc.i4   0xEB1608F
0xaa052  beq      loc_AA91B
0xaa057  br       loc_AAFB5
0xaa05c  ldloc.3
0xaa05d  ldc.i4   0x16FCDDFC
0xaa062  bgt.un.s loc_AA08A
0xaa064  ldloc.3
0xaa065  ldc.i4   0x125DAB45
0xaa06a  beq      loc_AA666
0xaa06f  ldloc.3
0xaa070  ldc.i4   0x15CAC75A
0xaa075  beq      loc_AA56A
0xaa07a  ldloc.3
0xaa07b  ldc.i4   0x16FCDDFC
0xaa080  beq      loc_AAC39
0xaa085  br       loc_AAFB5
0xaa08a  ldloc.3
0xaa08b  ldc.i4   0x19D3A69B
0xaa090  beq      loc_AAB67
0xaa095  ldloc.3
0xaa096  ldc.i4   0x21505501
0xaa09b  beq      loc_AAAE9
0xaa0a0  ldloc.3
0xaa0a1  ldc.i4   0x21CA76B1
0xaa0a6  beq      loc_AABBB
0xaa0ab  br       loc_AAFB5
0xaa0b0  ldloc.3
0xaa0b1  ldc.i4   0x2B4A1C58
0xaa0b6  bgt.un.s loc_AA101
0xaa0b8  ldloc.3
0xaa0b9  ldc.i4   0x253D0E99
0xaa0be  bgt.un.s loc_AA0DB
0xaa0c0  ldloc.3
0xaa0c1  ldc.i4   0x2502C364
0xaa0c6  beq      loc_AA7CB
0xaa0cb  ldloc.3
0xaa0cc  ldc.i4   0x253D0E99
0xaa0d1  beq      loc_AA7E0
0xaa0d6  br       loc_AAFB5
0xaa0db  ldloc.3
0xaa0dc  ldc.i4   0x287B25E8
0xaa0e1  beq      loc_AAA2C
0xaa0e6  ldloc.3
0xaa0e7  ldc.i4   0x2A26C019
0xaa0ec  beq      loc_AA8C7
0xaa0f1  ldloc.3
0xaa0f2  ldc.i4   0x2B4A1C58
0xaa0f7  beq      loc_AA85E
0xaa0fc  br       loc_AAFB5
0xaa101  ldloc.3
0xaa102  ldc.i4   0x33EA9E4D
0xaa107  bgt.un.s loc_AA12F
0xaa109  ldloc.3
0xaa10a  ldc.i4   0x2C7B5691
0xaa10f  beq      loc_AA945
0xaa114  ldloc.3
0xaa115  ldc.i4   0x31428ACF
0xaa11a  beq      loc_AAA17
0xaa11f  ldloc.3
0xaa120  ldc.i4   0x33EA9E4D
0xaa125  beq      loc_AA6F9
0xaa12a  br       loc_AAFB5
0xaa12f  ldloc.3
0xaa130  ldc.i4   0x35D28610
0xaa135  beq      loc_AA9AE
0xaa13a  ldloc.3
0xaa13b  ldc.i4   0x374320A6
0xaa140  beq      loc_AA5FD
0xaa145  ldloc.3
0xaa146  ldc.i4   0x3934191A
0xaa14b  beq      loc_AA930
0xaa150  br       loc_AAFB5
0xaa155  ldloc.3
0xaa156  ldc.i4   0x4812CA71
0xaa15b  bgt.un   loc_AA205
0xaa160  ldloc.3
0xaa161  ldc.i4   0x3FD195A0
0xaa166  bgt.un.s loc_AA1B1
0xaa168  ldloc.3
0xaa169  ldc.i4   0x3B7D2C0F
0xaa16e  bgt.un.s loc_AA18B
0xaa170  ldloc.3
0xaa171  ldc.i4   0x3B0F160D
0xaa176  beq      loc_AA738
0xaa17b  ldloc.3
0xaa17c  ldc.i4   0x3B7D2C0F
0xaa181  beq      loc_AA96F
0xaa186  br       loc_AAFB5
0xaa18b  ldloc.3
0xaa18c  ldc.i4   0x3CC956EC
0xaa191  beq      loc_AA80A
0xaa196  ldloc.3
0xaa197  ldc.i4   0x3DA59EE9
0xaa19c  beq      loc_AA849
0xaa1a1  ldloc.3
0xaa1a2  ldc.i4   0x3FD195A0
0xaa1a7  beq      loc_AA9D8
0xaa1ac  br       loc_AAFB5
0xaa1b1  ldloc.3
0xaa1b2  ldc.i4   0x44C9766B
0xaa1b7  bgt.un.s loc_AA1DF
0xaa1b9  ldloc.3
0xaa1ba  ldc.i4   0x4086F1A7
0xaa1bf  beq      loc_AA9C3
0xaa1c4  ldloc.3
0xaa1c5  ldc.i4   0x412DBEF0
0xaa1ca  beq      loc_AA5D3
0xaa1cf  ldloc.3
0xaa1d0  ldc.i4   0x44C9766B
0xaa1d5  beq      loc_AAA95
0xaa1da  br       loc_AAFB5
0xaa1df  ldloc.3
0xaa1e0  ldc.i4   0x45C3CB96
0xaa1e5  beq      loc_AAA6B
0xaa1ea  ldloc.3
0xaa1eb  ldc.i4   0x47F8B79E
0xaa1f0  beq      loc_AAA02
0xaa1f5  ldloc.3
0xaa1f6  ldc.i4   0x4812CA71
0xaa1fb  beq      loc_AAA41
0xaa200  br       loc_AAFB5
0xaa205  ldloc.3
0xaa206  ldc.i4   0x57E82D6B
0xaa20b  bgt.un.s loc_AA256
0xaa20d  ldloc.3
0xaa20e  ldc.i4   0x548BFA1C
0xaa213  bgt.un.s loc_AA230
0xaa215  ldloc.3
0xaa216  ldc.i4   0x53C19D76
0xaa21b  beq      loc_AAAD4
0xaa220  ldloc.3
0xaa221  ldc.i4   0x548BFA1C
0xaa226  beq      loc_AAA80
0xaa22b  br       loc_AAFB5
0xaa230  ldloc.3
0xaa231  ldc.i4   0x5538BC1E
0xaa236  beq      loc_AA6E4
0xaa23b  ldloc.3
0xaa23c  ldc.i4   0x5711111F
0xaa241  beq      loc_AA5BE
0xaa246  ldloc.3
0xaa247  ldc.i4   0x57E82D6B
0xaa24c  beq      loc_AAB52
0xaa251  br       loc_AAFB5
0xaa256  ldloc.3
0xaa257  ldc.i4   0x5C8AF1CD
0xaa25c  bgt.un.s loc_AA284
0xaa25e  ldloc.3
0xaa25f  ldc.i4   0x5B0E1767
0xaa264  beq      loc_AA89D
0xaa269  ldloc.3
0xaa26a  ldc.i4   0x5B6F04F4
0xaa26f  beq      loc_AA5A9
0xaa274  ldloc.3
0xaa275  ldc.i4   0x5C8AF1CD
0xaa27a  beq      loc_AAAFE
0xaa27f  br       loc_AAFB5
0xaa284  ldloc.3
0xaa285  ldc.i4   0x5FAE6431
0xaa28a  beq      loc_AA888
0xaa28f  ldloc.3
0xaa290  ldc.i4   0x62BC4A98
0xaa295  beq      loc_AAB13
0xaa29a  ldloc.3
0xaa29b  ldc.i4   0x63B61CC0
0xaa2a0  beq      loc_AA651
0xaa2a5  br       loc_AAFB5
0xaa2aa  ldloc.3
0xaa2ab  ldc.i4   0xB2B12660
0xaa2b0  bgt.un   loc_AA40A
0xaa2b5  ldloc.3
0xaa2b6  ldc.i4   0x895E7ACB
0xaa2bb  bgt.un   loc_AA365
0xaa2c0  ldloc.3
0xaa2c1  ldc.i4   0x7A57773B
0xaa2c6  bgt.un.s loc_AA311
0xaa2c8  ldloc.3
0xaa2c9  ldc.i4   0x6A29284A
0xaa2ce  bgt.un.s loc_AA2EB
0xaa2d0  ldloc.3
0xaa2d1  ldc.i4   0x698F8C29
0xaa2d6  beq      loc_AAB3D
0xaa2db  ldloc.3
0xaa2dc  ldc.i4   0x6A29284A
0xaa2e1  beq      loc_AAA56
0xaa2e6  br       loc_AAFB5
0xaa2eb  ldloc.3
0xaa2ec  ldc.i4   0x6BCB2C1D
0xaa2f1  beq      loc_AA999
0xaa2f6  ldloc.3
0xaa2f7  ldc.i4   0x7808E88A
0xaa2fc  beq      loc_AA78C
0xaa301  ldloc.3
0xaa302  ldc.i4   0x7A57773B
0xaa307  beq      loc_AA777
0xaa30c  br       loc_AAFB5
0xaa311  ldloc.3
0xaa312  ldc.i4   0x8562E628
0xaa317  bgt.un.s loc_AA33F
0xaa319  ldloc.3
0xaa31a  ldc.i4   0x7C1A58E2
0xaa31f  beq      loc_AAB28
0xaa324  ldloc.3
0xaa325  ldc.i4   0x7CB42147
0xaa32a  beq      loc_AA7F5
0xaa32f  ldloc.3
0xaa330  ldc.i4   0x8562E628
0xaa335  beq      loc_AA7A1
0xaa33a  br       loc_AAFB5
0xaa33f  ldloc.3
0xaa340  ldc.i4   0x85E3723B
0xaa345  beq      loc_AA57F
0xaa34a  ldloc.3
0xaa34b  ldc.i4   0x87B406C5
0xaa350  beq      loc_AA612
0xaa355  ldloc.3
0xaa356  ldc.i4   0x895E7ACB
0xaa35b  beq      loc_AABA6
0xaa360  br       loc_AAFB5
0xaa365  ldloc.3
0xaa366  ldc.i4   0xA1BAE209
0xaa36b  bgt.un.s loc_AA3B6
0xaa36d  ldloc.3
0xaa36e  ldc.i4   0x96C8FF32
0xaa373  bgt.un.s loc_AA390
0xaa375  ldloc.3
0xaa376  ldc.i4   0x9523EB57
0xaa37b  beq      loc_AAC0F
0xaa380  ldloc.3
0xaa381  ldc.i4   0x96C8FF32
0xaa386  beq      loc_AACA2
0xaa38b  br       loc_AAFB5
  ... truncated ...
```
