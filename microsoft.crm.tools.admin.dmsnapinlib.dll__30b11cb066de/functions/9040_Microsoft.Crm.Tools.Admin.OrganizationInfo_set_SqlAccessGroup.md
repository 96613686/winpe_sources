# Microsoft.Crm.Tools.Admin.OrganizationInfo::set_SqlAccessGroup

- ea: `0x9040`
- end: `0x9052`
- name: `Microsoft.Crm.Tools.Admin.OrganizationInfo::set_SqlAccessGroup`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x9730`

## string_xrefs

- `0x9046`: `ServerInstallInfo.SqlAccessGroup`

## pseudocode

```c

```

## disassembly

```asm
0x9040  ldarg.0
0x9041  call     instance class [mscorlib]System.Collections.IDictionary [Microsoft.Crm.Setup.Shared]Microsoft.Crm.Setup.Shared.PropertyBag::get_Data()
0x9046  ldstr    aServerinstalli_1// "ServerInstallInfo.SqlAccessGroup"
0x904b  ldarg.1
0x904c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x9051  ret
```
