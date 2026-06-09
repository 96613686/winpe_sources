# Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlInnerFrameBuilder::ConstructRuntimeUrl

- ea: `0x15420`
- end: `0x154e0`
- name: `Microsoft.Crm.Application.Components.Sdk.FormControls.Web.PowerBIControlInnerFrameBuilder::ConstructRuntimeUrl`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x153a0`

## callees

- `0x15420`

## string_xrefs

- `0x15442`: `powerBIUrl={0}&loginLabel={1}&componentId={2}&direction={3}&env={4}&loginText={5}&client={6}&mode={7}`

## pseudocode

```c

```

## disassembly

```asm
0x15420  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_FirstPartyIntegrationUrl()
0x15425  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x1542a  stloc.0
0x1542b  ldloc.0
0x1542c  dup
0x1542d  callvirt instance string [System]System.UriBuilder::get_Path()
0x15432  ldstr    aRuntimeHtml// "runtime.html"
0x15437  call     string [mscorlib]System.String::Concat(string, string)
0x1543c  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x15441  ldloc.0
0x15442  ldstr    aPowerbiurl0Log// "powerBIUrl={0}&loginLabel={1}&component"...
0x15447  ldc.i4.8
0x15448  newarr   [mscorlib]System.Object
0x1544d  dup
0x1544e  ldc.i4.0
0x1544f  ldarg.1
0x15450  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x15455  stelem.ref
0x15456  dup
0x15457  ldc.i4.1
0x15458  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x1545d  ldstr    aPowerbitileLog// "PowerBITile_LoginButton_Label"
0x15462  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x15467  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x1546c  stelem.ref
0x1546d  dup
0x1546e  ldc.i4.2
0x1546f  ldarg.2
0x15470  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x15475  stelem.ref
0x15476  dup
0x15477  ldc.i4.3
0x15478  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::get_TextDirection()
0x1547d  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x15482  stelem.ref
0x15483  dup
0x15484  ldc.i4.4
0x15485  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.PowerBIUtility::get_EnvironmentType()
0x1548a  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x1548f  stelem.ref
0x15490  dup
0x15491  ldc.i4.5
0x15492  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x15497  ldstr    aPowerbitileAut// "PowerBITile_AuthError_Label"
0x1549c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x154a1  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x154a6  stelem.ref
0x154a7  dup
0x154a8  ldc.i4.6
0x154a9  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsForOutlookClient()
0x154ae  brtrue.s loc_154B7
0x154b0  ldstr    aWeb// "web"
0x154b5  br.s     loc_154BC
0x154b7  ldstr    aOutlook// "outlook"
0x154bc  stelem.ref
0x154bd  dup
0x154be  ldc.i4.7
0x154bf  ldarg.3
0x154c0  brfalse.s loc_154C9
0x154c2  ldstr    aDashboard// "dashboard"
0x154c7  br.s     loc_154CE
0x154c9  ldstr    aTile// "tile"
0x154ce  stelem.ref
0x154cf  call     string [mscorlib]System.String::Format(string, object[])
0x154d4  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x154d9  ldloc.0
0x154da  callvirt instance string [mscorlib]System.Object::ToString()
0x154df  ret
```
