# Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::DoesErrorContainPlaceholder

- ea: `0x13b00`
- end: `0x13fb0`
- name: `Microsoft.Crm.Common.Application.Web.Pages.ErrorHandlerPage::DoesErrorContainPlaceholder`
- size: `1200`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x13920`

## callees

- `0x13b00`
- `0x1db30`

## pseudocode

```c

```

## disassembly

```asm
0x13b00  ldarg.0
0x13b01  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13b06  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x13b0b  stloc.0
0x13b0c  ldloc.0
0x13b0d  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x13b12  stloc.1
0x13b13  ldloc.1
0x13b14  ldc.i4   0xAC22F4DE
0x13b19  bgt.un   loc_13C31
0x13b1e  ldloc.1
0x13b1f  ldc.i4   0x8124EFC4
0x13b24  bgt.un   loc_13BAD
0x13b29  ldloc.1
0x13b2a  ldc.i4   0x5F227BA7
0x13b2f  bgt.un.s loc_13B6F
0x13b31  ldloc.1
0x13b32  ldc.i4   0x5B22755B
0x13b37  bgt.un.s loc_13B54
0x13b39  ldloc.1
0x13b3a  ldc.i4   0x5A2273C8
0x13b3f  beq      loc_13E55
0x13b44  ldloc.1
0x13b45  ldc.i4   0x5B22755B
0x13b4a  beq      loc_13E40
0x13b4f  br       loc_13FAE
0x13b54  ldloc.1
0x13b55  ldc.i4   0x5C2276EE
0x13b5a  beq      loc_13E2B
0x13b5f  ldloc.1
0x13b60  ldc.i4   0x5F227BA7
0x13b65  beq      loc_13E94
0x13b6a  br       loc_13FAE
0x13b6f  ldloc.1
0x13b70  ldc.i4   0x61227ECD
0x13b75  bgt.un.s loc_13B92
0x13b77  ldloc.1
0x13b78  ldc.i4   0x60227D3A
0x13b7d  beq      loc_13E7F
0x13b82  ldloc.1
0x13b83  ldc.i4   0x61227ECD
0x13b88  beq      loc_13E6A
0x13b8d  br       loc_13FAE
0x13b92  ldloc.1
0x13b93  ldc.i4   0x6E39B680
0x13b98  beq      loc_13D44
0x13b9d  ldloc.1
0x13b9e  ldc.i4   0x8124EFC4
0x13ba3  beq      loc_13F72
0x13ba8  br       loc_13FAE
0x13bad  ldloc.1
0x13bae  ldc.i4   0xA522E9D9
0x13bb3  bgt.un.s loc_13BF3
0x13bb5  ldloc.1
0x13bb6  ldc.i4   0x8424F47D
0x13bbb  bgt.un.s loc_13BD8
0x13bbd  ldloc.1
0x13bbe  ldc.i4   0x8224F157
0x13bc3  beq      loc_13F81
0x13bc8  ldloc.1
0x13bc9  ldc.i4   0x8424F47D
0x13bce  beq      loc_13F63
0x13bd3  br       loc_13FAE
0x13bd8  ldloc.1
0x13bd9  ldc.i4   0xA422E846
0x13bde  beq      loc_13E16
0x13be3  ldloc.1
0x13be4  ldc.i4   0xA522E9D9
0x13be9  beq      loc_13E01
0x13bee  br       loc_13FAE
0x13bf3  ldloc.1
0x13bf4  ldc.i4   0xAB22F34B
0x13bf9  bgt.un.s loc_13C16
0x13bfb  ldloc.1
0x13bfc  ldc.i4   0xAA22F1B8
0x13c01  beq      loc_13D98
0x13c06  ldloc.1
0x13c07  ldc.i4   0xAB22F34B
0x13c0c  beq      loc_13D83
0x13c11  br       loc_13FAE
0x13c16  ldloc.1
0x13c17  ldc.i4   0xAB2531E2
0x13c1c  beq      loc_13F45
0x13c21  ldloc.1
0x13c22  ldc.i4   0xAC22F4DE
0x13c27  beq      loc_13D6E
0x13c2c  br       loc_13FAE
0x13c31  ldloc.1
0x13c32  ldc.i4   0xB022FB2A
0x13c37  bgt.un   loc_13CC0
0x13c3c  ldloc.1
0x13c3d  ldc.i4   0xAE22F804
0x13c42  bgt.un.s loc_13C82
0x13c44  ldloc.1
0x13c45  ldc.i4   0xAD22F671
0x13c4a  bgt.un.s loc_13C67
0x13c4c  ldloc.1
0x13c4d  ldc.i4   0xAC253375
0x13c52  beq      loc_13F54
0x13c57  ldloc.1
0x13c58  ldc.i4   0xAD22F671
0x13c5d  beq      loc_13D59
0x13c62  br       loc_13FAE
0x13c67  ldloc.1
0x13c68  ldc.i4   0xAD253508
0x13c6d  beq      loc_13F27
0x13c72  ldloc.1
0x13c73  ldc.i4   0xAE22F804
0x13c78  beq      loc_13DEC
0x13c7d  br       loc_13FAE
0x13c82  ldloc.1
0x13c83  ldc.i4   0xAF22F997
0x13c88  bgt.un.s loc_13CA5
0x13c8a  ldloc.1
0x13c8b  ldc.i4   0xAE25369B
0x13c90  beq      loc_13F36
0x13c95  ldloc.1
0x13c96  ldc.i4   0xAF22F997
0x13c9b  beq      loc_13DD7
0x13ca0  br       loc_13FAE
0x13ca5  ldloc.1
0x13ca6  ldc.i4   0xAF25382E
0x13cab  beq      loc_13EFD
0x13cb0  ldloc.1
0x13cb1  ldc.i4   0xB022FB2A
0x13cb6  beq      loc_13DC2
0x13cbb  br       loc_13FAE
0x13cc0  ldloc.1
0x13cc1  ldc.i4   0xB2253CE7
0x13cc6  bgt.un.s loc_13D06
0x13cc8  ldloc.1
0x13cc9  ldc.i4   0xB122FCBD
0x13cce  bgt.un.s loc_13CEB
0x13cd0  ldloc.1
0x13cd1  ldc.i4   0xB02539C1
0x13cd6  beq      loc_13F12
0x13cdb  ldloc.1
0x13cdc  ldc.i4   0xB122FCBD
0x13ce1  beq      loc_13DAD
0x13ce6  br       loc_13FAE
0x13ceb  ldloc.1
0x13cec  ldc.i4   0xB1253B54
0x13cf1  beq      loc_13ED3
0x13cf6  ldloc.1
0x13cf7  ldc.i4   0xB2253CE7
0x13cfc  beq      loc_13EE8
0x13d01  br       loc_13FAE
0x13d06  ldloc.1
0x13d07  ldc.i4   0xB425400D
0x13d0c  bgt.un.s loc_13D29
0x13d0e  ldloc.1
0x13d0f  ldc.i4   0xB3253E7A
0x13d14  beq      loc_13EA9
0x13d19  ldloc.1
0x13d1a  ldc.i4   0xB425400D
0x13d1f  beq      loc_13EBE
0x13d24  br       loc_13FAE
0x13d29  ldloc.1
0x13d2a  ldc.i4   0xCDA273E3
0x13d2f  beq      loc_13F9F
0x13d34  ldloc.1
0x13d35  ldc.i4   0xCEA27576
0x13d3a  beq      loc_13F90
0x13d3f  br       loc_13FAE
0x13d44  ldloc.0
0x13d45  ldstr    a80040494// "80040494"
0x13d4a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13d4f  brtrue   loc_13FAC
0x13d54  br       loc_13FAE
0x13d59  ldloc.0
0x13d5a  ldstr    a80048310// "80048310"
0x13d5f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13d64  brtrue   loc_13FAC
0x13d69  br       loc_13FAE
0x13d6e  ldloc.0
0x13d6f  ldstr    a80048311// "80048311"
0x13d74  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13d79  brtrue   loc_13FAC
0x13d7e  br       loc_13FAE
0x13d83  ldloc.0
0x13d84  ldstr    a80048312// "80048312"
0x13d89  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13d8e  brtrue   loc_13FAC
0x13d93  br       loc_13FAE
0x13d98  ldloc.0
0x13d99  ldstr    a80048313// "80048313"
0x13d9e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13da3  brtrue   loc_13FAC
0x13da8  br       loc_13FAE
0x13dad  ldloc.0
0x13dae  ldstr    a80048314// "80048314"
0x13db3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13db8  brtrue   loc_13FAC
0x13dbd  br       loc_13FAE
0x13dc2  ldloc.0
0x13dc3  ldstr    a80048315// "80048315"
0x13dc8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13dcd  brtrue   loc_13FAC
0x13dd2  br       loc_13FAE
0x13dd7  ldloc.0
0x13dd8  ldstr    a80048316// "80048316"
0x13ddd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13de2  brtrue   loc_13FAC
0x13de7  br       loc_13FAE
0x13dec  ldloc.0
0x13ded  ldstr    a80048317// "80048317"
0x13df2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13df7  brtrue   loc_13FAC
0x13dfc  br       loc_13FAE
0x13e01  ldloc.0
0x13e02  ldstr    a80048318// "80048318"
0x13e07  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e0c  brtrue   loc_13FAC
0x13e11  br       loc_13FAE
0x13e16  ldloc.0
0x13e17  ldstr    a80048319// "80048319"
0x13e1c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e21  brtrue   loc_13FAC
0x13e26  br       loc_13FAE
0x13e2b  ldloc.0
0x13e2c  ldstr    a8004831a// "8004831A"
0x13e31  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e36  brtrue   loc_13FAC
0x13e3b  br       loc_13FAE
0x13e40  ldloc.0
0x13e41  ldstr    a8004831b// "8004831B"
0x13e46  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e4b  brtrue   loc_13FAC
0x13e50  br       loc_13FAE
0x13e55  ldloc.0
0x13e56  ldstr    a8004831c// "8004831C"
0x13e5b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e60  brtrue   loc_13FAC
0x13e65  br       loc_13FAE
0x13e6a  ldloc.0
0x13e6b  ldstr    a8004831d// "8004831D"
0x13e70  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e75  brtrue   loc_13FAC
0x13e7a  br       loc_13FAE
0x13e7f  ldloc.0
0x13e80  ldstr    a8004831e// "8004831E"
0x13e85  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e8a  brtrue   loc_13FAC
0x13e8f  br       loc_13FAE
0x13e94  ldloc.0
0x13e95  ldstr    a8004831f// "8004831F"
0x13e9a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13e9f  brtrue   loc_13FAC
0x13ea4  br       loc_13FAE
0x13ea9  ldloc.0
0x13eaa  ldstr    a80048320// "80048320"
0x13eaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13eb4  brtrue   loc_13FAC
0x13eb9  br       loc_13FAE
0x13ebe  ldloc.0
0x13ebf  ldstr    a80048321// "80048321"
0x13ec4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13ec9  brtrue   loc_13FAC
0x13ece  br       loc_13FAE
0x13ed3  ldloc.0
0x13ed4  ldstr    a80048322// "80048322"
0x13ed9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13ede  brtrue   loc_13FAC
0x13ee3  br       loc_13FAE
0x13ee8  ldloc.0
0x13ee9  ldstr    a80048323// "80048323"
0x13eee  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13ef3  brtrue   loc_13FAC
0x13ef8  br       loc_13FAE
0x13efd  ldloc.0
0x13efe  ldstr    a80048324// "80048324"
0x13f03  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f08  brtrue   loc_13FAC
0x13f0d  br       loc_13FAE
0x13f12  ldloc.0
0x13f13  ldstr    a80048325// "80048325"
0x13f18  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f1d  brtrue   loc_13FAC
0x13f22  br       loc_13FAE
0x13f27  ldloc.0
0x13f28  ldstr    a80048326// "80048326"
0x13f2d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f32  brtrue.s loc_13FAC
0x13f34  br.s     loc_13FAE
0x13f36  ldloc.0
0x13f37  ldstr    a80048327// "80048327"
0x13f3c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f41  brtrue.s loc_13FAC
0x13f43  br.s     loc_13FAE
0x13f45  ldloc.0
0x13f46  ldstr    a80048328// "80048328"
0x13f4b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f50  brtrue.s loc_13FAC
0x13f52  br.s     loc_13FAE
0x13f54  ldloc.0
0x13f55  ldstr    a80048329// "80048329"
0x13f5a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x13f5f  brtrue.s loc_13FAC
0x13f61  br.s     loc_13FAE
0x13f63  ldloc.0
  ... truncated ...
```
