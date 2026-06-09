# Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::.ctor

- ea: `0x136b0`
- end: `0x136df`
- name: `Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x135e0`
- `0x13630`
- `0x13690`

## string_xrefs

- `0x136b7`: `UpdateUpsertAttributes`

## pseudocode

```c

```

## disassembly

```asm
0x136b0  ldarg.0
0x136b1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x136b6  ldarg.0
0x136b7  ldstr    aUpdateupsertat// "UpdateUpsertAttributes"
0x136bc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x136c1  ldarg.0
0x136c2  ldnull
0x136c3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::set_WizardDataXml(string value)
0x136c8  ldarg.0
0x136c9  ldc.i4.0
0x136ca  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::set_UpsertModeCode(int32 value)
0x136cf  ldarg.0
0x136d0  ldloca.s 0
0x136d2  initobj  [mscorlib]System.Guid
0x136d8  ldloc.0
0x136d9  call     instance void Microsoft.Crm.Sdk.Messages.Internal.UpdateUpsertAttributesRequest::set_EntityKeyId(valuetype [mscorlib]System.Guid value)
0x136de  ret
```
