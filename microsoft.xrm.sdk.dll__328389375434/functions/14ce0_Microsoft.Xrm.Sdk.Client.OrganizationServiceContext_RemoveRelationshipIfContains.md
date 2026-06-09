# Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::RemoveRelationshipIfContains

- ea: `0x14ce0`
- end: `0x14cf8`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::RemoveRelationshipIfContains`
- size: `24`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x13bd0`
- `0x13c70`
- `0x13fa0`

## callees

- `0x3930`
- `0x3950`
- `0x3970`
- `0x14d00`

## pseudocode

```c

```

## disassembly

```asm
0x14ce0  ldarg.0
0x14ce1  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Source()
0x14ce6  ldarg.0
0x14ce7  callvirt instance class Microsoft.Xrm.Sdk.Relationship Microsoft.Xrm.Sdk.LinkDescriptor::get_Relationship()
0x14cec  ldarg.0
0x14ced  callvirt instance class Microsoft.Xrm.Sdk.Entity Microsoft.Xrm.Sdk.LinkDescriptor::get_Target()
0x14cf2  call     bool Microsoft.Xrm.Sdk.Client.OrganizationServiceContext::RemoveRelationshipIfContains(class Microsoft.Xrm.Sdk.Entity source, class Microsoft.Xrm.Sdk.Relationship relationship, class Microsoft.Xrm.Sdk.Entity target)
0x14cf7  ret
```
