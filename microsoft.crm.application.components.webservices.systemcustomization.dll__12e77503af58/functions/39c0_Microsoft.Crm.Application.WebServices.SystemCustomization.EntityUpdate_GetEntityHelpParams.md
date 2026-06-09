# Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityHelpParams

- ea: `0x39c0`
- end: `0x39f5`
- name: `Microsoft.Crm.Application.WebServices.SystemCustomization.EntityUpdate::GetEntityHelpParams`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x3450`

## callees

- `0x190`
- `0x200`
- `0x2b0`
- `0x39c0`

## pseudocode

```c

```

## disassembly

```asm
0x39c0  ldarg.1
0x39c1  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x39c6  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::Exists(string name)
0x39cb  brfalse.s loc_39F4
0x39cd  ldarg.0
0x39ce  ldarg.1
0x39cf  ldstr    aEntityhelpurl// "entityhelpurl"
0x39d4  ldsfld   string [mscorlib]System.String::Empty
0x39d9  callvirt instance string Microsoft.Crm.Application.WebServices.ParameterBag::GetString(string name, string defaultValue)
0x39de  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_EntityHelpUrl(string)
0x39e3  ldarg.0
0x39e4  ldarg.1
0x39e5  ldstr    aEntityhelpurle// "entityhelpurlenabled"
0x39ea  callvirt instance bool Microsoft.Crm.Application.WebServices.ParameterBag::GetBool(string name)
0x39ef  callvirt instance void [Microsoft.Crm.MetadataService]Microsoft.Crm.Metadata.EntityUpdateInfo::set_EntityHelpUrlEnabled(bool)
0x39f4  ret
```
