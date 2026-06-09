# Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::.ctor

- ea: `0x8540`
- end: `0x8575`
- name: `Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::.ctor`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8ca0`

## callees

- `0x8540`
- `0x8580`

## string_xrefs

- `0x856a`: `Yammer access keys are not set.`

## pseudocode

```c

```

## disassembly

```asm
0x8540  ldarg.0
0x8541  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppPage::.ctor()
0x8546  ldarg.0
0x8547  call     instance void Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::ReadKeys()
0x854c  ldarg.0
0x854d  ldfld    string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::applicationId
0x8552  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8557  brtrue.s loc_8569
0x8559  ldarg.0
0x855a  ldfld    string Microsoft.Crm.Common.Web.Tools.Yammer.YammerOAuthCommon::applicationSecret
0x855f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8564  ldc.i4.0
0x8565  ceq
0x8567  br.s     loc_856A
0x8569  ldc.i4.0
0x856a  ldstr    aYammerAccessKe// "Yammer access keys are not set."
0x856f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x8574  ret
```
