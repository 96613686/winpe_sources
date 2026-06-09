# Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::SetOutlookCommandActionType

- ea: `0x97230`
- end: `0x9747e`
- name: `Microsoft.Crm.Application.Platform.Ribbon.RibbonXml.RibbonCommandDefinitionGenerator::SetOutlookCommandActionType`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x96f40`

## callees

- `0x97230`
- `0x9ca50`

## string_xrefs

- `0x97373`: `OpenOlkForm`
- `0x9739d`: `ConfigWizard`
- `0x973eb`: `CheckForUpdates`

## pseudocode

```c

```

## disassembly

```asm
0x97230  ldarg.1
0x97231  ldstr    aActiontype_0// "ActionType"
0x97236  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x9723b  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x97240  call     string [System.Xml.Linq]System.Xml.Linq.XAttribute::op_Explicit(class [System.Xml.Linq]System.Xml.Linq.XAttribute)
0x97245  stloc.0
0x97246  ldloc.0
0x97247  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x9724c  stloc.1
0x9724d  ldloc.1
0x9724e  ldc.i4   0x4F04A614
0x97253  bgt.un.s loc_972A9
0x97255  ldloc.1
0x97256  ldc.i4   0x318838A9
0x9725b  bgt.un.s loc_97283
0x9725d  ldloc.1
0x9725e  ldc.i4   0x11F4191
0x97263  beq      loc_97372
0x97268  ldloc.1
0x97269  ldc.i4   0x103B4B9B
0x9726e  beq      loc_97348
0x97273  ldloc.1
0x97274  ldc.i4   0x318838A9
0x97279  beq      loc_973F9
0x9727e  br       loc_97476
0x97283  ldloc.1
0x97284  ldc.i4   0x499E8978
0x97289  beq      loc_9739C
0x9728e  ldloc.1
0x9728f  ldc.i4   0x4B058728
0x97294  beq      loc_97387
0x97299  ldloc.1
0x9729a  ldc.i4   0x4F04A614
0x9729f  beq      loc_973D8
0x972a4  br       loc_97476
0x972a9  ldloc.1
0x972aa  ldc.i4   0x89A71BBA
0x972af  bgt.un.s loc_972CE
0x972b1  ldloc.1
0x972b2  ldc.i4   0x6D03F8F2
0x972b7  beq.s    loc_9731E
0x972b9  ldloc.1
0x972ba  ldc.i4   0x761F0DE6
0x972bf  beq.s    loc_97309
0x972c1  ldloc.1
0x972c2  ldc.i4   0x89A71BBA
0x972c7  beq.s    loc_97333
0x972c9  br       loc_97476
0x972ce  ldloc.1
0x972cf  ldc.i4   0xAA518B08
0x972d4  bgt.un.s loc_972F1
0x972d6  ldloc.1
0x972d7  ldc.i4   0x8CA7DA88
0x972dc  beq      loc_973B1
0x972e1  ldloc.1
0x972e2  ldc.i4   0xAA518B08
0x972e7  beq      loc_973EA
0x972ec  br       loc_97476
0x972f1  ldloc.1
0x972f2  ldc.i4   0xB89DF01A
0x972f7  beq.s    loc_9735D
0x972f9  ldloc.1
0x972fa  ldc.i4   0xD5EA6FB3
0x972ff  beq      loc_973C6
0x97304  br       loc_97476
0x97309  ldloc.0
0x9730a  ldstr    aGoto// "GoTo"
0x9730f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97314  brtrue   loc_97408
0x97319  br       loc_97476
0x9731e  ldloc.0
0x9731f  ldstr    aGooffline// "GoOffline"
0x97324  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97329  brtrue   loc_97410
0x9732e  br       loc_97476
0x97333  ldloc.0
0x97334  ldstr    aSync// "Sync"
0x97339  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9733e  brtrue   loc_97418
0x97343  br       loc_97476
0x97348  ldloc.0
0x97349  ldstr    aPromote// "Promote"
0x9734e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97353  brtrue   loc_97420
0x97358  br       loc_97476
0x9735d  ldloc.0
0x9735e  ldstr    aHelp_1// "Help"
0x97363  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97368  brtrue   loc_97428
0x9736d  br       loc_97476
0x97372  ldloc.0
0x97373  ldstr    aOpenolkform// "OpenOlkForm"
0x97378  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9737d  brtrue   loc_97430
0x97382  br       loc_97476
0x97387  ldloc.0
0x97388  ldstr    aSettings// "Settings"
0x9738d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97392  brtrue   loc_97438
0x97397  br       loc_97476
0x9739c  ldloc.0
0x9739d  ldstr    aConfigwizard// "ConfigWizard"
0x973a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x973a7  brtrue   loc_97440
0x973ac  br       loc_97476
0x973b1  ldloc.0
0x973b2  ldstr    aSignout// "SignOut"
0x973b7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x973bc  brtrue   loc_97449
0x973c1  br       loc_97476
0x973c6  ldloc.0
0x973c7  ldstr    aSignoutforgetm// "SignOutForgetMe"
0x973cc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x973d1  brtrue.s loc_97452
0x973d3  br       loc_97476
0x973d8  ldloc.0
0x973d9  ldstr    aSetregarding// "SetRegarding"
0x973de  call     bool [mscorlib]System.String::op_Equality(string, string)
0x973e3  brtrue.s loc_9745B
0x973e5  br       loc_97476
0x973ea  ldloc.0
0x973eb  ldstr    aCheckforupdate// "CheckForUpdates"
0x973f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x973f5  brtrue.s loc_97464
0x973f7  br.s     loc_97476
0x973f9  ldloc.0
0x973fa  ldstr    aOutlookimport// "OutlookImport"
0x973ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x97404  brtrue.s loc_9746D
0x97406  br.s     loc_97476
0x97408  ldarg.2
0x97409  ldc.i4.2
0x9740a  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9740f  ret
0x97410  ldarg.2
0x97411  ldc.i4.3
0x97412  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97417  ret
0x97418  ldarg.2
0x97419  ldc.i4.4
0x9741a  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9741f  ret
0x97420  ldarg.2
0x97421  ldc.i4.5
0x97422  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97427  ret
0x97428  ldarg.2
0x97429  ldc.i4.6
0x9742a  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9742f  ret
0x97430  ldarg.2
0x97431  ldc.i4.7
0x97432  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97437  ret
0x97438  ldarg.2
0x97439  ldc.i4.8
0x9743a  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9743f  ret
0x97440  ldarg.2
0x97441  ldc.i4.s 9
0x97443  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97448  ret
0x97449  ldarg.2
0x9744a  ldc.i4.s 0xA
0x9744c  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97451  ret
0x97452  ldarg.2
0x97453  ldc.i4.s 0xB
0x97455  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9745a  ret
0x9745b  ldarg.2
0x9745c  ldc.i4.s 0xC
0x9745e  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97463  ret
0x97464  ldarg.2
0x97465  ldc.i4.s 0xD
0x97467  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9746c  ret
0x9746d  ldarg.2
0x9746e  ldc.i4.s 0xE
0x97470  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x97475  ret
0x97476  ldarg.2
0x97477  ldc.i4.1
0x97478  stfld    int32 [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.Ribbon.OutlookActionAttributes::ActionType
0x9747d  ret
```
