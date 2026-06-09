# Microsoft.Crm.Application.Forms.FormScript::RenderScriptErrorFunction

- ea: `0x2cf70`
- end: `0x2d031`
- name: `Microsoft.Crm.Application.Forms.FormScript::RenderScriptErrorFunction`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x2ce10`

## string_xrefs

- `0x2cf97`: `Error_With_Field_Client_Side_Event`
- `0x2cfbc`: `Error_With_Field_Client_Side_Event_Field`
- `0x2cfe1`: `Error_With_Field_Client_Side_Event_Event`
- `0x2d006`: `Error_With_Field_Client_Side_Event_Error`

## pseudocode

```c

```

## disassembly

```asm
0x2cf70  ldarg.1
0x2cf71  ldstr    aFunctionDispla// "function displayError(controlName, even"...
0x2cf76  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2cf7b  ldarg.1
0x2cf7c  ldstr    asc_F6722// "{"
0x2cf81  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2cf86  ldarg.1
0x2cf87  ldstr    aAlert// "\talert("
0x2cf8c  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cf91  ldarg.1
0x2cf92  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2cf97  ldstr    aErrorWithField// "Error_With_Field_Client_Side_Event"
0x2cf9c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cfa1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2cfa6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cfab  ldarg.1
0x2cfac  ldstr    aNN// " + '\\n\\n' + "
0x2cfb1  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cfb6  ldarg.1
0x2cfb7  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2cfbc  ldstr    aErrorWithField_0// "Error_With_Field_Client_Side_Event_Fiel"...
0x2cfc1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cfc6  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2cfcb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cfd0  ldarg.1
0x2cfd1  ldstr    aControlnameNN// " + controlName + '\\n\\n' + "
0x2cfd6  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cfdb  ldarg.1
0x2cfdc  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2cfe1  ldstr    aErrorWithField_1// "Error_With_Field_Client_Side_Event_Even"...
0x2cfe6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2cfeb  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2cff0  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2cff5  ldarg.1
0x2cff6  ldstr    aEventnameNN// " + eventName + '\\n\\n' + "
0x2cffb  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2d000  ldarg.1
0x2d001  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2d006  ldstr    aErrorWithField_2// "Error_With_Field_Client_Side_Event_Erro"...
0x2d00b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2d010  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncode(string)
0x2d015  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x2d01a  ldarg.1
0x2d01b  ldstr    aErrordescripti// " + errorDescription);"
0x2d020  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2d025  ldarg.1
0x2d026  ldstr    asc_F6726// "}"
0x2d02b  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x2d030  ret
```
