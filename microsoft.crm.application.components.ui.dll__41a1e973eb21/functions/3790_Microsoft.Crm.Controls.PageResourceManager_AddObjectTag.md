# Microsoft.Crm.Controls.PageResourceManager::AddObjectTag

- ea: `0x3790`
- end: `0x3864`
- name: `Microsoft.Crm.Controls.PageResourceManager::AddObjectTag`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3550`
- `0x6c40`

## callees

- `0x3790`
- `0x3880`

## string_xrefs

- `0x37dc`: `<object id={0} classid='clsid:{1}' style='display:none'></object>`
- `0x3819`: `<object id={0} classid='clsid:{1}' style='display:none'></object>`
- `0x3841`: `<object id={0} classid='clsid:{1}' style='display:none'></object>`

## pseudocode

```c

```

## disassembly

```asm
0x3790  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x3795  brtrue.s loc_3798
0x3797  ret
0x3798  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_Current()
0x379d  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.ClientContext::get_ClientCrmVersion()
0x37a2  ldstr    aDb6b56b928e745// "DB6B56B9-28E7-459c-9978-DC853F1D5C2E"
0x37a7  stloc.0
0x37a8  ldstr    aE9a1cbf0398d42// "E9A1CBF0-398D-422F-BA0D-A6DBD5181DC1"
0x37ad  stloc.1
0x37ae  callvirt instance int32 [mscorlib]System.Version::get_Major()
0x37b3  ldc.i4.4
0x37b4  bne.un.s loc_37C2
0x37b6  ldstr    aDb6b56b928e745// "DB6B56B9-28E7-459c-9978-DC853F1D5C2E"
0x37bb  stloc.0
0x37bc  ldstr    aE9a1cbf0398d42// "E9A1CBF0-398D-422F-BA0D-A6DBD5181DC1"
0x37c1  stloc.1
0x37c2  ldc.i4.m1
0x37c3  ldarg.1
0x37c4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x37c9  ldstr    aGlobalAshx// "global.ashx"
0x37ce  ldc.i4.4
0x37cf  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x37d4  beq.s    loc_37FF
0x37d6  ldarg.0
0x37d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x37dc  ldstr    aObjectId0Class// "<object id={0} classid='clsid:{1}' styl"...
0x37e1  ldc.i4.2
0x37e2  newarr   [mscorlib]System.Object
0x37e7  dup
0x37e8  ldc.i4.0
0x37e9  ldstr    aCrmrcutil// "crmRcUtil"
0x37ee  stelem.ref
0x37ef  dup
0x37f0  ldc.i4.1
0x37f1  ldloc.0
0x37f2  stelem.ref
0x37f3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x37f8  ldc.i4.0
0x37f9  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string header, bool lowercase)
0x37fe  ret
0x37ff  ldc.i4.m1
0x3800  ldarg.1
0x3801  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x3806  ldstr    aAttachmentJs// "attachment.js"
0x380b  ldc.i4.4
0x380c  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x3811  beq.s    loc_3863
0x3813  ldarg.0
0x3814  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3819  ldstr    aObjectId0Class// "<object id={0} classid='clsid:{1}' styl"...
0x381e  ldc.i4.2
0x381f  newarr   [mscorlib]System.Object
0x3824  dup
0x3825  ldc.i4.0
0x3826  ldstr    aCrmrcutil// "crmRcUtil"
0x382b  stelem.ref
0x382c  dup
0x382d  ldc.i4.1
0x382e  ldloc.0
0x382f  stelem.ref
0x3830  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3835  ldc.i4.0
0x3836  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string header, bool lowercase)
0x383b  ldarg.0
0x383c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3841  ldstr    aObjectId0Class// "<object id={0} classid='clsid:{1}' styl"...
0x3846  ldc.i4.2
0x3847  newarr   [mscorlib]System.Object
0x384c  dup
0x384d  ldc.i4.0
0x384e  ldstr    aUploadsync// "UploadSync"
0x3853  stelem.ref
0x3854  dup
0x3855  ldc.i4.1
0x3856  ldloc.1
0x3857  stelem.ref
0x3858  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x385d  ldc.i4.0
0x385e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetCustomResource(string header, bool lowercase)
0x3863  ret
```
