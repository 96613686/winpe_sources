# Microsoft.Crm.Web.Sfa.SfaUtility::BuildRefreshRevenueFieldsScript

- ea: `0x20`
- end: `0x52`
- name: `Microsoft.Crm.Web.Sfa.SfaUtility::BuildRefreshRevenueFieldsScript`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x28`: `try{window.opener.RefreshRevenueFields(`

## pseudocode

```c

```

## disassembly

```asm
0x20  ldc.i4.s 0x64
0x22  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x27  dup
0x28  ldstr    aTryWindowOpene// "try{window.opener.RefreshRevenueFields("
0x2d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x32  pop
0x33  dup
0x34  ldarg.0
0x35  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x3a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x3f  pop
0x40  dup
0x41  ldstr    aCatchE// ");}catch(e){}"
0x46  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x4b  pop
0x4c  callvirt instance string [mscorlib]System.Object::ToString()
0x51  ret
```
