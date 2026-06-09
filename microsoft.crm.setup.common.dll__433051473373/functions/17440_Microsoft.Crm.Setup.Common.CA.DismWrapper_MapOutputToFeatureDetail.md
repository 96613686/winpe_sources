# Microsoft.Crm.Setup.Common.CA.DismWrapper::MapOutputToFeatureDetail

- ea: `0x17440`
- end: `0x174f7`
- name: `Microsoft.Crm.Setup.Common.CA.DismWrapper::MapOutputToFeatureDetail`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x17300`
- `0x17360`

## callees

- `0x17440`
- `0x17500`
- `0x177a0`

## string_xrefs

- `0x1746b`: `featureName`
- `0x17453`: `Feature Name :\s+(?<featureName>.*)\r\nDisplay Name :\s+(?<displayName>.*)\r\nDescription :\s+(?<description>.*)\r\nRestart Required :\s+(?<restartRequired>.*)\r\nState :\s+(?<state>.*)\r\n\r\nCustom Properties:\r\n\r\n(?<customProperties>.*)\r\n\r\n`

## pseudocode

```c

```

## disassembly

```asm
0x17440  ldarg.1
0x17441  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17446  brfalse.s loc_17453
0x17448  ldstr    aData// "data"
0x1744d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17452  throw
0x17453  ldstr    aFeatureNameSFe// "Feature Name :\\s+(?<featureName>.*)\\r"...
0x17458  ldc.i4.s 0x18
0x1745a  call     class [System]System.Text.RegularExpressions.Regex [Microsoft.Crm.Core]Microsoft.Crm.CrmRegexCache::GetRegex(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x1745f  ldarg.1
0x17460  callvirt instance class [System]System.Text.RegularExpressions.Match [System]System.Text.RegularExpressions.Regex::Match(string)
0x17465  dup
0x17466  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x1746b  ldstr    aFeaturename// "featureName"
0x17470  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x17475  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x1747a  stloc.0
0x1747b  dup
0x1747c  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x17481  ldstr    aState// "state"
0x17486  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x1748b  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x17490  stloc.1
0x17491  dup
0x17492  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x17497  ldstr    aDisplayname_0// "displayName"
0x1749c  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x174a1  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x174a6  stloc.2
0x174a7  dup
0x174a8  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x174ad  ldstr    aRestartrequire// "restartRequired"
0x174b2  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x174b7  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x174bc  stloc.3
0x174bd  callvirt instance class [System]System.Text.RegularExpressions.GroupCollection [System]System.Text.RegularExpressions.Match::get_Groups()
0x174c2  ldstr    aCustomproperti// "customProperties"
0x174c7  callvirt instance class [System]System.Text.RegularExpressions.Group [System]System.Text.RegularExpressions.GroupCollection::get_Item(string)
0x174cc  callvirt instance string [System]System.Text.RegularExpressions.Capture::get_Value()
0x174d1  stloc.s  4
0x174d3  ldarg.0
0x174d4  ldloc.s  4
0x174d6  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> Microsoft.Crm.Setup.Common.CA.DismWrapper::ExtractCustomProperties(string customPropertyString)
0x174db  stloc.s  5
0x174dd  ldloc.3
0x174de  ldloca.s 6
0x174e0  call     T0x2B000024
0x174e5  brtrue.s loc_174EA
0x174e7  ldc.i4.2
0x174e8  stloc.s  6
0x174ea  ldloc.0
0x174eb  ldloc.2
0x174ec  ldloc.1
0x174ed  ldloc.s  6
0x174ef  ldloc.s  5
0x174f1  newobj   instance void Microsoft.Crm.Setup.Common.CA.WindowsFeatureDetail::.ctor(string featureName, string displayName, string state, valuetype Microsoft.Crm.Setup.Common.CA.WindowsFeatureRestartType restartType, class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> customProperties)
0x174f6  ret
```
