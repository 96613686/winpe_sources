# Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::Render

- ea: `0x99f60`
- end: `0x9a52c`
- name: `Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::Render`
- size: `1484`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x472c0`
- `0x99910`
- `0x99920`
- `0x99930`
- `0x99940`
- `0x99950`
- `0x99960`
- `0x99a70`
- `0x99f60`

## string_xrefs

- `0x9a212`: `Form_Libraries_And_Event_Handler_Control_ControlTypeCombo_Caption`
- `0x9a256`: `'><label for='controlTypeCombo'>`
- `0x9a27e`: `controlTypeCombo`
- `0x9a28e`: `Mscrm.FormLibraryAndEventHandlerUtils.onChangeControlCombo();`
- `0x9a2d9`: `<tr id="entityComboRow"><td style='`
- `0x9a304`: `'><label for='entityCombo'>`
- `0x9a32c`: `entityCombo`
- `0x9a33c`: `Mscrm.FormLibraryAndEventHandlerUtils.onChangeEntityCombo();`
- `0x9a37d`: `<tr id="columnComboRow"><td style='`
- `0x9a3a9`: `'><label for='columnCombo'>`
- `0x9a3d2`: `columnCombo`
- `0x9a3e2`: `Mscrm.FormLibraryAndEventHandlerUtils.onChangeColumnCombo();`
- `0x9a409`: `Form_Libraries_And_Event_Handler_Control_EventType_Combo`
- `0x9a44d`: `'><label for='eventTypeCombo'>`
- `0x9a475`: `eventTypeCombo`
- `0x9a485`: `Mscrm.FormLibraryAndEventHandlerUtils.onChangeEventCombo();`

## pseudocode

```c

```

## disassembly

```asm
0x99f60  ldarg.1
0x99f61  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x99f66  stloc.0
0x99f67  ldloc.0
0x99f68  ldstr    aDivIdJscriptli// "<div id='jscriptLibraryControl' style='"...
0x99f6d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99f72  ldloc.0
0x99f73  ldstr    aTableCellpaddi_0// "<table cellpadding='0' cellspacing='0' "...
0x99f78  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99f7d  ldloc.0
0x99f7e  ldstr    aTrTd// "<tr><td>"
0x99f83  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99f88  ldloc.0
0x99f89  ldstr    aTableOnclickMs// "<table onclick='Mscrm.FormLibraryAndEve"...
0x99f8e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99f93  ldloc.0
0x99f94  ldstr    aATitleSelecten// "<a title='' selectEnable='true' onclick"...
0x99f99  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99f9e  ldarg.0
0x99f9f  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_collapseFormLibrarySection
0x99fa4  brfalse.s loc_99FE5
0x99fa6  ldloc.0
0x99fa7  ldstr    aImgIdLibraryse// "<img id='librarySectionImage' src='/_im"...
0x99fac  ldarg.0
0x99fad  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_isRightToLeft
0x99fb2  brtrue.s loc_99FBB
0x99fb4  ldstr    aStyleCursorPoi_0// " style='cursor:pointer;'"
0x99fb9  br.s     loc_99FD4
0x99fbb  ldstr    aStyleCursorPoi_1// " style='cursor:pointer;"
0x99fc0  ldstr    aH// "h"
0x99fc5  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x99fca  ldstr    asc_122D78// "'"
0x99fcf  call     string [mscorlib]System.String::Concat(string, string, string)
0x99fd4  ldstr    asc_111CB6// ">"
0x99fd9  call     string [mscorlib]System.String::Concat(string, string, string)
0x99fde  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x99fe3  br.s     loc_9A022
0x99fe5  ldloc.0
0x99fe6  ldstr    aImgIdLibraryse_0// "<img id='librarySectionImage' src='/_im"...
0x99feb  ldarg.0
0x99fec  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_isRightToLeft
0x99ff1  brtrue.s loc_99FFA
0x99ff3  ldstr    aStyleCursorPoi_0// " style='cursor:pointer;'"
0x99ff8  br.s     loc_9A013
0x99ffa  ldstr    aStyleCursorPoi_1// " style='cursor:pointer;"
0x99fff  ldstr    aH// "h"
0x9a004  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x9a009  ldstr    asc_122D78// "'"
0x9a00e  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a013  ldstr    asc_111CB6// ">"
0x9a018  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a01d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a022  ldloc.0
0x9a023  ldstr    aATdTdB// "</a><td/><td><b>"
0x9a028  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a02d  ldarg.0
0x9a02e  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a033  ldstr    aFormLibrariesA_7// "Form_Libraries_And_Event_Handler_Contro"...
0x9a038  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a03d  ldloc.0
0x9a03e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x9a043  ldloc.0
0x9a044  ldstr    aBTdTrTable// "</b></td></tr></table>"
0x9a049  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a04e  ldloc.0
0x9a04f  ldstr    aTdTr// "</td></tr>"
0x9a054  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a059  ldloc.0
0x9a05a  ldstr    aTrTdHrTdTr// "<tr><td><hr></td></tr>"
0x9a05f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a064  ldloc.0
0x9a065  ldstr    aTrTd// "<tr><td>"
0x9a06a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a06f  ldarg.0
0x9a070  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_collapseFormLibrarySection
0x9a075  brfalse.s loc_9A084
0x9a077  ldloc.0
0x9a078  ldstr    aTableIdLibrary// "<table id='librarySection' width='100%'"...
0x9a07d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a082  br.s     loc_9A08F
0x9a084  ldloc.0
0x9a085  ldstr    aTableIdLibrary_0// "<table id='librarySection' width='100%'"...
0x9a08a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a08f  ldloc.0
0x9a090  ldstr    aTrTdIdFormlibr// "<tr><td id='formLibrariesDescriptionLab"...
0x9a095  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a09a  ldarg.0
0x9a09b  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a0a0  ldstr    aFormLibrariesA_8// "Form_Libraries_And_Event_Handler_Contro"...
0x9a0a5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a0aa  ldloc.0
0x9a0ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x9a0b0  ldloc.0
0x9a0b1  ldstr    aTdTr// "</td></tr>"
0x9a0b6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0bb  ldloc.0
0x9a0bc  ldstr    aTrTd// "<tr><td>"
0x9a0c1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0c6  ldarg.0
0x9a0c7  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_FormLibraryMenuBar()
0x9a0cc  ldarg.1
0x9a0cd  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x9a0d2  ldloc.0
0x9a0d3  ldstr    aDivIdLibrarygr// "<div id='libraryGrid' style='height:115"...
0x9a0d8  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0dd  ldloc.0
0x9a0de  ldstr    aTable// "</table>"
0x9a0e3  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0e8  ldloc.0
0x9a0e9  ldstr    aTdTr// "</td></tr>"
0x9a0ee  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0f3  ldloc.0
0x9a0f4  ldstr    aTrTdBrTdTr// "<tr><td><br/></td></tr>"
0x9a0f9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a0fe  ldloc.0
0x9a0ff  ldstr    aTrTd// "<tr><td>"
0x9a104  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a109  ldloc.0
0x9a10a  ldstr    aTableOnclickMs_0// "<table onclick='Mscrm.FormLibraryAndEve"...
0x9a10f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a114  ldloc.0
0x9a115  ldstr    aATitleSelecten// "<a title='' selectEnable='true' onclick"...
0x9a11a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a11f  ldloc.0
0x9a120  ldstr    aImgIdHandlerse// "<img id='handlerSectionImage' src='/_im"...
0x9a125  ldarg.0
0x9a126  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_isRightToLeft
0x9a12b  brtrue.s loc_9A134
0x9a12d  ldstr    aStyleCursorPoi_0// " style='cursor:pointer;'"
0x9a132  br.s     loc_9A14D
0x9a134  ldstr    aStyleCursorPoi_1// " style='cursor:pointer;"
0x9a139  ldstr    aH// "h"
0x9a13e  call     string Microsoft.Crm.Application.Utility.WebUtility::FlipImage(string direction)
0x9a143  ldstr    asc_122D78// "'"
0x9a148  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a14d  ldstr    asc_111CB6// ">"
0x9a152  call     string [mscorlib]System.String::Concat(string, string, string)
0x9a157  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a15c  ldloc.0
0x9a15d  ldstr    aATdTdB// "</a><td/><td><b>"
0x9a162  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a167  ldarg.0
0x9a168  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a16d  ldstr    aFormLibrariesA_9// "Form_Libraries_And_Event_Handler_Contro"...
0x9a172  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a177  ldloc.0
0x9a178  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x9a17d  ldloc.0
0x9a17e  ldstr    aBTdTrTable// "</b></td></tr></table>"
0x9a183  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a188  ldloc.0
0x9a189  ldstr    aTdTr// "</td></tr>"
0x9a18e  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a193  ldloc.0
0x9a194  ldstr    aTrTdHrTdTr_0// "<tr><td ><hr></td></tr>"
0x9a199  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a19e  ldloc.0
0x9a19f  ldstr    aTrTd_2// "<tr><td >"
0x9a1a4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1a9  ldloc.0
0x9a1aa  ldstr    aDivIdHandlerse// "<div id='handlerSection'>"
0x9a1af  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1b4  ldloc.0
0x9a1b5  ldstr    aTableWidth100S// "<table width='100%' style='table-layout"...
0x9a1ba  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1bf  ldloc.0
0x9a1c0  ldstr    aTrTdIdFormeven// "<tr><td id='formEventHandlerDescription"...
0x9a1c5  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1ca  ldarg.0
0x9a1cb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a1d0  ldstr    aFormLibrariesA_10// "Form_Libraries_And_Event_Handler_Contro"...
0x9a1d5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a1da  ldloc.0
0x9a1db  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string, class [mscorlib]System.IO.TextWriter)
0x9a1e0  ldloc.0
0x9a1e1  ldstr    aTdTr// "</td></tr>"
0x9a1e6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1eb  ldloc.0
0x9a1ec  ldstr    aTrTdBrTdTr_0// "<tr><td ><br/></td></tr>"
0x9a1f1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a1f6  ldloc.0
0x9a1f7  ldstr    aTable// "</table>"
0x9a1fc  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a201  ldloc.0
0x9a202  ldstr    aTableCellpaddi_1// "<table cellpadding='1' width='60%' styl"...
0x9a207  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a20c  ldarg.0
0x9a20d  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a212  ldstr    aFormLibrariesA_11// "Form_Libraries_And_Event_Handler_Contro"...
0x9a217  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a21c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x9a221  stloc.1
0x9a222  ldloc.0
0x9a223  ldc.i4.5
0x9a224  newarr   [mscorlib]System.String
0x9a229  dup
0x9a22a  ldc.i4.0
0x9a22b  ldstr    aTrTdStyle_0// "<tr><td style='"
0x9a230  stelem.ref
0x9a231  dup
0x9a232  ldc.i4.1
0x9a233  ldarg.0
0x9a234  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_isRightToLeft
0x9a239  brtrue.s loc_9A242
0x9a23b  ldstr    aPaddingRight10// "padding-right:10px"
0x9a240  br.s     loc_9A247
0x9a242  ldstr    aPaddingLeft10p// "padding-left:10px"
0x9a247  stelem.ref
0x9a248  dup
0x9a249  ldc.i4.2
0x9a24a  ldstr    aTextOverflowEl// ";text-overflow:ellipsis;overflow:hidden"...
0x9a24f  stelem.ref
0x9a250  dup
0x9a251  ldc.i4.3
0x9a252  ldloc.1
0x9a253  stelem.ref
0x9a254  dup
0x9a255  ldc.i4.4
0x9a256  ldstr    aLabelForContro// "'><label for='controlTypeCombo'>"
0x9a25b  stelem.ref
0x9a25c  call     string [mscorlib]System.String::Concat(string[])
0x9a261  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a266  ldloc.0
0x9a267  ldloc.1
0x9a268  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a26d  ldloc.0
0x9a26e  ldstr    aLabelTdTd// "</label></td><td>"
0x9a273  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a278  ldarg.0
0x9a279  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_ControlTypeCombo()
0x9a27e  ldstr    aControltypecom// "controlTypeCombo"
0x9a283  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9a288  ldarg.0
0x9a289  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_ControlTypeCombo()
0x9a28e  ldstr    aMscrmFormlibra_10// "Mscrm.FormLibraryAndEventHandlerUtils.o"...
0x9a293  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string)
0x9a298  ldarg.0
0x9a299  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_ControlTypeCombo()
0x9a29e  ldarg.1
0x9a29f  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x9a2a4  ldloc.0
0x9a2a5  ldstr    aTdTr// "</td></tr>"
0x9a2aa  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a2af  ldarg.0
0x9a2b0  call     instance bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_IsJsEditableGridJsEventsEnabled()
0x9a2b5  brfalse  loc_9A403
0x9a2ba  ldarg.0
0x9a2bb  ldfld    class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_resourceManager
0x9a2c0  ldstr    aFormLibrariesA_12// "Form_Libraries_And_Event_Handler_Contro"...
0x9a2c5  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x9a2ca  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x9a2cf  stloc.3
0x9a2d0  ldloc.0
0x9a2d1  ldc.i4.5
0x9a2d2  newarr   [mscorlib]System.String
0x9a2d7  dup
0x9a2d8  ldc.i4.0
0x9a2d9  ldstr    aTrIdEntitycomb// "<tr id=\"entityComboRow\"><td style='"
0x9a2de  stelem.ref
0x9a2df  dup
0x9a2e0  ldc.i4.1
0x9a2e1  ldarg.0
0x9a2e2  ldfld    bool Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::_isRightToLeft
0x9a2e7  brtrue.s loc_9A2F0
0x9a2e9  ldstr    aPaddingRight10// "padding-right:10px"
0x9a2ee  br.s     loc_9A2F5
0x9a2f0  ldstr    aPaddingLeft10p// "padding-left:10px"
0x9a2f5  stelem.ref
0x9a2f6  dup
0x9a2f7  ldc.i4.2
0x9a2f8  ldstr    aTextOverflowEl// ";text-overflow:ellipsis;overflow:hidden"...
0x9a2fd  stelem.ref
0x9a2fe  dup
0x9a2ff  ldc.i4.3
0x9a300  ldloc.3
0x9a301  stelem.ref
0x9a302  dup
0x9a303  ldc.i4.4
0x9a304  ldstr    aLabelForEntity// "'><label for='entityCombo'>"
0x9a309  stelem.ref
0x9a30a  call     string [mscorlib]System.String::Concat(string[])
0x9a30f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a314  ldloc.0
0x9a315  ldloc.3
0x9a316  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a31b  ldloc.0
0x9a31c  ldstr    aLabelTdTd// "</label></td><td>"
0x9a321  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x9a326  ldarg.0
0x9a327  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EntityCombo()
0x9a32c  ldstr    aEntitycombo// "entityCombo"
0x9a331  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x9a336  ldarg.0
0x9a337  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EntityCombo()
0x9a33c  ldstr    aMscrmFormlibra_11// "Mscrm.FormLibraryAndEventHandlerUtils.o"...
0x9a341  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select::set_OnChange(string)
0x9a346  ldarg.0
0x9a347  call     instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Application.Components.UI.Select Microsoft.Crm.Application.Controls.FormLibraryAndEventHandlerControl::get_EntityCombo()
0x9a34c  ldarg.1
0x9a34d  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
  ... truncated ...
```
