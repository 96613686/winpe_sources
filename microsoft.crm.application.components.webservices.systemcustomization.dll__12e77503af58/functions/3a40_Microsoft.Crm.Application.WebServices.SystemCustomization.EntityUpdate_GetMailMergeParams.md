# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetMailMergeParams

- ea: `0x3a40`
- end: `0x3a5f`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetMailMergeParams`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x2b0`
- `0x3a40`

## pseudocode

```c

```

## disassembly

```asm
0x3a40  ldarg.1
0x3a41  ldstr    aMailmergecheck// "mailmergecheck"
0x3a46  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x3a4b  brfalse.s loc_3A5E
0x3a4d  ldarg.0
0x3a4e  ldarg.1
0x3a4f  ldstr    aMailmergecheck// "mailmergecheck"
0x3a54  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x3a59  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_IsMailMergeEnabled(bool)
0x3a5e  ret
```
