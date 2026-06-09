# Microsoft.Crm.Application.Themes.ConfigurableTheme::PopulateElementStyle

- ea: `0x2d280`
- end: `0x2d97e`
- name: `Microsoft.Crm.Application.Themes.ConfigurableTheme::PopulateElementStyle`
- size: `1790`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2d280`
- `0x2d990`
- `0x2d9b0`
- `0x2d9d0`
- `0x2d9f0`
- `0x2da10`
- `0x2da30`
- `0x2da50`
- `0x2da70`
- `0x2da90`
- `0x2dab0`
- `0x2dad0`
- `0x2daf0`
- `0x2db10`
- `0x2db30`
- `0x2db50`
- `0x2db70`
- `0x2db90`
- `0x2dbb0`
- `0x2dbd0`
- `0x2dbf0`
- `0x2dc10`
- `0x2dc30`
- `0x2dc50`
- `0x2dc70`
- `0x2dc90`
- `0x2dcb0`
- `0x2dcd0`
- `0x2dcf0`
- `0x2dd10`
- `0x2dd30`
- `0x2dd50`
- `0x2dd70`
- `0x2dd90`
- `0x2ddb0`
- `0x2ddd0`
- `0x2ddf0`
- `0x2de10`
- `0x2de30`
- `0x2de50`
- `0x9ca50`

## string_xrefs

- `0x2d518`: `GlobalLink`
- `0x2d52d`: `GlobalLinkImportant`

## pseudocode

```c

```

## disassembly

```asm
0x2d280  ldarg.1
0x2d281  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x2d286  stloc.0
0x2d287  ldloc.0
0x2d288  ldc.i4   0x6245F47F
0x2d28d  bgt.un   loc_2D3C6
0x2d292  ldloc.0
0x2d293  ldc.i4   0x2BA8300D
0x2d298  bgt.un   loc_2D32C
0x2d29d  ldloc.0
0x2d29e  ldc.i4   0x194143DA
0x2d2a3  bgt.un.s loc_2D2E3
0x2d2a5  ldloc.0
0x2d2a6  ldc.i4   0x146AE3A4
0x2d2ab  bgt.un.s loc_2D2C8
0x2d2ad  ldloc.0
0x2d2ae  ldc.i4   0x9231D0E
0x2d2b3  beq      loc_2D556
0x2d2b8  ldloc.0
0x2d2b9  ldc.i4   0x146AE3A4
0x2d2be  beq      loc_2D56B
0x2d2c3  br       loc_2D96D
0x2d2c8  ldloc.0
0x2d2c9  ldc.i4   0x16EDA9D0
0x2d2ce  beq      loc_2D70F
0x2d2d3  ldloc.0
0x2d2d4  ldc.i4   0x194143DA
0x2d2d9  beq      loc_2D667
0x2d2de  br       loc_2D96D
0x2d2e3  ldloc.0
0x2d2e4  ldc.i4   0x22E8A14E
0x2d2e9  bgt.un.s loc_2D306
0x2d2eb  ldloc.0
0x2d2ec  ldc.i4   0x21886CC7
0x2d2f1  beq      loc_2D691
0x2d2f6  ldloc.0
0x2d2f7  ldc.i4   0x22E8A14E
0x2d2fc  beq      loc_2D5FE
0x2d301  br       loc_2D96D
0x2d306  ldloc.0
0x2d307  ldc.i4   0x26367B85
0x2d30c  beq      loc_2D5AA
0x2d311  ldloc.0
0x2d312  ldc.i4   0x26DD801D
0x2d317  beq      loc_2D778
0x2d31c  ldloc.0
0x2d31d  ldc.i4   0x2BA8300D
0x2d322  beq      loc_2D6BB
0x2d327  br       loc_2D96D
0x2d32c  ldloc.0
0x2d32d  ldc.i4   0x4AC2E3F4
0x2d332  bgt.un.s loc_2D37D
0x2d334  ldloc.0
0x2d335  ldc.i4   0x41AB06B7
0x2d33a  bgt.un.s loc_2D357
0x2d33c  ldloc.0
0x2d33d  ldc.i4   0x30392A31
0x2d342  beq      loc_2D7CC
0x2d347  ldloc.0
0x2d348  ldc.i4   0x41AB06B7
0x2d34d  beq      loc_2D63D
0x2d352  br       loc_2D96D
0x2d357  ldloc.0
0x2d358  ldc.i4   0x44C9F11F
0x2d35d  beq      loc_2D5BF
0x2d362  ldloc.0
0x2d363  ldc.i4   0x4926313E
0x2d368  beq      loc_2D67C
0x2d36d  ldloc.0
0x2d36e  ldc.i4   0x4AC2E3F4
0x2d373  beq      loc_2D628
0x2d378  br       loc_2D96D
0x2d37d  ldloc.0
0x2d37e  ldc.i4   0x5BD5EA6F
0x2d383  bgt.un.s loc_2D3A0
0x2d385  ldloc.0
0x2d386  ldc.i4   0x4C85DEE7
0x2d38b  beq      loc_2D541
0x2d390  ldloc.0
0x2d391  ldc.i4   0x5BD5EA6F
0x2d396  beq      loc_2D6E5
0x2d39b  br       loc_2D96D
0x2d3a0  ldloc.0
0x2d3a1  ldc.i4   0x5C768F79
0x2d3a6  beq      loc_2D6FA
0x2d3ab  ldloc.0
0x2d3ac  ldc.i4   0x5FB488BE
0x2d3b1  beq      loc_2D613
0x2d3b6  ldloc.0
0x2d3b7  ldc.i4   0x6245F47F
0x2d3bc  beq      loc_2D6A6
0x2d3c1  br       loc_2D96D
0x2d3c6  ldloc.0
0x2d3c7  ldc.i4   0xAAD91D85
0x2d3cc  bgt.un   loc_2D46B
0x2d3d1  ldloc.0
0x2d3d2  ldc.i4   0x98BCEB06
0x2d3d7  bgt.un.s loc_2D422
0x2d3d9  ldloc.0
0x2d3da  ldc.i4   0x8335FADF
0x2d3df  bgt.un.s loc_2D3FC
0x2d3e1  ldloc.0
0x2d3e2  ldc.i4   0x7FEF4FF4
0x2d3e7  beq      loc_2D724
0x2d3ec  ldloc.0
0x2d3ed  ldc.i4   0x8335FADF
0x2d3f2  beq      loc_2D80B
0x2d3f7  br       loc_2D96D
0x2d3fc  ldloc.0
0x2d3fd  ldc.i4   0x8487F8CD
0x2d402  beq      loc_2D580
0x2d407  ldloc.0
0x2d408  ldc.i4   0x8D05206D
0x2d40d  beq      loc_2D739
0x2d412  ldloc.0
0x2d413  ldc.i4   0x98BCEB06
0x2d418  beq      loc_2D517
0x2d41d  br       loc_2D96D
0x2d422  ldloc.0
0x2d423  ldc.i4   0xA4223C0C
0x2d428  bgt.un.s loc_2D445
0x2d42a  ldloc.0
0x2d42b  ldc.i4   0xA3D77D9B
0x2d430  beq      loc_2D5D4
0x2d435  ldloc.0
0x2d436  ldc.i4   0xA4223C0C
0x2d43b  beq      loc_2D52C
0x2d440  br       loc_2D96D
0x2d445  ldloc.0
0x2d446  ldc.i4   0xA51EA50A
0x2d44b  beq      loc_2D7E1
0x2d450  ldloc.0
0x2d451  ldc.i4   0xA7CD4FC5
0x2d456  beq      loc_2D5E9
0x2d45b  ldloc.0
0x2d45c  ldc.i4   0xAAD91D85
0x2d461  beq      loc_2D595
0x2d466  br       loc_2D96D
0x2d46b  ldloc.0
0x2d46c  ldc.i4   0xD1496D30
0x2d471  bgt.un.s loc_2D4B9
0x2d473  ldloc.0
0x2d474  ldc.i4   0xCA400146
0x2d479  bgt.un.s loc_2D496
0x2d47b  ldloc.0
0x2d47c  ldc.i4   0xB79C2C61
0x2d481  beq      loc_2D74E
0x2d486  ldloc.0
0x2d487  ldc.i4   0xCA400146
0x2d48c  beq      loc_2D820
0x2d491  br       loc_2D96D
0x2d496  ldloc.0
0x2d497  ldc.i4   0xCECA5724
0x2d49c  beq      loc_2D7B7
0x2d4a1  ldloc.0
0x2d4a2  ldc.i4   0xD1132120
0x2d4a7  beq.s    loc_2D502
0x2d4a9  ldloc.0
0x2d4aa  ldc.i4   0xD1496D30
0x2d4af  beq      loc_2D78D
0x2d4b4  br       loc_2D96D
0x2d4b9  ldloc.0
0x2d4ba  ldc.i4   0xD3D9DF9D
0x2d4bf  bgt.un.s loc_2D4DC
0x2d4c1  ldloc.0
0x2d4c2  ldc.i4   0xD26DC01B
0x2d4c7  beq      loc_2D7A2
0x2d4cc  ldloc.0
0x2d4cd  ldc.i4   0xD3D9DF9D
0x2d4d2  beq      loc_2D652
0x2d4d7  br       loc_2D96D
0x2d4dc  ldloc.0
0x2d4dd  ldc.i4   0xD6F1F527
0x2d4e2  beq      loc_2D7F6
0x2d4e7  ldloc.0
0x2d4e8  ldc.i4   0xD832E50C
0x2d4ed  beq      loc_2D6D0
0x2d4f2  ldloc.0
0x2d4f3  ldc.i4   0xE9B7D5DF
0x2d4f8  beq      loc_2D763
0x2d4fd  br       loc_2D96D
0x2d502  ldarg.1
0x2d503  ldstr    aControleffects// "ControlEffects"
0x2d508  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d50d  brtrue   loc_2D835
0x2d512  br       loc_2D96D
0x2d517  ldarg.1
0x2d518  ldstr    aGloballink// "GlobalLink"
0x2d51d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d522  brtrue   loc_2D83D
0x2d527  br       loc_2D96D
0x2d52c  ldarg.1
0x2d52d  ldstr    aGloballinkimpo// "GlobalLinkImportant"
0x2d532  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d537  brtrue   loc_2D845
0x2d53c  br       loc_2D96D
0x2d541  ldarg.1
0x2d542  ldstr    aHovereffectcol// "HoverEffectColorChange"
0x2d547  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d54c  brtrue   loc_2D84D
0x2d551  br       loc_2D96D
0x2d556  ldarg.1
0x2d557  ldstr    aHovereffectcol_0// "HoverEffectColorAndBorderChange"
0x2d55c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d561  brtrue   loc_2D855
0x2d566  br       loc_2D96D
0x2d56b  ldarg.1
0x2d56c  ldstr    aHovereffectcol_1// "HoverEffectColorAndBorderChangeImportan"...
0x2d571  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d576  brtrue   loc_2D85D
0x2d57b  br       loc_2D96D
0x2d580  ldarg.1
0x2d581  ldstr    aHovereffectbor// "HoverEffectBorderColorChangeImportant"
0x2d586  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d58b  brtrue   loc_2D865
0x2d590  br       loc_2D96D
0x2d595  ldarg.1
0x2d596  ldstr    aMainnavbarcolo// "MainNavBarColor"
0x2d59b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d5a0  brtrue   loc_2D86D
0x2d5a5  br       loc_2D96D
0x2d5aa  ldarg.1
0x2d5ab  ldstr    aMainnavbarcolo_0// "MainNavBarColorImportant"
0x2d5b0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d5b5  brtrue   loc_2D875
0x2d5ba  br       loc_2D96D
0x2d5bf  ldarg.1
0x2d5c0  ldstr    aMainnavbarbord// "MainNavBarBorderColor"
0x2d5c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d5ca  brtrue   loc_2D87D
0x2d5cf  br       loc_2D96D
0x2d5d4  ldarg.1
0x2d5d5  ldstr    aMainnavbarhove// "MainNavBarHoverColor"
0x2d5da  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d5df  brtrue   loc_2D885
0x2d5e4  br       loc_2D96D
0x2d5e9  ldarg.1
0x2d5ea  ldstr    aMainnavtabbutt// "MainNavTabButtonImageSelectedBorderColo"...
0x2d5ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d5f4  brtrue   loc_2D88D
0x2d5f9  br       loc_2D96D
0x2d5fe  ldarg.1
0x2d5ff  ldstr    aProcesscontrol// "ProcessControlColor"
0x2d604  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d609  brtrue   loc_2D895
0x2d60e  br       loc_2D96D
0x2d613  ldarg.1
0x2d614  ldstr    aSecondarynavba// "SecondaryNavBarColor"
0x2d619  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d61e  brtrue   loc_2D89D
0x2d623  br       loc_2D96D
0x2d628  ldarg.1
0x2d629  ldstr    aSecondarynavba_0// "SecondaryNavBarColorImportant"
0x2d62e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d633  brtrue   loc_2D8A5
0x2d638  br       loc_2D96D
0x2d63d  ldarg.1
0x2d63e  ldstr    aHeadercolor// "HeaderColor"
0x2d643  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d648  brtrue   loc_2D8AD
0x2d64d  br       loc_2D96D
0x2d652  ldarg.1
0x2d653  ldstr    aSelectedeffect// "SelectedEffect"
0x2d658  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d65d  brtrue   loc_2D8B5
0x2d662  br       loc_2D96D
0x2d667  ldarg.1
0x2d668  ldstr    aControleffects_0// "ControlEffectsBackColor"
0x2d66d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d672  brtrue   loc_2D8BD
0x2d677  br       loc_2D96D
0x2d67c  ldarg.1
0x2d67d  ldstr    aControleffects_1// "ControlEffectsBorder"
0x2d682  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d687  brtrue   loc_2D8C5
0x2d68c  br       loc_2D96D
0x2d691  ldarg.1
0x2d692  ldstr    aSelectedeffect_0// "SelectedEffectColorAndBorderChange"
0x2d697  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d69c  brtrue   loc_2D8CD
0x2d6a1  br       loc_2D96D
0x2d6a6  ldarg.1
0x2d6a7  ldstr    aSelectedeffect_1// "SelectedEffectColorAndBorderChangeImpor"...
0x2d6ac  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d6b1  brtrue   loc_2D8D5
0x2d6b6  br       loc_2D96D
0x2d6bb  ldarg.1
0x2d6bc  ldstr    aSelectedeffect_2// "SelectedEffectImportant"
0x2d6c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d6c6  brtrue   loc_2D8DD
0x2d6cb  br       loc_2D96D
0x2d6d0  ldarg.1
0x2d6d1  ldstr    aSelectedeffect_3// "SelectedEffectBackColorAndBorder"
0x2d6d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d6db  brtrue   loc_2D8E5
0x2d6e0  br       loc_2D96D
0x2d6e5  ldarg.1
0x2d6e6  ldstr    aProcesscontrol_0// "ProcessControlBackColor"
0x2d6eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2d6f0  brtrue   loc_2D8ED
  ... truncated ...
```
