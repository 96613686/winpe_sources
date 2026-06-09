# Microsoft.Crm.Application.Components.UI.Lookup::RenderButton

- ea: `0x1fdf0`
- end: `0x1ffb2`
- name: `Microsoft.Crm.Application.Components.UI.Lookup::RenderButton`
- size: `450`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1fa80`

## callees

- `0x142c0`
- `0x1a3b0`
- `0x1a400`
- `0x1f300`
- `0x1f390`
- `0x1fdf0`
- `0x23c20`
- `0x24210`
- `0x24280`

## pseudocode

```c

```

## disassembly

```asm
0x1fdf0  ldarg.0
0x1fdf1  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1fdf6  brtrue.s loc_1FE6F
0x1fdf8  ldarg.1
0x1fdf9  ldstr    aTdStyleWidth21// "<td style=\"width: 21px\" CLASS=\"Looku"...
0x1fdfe  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fe03  ldarg.0
0x1fe04  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControl::get_ReadOnly()
0x1fe09  brtrue.s loc_1FE13
0x1fe0b  ldarg.0
0x1fe0c  callvirt instance bool Microsoft.Crm.Application.Components.UI.CrmUIControlBase::get_Disabled()
0x1fe11  brfalse.s loc_1FE41
0x1fe13  ldc.i4.1
0x1fe14  stloc.1
0x1fe15  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1fe1a  ldc.i4.1
0x1fe1b  newarr   [mscorlib]System.Char
0x1fe20  dup
0x1fe21  ldc.i4.0
0x1fe22  ldc.i4.s 0x2F
0x1fe24  stelem.i2
0x1fe25  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1fe2a  ldstr    aImgsBtnDisLook// "/_imgs/btn_dis_lookup.png"
0x1fe2f  call     string [mscorlib]System.String::Concat(string, string)
0x1fe34  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fe39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fe3e  stloc.0
0x1fe3f  br.s     loc_1FEA6
0x1fe41  ldc.i4.0
0x1fe42  stloc.1
0x1fe43  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1fe48  ldc.i4.1
0x1fe49  newarr   [mscorlib]System.Char
0x1fe4e  dup
0x1fe4f  ldc.i4.0
0x1fe50  ldc.i4.s 0x2F
0x1fe52  stelem.i2
0x1fe53  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1fe58  ldstr    aImgsBtnOffLook// "/_imgs/btn_off_lookup.png"
0x1fe5d  call     string [mscorlib]System.String::Concat(string, string)
0x1fe62  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fe67  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fe6c  stloc.0
0x1fe6d  br.s     loc_1FEA6
0x1fe6f  ldarg.1
0x1fe70  ldstr    aTdStyleWidth0p// "<td style=\"width:0px\">"
0x1fe75  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1fe7a  ldc.i4.1
0x1fe7b  stloc.1
0x1fe7c  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x1fe81  ldc.i4.1
0x1fe82  newarr   [mscorlib]System.Char
0x1fe87  dup
0x1fe88  ldc.i4.0
0x1fe89  ldc.i4.s 0x2F
0x1fe8b  stelem.i2
0x1fe8c  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x1fe91  ldstr    aImgsImagestrip// "/_imgs/imagestrips/transparent_spacer.g"...
0x1fe96  call     string [mscorlib]System.String::Concat(string, string)
0x1fe9b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fea0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fea5  stloc.0
0x1fea6  ldloc.0
0x1fea7  newobj   instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri source)
0x1feac  stloc.2
0x1fead  ldloc.2
0x1feae  ldarg.0
0x1feaf  callvirt instance string [System.Web]System.Web.UI.Control::get_ID()
0x1feb4  callvirt instance void [System.Web]System.Web.UI.Control::set_ID(string)
0x1feb9  ldloc.2
0x1feba  ldstr    aAlt// "alt"
0x1febf  ldsfld   string [mscorlib]System.String::Empty
0x1fec4  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1fec9  ldloc.1
0x1feca  brfalse.s loc_1FEEC
0x1fecc  ldloc.2
0x1fecd  ldstr    aStyle_0// "style"
0x1fed2  ldstr    aCursorDefault_0// "cursor:default;"
0x1fed7  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1fedc  ldloc.2
0x1fedd  ldstr    aLookupdisabled// "lookupdisabled"
0x1fee2  ldstr    aTrue// "true"
0x1fee7  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1feec  ldarg.0
0x1feed  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_LookupImageClass()
0x1fef2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1fef7  brtrue.s loc_1FF07
0x1fef9  ldloc.2
0x1fefa  ldarg.0
0x1fefb  call     instance string Microsoft.Crm.Application.Components.UI.Lookup::get_LookupImageClass()
0x1ff00  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1ff05  br.s     loc_1FF12
0x1ff07  ldloc.2
0x1ff08  ldstr    aMsCrmLookup_0// "ms-crm-Lookup"
0x1ff0d  callvirt instance void Microsoft.Crm.Application.Components.UI.ImageStripImage::set_CssClass(string value)
0x1ff12  ldarg.0
0x1ff13  ldfld    string Microsoft.Crm.Application.Components.UI.Lookup::_buttonFunction
0x1ff18  brfalse.s loc_1FF33
0x1ff1a  ldarg.0
0x1ff1b  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1ff20  brtrue.s loc_1FF33
0x1ff22  ldloc.2
0x1ff23  ldstr    aOnclick_0// "onclick"
0x1ff28  ldarg.0
0x1ff29  ldfld    string Microsoft.Crm.Application.Components.UI.Lookup::_buttonFunction
0x1ff2e  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1ff33  ldarg.0
0x1ff34  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.Lookup::_expandos
0x1ff39  brfalse.s loc_1FF7F
0x1ff3b  ldarg.0
0x1ff3c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Application.Components.UI.Lookup::_expandos
0x1ff41  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x1ff46  stloc.3
0x1ff47  br.s     loc_1FF66
0x1ff49  ldloca.s 3
0x1ff4b  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x1ff50  stloc.s  4
0x1ff52  ldloc.2
0x1ff53  ldloca.s 4
0x1ff55  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x1ff5a  ldloca.s 4
0x1ff5c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x1ff61  callvirt instance void Microsoft.Crm.Application.Components.UI.CrmUIControl::AddExpando(string name, string value)
0x1ff66  ldloca.s 3
0x1ff68  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x1ff6d  brtrue.s loc_1FF49
0x1ff6f  leave.s  loc_1FF7F
0x1ff71  ldloca.s 3
0x1ff73  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x1ff79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff7e  endfinally
0x1ff7f  ldloc.2
0x1ff80  ldarg.1
0x1ff81  callvirt instance void [System.Web]System.Web.UI.Control::RenderControl(class [System.Web]System.Web.UI.HtmlTextWriter)
0x1ff86  leave.s  loc_1FF92
0x1ff88  ldloc.2
0x1ff89  brfalse.s loc_1FF91
0x1ff8b  ldloc.2
0x1ff8c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ff91  endfinally
0x1ff92  ldarg.0
0x1ff93  call     instance bool Microsoft.Crm.Application.Components.UI.Lookup::get_IsDisplayOnlyLookup()
0x1ff98  brtrue.s loc_1FFA6
0x1ff9a  ldarg.1
0x1ff9b  ldstr    aAHrefOnclickMs// "<a href=\"#\" onclick=\"Mscrm.Utilities"...
0x1ffa0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ffa5  ret
0x1ffa6  ldarg.1
0x1ffa7  ldstr    aSpanSpan// "<span></span>"
0x1ffac  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x1ffb1  ret
```
