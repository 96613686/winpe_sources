# Microsoft.Crm.Tools.Admin.OrganizationOperation::SetCompletionMessage

- ea: `0x9890`
- end: `0x98ab`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::SetCompletionMessage`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12000`

## string_xrefs

- `0x9896`: `Installer.FailureMessage`

## pseudocode

```c

```

## disassembly

```asm
0x9890  ldarg.0
0x9891  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.Installer::get_Data()
0x9896  ldstr    aInstallerFailu// "Installer.FailureMessage"
0x989b  callvirt instance object [mscorlib]System.Collections.IDictionary::get_Item(object)
0x98a0  castclass [mscorlib]System.String
0x98a5  stsfld   string Microsoft.Crm.Tools.Admin.OrganizationOperation::_completionDetails
0x98aa  ret
```
