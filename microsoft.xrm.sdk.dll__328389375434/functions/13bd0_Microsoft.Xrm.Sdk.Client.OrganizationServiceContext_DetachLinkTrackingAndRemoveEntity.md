# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity

- ea: `0x13bd0`
- end: `0x13bdf`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTrackingAndRemoveEntity`
- size: `15`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x135a0`
- `0x13760`
- `0x14760`
- `0x23d90`
- `0x24360`

## callees

- `0x13ba0`
- `0x14ce0`

## pseudocode

```c

```

## disassembly

```asm
0x13bd0  ldarg.0
0x13bd1  ldarg.1
0x13bd2  call     instance void Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::DetachLinkTracking(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13bd7  ldarg.1
0x13bd8  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::RemoveRelationshipIfContains(class Microsoft.Xrm.Sdk.LinkDescriptor existingLink)
0x13bdd  pop
0x13bde  ret
```
