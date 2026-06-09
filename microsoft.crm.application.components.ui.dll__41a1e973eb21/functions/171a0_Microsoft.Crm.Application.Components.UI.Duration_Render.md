# Microsoft.Crm.Application.Components.UI.Duration::Render

- ea: `0x171a0`
- end: `0x176e2`
- name: `Microsoft.Crm.Application.Components.UI.Duration::Render`
- size: `1346`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x17080`
- `0x170a0`
- `0x171a0`
- `0x176f0`
- `0x177d0`
- `0x179b0`
- `0x179d0`
- `0x17a00`
- `0x23c20`
- `0x23c30`
- `0x24120`
- `0x241d0`
- `0x241e0`
- `0x241f0`
- `0x24200`
- `0x24280`
- `0x242c0`
- `0x242d0`

## pseudocode

```c

```

## disassembly

```asm
0x171a0  ldarg.0
0x171a1  call     instance void Microsoft.Crm.Application.Components.UI.Duration::InitStrings()
0x171a6  ldsfld   string [mscorlib]System.String::Empty
0x171ab  stloc.0
0x171ac  ldarg.0
0x171ad  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinute
0x171b2  ldc.r8   1.0
0x171bb  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x171c0  stloc.1
0x171c1  ldarg.0
0x171c2  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x171c7  ldc.r8   5.0
0x171d0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x171d5  stloc.2
0x171d6  ldarg.0
0x171d7  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x171dc  ldc.r8   15.0
0x171e5  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x171ea  stloc.3
0x171eb  ldarg.0
0x171ec  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x171f1  ldc.r8   30.0
0x171fa  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x171ff  stloc.s  4
0x17201  ldarg.0
0x17202  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locMinutes
0x17207  ldc.r8   45.0
0x17210  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17215  stloc.s  5
0x17217  ldarg.0
0x17218  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHour
0x1721d  ldc.r8   1.0
0x17226  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x1722b  stloc.s  6
0x1722d  ldarg.0
0x1722e  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17233  ldc.r8   1.5
0x1723c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17241  stloc.s  7
0x17243  ldarg.0
0x17244  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17249  ldc.r8   2.0
0x17252  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17257  stloc.s  8
0x17259  ldarg.0
0x1725a  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x1725f  ldc.r8   2.5
0x17268  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x1726d  stloc.s  9
0x1726f  ldarg.0
0x17270  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17275  ldc.r8   3.0
0x1727e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17283  stloc.s  0xA
0x17285  ldarg.0
0x17286  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x1728b  ldc.r8   3.5
0x17294  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17299  stloc.s  0xB
0x1729b  ldarg.0
0x1729c  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x172a1  ldc.r8   4.0
0x172aa  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x172af  stloc.s  0xC
0x172b1  ldarg.0
0x172b2  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x172b7  ldc.r8   4.5
0x172c0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x172c5  stloc.s  0xD
0x172c7  ldarg.0
0x172c8  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x172cd  ldc.r8   5.0
0x172d6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x172db  stloc.s  0xE
0x172dd  ldarg.0
0x172de  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x172e3  ldc.r8   5.5
0x172ec  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x172f1  stloc.s  0xF
0x172f3  ldarg.0
0x172f4  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x172f9  ldc.r8   6.0
0x17302  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17307  stloc.s  0x10
0x17309  ldarg.0
0x1730a  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x1730f  ldc.r8   6.5
0x17318  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x1731d  stloc.s  0x11
0x1731f  ldarg.0
0x17320  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17325  ldc.r8   7.0
0x1732e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17333  stloc.s  0x12
0x17335  ldarg.0
0x17336  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x1733b  ldc.r8   7.5
0x17344  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17349  stloc.s  0x13
0x1734b  ldarg.0
0x1734c  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locHours
0x17351  ldc.r8   8.0
0x1735a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x1735f  stloc.s  0x14
0x17361  ldarg.0
0x17362  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDay
0x17367  ldc.r8   1.0
0x17370  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x17375  stloc.s  0x15
0x17377  ldarg.0
0x17378  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDays
0x1737d  ldc.r8   2.0
0x17386  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x1738b  stloc.s  0x16
0x1738d  ldarg.0
0x1738e  ldfld    string Microsoft.Crm.Application.Components.UI.Duration::_locDays
0x17393  ldc.r8   3.0
0x1739c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.DateTimeUtility::GenerateDurationDescription(string, float64)
0x173a1  stloc.s  0x17
0x173a3  ldarg.0
0x173a4  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x173a9  ldarg.0
0x173aa  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x173af  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControlBase::set_Disabled(bool value)
0x173b4  ldarg.0
0x173b5  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x173ba  ldarg.0
0x173bb  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_Required()
0x173c0  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_Required(int32 value)
0x173c5  ldarg.0
0x173c6  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x173cb  ldarg.0
0x173cc  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ImeMode()
0x173d1  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_ImeMode(valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeIMEMode value)
0x173d6  ldarg.0
0x173d7  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x173dc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x173e1  ldstr    aGeneralDuratio// "General.Duration.ButtonLabel"
0x173e6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x173eb  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_ButtonTitle(string value)
0x173f0  ldarg.0
0x173f1  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x173f6  brfalse.s loc_17409
0x173f8  ldarg.0
0x173f9  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x173fe  ldarg.0
0x173ff  callvirt instance int32 Microsoft.Crm.Application.Components.UI.CrmUIControl::get_TabIndex()
0x17404  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::set_TabIndex(int32 value)
0x17409  ldarg.0
0x1740a  ldfld    bool Microsoft.Crm.Application.Components.UI.Duration::_isOnlyDays
0x1740f  brtrue   loc_17547
0x17414  ldarg.0
0x17415  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1741a  ldloc.0
0x1741b  ldloc.0
0x1741c  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17421  ldarg.0
0x17422  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17427  ldloc.1
0x17428  ldloc.1
0x17429  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x1742e  ldarg.0
0x1742f  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17434  ldloc.2
0x17435  ldloc.2
0x17436  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x1743b  ldarg.0
0x1743c  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17441  ldloc.3
0x17442  ldloc.3
0x17443  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17448  ldarg.0
0x17449  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1744e  ldloc.s  4
0x17450  ldloc.s  4
0x17452  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17457  ldarg.0
0x17458  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1745d  ldloc.s  5
0x1745f  ldloc.s  5
0x17461  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17466  ldarg.0
0x17467  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1746c  ldloc.s  6
0x1746e  ldloc.s  6
0x17470  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17475  ldarg.0
0x17476  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1747b  ldloc.s  7
0x1747d  ldloc.s  7
0x1747f  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17484  ldarg.0
0x17485  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1748a  ldloc.s  8
0x1748c  ldloc.s  8
0x1748e  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17493  ldarg.0
0x17494  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17499  ldloc.s  9
0x1749b  ldloc.s  9
0x1749d  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174a2  ldarg.0
0x174a3  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174a8  ldloc.s  0xA
0x174aa  ldloc.s  0xA
0x174ac  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174b1  ldarg.0
0x174b2  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174b7  ldloc.s  0xB
0x174b9  ldloc.s  0xB
0x174bb  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174c0  ldarg.0
0x174c1  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174c6  ldloc.s  0xC
0x174c8  ldloc.s  0xC
0x174ca  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174cf  ldarg.0
0x174d0  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174d5  ldloc.s  0xD
0x174d7  ldloc.s  0xD
0x174d9  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174de  ldarg.0
0x174df  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174e4  ldloc.s  0xE
0x174e6  ldloc.s  0xE
0x174e8  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174ed  ldarg.0
0x174ee  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x174f3  ldloc.s  0xF
0x174f5  ldloc.s  0xF
0x174f7  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x174fc  ldarg.0
0x174fd  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17502  ldloc.s  0x10
0x17504  ldloc.s  0x10
0x17506  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x1750b  ldarg.0
0x1750c  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17511  ldloc.s  0x11
0x17513  ldloc.s  0x11
0x17515  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x1751a  ldarg.0
0x1751b  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17520  ldloc.s  0x12
0x17522  ldloc.s  0x12
0x17524  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17529  ldarg.0
0x1752a  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1752f  ldloc.s  0x13
0x17531  ldloc.s  0x13
0x17533  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17538  ldarg.0
0x17539  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1753e  ldloc.s  0x14
0x17540  ldloc.s  0x14
0x17542  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17547  ldarg.0
0x17548  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1754d  ldloc.s  0x15
0x1754f  ldloc.s  0x15
0x17551  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17556  ldarg.0
0x17557  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1755c  ldloc.s  0x16
0x1755e  ldloc.s  0x16
0x17560  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17565  ldarg.0
0x17566  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x1756b  ldloc.s  0x17
0x1756d  ldloc.s  0x17
0x1756f  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::AddItem(string text, string value)
0x17574  ldarg.0
0x17575  ldfld    int32 Microsoft.Crm.Application.Components.UI.Duration::_minutes
0x1757a  ldc.i4   0x80000000
0x1757f  beq.s    loc_1759A
0x17581  ldarg.0
0x17582  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x17587  ldarg.0
0x17588  ldarg.0
0x17589  ldfld    int32 Microsoft.Crm.Application.Components.UI.Duration::_minutes
0x1758e  call     instance string Microsoft.Crm.Application.Components.UI.Duration::formatDuration(int32 minutes)
0x17593  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_Selected(string value)
0x17598  br.s     loc_175AA
0x1759a  ldarg.0
0x1759b  ldfld    class Microsoft.Crm.Application.Components.UI.EditableSelect Microsoft.Crm.Application.Components.UI.Duration::_select
0x175a0  ldsfld   string [mscorlib]System.String::Empty
0x175a5  callvirt instance void Microsoft.Crm.Application.Components.UI.EditableSelect::set_Selected(string value)
0x175aa  ldarg.1
0x175ab  ldstr    aInputTypeHidde_2// "<input type='hidden' class='ms-crm-Dura"...
0x175b0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x175b5  ldarg.0
0x175b6  ldfld    int32 Microsoft.Crm.Application.Components.UI.Duration::_minutes
0x175bb  ldc.i4   0x80000000
0x175c0  beq.s    loc_175DE
0x175c2  ldarg.1
0x175c3  ldstr    aInitialvalue_0// "InitialValue"
0x175c8  ldarg.0
0x175c9  ldflda   int32 Microsoft.Crm.Application.Components.UI.Duration::_minutes
0x175ce  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x175d3  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
  ... truncated ...
```
