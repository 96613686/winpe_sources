# Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::get_Id

- ea: `0x10ac0`
- end: `0x10adf`
- name: `Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::get_Id`
- size: `31`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x104d0`
- `0x10880`

## callees

- `0x10ac0`
- `0x10ae0`

## pseudocode

```c

```

## disassembly

```asm
0x10ac0  ldarg.0
0x10ac1  call     instance class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::get_EntityDescriptor()
0x10ac6  brfalse.s loc_10AD9
0x10ac8  ldarg.0
0x10ac9  call     instance class [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor Microsoft.Crm.Authentication.Claims.SecurityTokenServiceMetadata::get_EntityDescriptor()
0x10ace  callvirt instance class [System.IdentityModel]System.IdentityModel.Metadata.EntityId [System.IdentityModel]System.IdentityModel.Metadata.EntityDescriptor::get_EntityId()
0x10ad3  callvirt instance string [System.IdentityModel]System.IdentityModel.Metadata.EntityId::get_Id()
0x10ad8  ret
0x10ad9  ldsfld   string [mscorlib]System.String::Empty
0x10ade  ret
```
