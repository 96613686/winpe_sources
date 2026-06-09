# Microsoft.Crm.Web.Reporting.CrmReportViewerMessages::GetLocalizedNameForRenderingExtension

- ea: `0xc1970`
- end: `0xc1b17`
- name: `Microsoft.Crm.Web.Reporting.CrmReportViewerMessages::GetLocalizedNameForRenderingExtension`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xc1970`
- `0x10a280`

## string_xrefs

- `0xc1a64`: `EXCELOPENXML`
- `0xc1a97`: `WORDOPENXML`
- `0xc1aaa`: `ReportViewer_Rendering_Extension_XML`
- `0xc1aba`: `ReportViewer_Rendering_Extension_CSV`
- `0xc1aca`: `ReportViewer_Rendering_Extension_PDF`
- `0xc1ada`: `ReportViewer_Rendering_Extension_MHTML`
- `0xc1aea`: `ReportViewer_Rendering_Extension_EXCEL`
- `0xc1afa`: `ReportViewer_Rendering_Extension_IMAGE`
- `0xc1b0a`: `ReportViewer_Rendering_Extension_WORD`

## pseudocode

```c

```

## disassembly

```asm
0xc1970  ldarg.1
0xc1971  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0xc1976  stloc.0
0xc1977  ldloc.0
0xc1978  ldc.i4   0x43E9176D
0xc197d  bgt.un.s loc_C19BA
0xc197f  ldloc.0
0xc1980  ldc.i4   0x1D4A85D6
0xc1985  bgt.un.s loc_C199F
0xc1987  ldloc.0
0xc1988  ldc.i4   0x60854CA
0xc198d  beq      loc_C1A96
0xc1992  ldloc.0
0xc1993  ldc.i4   0x1D4A85D6
0xc1998  beq.s    loc_C19FA
0xc199a  br       loc_C1B15
0xc199f  ldloc.0
0xc19a0  ldc.i4   0x33376E50
0xc19a5  beq      loc_C1A4E
0xc19aa  ldloc.0
0xc19ab  ldc.i4   0x43E9176D
0xc19b0  beq      loc_C1A39
0xc19b5  br       loc_C1B15
0xc19ba  ldloc.0
0xc19bb  ldc.i4   0x6D01E13D
0xc19c0  bgt.un.s loc_C19DD
0xc19c2  ldloc.0
0xc19c3  ldc.i4   0x5BBAD75A
0xc19c8  beq      loc_C1A75
0xc19cd  ldloc.0
0xc19ce  ldc.i4   0x6D01E13D
0xc19d3  beq      loc_C1A87
0xc19d8  br       loc_C1B15
0xc19dd  ldloc.0
0xc19de  ldc.i4   0x7B21A23F
0xc19e3  beq.s    loc_C1A0F
0xc19e5  ldloc.0
0xc19e6  ldc.i4   0x927C23E1
0xc19eb  beq.s    loc_C1A63
0xc19ed  ldloc.0
0xc19ee  ldc.i4   0xAE047875
0xc19f3  beq.s    loc_C1A24
0xc19f5  br       loc_C1B15
0xc19fa  ldarg.1
0xc19fb  ldstr    aXml// "XML"
0xc1a00  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a05  brtrue   loc_C1AA5
0xc1a0a  br       loc_C1B15
0xc1a0f  ldarg.1
0xc1a10  ldstr    aCsv_0// "CSV"
0xc1a15  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a1a  brtrue   loc_C1AB5
0xc1a1f  br       loc_C1B15
0xc1a24  ldarg.1
0xc1a25  ldstr    aPdf// "PDF"
0xc1a2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a2f  brtrue   loc_C1AC5
0xc1a34  br       loc_C1B15
0xc1a39  ldarg.1
0xc1a3a  ldstr    aMhtml// "MHTML"
0xc1a3f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a44  brtrue   loc_C1AD5
0xc1a49  br       loc_C1B15
0xc1a4e  ldarg.1
0xc1a4f  ldstr    aExcel_0// "EXCEL"
0xc1a54  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a59  brtrue   loc_C1AE5
0xc1a5e  br       loc_C1B15
0xc1a63  ldarg.1
0xc1a64  ldstr    aExcelopenxml// "EXCELOPENXML"
0xc1a69  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a6e  brtrue.s loc_C1AE5
0xc1a70  br       loc_C1B15
0xc1a75  ldarg.1
0xc1a76  ldstr    aImage_1// "IMAGE"
0xc1a7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a80  brtrue.s loc_C1AF5
0xc1a82  br       loc_C1B15
0xc1a87  ldarg.1
0xc1a88  ldstr    aWord// "WORD"
0xc1a8d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1a92  brtrue.s loc_C1B05
0xc1a94  br.s     loc_C1B15
0xc1a96  ldarg.1
0xc1a97  ldstr    aWordopenxml// "WORDOPENXML"
0xc1a9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc1aa1  brtrue.s loc_C1B05
0xc1aa3  br.s     loc_C1B15
0xc1aa5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1aaa  ldstr    aReportviewerRe_0// "ReportViewer_Rendering_Extension_XML"
0xc1aaf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1ab4  ret
0xc1ab5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1aba  ldstr    aReportviewerRe_1// "ReportViewer_Rendering_Extension_CSV"
0xc1abf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1ac4  ret
0xc1ac5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1aca  ldstr    aReportviewerRe_2// "ReportViewer_Rendering_Extension_PDF"
0xc1acf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1ad4  ret
0xc1ad5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1ada  ldstr    aReportviewerRe_3// "ReportViewer_Rendering_Extension_MHTML"
0xc1adf  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1ae4  ret
0xc1ae5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1aea  ldstr    aReportviewerRe_4// "ReportViewer_Rendering_Extension_EXCEL"
0xc1aef  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1af4  ret
0xc1af5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1afa  ldstr    aReportviewerRe_5// "ReportViewer_Rendering_Extension_IMAGE"
0xc1aff  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1b04  ret
0xc1b05  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0xc1b0a  ldstr    aReportviewerRe_6// "ReportViewer_Rendering_Extension_WORD"
0xc1b0f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0xc1b14  ret
0xc1b15  ldnull
0xc1b16  ret
```
