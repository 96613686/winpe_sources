# Microsoft.Crm.Application.Components.UI.Duration::InitStrings

- ea: `0x177d0`
- end: `0x17888`
- name: `Microsoft.Crm.Application.Components.UI.Duration::InitStrings`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x171a0`
- `0x176f0`

## callees

- `0x177d0`

## string_xrefs

- `0x17875`: `At least one display string for duration control does not have a replaceable parameter.`

## pseudocode

```c

```

## disassembly

```asm
0x177d0  ldarg.0
0x177d1  ldfld    bool Microsoft.Crm.Application.Components.UI.Duration::_stringsInitialized
0x177d6  brtrue   loc_17887
0x177db  ldarg.0
0x177dc  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinute
0x177e1  brfalse.s loc_1780B
0x177e3  ldarg.0
0x177e4  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x177e9  brfalse.s loc_1780B
0x177eb  ldarg.0
0x177ec  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHour
0x177f1  brfalse.s loc_1780B
0x177f3  ldarg.0
0x177f4  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x177f9  brfalse.s loc_1780B
0x177fb  ldarg.0
0x177fc  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDay
0x17801  brfalse.s loc_1780B
0x17803  ldarg.0
0x17804  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDays
0x17809  brtrue.s loc_17816
0x1780b  ldstr    aDisplayStrings// "Display strings have not been set for t"...
0x17810  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x17815  throw
0x17816  ldstr    a0ND// "{0[:N\\d+]*}"
0x1781b  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string)
0x17820  stloc.0
0x17821  ldloc.0
0x17822  ldarg.0
0x17823  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinute
0x17828  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x1782d  brfalse.s loc_17875
0x1782f  ldloc.0
0x17830  ldarg.0
0x17831  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x17836  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x1783b  brfalse.s loc_17875
0x1783d  ldloc.0
0x1783e  ldarg.0
0x1783f  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHour
0x17844  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x17849  brfalse.s loc_17875
0x1784b  ldloc.0
0x1784c  ldarg.0
0x1784d  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17852  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x17857  brfalse.s loc_17875
0x17859  ldloc.0
0x1785a  ldarg.0
0x1785b  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDay
0x17860  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x17865  brfalse.s loc_17875
0x17867  ldloc.0
0x17868  ldarg.0
0x17869  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDays
0x1786e  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x17873  brtrue.s loc_17880
0x17875  ldstr    aAtLeastOneDisp// "At least one display string for duratio"...
0x1787a  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1787f  throw
0x17880  ldarg.0
0x17881  ldc.i4.1
0x17882  stfld    bool Microsoft.Crm.Application.Components.UI.Duration::_stringsInitialized
0x17887  ret
```
