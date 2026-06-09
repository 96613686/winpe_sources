# Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GetFileType

- ea: `0x12eef0`
- end: `0x12f888`
- name: `Microsoft.Crm.ObjectModel.OfficeGraphDocumentHelper::GetFileType`
- size: `2456`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x12ede0`

## callees

- `0x12eef0`
- `0x22be40`

## string_xrefs

- `0x12f722`: `text/xml`
- `0x12f2b4`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x12f2de`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x12f308`: `application/vnd.openxmlformats-officedocument.wordprocessingml.template`
- `0x12f31d`: `application/vnd.oasis.opendocument.text`
- `0x12f347`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`
- `0x12f386`: `application/vnd.oasis.opendocument.chart`
- `0x12f39b`: `application/vnd.oasis.opendocument.spreadsheet`
- `0x12f42e`: `application/msaccess`
- `0x12f443`: `application/x-msaccess`
- `0x12f4c1`: `application/x-rar-compressed`

## pseudocode

```c

```

## disassembly

```asm
0x12eef0  ldsfld   string [mscorlib]System.String::Empty
0x12eef5  stloc.0
0x12eef6  ldarg.0
0x12eef7  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x12eefc  stloc.1
0x12eefd  ldloc.1
0x12eefe  ldc.i4   0x84EBB23D
0x12ef03  bgt.un   loc_12F0D3
0x12ef08  ldloc.1
0x12ef09  ldc.i4   0x3E10666B
0x12ef0e  bgt.un   loc_12EFF3
0x12ef13  ldloc.1
0x12ef14  ldc.i4   0x1DAC5892
0x12ef19  bgt.un.s loc_12EF87
0x12ef1b  ldloc.1
0x12ef1c  ldc.i4   0x7DE9767
0x12ef21  bgt.un.s loc_12EF49
0x12ef23  ldloc.1
0x12ef24  ldc.i4   0x6980982
0x12ef29  beq      loc_12F3EE
0x12ef2e  ldloc.1
0x12ef2f  ldc.i4   0x739F695
0x12ef34  beq      loc_12F592
0x12ef39  ldloc.1
0x12ef3a  ldc.i4   0x7DE9767
0x12ef3f  beq      loc_12F307
0x12ef44  br       loc_12F886
0x12ef49  ldloc.1
0x12ef4a  ldc.i4   0x1219A2AC
0x12ef4f  bgt.un.s loc_12EF6C
0x12ef51  ldloc.1
0x12ef52  ldc.i4   0xBDF469E
0x12ef57  beq      loc_12F385
0x12ef5c  ldloc.1
0x12ef5d  ldc.i4   0x1219A2AC
0x12ef62  beq      loc_12F418
0x12ef67  br       loc_12F886
0x12ef6c  ldloc.1
0x12ef6d  ldc.i4   0x12648E18
0x12ef72  beq      loc_12F721
0x12ef77  ldloc.1
0x12ef78  ldc.i4   0x1DAC5892
0x12ef7d  beq      loc_12F2F2
0x12ef82  br       loc_12F886
0x12ef87  ldloc.1
0x12ef88  ldc.i4   0x25DD7BDB
0x12ef8d  bgt.un.s loc_12EFB5
0x12ef8f  ldloc.1
0x12ef90  ldc.i4   0x1F391A45
0x12ef95  beq      loc_12F4EA
0x12ef9a  ldloc.1
0x12ef9b  ldc.i4   0x2496F8E7
0x12efa0  beq      loc_12F370
0x12efa5  ldloc.1
0x12efa6  ldc.i4   0x25DD7BDB
0x12efab  beq      loc_12F57D
0x12efb0  br       loc_12F886
0x12efb5  ldloc.1
0x12efb6  ldc.i4   0x280D3A04
0x12efbb  bgt.un.s loc_12EFD8
0x12efbd  ldloc.1
0x12efbe  ldc.i4   0x27CFEF18
0x12efc3  beq      loc_12F2DD
0x12efc8  ldloc.1
0x12efc9  ldc.i4   0x280D3A04
0x12efce  beq      loc_12F39A
0x12efd3  br       loc_12F886
0x12efd8  ldloc.1
0x12efd9  ldc.i4   0x3B601E97
0x12efde  beq      loc_12F442
0x12efe3  ldloc.1
0x12efe4  ldc.i4   0x3E10666B
0x12efe9  beq      loc_12F529
0x12efee  br       loc_12F886
0x12eff3  ldloc.1
0x12eff4  ldc.i4   0x61B8D270
0x12eff9  bgt.un.s loc_12F067
0x12effb  ldloc.1
0x12effc  ldc.i4   0x47BC6E8F
0x12f001  bgt.un.s loc_12F029
0x12f003  ldloc.1
0x12f004  ldc.i4   0x40C8F111
0x12f009  beq      loc_12F31C
0x12f00e  ldloc.1
0x12f00f  ldc.i4   0x46DB7D36
0x12f014  beq      loc_12F29E
0x12f019  ldloc.1
0x12f01a  ldc.i4   0x47BC6E8F
0x12f01f  beq      loc_12F514
0x12f024  br       loc_12F886
0x12f029  ldloc.1
0x12f02a  ldc.i4   0x5B5E4B53
0x12f02f  bgt.un.s loc_12F04C
0x12f031  ldloc.1
0x12f032  ldc.i4   0x5413A933
0x12f037  beq      loc_12F610
0x12f03c  ldloc.1
0x12f03d  ldc.i4   0x5B5E4B53
0x12f042  beq      loc_12F346
0x12f047  br       loc_12F886
0x12f04c  ldloc.1
0x12f04d  ldc.i4   0x5E106874
0x12f052  beq      loc_12F664
0x12f057  ldloc.1
0x12f058  ldc.i4   0x61B8D270
0x12f05d  beq      loc_12F5D1
0x12f062  br       loc_12F886
0x12f067  ldloc.1
0x12f068  ldc.i4   0x6CDFE674
0x12f06d  bgt.un.s loc_12F095
0x12f06f  ldloc.1
0x12f070  ldc.i4   0x66699C39
0x12f075  beq      loc_12F5BC
0x12f07a  ldloc.1
0x12f07b  ldc.i4   0x6AE0CB68
0x12f080  beq      loc_12F42D
0x12f085  ldloc.1
0x12f086  ldc.i4   0x6CDFE674
0x12f08b  beq      loc_12F568
0x12f090  br       loc_12F886
0x12f095  ldloc.1
0x12f096  ldc.i4   0x79A13FEA
0x12f09b  bgt.un.s loc_12F0B8
0x12f09d  ldloc.1
0x12f09e  ldc.i4   0x75D8656E
0x12f0a3  beq      loc_12F6E2
0x12f0a8  ldloc.1
0x12f0a9  ldc.i4   0x79A13FEA
0x12f0ae  beq      loc_12F2C8
0x12f0b3  br       loc_12F886
0x12f0b8  ldloc.1
0x12f0b9  ldc.i4   0x80069FD1
0x12f0be  beq      loc_12F46C
0x12f0c3  ldloc.1
0x12f0c4  ldc.i4   0x84EBB23D
0x12f0c9  beq      loc_12F496
0x12f0ce  br       loc_12F886
0x12f0d3  ldloc.1
0x12f0d4  ldc.i4   0xD23BD685
0x12f0d9  bgt.un   loc_12F1BE
0x12f0de  ldloc.1
0x12f0df  ldc.i4   0xB00ABF3A
0x12f0e4  bgt.un.s loc_12F152
0x12f0e6  ldloc.1
0x12f0e7  ldc.i4   0x9C3F78DA
0x12f0ec  bgt.un.s loc_12F114
0x12f0ee  ldloc.1
0x12f0ef  ldc.i4   0x8E86CED8
0x12f0f4  beq      loc_12F64F
0x12f0f9  ldloc.1
0x12f0fa  ldc.i4   0x93524AB9
0x12f0ff  beq      loc_12F553
0x12f104  ldloc.1
0x12f105  ldc.i4   0x9C3F78DA
0x12f10a  beq      loc_12F331
0x12f10f  br       loc_12F886
0x12f114  ldloc.1
0x12f115  ldc.i4   0xA9D8CD5D
0x12f11a  bgt.un.s loc_12F137
0x12f11c  ldloc.1
0x12f11d  ldc.i4   0xA08E034E
0x12f122  beq      loc_12F6B8
0x12f127  ldloc.1
0x12f128  ldc.i4   0xA9D8CD5D
0x12f12d  beq      loc_12F63A
0x12f132  br       loc_12F886
0x12f137  ldloc.1
0x12f138  ldc.i4   0xACCCDD84
0x12f13d  beq      loc_12F3AF
0x12f142  ldloc.1
0x12f143  ldc.i4   0xB00ABF3A
0x12f148  beq      loc_12F679
0x12f14d  br       loc_12F886
0x12f152  ldloc.1
0x12f153  ldc.i4   0xB94FF6E3
0x12f158  bgt.un.s loc_12F180
0x12f15a  ldloc.1
0x12f15b  ldc.i4   0xB22394CD
0x12f160  beq      loc_12F481
0x12f165  ldloc.1
0x12f166  ldc.i4   0xB71B3E3F
0x12f16b  beq      loc_12F6A3
0x12f170  ldloc.1
0x12f171  ldc.i4   0xB94FF6E3
0x12f176  beq      loc_12F4FF
0x12f17b  br       loc_12F886
0x12f180  ldloc.1
0x12f181  ldc.i4   0xC0FE6950
0x12f186  bgt.un.s loc_12F1A3
0x12f188  ldloc.1
0x12f189  ldc.i4   0xBD87259A
0x12f18e  beq      loc_12F4D5
0x12f193  ldloc.1
0x12f194  ldc.i4   0xC0FE6950
0x12f199  beq      loc_12F3D9
0x12f19e  br       loc_12F886
0x12f1a3  ldloc.1
0x12f1a4  ldc.i4   0xCAECFDD3
0x12f1a9  beq      loc_12F625
0x12f1ae  ldloc.1
0x12f1af  ldc.i4   0xD23BD685
0x12f1b4  beq      loc_12F6F7
0x12f1b9  br       loc_12F886
0x12f1be  ldloc.1
0x12f1bf  ldc.i4   0xE6A51466
0x12f1c4  bgt.un.s loc_12F232
0x12f1c6  ldloc.1
0x12f1c7  ldc.i4   0xD7FA74F2
0x12f1cc  bgt.un.s loc_12F1F4
0x12f1ce  ldloc.1
0x12f1cf  ldc.i4   0xD588A095
0x12f1d4  beq      loc_12F53E
0x12f1d9  ldloc.1
0x12f1da  ldc.i4   0xD6BDE9F4
0x12f1df  beq      loc_12F4AB
0x12f1e4  ldloc.1
0x12f1e5  ldc.i4   0xD7FA74F2
0x12f1ea  beq      loc_12F3C4
0x12f1ef  br       loc_12F886
0x12f1f4  ldloc.1
0x12f1f5  ldc.i4   0xE3B1EAC2
0x12f1fa  bgt.un.s loc_12F217
0x12f1fc  ldloc.1
0x12f1fd  ldc.i4   0xDED4A8C3
0x12f202  beq      loc_12F403
0x12f207  ldloc.1
0x12f208  ldc.i4   0xE3B1EAC2
0x12f20d  beq      loc_12F70C
0x12f212  br       loc_12F886
0x12f217  ldloc.1
0x12f218  ldc.i4   0xE54664F4
0x12f21d  beq      loc_12F2B3
0x12f222  ldloc.1
0x12f223  ldc.i4   0xE6A51466
0x12f228  beq      loc_12F35B
0x12f22d  br       loc_12F886
0x12f232  ldloc.1
0x12f233  ldc.i4   0xEC30189C
0x12f238  bgt.un.s loc_12F260
0x12f23a  ldloc.1
0x12f23b  ldc.i4   0xE88A7C5D
0x12f240  beq      loc_12F6CD
0x12f245  ldloc.1
0x12f246  ldc.i4   0xEB95C86C
0x12f24b  beq      loc_12F4C0
0x12f250  ldloc.1
0x12f251  ldc.i4   0xEC30189C
0x12f256  beq      loc_12F5FB
0x12f25b  br       loc_12F886
0x12f260  ldloc.1
0x12f261  ldc.i4   0xF1AF421A
0x12f266  bgt.un.s loc_12F283
0x12f268  ldloc.1
0x12f269  ldc.i4   0xEF511109
0x12f26e  beq      loc_12F5A7
0x12f273  ldloc.1
0x12f274  ldc.i4   0xF1AF421A
0x12f279  beq      loc_12F457
0x12f27e  br       loc_12F886
0x12f283  ldloc.1
0x12f284  ldc.i4   0xFC54371A
0x12f289  beq      loc_12F68E
0x12f28e  ldloc.1
0x12f28f  ldc.i4   0xFC8B3D09
0x12f294  beq      loc_12F5E6
0x12f299  br       loc_12F886
0x12f29e  ldarg.0
0x12f29f  ldstr    aApplicationVnd// "application/vnd.ms-powerpoint"
0x12f2a4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f2a9  brtrue   loc_12F736
0x12f2ae  br       loc_12F886
0x12f2b3  ldarg.0
0x12f2b4  ldstr    aApplicationVnd_0// "application/vnd.openxmlformats-officedo"...
0x12f2b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f2be  brtrue   loc_12F73C
0x12f2c3  br       loc_12F886
0x12f2c8  ldarg.0
0x12f2c9  ldstr    aApplicationMsw// "application/msword"
0x12f2ce  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f2d3  brtrue   loc_12F742
0x12f2d8  br       loc_12F886
0x12f2dd  ldarg.0
0x12f2de  ldstr    aApplicationVnd_1// "application/vnd.openxmlformats-officedo"...
0x12f2e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f2e8  brtrue   loc_12F748
0x12f2ed  br       loc_12F886
0x12f2f2  ldarg.0
0x12f2f3  ldstr    aApplicationVnd_2// "application/vnd.ms-word.document.macroE"...
0x12f2f8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f2fd  brtrue   loc_12F74E
0x12f302  br       loc_12F886
0x12f307  ldarg.0
0x12f308  ldstr    aApplicationVnd_3// "application/vnd.openxmlformats-officedo"...
0x12f30d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f312  brtrue   loc_12F754
0x12f317  br       loc_12F886
0x12f31c  ldarg.0
0x12f31d  ldstr    aApplicationVnd_4// "application/vnd.oasis.opendocument.text"
0x12f322  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12f327  brtrue   loc_12F75A
  ... truncated ...
```
