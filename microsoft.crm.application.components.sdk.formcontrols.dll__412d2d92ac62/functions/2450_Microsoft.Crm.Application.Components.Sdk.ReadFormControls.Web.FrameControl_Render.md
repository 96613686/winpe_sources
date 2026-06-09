# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::Render

- ea: `0x2450`
- end: `0x27dc`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::Render`
- size: `908`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x1260`
- `0x1290`
- `0x2320`
- `0x2340`
- `0x2360`
- `0x2370`
- `0x2380`
- `0x23c0`
- `0x2420`
- `0x2450`
- `0x18d80`

## string_xrefs

- `0x2792`: `security`
- `0x2494`: `ms-crm-Custom-Read`

## pseudocode

```c

```

## disassembly

```asm
0x2450  ldarg.1
0x2451  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x2456  stloc.0
0x2457  ldloc.0
0x2458  ldstr    aIframeFramebor_0// "<iframe frameborder=0 "
0x245d  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2462  ldstr    aId// "id"
0x2467  ldarg.0
0x2468  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x246d  ldarg.1
0x246e  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2473  ldloc.0
0x2474  ldstr    aOnloadIfIsnull// "onload = 'if(!IsNull(Mscrm.InlineIFrame"...
0x2479  ldarg.0
0x247a  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x247f  ldstr    asc_3154E// "\")'"
0x2484  call     string [mscorlib]System.String::Concat(string, string, string)
0x2489  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x248e  ldarg.1
0x248f  ldstr    aClass// "class"
0x2494  ldstr    aMsCrmCustomRea// "ms-crm-Custom-Read"
0x2499  ldc.i4.0
0x249a  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x249f  ldsfld   string [mscorlib]System.String::Empty
0x24a4  stloc.1
0x24a5  ldarg.0
0x24a6  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Border()
0x24ab  brtrue.s loc_24B3
0x24ad  ldstr    aBorder0// "border:0;"
0x24b2  stloc.1
0x24b3  ldloc.1
0x24b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24b9  brtrue.s loc_24C7
0x24bb  ldstr    aStyle// "style"
0x24c0  ldloc.1
0x24c1  ldarg.1
0x24c2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x24c7  ldarg.1
0x24c8  ldstr    aTabindex// "tabindex"
0x24cd  ldarg.0
0x24ce  callvirt instance int32 Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_TabIndex()
0x24d3  stloc.2
0x24d4  ldloca.s 2
0x24d6  ldstr    aD// "D"
0x24db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x24e0  call     instance string [mscorlib]System.Int32::ToString(string, class [mscorlib]System.IFormatProvider)
0x24e5  ldc.i4.0
0x24e6  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x24eb  ldarg.0
0x24ec  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Url()
0x24f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x24f6  brtrue   loc_2718
0x24fb  ldarg.0
0x24fc  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Url()
0x2501  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2506  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x250b  stloc.3
0x250c  ldnull
0x250d  stloc.s  4
0x250f  ldloc.3
0x2510  ldc.i4.1
0x2511  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_AllowParamsNoEqual(bool)
0x2516  ldarg.0
0x2517  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_PassParameters()
0x251c  brfalse  loc_2618
0x2521  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2526  ldstr    aType0Typename1// "type={0}&typename={1}&id={2}"
0x252b  ldc.i4.3
0x252c  newarr   [mscorlib]System.Object
0x2531  dup
0x2532  ldc.i4.0
0x2533  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2538  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x253d  ldc.i4.2
0x253e  newarr   [mscorlib]System.Object
0x2543  dup
0x2544  ldc.i4.0
0x2545  ldstr    aEntity// "_entity"
0x254a  stelem.ref
0x254b  dup
0x254c  ldc.i4.1
0x254d  ldstr    aTypecode// "TypeCode"
0x2552  stelem.ref
0x2553  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2558  stelem.ref
0x2559  dup
0x255a  ldc.i4.1
0x255b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2560  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x2565  ldc.i4.2
0x2566  newarr   [mscorlib]System.Object
0x256b  dup
0x256c  ldc.i4.0
0x256d  ldstr    aEntity// "_entity"
0x2572  stelem.ref
0x2573  dup
0x2574  ldc.i4.1
0x2575  ldstr    aTypename// "TypeName"
0x257a  stelem.ref
0x257b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2580  stelem.ref
0x2581  dup
0x2582  ldc.i4.2
0x2583  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2588  ldstr    aGetdataData01// "{{{{:~getData(#data,'{0}','{1}')}}}}"
0x258d  ldc.i4.2
0x258e  newarr   [mscorlib]System.Object
0x2593  dup
0x2594  ldc.i4.0
0x2595  ldstr    aEntity// "_entity"
0x259a  stelem.ref
0x259b  dup
0x259c  ldc.i4.1
0x259d  ldstr    aId_0// "Id"
0x25a2  stelem.ref
0x25a3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25a8  stelem.ref
0x25a9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x25ae  stloc.s  4
0x25b0  ldloc.3
0x25b1  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25b6  ldstr    aOrgname// "orgname"
0x25bb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x25c0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x25c5  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x25ca  ldloc.3
0x25cb  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25d0  ldstr    aUserlcid// "userlcid"
0x25d5  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x25da  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x25df  stloc.2
0x25e0  ldloca.s 2
0x25e2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x25e7  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x25ec  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x25f1  ldloc.3
0x25f2  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x25f7  ldstr    aOrglcid// "orglcid"
0x25fc  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.Organization::get_CurrentSettings()
0x2601  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IOrganizationSettings::get_LanguageCode()
0x2606  stloc.2
0x2607  ldloca.s 2
0x2609  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x260e  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2613  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2618  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_IsAvailable()
0x261d  brfalse.s loc_267A
0x261f  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x2624  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x2629  call     class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> [Microsoft.Crm.Core]IdentityExtensions::PassiveAuthUrlParameters(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x262e  stloc.s  6
0x2630  ldloc.s  6
0x2632  brfalse.s loc_267A
0x2634  ldloc.s  6
0x2636  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x263b  stloc.s  7
0x263d  br.s     loc_2661
0x263f  ldloca.s 7
0x2641  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x2646  stloc.s  8
0x2648  ldloc.3
0x2649  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x264e  ldloca.s 8
0x2650  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2655  ldloca.s 8
0x2657  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x265c  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x2661  ldloca.s 7
0x2663  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x2668  brtrue.s loc_263F
0x266a  leave.s  loc_267A
0x266c  ldloca.s 7
0x266e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x2674  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2679  endfinally
0x267a  ldloc.3
0x267b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Fragment()
0x2680  stloc.s  5
0x2682  ldloc.3
0x2683  ldsfld   string [mscorlib]System.String::Empty
0x2688  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::set_Fragment(string)
0x268d  ldarg.1
0x268e  ldstr    aUrl_0// "url=\""
0x2693  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2698  ldarg.1
0x2699  ldloc.3
0x269a  callvirt instance string [mscorlib]System.Object::ToString()
0x269f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x26a4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26a9  ldloc.s  4
0x26ab  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26b0  brtrue.s loc_26D3
0x26b2  ldarg.1
0x26b3  ldloc.3
0x26b4  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2<string, string> [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Query()
0x26b9  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<string, string>::get_Count()
0x26be  brfalse.s loc_26C4
0x26c0  ldc.i4.s 0x26
0x26c2  br.s     loc_26C6
0x26c4  ldc.i4.s 0x3F
0x26c6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x26cb  ldarg.1
0x26cc  ldloc.s  4
0x26ce  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26d3  ldloc.s  5
0x26d5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x26da  brtrue.s loc_26F1
0x26dc  ldarg.1
0x26dd  ldc.i4.s 0x23
0x26df  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x26e4  ldarg.1
0x26e5  ldloc.s  5
0x26e7  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlAttributeEncode(string)
0x26ec  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x26f1  ldarg.1
0x26f2  ldc.i4.s 0x22
0x26f4  callvirt instance void [mscorlib]System.IO.TextWriter::Write(char)
0x26f9  ldstr    aSrc// "src"
0x26fe  ldstr    aStaticBlankHtm// "/_static/blank.htm"
0x2703  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2708  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x270d  callvirt instance string [mscorlib]System.Object::ToString()
0x2712  ldarg.1
0x2713  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x2718  ldarg.0
0x2719  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_IsWebResourceControl()
0x271e  brfalse.s loc_273B
0x2720  ldarg.1
0x2721  ldstr    aIswebresource// "isWebResource"
0x2726  ldarg.0
0x2727  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_IsWebResourceControl()
0x272c  stloc.s  9
0x272e  ldloca.s 9
0x2730  call     instance string [mscorlib]System.Boolean::ToString()
0x2735  ldc.i4.0
0x2736  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x273b  ldarg.0
0x273c  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Security()
0x2741  brfalse.s loc_2789
0x2743  ldarg.0
0x2744  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Url()
0x2749  ldstr    asc_3165E// "/"
0x274e  ldc.i4.5
0x274f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2754  brfalse.s loc_276A
0x2756  ldarg.0
0x2757  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Url()
0x275c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2761  call     class [System]System.Uri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetAbsoluteUrl(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2766  stloc.s  0xA
0x2768  br.s     loc_2779
0x276a  ldarg.0
0x276b  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Url()
0x2770  ldc.i4.0
0x2771  ldloca.s 0xA
0x2773  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x2778  pop
0x2779  ldloc.s  0xA
0x277b  call     bool Microsoft.Crm.Application.Components.Sdk.FormControls.Web.FrameControlHelper::ShouldSecurityBeDisabled(class [System]System.Uri frameUri)
0x2780  brfalse.s loc_2789
0x2782  ldarg.0
0x2783  ldc.i4.0
0x2784  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::set_Security(bool value)
0x2789  ldarg.0
0x278a  call     instance bool Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Security()
0x278f  brfalse.s loc_27B3
0x2791  ldarg.1
0x2792  ldstr    aSecurity// "security"
0x2797  ldstr    aRestricted// "restricted"
0x279c  ldc.i4.0
0x279d  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x27a2  ldarg.1
0x27a3  ldstr    aSandbox// "sandbox"
0x27a8  ldstr    asc_30804// ""
0x27ad  ldc.i4.0
0x27ae  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x27b3  ldstr    aScrolling// "scrolling"
0x27b8  ldarg.0
0x27b9  call     instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.FrameControl::get_Scrolling()
0x27be  ldarg.1
0x27bf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x27c4  ldloc.0
0x27c5  ldarg.0
0x27c6  callvirt instance string Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.CrmWebFormControlBase::get_Expandos()
0x27cb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27d0  ldloc.0
0x27d1  ldstr    aIframe_0// "></iframe>"
0x27d6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x27db  ret
```
