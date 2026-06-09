# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::Render

- ea: `0x21860`
- end: `0x21a2b`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::Render`
- size: `459`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x17930`
- `0x17a10`
- `0x21750`
- `0x21860`

## string_xrefs

- `0x21878`: `http://www.bing.com/maps/?where1=`
- `0x21883`: `MapsIntegration.LinkText`
- `0x218d8`: `<a tabIndex={3} class='ms-crm-gridurl' href='{0}' id=bingAddressLink target='_new' addressField='{1}'>{2}</a>`

## pseudocode

```c

```

## disassembly

```asm
0x21860  ldarg.0
0x21861  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::bingMapsHelper
0x21866  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.MapDisplayMode [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper::get_DisplayMode()
0x2186b  stloc.0
0x2186c  ldloc.0
0x2186d  ldc.i4.1
0x2186e  beq.s    loc_21878
0x21870  ldloc.0
0x21871  ldc.i4.2
0x21872  beq      loc_2193B
0x21877  ret
0x21878  ldstr    aHttpWwwBingCom// "http://www.bing.com/maps/?where1="
0x2187d  stloc.1
0x2187e  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x21883  ldstr    aMapsintegratio// "MapsIntegration.LinkText"
0x21888  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2188d  stloc.2
0x2188e  ldarg.0
0x2188f  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x21894  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x21899  brfalse.s loc_218D7
0x2189b  ldarg.1
0x2189c  ldstr    aDiv// "div"
0x218a1  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x218a6  ldstr    aId// "id"
0x218ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x218b0  ldstr    a0_1// "{0}"
0x218b5  ldc.i4.1
0x218b6  newarr   [mscorlib]System.Object
0x218bb  dup
0x218bc  ldc.i4.0
0x218bd  ldarg.0
0x218be  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x218c3  stelem.ref
0x218c4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x218c9  ldarg.1
0x218ca  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x218cf  ldarg.1
0x218d0  ldc.i4.s 0x3E
0x218d2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x218d7  ldarg.1
0x218d8  ldstr    aATabindex3Clas// "<a tabIndex={3} class='ms-crm-gridurl' "...
0x218dd  ldc.i4.4
0x218de  newarr   [mscorlib]System.Object
0x218e3  dup
0x218e4  ldc.i4.0
0x218e5  ldloc.1
0x218e6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x218eb  stelem.ref
0x218ec  dup
0x218ed  ldc.i4.1
0x218ee  ldarg.0
0x218ef  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::get_AddressField()
0x218f4  dup
0x218f5  brtrue.s loc_218FD
0x218f7  pop
0x218f8  ldsfld   string [mscorlib]System.String::Empty
0x218fd  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x21902  stelem.ref
0x21903  dup
0x21904  ldc.i4.2
0x21905  ldloc.2
0x21906  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x2190b  stelem.ref
0x2190c  dup
0x2190d  ldc.i4.3
0x2190e  ldarg.0
0x2190f  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x21914  box      [mscorlib]System.Int32
0x21919  stelem.ref
0x2191a  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object[])
0x2191f  ldarg.0
0x21920  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x21925  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x2192a  brfalse  loc_21A2A
0x2192f  ldarg.1
0x21930  ldstr    aDiv_0// "</div>"
0x21935  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2193a  ret
0x2193b  ldarg.1
0x2193c  ldstr    aDivTabindex3Id// "<div tabIndex={3} id='{0}' bingMapsApiK"...
0x21941  ldc.i4.5
0x21942  newarr   [mscorlib]System.Object
0x21947  dup
0x21948  ldc.i4.0
0x21949  ldarg.0
0x2194a  callvirt instance string [System.Web]System.Web.UI.Control::get_ClientID()
0x2194f  ldstr    aContainer// "_container"
0x21954  call     string [mscorlib]System.String::Concat(string, string)
0x21959  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x2195e  stelem.ref
0x2195f  dup
0x21960  ldc.i4.1
0x21961  ldarg.0
0x21962  ldfld    class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::bingMapsHelper
0x21967  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.BingMapsIntegrationHelper::get_ApiKey()
0x2196c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x21971  stelem.ref
0x21972  dup
0x21973  ldc.i4.2
0x21974  ldarg.0
0x21975  call     instance string Microsoft.Crm.Application.Components.Sdk.FormControls.Web.MapsControl::get_AddressField()
0x2197a  dup
0x2197b  brtrue.s loc_21983
0x2197d  pop
0x2197e  ldsfld   string [mscorlib]System.String::Empty
0x21983  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x21988  stelem.ref
0x21989  dup
0x2198a  ldc.i4.3
0x2198b  ldarg.0
0x2198c  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x21991  box      [mscorlib]System.Int32
0x21996  stelem.ref
0x21997  dup
0x21998  ldc.i4.4
0x21999  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2199e  ldstr    aRibbonFormedit// "Ribbon.Formeditor.Button.BingMap.LabelT"...
0x219a3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x219a8  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x219ad  stelem.ref
0x219ae  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string, object[])
0x219b3  ldarg.0
0x219b4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x219b9  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x219be  brfalse.s loc_219FC
0x219c0  ldarg.1
0x219c1  ldstr    aDiv// "div"
0x219c6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteBeginTag(string)
0x219cb  ldstr    aId// "id"
0x219d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x219d5  ldstr    a0_1// "{0}"
0x219da  ldc.i4.1
0x219db  newarr   [mscorlib]System.Object
0x219e0  dup
0x219e1  ldc.i4.0
0x219e2  ldarg.0
0x219e3  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x219e8  stelem.ref
0x219e9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x219ee  ldarg.1
0x219ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x219f4  ldarg.1
0x219f5  ldc.i4.s 0x3E
0x219f7  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x219fc  ldarg.1
0x219fd  ldstr    aDivDiv_0// "<div></div>"
0x21a02  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x21a07  ldarg.0
0x21a08  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended Microsoft.Crm.Application.Components.Sdk.FormControls.Web.CrmWebFormControlBase::get_CurrentForm()
0x21a0d  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.CustomizableFormExtended::get_IsTurboForm()
0x21a12  brfalse.s loc_21A1F
0x21a14  ldarg.1
0x21a15  ldstr    aDiv// "div"
0x21a1a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x21a1f  ldarg.1
0x21a20  ldstr    aDiv// "div"
0x21a25  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteEndTag(string)
0x21a2a  ret
```
