# Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath_0

- ea: `0xa550`
- end: `0xa573`
- name: `Microsoft.Crm.Tools.Admin.ProvisioningPath::ConstructPath_0`
- size: `35`
- prototype: ``
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x7560`
- `0x9980`
- `0x99c0`
- `0xa540`
- `0xcb90`
- `0x10960`
- `0x15840`

## callees

- `0xa480`
- `0xa4f0`
- `0xa550`

## pseudocode

```c

```

## disassembly

```asm
0xa550  ldarg.0
0xa551  brtrue.s loc_A55A
0xa553  call     int32 Microsoft.Crm.Tools.Admin.ProvisioningPath::InstalledLanguageCode()
0xa558  starg.s  0
0xa55a  ldarg.0
0xa55b  call     string Microsoft.Crm.Tools.Admin.ProvisioningPath::GetBasePath(int32 languageId)
0xa560  ldstr    aXrmSql// "Xrm\\sql"
0xa565  stloc.0
0xa566  ldloc.0
0xa567  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa56c  ldarg.1
0xa56d  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xa572  ret
```
