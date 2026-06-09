# Microsoft.Crm.Web.DebugInfo::RenderVersionNumbers

- ea: `0x2b560`
- end: `0x2b5c9`
- name: `Microsoft.Crm.Web.DebugInfo::RenderVersionNumbers`
- size: `105`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x2b560`
- `0x2b6a0`

## string_xrefs

- `0x2b56d`: `Debug_Info_Components_App`
- `0x2b572`: `/bin/Microsoft.Crm.Application.Components.Application.dll`
- `0x2b57e`: `Debug_Info_Components_UI`
- `0x2b583`: `/bin/Microsoft.Crm.Application.Components.UI.dll`
- `0x2b58f`: `Debug_Info_Components_Platform`
- `0x2b594`: `/bin/Microsoft.Crm.Application.Components.Platform.dll`
- `0x2b5a0`: `Debug_Info_Components_Resource`
- `0x2b5a5`: `/bin/Microsoft.Crm.Application.Components.Strings.dll`

## pseudocode

```c

```

## disassembly

```asm
0x2b560  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2b565  newobj   instance void [mscorlib]System.IO.StringWriter::.ctor(class [mscorlib]System.IFormatProvider)
0x2b56a  stloc.0
0x2b56b  ldarg.0
0x2b56c  ldloc.0
0x2b56d  ldstr    aDebugInfoCompo// "Debug_Info_Components_App"
0x2b572  ldstr    aBinMicrosoftCr// "/bin/Microsoft.Crm.Application.Componen"...
0x2b577  call     instance void Microsoft.Crm.Web.DebugInfo::RenderVersionLine(class [mscorlib]System.IO.StringWriter writer, string resxStringId, string filename)
0x2b57c  ldarg.0
0x2b57d  ldloc.0
0x2b57e  ldstr    aDebugInfoCompo_0// "Debug_Info_Components_UI"
0x2b583  ldstr    aBinMicrosoftCr_0// "/bin/Microsoft.Crm.Application.Componen"...
0x2b588  call     instance void Microsoft.Crm.Web.DebugInfo::RenderVersionLine(class [mscorlib]System.IO.StringWriter writer, string resxStringId, string filename)
0x2b58d  ldarg.0
0x2b58e  ldloc.0
0x2b58f  ldstr    aDebugInfoCompo_1// "Debug_Info_Components_Platform"
0x2b594  ldstr    aBinMicrosoftCr_1// "/bin/Microsoft.Crm.Application.Componen"...
0x2b599  call     instance void Microsoft.Crm.Web.DebugInfo::RenderVersionLine(class [mscorlib]System.IO.StringWriter writer, string resxStringId, string filename)
0x2b59e  ldarg.0
0x2b59f  ldloc.0
0x2b5a0  ldstr    aDebugInfoCompo_2// "Debug_Info_Components_Resource"
0x2b5a5  ldstr    aBinMicrosoftCr_2// "/bin/Microsoft.Crm.Application.Componen"...
0x2b5aa  call     instance void Microsoft.Crm.Web.DebugInfo::RenderVersionLine(class [mscorlib]System.IO.StringWriter writer, string resxStringId, string filename)
0x2b5af  ldloc.0
0x2b5b0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.IO.StringWriter::GetStringBuilder()
0x2b5b5  callvirt instance string [mscorlib]System.Object::ToString()
0x2b5ba  stloc.1
0x2b5bb  leave.s  loc_2B5C7
0x2b5bd  ldloc.0
0x2b5be  brfalse.s loc_2B5C6
0x2b5c0  ldloc.0
0x2b5c1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b5c6  endfinally
0x2b5c7  ldloc.1
0x2b5c8  ret
```
