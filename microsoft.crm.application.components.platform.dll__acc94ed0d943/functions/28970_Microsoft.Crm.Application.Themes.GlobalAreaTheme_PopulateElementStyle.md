# Microsoft.Crm.Application.Themes.GlobalAreaTheme::PopulateElementStyle

- ea: `0x28970`
- end: `0x2a7a5`
- name: `Microsoft.Crm.Application.Themes.GlobalAreaTheme::PopulateElementStyle`
- size: `7733`
- prototype: ``
- caller_count: `0`
- callee_count: `172`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x28970`
- `0x2a7c0`
- `0x2a7e0`
- `0x2a800`
- `0x2a820`
- `0x2a840`
- `0x2a860`
- `0x2a880`
- `0x2a8a0`
- `0x2a8c0`
- `0x2a8e0`
- `0x2a900`
- `0x2a920`
- `0x2a940`
- `0x2a960`
- `0x2a980`
- `0x2a9a0`
- `0x2a9c0`
- `0x2a9e0`
- `0x2aa00`
- `0x2aa20`
- `0x2aa40`
- `0x2aa60`
- `0x2aa80`
- `0x2aaa0`
- `0x2aac0`
- `0x2aae0`
- `0x2ab00`
- `0x2ab20`
- `0x2ab40`
- `0x2ab60`
- `0x2ab80`
- `0x2aba0`
- `0x2abc0`
- `0x2abe0`
- `0x2ac00`
- `0x2ac20`
- `0x2ac40`
- `0x2ac60`
- `0x2ac80`
- `0x2aca0`
- `0x2acc0`
- `0x2ace0`
- `0x2ad00`
- `0x2ad20`
- `0x2ad40`
- `0x2ad60`
- `0x2ad80`
- `0x2ada0`
- `0x2adc0`

## string_xrefs

- `0x29475`: `GlobalLinkMain`
- `0x2948a`: `GlobalLinkSecondary`
- `0x2949f`: `LinkMenuCore`
- `0x29658`: `ContextMenuRightPartHoverBorder`
- `0x29697`: `ContextMenuItemLink`
- `0x29826`: `ServiceCalendarLine`
- `0x2983b`: `ServiceCalendarBorder`
- `0x29850`: `ServiceCalendarDateSections`
- `0x29865`: `ServiceCalendarTitleBack`
- `0x29937`: `MenuLabelOpened`
- `0x29b83`: `CompControlSideStrip`
- `0x29b98`: `CompControlBorder`
- `0x29c7f`: `CommandButtonHover`
- `0x29c94`: `CommandSplitButtonHover`
- `0x29e38`: `ResourceHelperLinkText`
- `0x29eb6`: `CommandBarButtonSelectionBackColor`
- `0x29ecb`: `CommandBarButtonSelectionImportant`
- `0x29ee0`: `CommandBarButtonSelectionBackColorImportant`
- `0x29ef5`: `CommandBarSplitButtonSelectionImportant`
- `0x2a01b`: `ServiceCalendarLink`
- `0x2a045`: `EditViewTasksHover`
- `0x2a102`: `QuickCreateFormHeader`
- `0x2a117`: `ChartsLink`
- `0x2a12c`: `ChartsLinkHover`
- `0x2a156`: `DevResourcesGlobalLink`
- `0x2a16b`: `DocumentManagementLink`
- `0x2a180`: `SocialInsightsLink`
- `0x2a213`: `NavTourLearningLink`

## pseudocode

```c

```

## disassembly

```asm
0x28970  ldarg.1
0x28971  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x28976  stloc.0
0x28977  ldloc.0
0x28978  ldc.i4   0x7F0FE78D
0x2897d  bgt.un   loc_28ED6
0x28982  ldloc.0
0x28983  ldc.i4   0x3AD5E5C4
0x28988  bgt.un   loc_28C2C
0x2898d  ldloc.0
0x2898e  ldc.i4   0x2160E6DC
0x28993  bgt.un   loc_28AE2
0x28998  ldloc.0
0x28999  ldc.i4   0x16AAC811
0x2899e  bgt.un   loc_28A3D
0x289a3  ldloc.0
0x289a4  ldc.i4   0xCFE4D5C
0x289a9  bgt.un.s loc_289F4
0x289ab  ldloc.0
0x289ac  ldc.i4   0x3BFB77E
0x289b1  bgt.un.s loc_289CE
0x289b3  ldloc.0
0x289b4  ldc.i4   0x20CABF7
0x289b9  beq      loc_296AB
0x289be  ldloc.0
0x289bf  ldc.i4   0x3BFB77E
0x289c4  beq      loc_29C3F
0x289c9  br       loc_2A794
0x289ce  ldloc.0
0x289cf  ldc.i4   0x79665E1
0x289d4  beq      loc_29585
0x289d9  ldloc.0
0x289da  ldc.i4   0xB8731D8
0x289df  beq      loc_29A86
0x289e4  ldloc.0
0x289e5  ldc.i4   0xCFE4D5C
0x289ea  beq      loc_29F48
0x289ef  br       loc_2A794
0x289f4  ldloc.0
0x289f5  ldc.i4   0xDFFB8DA
0x289fa  bgt.un.s loc_28A17
0x289fc  ldloc.0
0x289fd  ldc.i4   0xDE4EF99
0x28a02  beq      loc_299B4
0x28a07  ldloc.0
0x28a08  ldc.i4   0xDFFB8DA
0x28a0d  beq      loc_29753
0x28a12  br       loc_2A794
0x28a17  ldloc.0
0x28a18  ldc.i4   0x11EBF619
0x28a1d  beq      loc_29FDB
0x28a22  ldloc.0
0x28a23  ldc.i4   0x13A014C5
0x28a28  beq      loc_29C2A
0x28a2d  ldloc.0
0x28a2e  ldc.i4   0x16AAC811
0x28a33  beq      loc_299DE
0x28a38  br       loc_2A794
0x28a3d  ldloc.0
0x28a3e  ldc.i4   0x1AC2C617
0x28a43  bgt.un.s loc_28A8E
0x28a45  ldloc.0
0x28a46  ldc.i4   0x185FB81F
0x28a4b  bgt.un.s loc_28A68
0x28a4d  ldloc.0
0x28a4e  ldc.i4   0x16F1A514
0x28a53  beq      loc_29960
0x28a58  ldloc.0
0x28a59  ldc.i4   0x185FB81F
0x28a5e  beq      loc_29C00
0x28a63  br       loc_2A794
0x28a68  ldloc.0
0x28a69  ldc.i4   0x18846991
0x28a6e  beq      loc_29BD6
0x28a73  ldloc.0
0x28a74  ldc.i4   0x194091BF
0x28a79  beq      loc_29CA8
0x28a7e  ldloc.0
0x28a7f  ldc.i4   0x1AC2C617
0x28a84  beq      loc_2977D
0x28a89  br       loc_2A794
0x28a8e  ldloc.0
0x28a8f  ldc.i4   0x1C0D316C
0x28a94  bgt.un.s loc_28ABC
0x28a96  ldloc.0
0x28a97  ldc.i4   0x1B0F94E8
0x28a9c  beq      loc_29BEB
0x28aa1  ldloc.0
0x28aa2  ldc.i4   0x1BA718BA
0x28aa7  beq      loc_2998A
0x28aac  ldloc.0
0x28aad  ldc.i4   0x1C0D316C
0x28ab2  beq      loc_2A1D3
0x28ab7  br       loc_2A794
0x28abc  ldloc.0
0x28abd  ldc.i4   0x1DB3745C
0x28ac2  beq      loc_29E76
0x28ac7  ldloc.0
0x28ac8  ldc.i4   0x1F01D795
0x28acd  beq      loc_29729
0x28ad2  ldloc.0
0x28ad3  ldc.i4   0x2160E6DC
0x28ad8  beq      loc_298CD
0x28add  br       loc_2A794
0x28ae2  ldloc.0
0x28ae3  ldc.i4   0x2E253A0A
0x28ae8  bgt.un   loc_28B87
0x28aed  ldloc.0
0x28aee  ldc.i4   0x2A560B80
0x28af3  bgt.un.s loc_28B3E
0x28af5  ldloc.0
0x28af6  ldc.i4   0x232080B5
0x28afb  bgt.un.s loc_28B18
0x28afd  ldloc.0
0x28afe  ldc.i4   0x2272E22D
0x28b03  beq      loc_29642
0x28b08  ldloc.0
0x28b09  ldc.i4   0x232080B5
0x28b0e  beq      loc_2990C
0x28b13  br       loc_2A794
0x28b18  ldloc.0
0x28b19  ldc.i4   0x25B2E47A
0x28b1e  beq      loc_29E61
0x28b23  ldloc.0
0x28b24  ldc.i4   0x26D59490
0x28b29  beq      loc_2A059
0x28b2e  ldloc.0
0x28b2f  ldc.i4   0x2A560B80
0x28b34  beq      loc_29603
0x28b39  br       loc_2A794
0x28b3e  ldloc.0
0x28b3f  ldc.i4   0x2AE04FAB
0x28b44  bgt.un.s loc_28B61
0x28b46  ldloc.0
0x28b47  ldc.i4   0x2A6F7B40
0x28b4c  beq      loc_295D9
0x28b51  ldloc.0
0x28b52  ldc.i4   0x2AE04FAB
0x28b57  beq      loc_297FB
0x28b5c  br       loc_2A794
0x28b61  ldloc.0
0x28b62  ldc.i4   0x2B4B4990
0x28b67  beq      loc_2A044
0x28b6c  ldloc.0
0x28b6d  ldc.i4   0x2C2C6B06
0x28b72  beq      loc_29B04
0x28b77  ldloc.0
0x28b78  ldc.i4   0x2E253A0A
0x28b7d  beq      loc_2988E
0x28b82  br       loc_2A794
0x28b87  ldloc.0
0x28b88  ldc.i4   0x3451F337
0x28b8d  bgt.un.s loc_28BD8
0x28b8f  ldloc.0
0x28b90  ldc.i4   0x2FE2FC56
0x28b95  bgt.un.s loc_28BB2
0x28b97  ldloc.0
0x28b98  ldc.i4   0x2FA2DED1
0x28b9d  beq      loc_29792
0x28ba2  ldloc.0
0x28ba3  ldc.i4   0x2FE2FC56
0x28ba8  beq      loc_2999F
0x28bad  br       loc_2A794
0x28bb2  ldloc.0
0x28bb3  ldc.i4   0x30559A48
0x28bb8  beq      loc_295EE
0x28bbd  ldloc.0
0x28bbe  ldc.i4   0x33881A91
0x28bc3  beq      loc_29435
0x28bc8  ldloc.0
0x28bc9  ldc.i4   0x3451F337
0x28bce  beq      loc_29A08
0x28bd3  br       loc_2A794
0x28bd8  ldloc.0
0x28bd9  ldc.i4   0x38D8725C
0x28bde  bgt.un.s loc_28C06
0x28be0  ldloc.0
0x28be1  ldc.i4   0x353899E9
0x28be6  beq      loc_29C69
0x28beb  ldloc.0
0x28bec  ldc.i4   0x3807044B
0x28bf1  beq      loc_295C4
0x28bf6  ldloc.0
0x28bf7  ldc.i4   0x38D8725C
0x28bfc  beq      loc_29879
0x28c01  br       loc_2A794
0x28c06  ldloc.0
0x28c07  ldc.i4   0x38FB243B
0x28c0c  beq      loc_29FB1
0x28c11  ldloc.0
0x28c12  ldc.i4   0x3A775381
0x28c17  beq      loc_2949E
0x28c1c  ldloc.0
0x28c1d  ldc.i4   0x3AD5E5C4
0x28c22  beq      loc_29B6D
0x28c27  br       loc_2A794
0x28c2c  ldloc.0
0x28c2d  ldc.i4   0x58CD6BEA
0x28c32  bgt.un   loc_28D81
0x28c37  ldloc.0
0x28c38  ldc.i4   0x4F64A932
0x28c3d  bgt.un   loc_28CDC
0x28c42  ldloc.0
0x28c43  ldc.i4   0x434ED17B
0x28c48  bgt.un.s loc_28C93
0x28c4a  ldloc.0
0x28c4b  ldc.i4   0x3EC656E1
0x28c50  bgt.un.s loc_28C6D
0x28c52  ldloc.0
0x28c53  ldc.i4   0x3E296D38
0x28c58  beq      loc_2A116
0x28c5d  ldloc.0
0x28c5e  ldc.i4   0x3EC656E1
0x28c63  beq      loc_2966C
0x28c68  br       loc_2A794
0x28c6d  ldloc.0
0x28c6e  ldc.i4   0x418233E5
0x28c73  beq      loc_29AC5
0x28c78  ldloc.0
0x28c79  ldc.i4   0x41DADCC6
0x28c7e  beq      loc_29B19
0x28c83  ldloc.0
0x28c84  ldc.i4   0x434ED17B
0x28c89  beq      loc_2A0D7
0x28c8e  br       loc_2A794
0x28c93  ldloc.0
0x28c94  ldc.i4   0x457F7F33
0x28c99  bgt.un.s loc_28CB6
0x28c9b  ldloc.0
0x28c9c  ldc.i4   0x445E04A4
0x28ca1  beq      loc_2A0C2
0x28ca6  ldloc.0
0x28ca7  ldc.i4   0x457F7F33
0x28cac  beq      loc_296EA
0x28cb1  br       loc_2A794
0x28cb6  ldloc.0
0x28cb7  ldc.i4   0x49E14257
0x28cbc  beq      loc_29EDF
0x28cc1  ldloc.0
0x28cc2  ldc.i4   0x4D888209
0x28cc7  beq      loc_29CFC
0x28ccc  ldloc.0
0x28ccd  ldc.i4   0x4F64A932
0x28cd2  beq      loc_29E37
0x28cd7  br       loc_2A794
0x28cdc  ldloc.0
0x28cdd  ldc.i4   0x548CF5E3
0x28ce2  bgt.un.s loc_28D2D
0x28ce4  ldloc.0
0x28ce5  ldc.i4   0x50AAB9D9
0x28cea  bgt.un.s loc_28D07
0x28cec  ldloc.0
0x28ced  ldc.i4   0x509C7F4D
0x28cf2  beq      loc_2A005
0x28cf7  ldloc.0
0x28cf8  ldc.i4   0x50AAB9D9
0x28cfd  beq      loc_29A71
0x28d02  br       loc_2A794
0x28d07  ldloc.0
0x28d08  ldc.i4   0x516754C6
0x28d0d  beq      loc_29A32
0x28d12  ldloc.0
0x28d13  ldc.i4   0x5338BB68
0x28d18  beq      loc_294DD
0x28d1d  ldloc.0
0x28d1e  ldc.i4   0x548CF5E3
0x28d23  beq      loc_298E2
0x28d28  br       loc_2A794
0x28d2d  ldloc.0
0x28d2e  ldc.i4   0x557F3213
0x28d33  bgt.un.s loc_28D5B
0x28d35  ldloc.0
0x28d36  ldc.i4   0x54F32448
0x28d3b  beq      loc_2973E
0x28d40  ldloc.0
0x28d41  ldc.i4   0x556BBB6B
0x28d46  beq      loc_29D11
0x28d4b  ldloc.0
0x28d4c  ldc.i4   0x557F3213
0x28d51  beq      loc_29ADA
0x28d56  br       loc_2A794
0x28d5b  ldloc.0
0x28d5c  ldc.i4   0x571746A0
0x28d61  beq      loc_2983A
0x28d66  ldloc.0
0x28d67  ldc.i4   0x57983BB1
0x28d6c  beq      loc_2A1BE
0x28d71  ldloc.0
0x28d72  ldc.i4   0x58CD6BEA
0x28d77  beq      loc_298F7
0x28d7c  br       loc_2A794
0x28d81  ldloc.0
0x28d82  ldc.i4   0x6C813ACE
0x28d87  bgt.un   loc_28E31
0x28d8c  ldloc.0
0x28d8d  ldc.i4   0x66614D76
0x28d92  bgt.un.s loc_28DDD
0x28d94  ldloc.0
0x28d95  ldc.i4   0x6302F8E9
0x28d9a  bgt.un.s loc_28DB7
  ... truncated ...
```
