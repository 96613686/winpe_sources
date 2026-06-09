# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderHiddenControls

- ea: `0x4d70`
- end: `0x4db0`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderHiddenControls`
- size: `64`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4cc0`

## callees

- `0x4db0`

## string_xrefs

- `0x4d7d`: `processid`
- `0x4d97`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x4d70  ldarg.1
0x4d71  ldstr    aDivStyleDispla// "<div style='display: none' class='hidde"...
0x4d76  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4d7b  pop
0x4d7c  ldarg.0
0x4d7d  ldstr    aProcessid// "processid"
0x4d82  ldarg.1
0x4d83  ldarg.2
0x4d84  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderHiddenTextControl(string attributeName, class [mscorlib]System.Text.StringBuilder target, string currentEntity)
0x4d89  ldarg.0
0x4d8a  ldstr    aStageid// "stageid"
0x4d8f  ldarg.1
0x4d90  ldarg.2
0x4d91  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderHiddenTextControl(string attributeName, class [mscorlib]System.Text.StringBuilder target, string currentEntity)
0x4d96  ldarg.0
0x4d97  ldstr    aTraversedpath// "traversedpath"
0x4d9c  ldarg.1
0x4d9d  ldarg.2
0x4d9e  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::RenderHiddenTextControl(string attributeName, class [mscorlib]System.Text.StringBuilder target, string currentEntity)
0x4da3  ldarg.1
0x4da4  ldstr    aDiv_0// "</div>"
0x4da9  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4dae  pop
0x4daf  ret
```
