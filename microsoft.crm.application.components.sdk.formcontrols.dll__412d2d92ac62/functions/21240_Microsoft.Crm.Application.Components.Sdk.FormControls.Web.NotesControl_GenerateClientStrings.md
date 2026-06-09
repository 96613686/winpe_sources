# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::GenerateClientStrings

- ea: `0x21240`
- end: `0x2156a`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.NotesControl::GenerateClientStrings`
- size: `810`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x20f50`

## string_xrefs

- `0x21324`: `CreateNoteTextWatermark`
- `0x213ea`: `PendingCreate`

## pseudocode

```c

```

## disassembly

```asm
0x21240  ldstr    asc_37E48// "{"
0x21245  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x2124a  stloc.0
0x2124b  ldloc.0
0x2124c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21251  ldstr    a01_5// "\"{0}\":{1}"
0x21256  ldc.i4.2
0x21257  newarr   [mscorlib]System.Object
0x2125c  dup
0x2125d  ldc.i4.0
0x2125e  ldstr    aYou// "You"
0x21263  stelem.ref
0x21264  dup
0x21265  ldc.i4.1
0x21266  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2126b  ldstr    aNotesv2You// "NotesV2.You"
0x21270  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21275  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x2127a  stelem.ref
0x2127b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21280  pop
0x21281  ldloc.0
0x21282  ldstr    asc_36702// ","
0x21287  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2128c  pop
0x2128d  ldloc.0
0x2128e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21293  ldstr    a01_5// "\"{0}\":{1}"
0x21298  ldc.i4.2
0x21299  newarr   [mscorlib]System.Object
0x2129e  dup
0x2129f  ldc.i4.0
0x212a0  ldstr    aGenericerrorme// "GenericErrorMessage"
0x212a5  stelem.ref
0x212a6  dup
0x212a7  ldc.i4.1
0x212a8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x212ad  ldstr    aNotesv2Generic// "NotesV2.GenericErrorMessage"
0x212b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x212b7  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x212bc  stelem.ref
0x212bd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x212c2  pop
0x212c3  ldloc.0
0x212c4  ldstr    asc_36702// ","
0x212c9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x212ce  pop
0x212cf  ldloc.0
0x212d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x212d5  ldstr    a01_5// "\"{0}\":{1}"
0x212da  ldc.i4.2
0x212db  newarr   [mscorlib]System.Object
0x212e0  dup
0x212e1  ldc.i4.0
0x212e2  ldstr    aJustnow// "JustNow"
0x212e7  stelem.ref
0x212e8  dup
0x212e9  ldc.i4.1
0x212ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x212ef  ldstr    aNotesv2Justnow// "NotesV2.JustNow"
0x212f4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x212f9  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x212fe  stelem.ref
0x212ff  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21304  pop
0x21305  ldloc.0
0x21306  ldstr    asc_36702// ","
0x2130b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21310  pop
0x21311  ldloc.0
0x21312  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21317  ldstr    a01_5// "\"{0}\":{1}"
0x2131c  ldc.i4.2
0x2131d  newarr   [mscorlib]System.Object
0x21322  dup
0x21323  ldc.i4.0
0x21324  ldstr    aCreatenotetext// "CreateNoteTextWatermark"
0x21329  stelem.ref
0x2132a  dup
0x2132b  ldc.i4.1
0x2132c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21331  ldstr    aNotesv2Newnote// "NotesV2.NewNoteHintText"
0x21336  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2133b  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x21340  stelem.ref
0x21341  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21346  pop
0x21347  ldloc.0
0x21348  ldstr    asc_36702// ","
0x2134d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21352  pop
0x21353  ldloc.0
0x21354  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21359  ldstr    a01_5// "\"{0}\":{1}"
0x2135e  ldc.i4.2
0x2135f  newarr   [mscorlib]System.Object
0x21364  dup
0x21365  ldc.i4.0
0x21366  ldstr    aTextwatermark// "TextWatermark"
0x2136b  stelem.ref
0x2136c  dup
0x2136d  ldc.i4.1
0x2136e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21373  ldstr    aNotesv2Descrip// "NotesV2.DescriptionHintText"
0x21378  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2137d  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x21382  stelem.ref
0x21383  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21388  pop
0x21389  ldloc.0
0x2138a  ldstr    asc_36702// ","
0x2138f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21394  pop
0x21395  ldloc.0
0x21396  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2139b  ldstr    a01_5// "\"{0}\":{1}"
0x213a0  ldc.i4.2
0x213a1  newarr   [mscorlib]System.Object
0x213a6  dup
0x213a7  ldc.i4.0
0x213a8  ldstr    aTitlewatermark// "TitleWatermark"
0x213ad  stelem.ref
0x213ae  dup
0x213af  ldc.i4.1
0x213b0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x213b5  ldstr    aNotesv2Titlehi// "NotesV2.TitleHintText"
0x213ba  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x213bf  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x213c4  stelem.ref
0x213c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x213ca  pop
0x213cb  ldloc.0
0x213cc  ldstr    asc_36702// ","
0x213d1  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x213d6  pop
0x213d7  ldloc.0
0x213d8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x213dd  ldstr    a01_5// "\"{0}\":{1}"
0x213e2  ldc.i4.2
0x213e3  newarr   [mscorlib]System.Object
0x213e8  dup
0x213e9  ldc.i4.0
0x213ea  ldstr    aPendingcreate// "PendingCreate"
0x213ef  stelem.ref
0x213f0  dup
0x213f1  ldc.i4.1
0x213f2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x213f7  ldstr    aNotesv2Noparen// "NotesV2.NoParentRecord"
0x213fc  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21401  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x21406  stelem.ref
0x21407  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x2140c  pop
0x2140d  ldloc.0
0x2140e  ldstr    asc_36702// ","
0x21413  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21418  pop
0x21419  ldloc.0
0x2141a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2141f  ldstr    a01_5// "\"{0}\":{1}"
0x21424  ldc.i4.2
0x21425  newarr   [mscorlib]System.Object
0x2142a  dup
0x2142b  ldc.i4.0
0x2142c  ldstr    aNonotesavailab// "NoNotesAvailable"
0x21431  stelem.ref
0x21432  dup
0x21433  ldc.i4.1
0x21434  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21439  ldstr    aNotesv2Nonotes// "NotesV2.NoNotesAvailable"
0x2143e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21443  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x21448  stelem.ref
0x21449  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x2144e  pop
0x2144f  ldloc.0
0x21450  ldstr    asc_36702// ","
0x21455  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2145a  pop
0x2145b  ldloc.0
0x2145c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21461  ldstr    a01_5// "\"{0}\":{1}"
0x21466  ldc.i4.2
0x21467  newarr   [mscorlib]System.Object
0x2146c  dup
0x2146d  ldc.i4.0
0x2146e  ldstr    aToday// "Today"
0x21473  stelem.ref
0x21474  dup
0x21475  ldc.i4.1
0x21476  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2147b  ldstr    aNotesv2Today// "NotesV2.Today"
0x21480  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21485  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x2148a  stelem.ref
0x2148b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21490  pop
0x21491  ldloc.0
0x21492  ldstr    asc_36702// ","
0x21497  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2149c  pop
0x2149d  ldloc.0
0x2149e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x214a3  ldstr    a01_5// "\"{0}\":{1}"
0x214a8  ldc.i4.2
0x214a9  newarr   [mscorlib]System.Object
0x214ae  dup
0x214af  ldc.i4.0
0x214b0  ldstr    aYesterday// "Yesterday"
0x214b5  stelem.ref
0x214b6  dup
0x214b7  ldc.i4.1
0x214b8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x214bd  ldstr    aNotesv2Yesterd// "NotesV2.Yesterday"
0x214c2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x214c7  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x214cc  stelem.ref
0x214cd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x214d2  pop
0x214d3  ldloc.0
0x214d4  ldstr    asc_36702// ","
0x214d9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x214de  pop
0x214df  ldloc.0
0x214e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x214e5  ldstr    a01_5// "\"{0}\":{1}"
0x214ea  ldc.i4.2
0x214eb  newarr   [mscorlib]System.Object
0x214f0  dup
0x214f1  ldc.i4.0
0x214f2  ldstr    aNoparenttoshow// "NoParentToShow"
0x214f7  stelem.ref
0x214f8  dup
0x214f9  ldc.i4.1
0x214fa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x214ff  ldstr    aNotesv2Noparen_0// "NotesV2.NoParentToShow"
0x21504  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x21509  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x2150e  stelem.ref
0x2150f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21514  pop
0x21515  ldloc.0
0x21516  ldstr    asc_36702// ","
0x2151b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21520  pop
0x21521  ldloc.0
0x21522  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x21527  ldstr    a01_5// "\"{0}\":{1}"
0x2152c  ldc.i4.2
0x2152d  newarr   [mscorlib]System.Object
0x21532  dup
0x21533  ldc.i4.0
0x21534  ldstr    aNonotestoshow// "NoNotesToShow"
0x21539  stelem.ref
0x2153a  dup
0x2153b  ldc.i4.1
0x2153c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21541  ldstr    aNotesv2Nonotes_0// "NotesV2.NoNotesToShow"
0x21546  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2154b  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.JsonConverter::GetJsonString(object)
0x21550  stelem.ref
0x21551  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x21556  pop
0x21557  ldloc.0
0x21558  ldstr    asc_37E64// "}"
0x2155d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x21562  pop
0x21563  ldloc.0
0x21564  callvirt instance string [mscorlib]System.Object::ToString()
0x21569  ret
```
