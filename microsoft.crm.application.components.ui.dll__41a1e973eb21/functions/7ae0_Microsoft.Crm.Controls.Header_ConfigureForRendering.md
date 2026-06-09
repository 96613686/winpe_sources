# Microsoft.Crm.Controls.Header::ConfigureForRendering

- ea: `0x7ae0`
- end: `0x7b8b`
- name: `Microsoft.Crm.Controls.Header::ConfigureForRendering`
- size: `171`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x7b90`
- `0x80a0`

## callees

- `0x2280`
- `0x2ef0`
- `0x31e0`
- `0x3250`
- `0x3e90`
- `0x3f80`
- `0x7000`
- `0x7ae0`
- `0x8630`
- `0x22280`
- `0x222a0`
- `0x222c0`
- `0x223f0`

## string_xrefs

- `0x7af6`: `_aWrpcTokens`
- `0x7b01`: `initialFormXml`
- `0x7b5c`: `InitWrpcTokens`

## pseudocode

```c

```

## disassembly

```asm
0x7ae0  ldarg.0
0x7ae1  ldfld    bool Microsoft.Crm.Controls.Header::_configuredForRendering
0x7ae6  brfalse.s loc_7AE9
0x7ae8  ret
0x7ae9  ldarg.0
0x7aea  call     instance void Microsoft.Crm.Controls.Header::PrepareChildControlHeadersForRendering()
0x7aef  ldarg.0
0x7af0  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::PrepareForRendering()
0x7af5  ldarg.0
0x7af6  ldstr    aAwrpctokens_0// "_aWrpcTokens"
0x7afb  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVarObject(string varId)
0x7b00  ldarg.0
0x7b01  ldstr    aInitialformxml// "initialFormXml"
0x7b06  ldstr    asc_3280A// ""
0x7b0b  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVar(string varId, string varValue)
0x7b10  ldarg.0
0x7b11  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Controls.Header> Microsoft.Crm.Controls.Header::controlHeaderList
0x7b16  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Controls.Header>::get_Count()
0x7b1b  ldc.i4.0
0x7b1c  ble.s    loc_7B29
0x7b1e  ldarg.0
0x7b1f  ldstr    aAcontrolheader// "_aControlHeaderList"
0x7b24  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetClientVarObject(string varId)
0x7b29  ldarg.0
0x7b2a  call     instance void Microsoft.Crm.Controls.Header::SetSolutionVariable()
0x7b2f  ldarg.0
0x7b30  call     instance bool Microsoft.Crm.Controls.PageResourceManager::get_RenderWrpcToken()
0x7b35  brfalse.s loc_7B83
0x7b37  ldarg.0
0x7b38  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_wrpcTokenUrls
0x7b3d  brfalse.s loc_7B83
0x7b3f  ldarg.0
0x7b40  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::_wrpcTokenUrls
0x7b45  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Count()
0x7b4a  ldc.i4.0
0x7b4b  ble.s    loc_7B83
0x7b4d  ldarg.0
0x7b4e  ldc.i4.1
0x7b4f  newarr   Microsoft.Crm.Application.Components.UI.ScriptBlock
0x7b54  dup
0x7b55  ldc.i4.0
0x7b56  newobj   instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::.ctor()
0x7b5b  dup
0x7b5c  ldstr    aInitwrpctokens// "InitWrpcTokens"
0x7b61  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Name(string value)
0x7b66  dup
0x7b67  ldc.i4   0x1F4
0x7b6c  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_Priority(int32 value)
0x7b71  dup
0x7b72  ldarg.0
0x7b73  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetWrpcInitJSBlock()
0x7b78  callvirt instance void Microsoft.Crm.Application.Components.UI.ScriptBlock::set_JSBody(string value)
0x7b7d  stelem.ref
0x7b7e  call     instance void Microsoft.Crm.Controls.PageResourceManager::SetScriptBlockForOnLoad(class Microsoft.Crm.Application.Components.UI.ScriptBlock[] scriptBlocks)
0x7b83  ldarg.0
0x7b84  ldc.i4.1
0x7b85  stfld    bool Microsoft.Crm.Controls.Header::_configuredForRendering
0x7b8a  ret
```
