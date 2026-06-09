# Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::.ctor

- ea: `0x49c0`
- end: `0x49ee`
- name: `Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::.ctor`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x48b0`
- `0x4900`
- `0x4950`
- `0x49a0`

## string_xrefs

- `0x49c7`: `SetStateAzureServiceConnection`

## pseudocode

```c

```

## disassembly

```asm
0x49c0  ldarg.0
0x49c1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x49c6  ldarg.0
0x49c7  ldstr    aSetstateazures// "SetStateAzureServiceConnection"
0x49cc  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x49d1  ldarg.0
0x49d2  ldnull
0x49d3  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x49d8  ldarg.0
0x49d9  ldc.i4.0
0x49da  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_State(int32 value)
0x49df  ldarg.0
0x49e0  ldc.i4.0
0x49e1  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_Status(int32 value)
0x49e6  ldarg.0
0x49e7  ldc.i4.0
0x49e8  call     instance void Microsoft.Crm.Sdk.Messages.Internal.SetStateAzureServiceConnectionRequest::set_CascadeModelState(bool value)
0x49ed  ret
```
