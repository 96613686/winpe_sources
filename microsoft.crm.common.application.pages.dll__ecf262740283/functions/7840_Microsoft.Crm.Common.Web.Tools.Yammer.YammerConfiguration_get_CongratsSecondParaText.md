# Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_CongratsSecondParaText

- ea: `0x7840`
- end: `0x7890`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_CongratsSecondParaText`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7770`

## string_xrefs

- `0x7869`: `Web.Tools.Yammer.Config.DisconnectFormatString`

## pseudocode

```c

```

## disassembly

```asm
0x7840  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7845  ldstr    aAHref0TargetBl// "<a href=\"{0}\" target=\"_blank\">"
0x784a  ldc.i4.1
0x784b  newarr   [mscorlib]System.Object
0x7850  dup
0x7851  ldc.i4.0
0x7852  ldarg.0
0x7853  call     instance string Microsoft.Crm.Common.Web.Tools.Yammer.YammerConfiguration::get_YammerApplicationManagementURL()
0x7858  stelem.ref
0x7859  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x785e  stloc.0
0x785f  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentUICulture()
0x7864  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x7869  ldstr    aWebToolsYammer_1// "Web.Tools.Yammer.Config.DisconnectForma"...
0x786e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x7873  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmHtmlEncode(string)
0x7878  ldc.i4.2
0x7879  newarr   [mscorlib]System.Object
0x787e  dup
0x787f  ldc.i4.0
0x7880  ldloc.0
0x7881  stelem.ref
0x7882  dup
0x7883  ldc.i4.1
0x7884  ldstr    aA// "</a>"
0x7889  stelem.ref
0x788a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x788f  ret
```
