# Microsoft.Crm.Application.Security.WrpcContext::RenderWrpcTokenAsHiddenInput

- ea: `0x13f70`
- end: `0x14017`
- name: `Microsoft.Crm.Application.Security.WrpcContext::RenderWrpcTokenAsHiddenInput`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x13f40`

## callees

- `0x13cc0`
- `0x13f70`

## string_xrefs

- `0x13f92`: `CRMWRPCToken`
- `0x13fd1`: `CRMWRPCTokenTimeStamp`

## pseudocode

```c

```

## disassembly

```asm
0x13f70  ldarg.0
0x13f71  ldfld    bool Microsoft.Crm.Application.Security.WrpcContext::_isTokenCheckIgnored
0x13f76  brfalse.s loc_13F79
0x13f78  ret
0x13f79  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x13f7e  stloc.0
0x13f7f  ldarg.1
0x13f80  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter)
0x13f85  stloc.1
0x13f86  ldarg.1
0x13f87  ldstr    aInputTypeHidde_0// "<input type=\"hidden\" name=\""
0x13f8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13f91  ldarg.1
0x13f92  ldstr    aCrmwrpctoken// "CRMWRPCToken"
0x13f97  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13f9c  ldarg.1
0x13f9d  ldstr    asc_4564C// "\" "
0x13fa2  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13fa7  ldstr    aValue_0// "value"
0x13fac  ldarg.0
0x13fad  ldarg.2
0x13fae  ldloc.0
0x13faf  call     instance string Microsoft.Crm.Application.Security.WrpcContext::GenerateToken(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPageUrl, valuetype [mscorlib]System.DateTime timestamp)
0x13fb4  ldloc.1
0x13fb5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmWriteHtmlAttribute(string, string, class [System.Web]System.Web.UI.HtmlTextWriter)
0x13fba  ldarg.1
0x13fbb  ldstr    asc_4886A// " />"
0x13fc0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13fc5  ldarg.1
0x13fc6  ldstr    aInputTypeHidde_0// "<input type=\"hidden\" name=\""
0x13fcb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13fd0  ldarg.1
0x13fd1  ldstr    aCrmwrpctokenti// "CRMWRPCTokenTimeStamp"
0x13fd6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13fdb  ldarg.1
0x13fdc  ldstr    asc_4564C// "\" "
0x13fe1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x13fe6  ldloc.1
0x13fe7  ldstr    aValue_0// "value"
0x13fec  ldloca.s 0
0x13fee  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x13ff3  stloc.2
0x13ff4  ldloca.s 2
0x13ff6  ldstr    aD_1// "D"
0x13ffb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x14000  call     instance string [mscorlib]System.Int64::ToString(string, class [mscorlib]System.IFormatProvider)
0x14005  ldc.i4.0
0x14006  callvirt instance void [System.Web]System.Web.UI.HtmlTextWriter::WriteAttribute(string, string, bool)
0x1400b  ldarg.1
0x1400c  ldstr    asc_4886A// " />"
0x14011  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x14016  ret
```
