# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::Render

- ea: `0x19460`
- end: `0x195ff`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::Render`
- size: `415`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x19460`
- `0x19680`

## string_xrefs

- `0x19518`: `<td class="postButtonCell"><button id="postButton" class="postButton" type="button" value="Post" accesskey="P" tabindex="3" title="{0}">{1}</Button></td>`
- `0x195a0`: `ActivityFeeds.SystemPostsFilter`

## pseudocode

```c

```

## disassembly

```asm
0x19460  ldarg.1
0x19461  ldstr    aDivId0Containe// "<div id='{0}_container' wallTabIndex='{"...
0x19466  ldarg.0
0x19467  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x1946c  ldarg.0
0x1946d  call     instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.ActivityFeedsControl::get_TabIndex()
0x19472  stloc.1
0x19473  ldloca.s 1
0x19475  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1947a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x1947f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x19484  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x19489  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x1948e  brtrue.s loc_19497
0x19490  ldsfld   string [mscorlib]System.String::Empty
0x19495  br.s     loc_1949C
0x19497  ldstr    aClassRtl// "class='rtl' "
0x1949c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object, object, object)
0x194a1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x194a6  stloc.0
0x194a7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x194ac  call     class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.YammerState::Read(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation)
0x194b1  callvirt instance bool [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Yammer.IYammerState::get_IsYammerConfiguredForOrg()
0x194b6  brtrue   loc_195F3
0x194bb  ldarg.1
0x194bc  ldstr    aDivClassRecord// "<div class=\"recordWall initialFiller\""...
0x194c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x194c6  ldarg.1
0x194c7  ldstr    aTableClassHead// "<table class=\"headerTable\" border=\"0"...
0x194cc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x194d1  ldarg.1
0x194d2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x194d7  ldstr    aTdClassPosttex// "<td class=\"postTextBoxCell\"><div clas"...
0x194dc  ldc.i4.2
0x194dd  newarr   [mscorlib]System.Object
0x194e2  dup
0x194e3  ldc.i4.0
0x194e4  ldloc.0
0x194e5  ldstr    aActivityfeedsP// "ActivityFeeds.PostTextBoxWatermarkText"
0x194ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x194ef  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x194f4  stelem.ref
0x194f5  dup
0x194f6  ldc.i4.1
0x194f7  ldloc.0
0x194f8  ldstr    aActivityfeedsP// "ActivityFeeds.PostTextBoxWatermarkText"
0x194fd  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19502  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19507  stelem.ref
0x19508  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1950d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19512  ldarg.1
0x19513  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19518  ldstr    aTdClassPostbut// "<td class=\"postButtonCell\"><button id"...
0x1951d  ldc.i4.2
0x1951e  newarr   [mscorlib]System.Object
0x19523  dup
0x19524  ldc.i4.0
0x19525  ldloc.0
0x19526  ldstr    aActivityfeedsP_0// "ActivityFeeds.PostButtonTitle"
0x1952b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19530  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x19535  stelem.ref
0x19536  dup
0x19537  ldc.i4.1
0x19538  ldloc.0
0x19539  ldstr    aActivityfeedsP_1// "ActivityFeeds.PostButtonText"
0x1953e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x19543  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19548  stelem.ref
0x19549  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1954e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x19553  ldarg.1
0x19554  ldstr    aTrTable// "</tr></table>"
0x19559  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1955e  ldarg.1
0x1955f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19564  ldstr    aDivClassWallfi// "<div class=\"wallFilter filters\" style"...
0x19569  ldc.i4.1
0x1956a  newarr   [mscorlib]System.Object
0x1956f  dup
0x19570  ldc.i4.0
0x19571  ldloc.0
0x19572  ldstr    aActivityfeedsA// "ActivityFeeds.AllFilter"
0x19577  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x1957c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x19581  stelem.ref
0x19582  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19587  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1958c  ldarg.1
0x1958d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x19592  ldstr    aDivClassFilter// "<div class=\"filter \"><a class=\"filte"...
0x19597  ldc.i4.1
0x19598  newarr   [mscorlib]System.Object
0x1959d  dup
0x1959e  ldc.i4.0
0x1959f  ldloc.0
0x195a0  ldstr    aActivityfeedsS// "ActivityFeeds.SystemPostsFilter"
0x195a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x195aa  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x195af  stelem.ref
0x195b0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x195b5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x195ba  ldarg.1
0x195bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x195c0  ldstr    aDivClassFilter// "<div class=\"filter \"><a class=\"filte"...
0x195c5  ldc.i4.1
0x195c6  newarr   [mscorlib]System.Object
0x195cb  dup
0x195cc  ldc.i4.0
0x195cd  ldloc.0
0x195ce  ldstr    aActivityfeedsU_0// "ActivityFeeds.UserPostsFilter"
0x195d3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x195d8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x195dd  stelem.ref
0x195de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x195e3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x195e8  ldarg.1
0x195e9  ldstr    aDivDivDiv// "</div></div></div>"
0x195ee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x195f3  ldarg.1
0x195f4  ldstr    aDiv_0// "</div>"
0x195f9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x195fe  ret
```
