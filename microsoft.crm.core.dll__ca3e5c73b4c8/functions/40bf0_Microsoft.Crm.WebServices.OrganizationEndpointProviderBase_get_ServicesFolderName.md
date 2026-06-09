# Microsoft.Crm.WebServices.OrganizationEndpointProviderBase::get_ServicesFolderName

- ea: `0x40bf0`
- end: `0x40c04`
- name: `Microsoft.Crm.WebServices.OrganizationEndpointProviderBase::get_ServicesFolderName`
- size: `20`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x40a50`
- `0x40e20`
- `0x41200`
- `0x69c60`
- `0x69d20`

## callees

- `0x40bf0`
- `0x40c90`

## string_xrefs

- `0x40bf8`: `XRMServices`
- `0x40bfe`: `MSCrmServices`

## pseudocode

```c

```

## disassembly

```asm
0x40bf0  ldarg.0
0x40bf1  callvirt instance bool Microsoft.Crm.WebServices.OrganizationEndpointProviderBase::get_XrmEnabled()
0x40bf6  brfalse.s loc_40BFE
0x40bf8  ldstr    aXrmservices// "XRMServices"
0x40bfd  ret
0x40bfe  ldstr    aMscrmservices_0// "MSCrmServices"
0x40c03  ret
```
