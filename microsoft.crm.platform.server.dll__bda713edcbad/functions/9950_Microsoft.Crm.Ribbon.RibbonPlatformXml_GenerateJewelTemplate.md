# Microsoft.Crm.Ribbon.RibbonPlatformXml::GenerateJewelTemplate

- ea: `0x9950`
- end: `0x9a37`
- name: `Microsoft.Crm.Ribbon.RibbonPlatformXml::GenerateJewelTemplate`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x9950`

## string_xrefs

- `0x9983`: `Command`
- `0x99df`: `ImageLeftSideWidth`
- `0x99f6`: `ImageRightSideWidth`

## pseudocode

```c

```

## disassembly

```asm
0x9950  ldstr    aUi// "UI"
0x9955  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x995a  ldstr    aJewel// "Jewel"
0x995f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9964  ldc.i4.8
0x9965  newarr   [mscorlib]System.Object
0x996a  dup
0x996b  ldc.i4.0
0x996c  ldstr    aId_0// "Id"
0x9971  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9976  ldstr    aMscrmJewel// "Mscrm.Jewel"
0x997b  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9980  stelem.ref
0x9981  dup
0x9982  ldc.i4.1
0x9983  ldstr    aCommand// "Command"
0x9988  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x998d  ldstr    aMscrmJewel// "Mscrm.Jewel"
0x9992  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9997  stelem.ref
0x9998  dup
0x9999  ldc.i4.2
0x999a  ldstr    aAlt// "Alt"
0x999f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x99a4  ldstr    aResourcesRibbo// "$Resources:Ribbon.Jewel.Tooltip"
0x99a9  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x99ae  stelem.ref
0x99af  dup
0x99b0  ldc.i4.3
0x99b1  ldstr    aLabeltext// "LabelText"
0x99b6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x99bb  ldstr    aResourcesRibbo_0// "$Resources:Ribbon.Jewel.Text"
0x99c0  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x99c5  stelem.ref
0x99c6  dup
0x99c7  ldc.i4.4
0x99c8  ldstr    aHeight// "Height"
0x99cd  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x99d2  ldstr    a24// "24"
0x99d7  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x99dc  stelem.ref
0x99dd  dup
0x99de  ldc.i4.5
0x99df  ldstr    aImageleftsidew// "ImageLeftSideWidth"
0x99e4  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x99e9  ldstr    a14// "14"
0x99ee  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x99f3  stelem.ref
0x99f4  dup
0x99f5  ldc.i4.6
0x99f6  ldstr    aImagerightside// "ImageRightSideWidth"
0x99fb  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9a00  ldstr    a14// "14"
0x9a05  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9a0a  stelem.ref
0x9a0b  dup
0x9a0c  ldc.i4.7
0x9a0d  ldstr    aTextdirection// "TextDirection"
0x9a12  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9a17  ldarg.0
0x9a18  brtrue.s loc_9A21
0x9a1a  ldstr    aLtr// "ltr"
0x9a1f  br.s     loc_9A26
0x9a21  ldstr    aRtl// "rtl"
0x9a26  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XAttribute::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9a2b  stelem.ref
0x9a2c  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object[])
0x9a31  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x9a36  ret
```
