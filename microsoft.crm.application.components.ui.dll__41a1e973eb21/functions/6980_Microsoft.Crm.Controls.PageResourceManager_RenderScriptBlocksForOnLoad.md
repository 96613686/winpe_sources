# Microsoft.Crm.Controls.PageResourceManager::RenderScriptBlocksForOnLoad

- ea: `0x6980`
- end: `0x69e5`
- name: `Microsoft.Crm.Controls.PageResourceManager::RenderScriptBlocksForOnLoad`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3ae0`

## callees

- `0x6900`
- `0x6980`

## string_xrefs

- `0x69b9`: `function pageManagerWindowUnloadHandler(){\n						try{\n							if(window.$removeHandler)\n								$removeHandler(window, 'unload', pageManagerWindowUnloadHandler);\n						}\n						catch(exc){}\n						window.onresize=null;window.onerror=null;window.onload=null;\n					}`

## pseudocode

```c

```

## disassembly

```asm
0x6980  ldarg.0
0x6981  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x6986  brfalse.s loc_69E4
0x6988  ldarg.0
0x6989  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x698e  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock>::get_Count()
0x6993  ldc.i4.0
0x6994  ble.s    loc_69E4
0x6996  ldarg.1
0x6997  ldstr    aScriptTypeText// "<script type=\"text/javascript\">"
0x699c  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69a1  ldarg.0
0x69a2  ldarg.1
0x69a3  callvirt instance class [mscorlib]System.IO.TextWriter [System.Web]System.Web.UI.HtmlTextWriter::get_InnerWriter()
0x69a8  call     instance void Microsoft.Crm.Controls.PageResourceManager::WriteOnLoadScriptBlocks(class [mscorlib]System.IO.TextWriter writer)
0x69ad  ldarg.1
0x69ae  ldstr    aIfWindowSysSys// "if(window.Sys){Sys.Application.add_load"...
0x69b3  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69b8  ldarg.1
0x69b9  ldstr    aFunctionPagema// "function pageManagerWindowUnloadHandler"...
0x69be  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69c3  ldarg.1
0x69c4  ldstr    aIfWindowWindow// "if(window && window.$addHandler){$addHa"...
0x69c9  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69ce  ldarg.1
0x69cf  ldstr    aIfWindowWindow_0// "if(window) { window.onunload = function"...
0x69d4  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69d9  ldarg.1
0x69da  ldstr    aScript// "</script>"
0x69df  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string)
0x69e4  ret
```
