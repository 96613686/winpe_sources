# Microsoft.Crm.Controls.Footer::ConfigureForRendering

- ea: `0x91a0`
- end: `0x92a0`
- name: `Microsoft.Crm.Controls.Footer::ConfigureForRendering`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8b20`

## callees

- `0x31e0`
- `0x3e90`
- `0x8ad0`
- `0x8af0`
- `0x8b60`
- `0x8f00`
- `0x9140`
- `0x91a0`
- `0x22280`
- `0x222a0`
- `0x222c0`
- `0x223f0`

## pseudocode

```c

```

## disassembly

```asm
0x91a0  ldarg.0
0x91a1  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::PrepareForRendering()
0x91a6  ldarg.0
0x91a7  call     instance bool Microsoft.Crm.Controls.Footer::get_ChunkScripts()
0x91ac  brfalse  loc_929F
0x91b1  ldarg.0
0x91b2  call     instance bool Microsoft.Crm.Controls.Footer::get_LoadGlobalJSAndScriptResourceJS()
0x91b7  brfalse.s loc_9214
0x91b9  ldarg.0
0x91ba  ldc.i4.2
0x91bb  newarr   Microsoft.Crm.Application.Components.UI.ScriptBlock
0x91c0  dup
0x91c1  ldc.i4.0
0x91c2  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x91c7  dup
0x91c8  ldstr    aLoadglobaljsan// "LoadGlobalJSAndScriptResourceJS"
0x91cd  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x91d2  dup
0x91d3  ldc.i4.s 0x64
0x91d5  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x91da  dup
0x91db  ldarg.0
0x91dc  ldc.i4.3
0x91dd  call     instance string Microsoft.Crm.Controls.Footer::GetLoadJsScriptsJsBlock(valuetype JsScriptPresets presets)
0x91e2  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x91e7  stelem.ref
0x91e8  dup
0x91e9  ldc.i4.1
0x91ea  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x91ef  dup
0x91f0  ldstr    aWaitglobaljsan// "WaitGlobalJSAndScriptResourceJsScriptsT"...
0x91f5  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x91fa  dup
0x91fb  ldc.i4.s 0x79
0x91fd  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x9202  dup
0x9203  ldarg.0
0x9204  call     instance string Microsoft.Crm.Controls.Footer::GetWaitJsScriptsLoadJsBlock()
0x9209  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x920e  stelem.ref
0x920f  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class Microsoft.Crm.Application.Components.UI.ScriptBlock[] scriptBlocks)
0x9214  ldarg.0
0x9215  ldc.i4.3
0x9216  newarr   Microsoft.Crm.Application.Components.UI.ScriptBlock
0x921b  dup
0x921c  ldc.i4.0
0x921d  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x9222  dup
0x9223  ldstr    aLoadjsscripts// "LoadJsScripts"
0x9228  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x922d  dup
0x922e  ldc.i4   0x96
0x9233  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x9238  dup
0x9239  ldarg.0
0x923a  ldc.i4.4
0x923b  call     instance string Microsoft.Crm.Controls.Footer::GetLoadJsScriptsJsBlock(valuetype JsScriptPresets presets)
0x9240  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x9245  stelem.ref
0x9246  dup
0x9247  ldc.i4.1
0x9248  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x924d  dup
0x924e  ldstr    aWaitremainingj// "WaitRemainingJsScriptsToLoad"
0x9253  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x9258  dup
0x9259  ldc.i4   0x97
0x925e  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x9263  dup
0x9264  ldarg.0
0x9265  call     instance string Microsoft.Crm.Controls.Footer::GetWaitJsScriptsLoadJsBlock()
0x926a  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x926f  stelem.ref
0x9270  dup
0x9271  ldc.i4.2
0x9272  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x9277  dup
0x9278  ldstr    aInitcontrols// "InitControls"
0x927d  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x9282  dup
0x9283  ldc.i4   0xC8
0x9288  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x928d  dup
0x928e  ldarg.0
0x928f  call     instance string Microsoft.Crm.Controls.Footer::GetInitControlsJsBlock()
0x9294  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x9299  stelem.ref
0x929a  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class Microsoft.Crm.Application.Components.UI.ScriptBlock[] scriptBlocks)
0x929f  ret
```
