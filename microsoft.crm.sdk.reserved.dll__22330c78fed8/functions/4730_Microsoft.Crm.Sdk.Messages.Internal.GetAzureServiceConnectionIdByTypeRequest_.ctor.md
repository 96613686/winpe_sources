# Microsoft.Crm.Sdk.Messages.Internal.GetAzureServiceConnectionIdByTypeRequest::.ctor

- ea: `0x4730`
- end: `0x4749`
- name: `Microsoft.Crm.Sdk.Messages.Internal.GetAzureServiceConnectionIdByTypeRequest::.ctor`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x4710`

## string_xrefs

- `0x4737`: `GetAzureServiceConnectionIdByType`

## pseudocode

```c

```

## disassembly

```asm
0x4730  ldarg.0
0x4731  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x4736  ldarg.0
0x4737  ldstr    aGetazureservic// "GetAzureServiceConnectionIdByType"
0x473c  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x4741  ldarg.0
0x4742  ldc.i4.0
0x4743  call     instance void Microsoft.Crm.Sdk.Messages.Internal.GetAzureServiceConnectionIdByTypeRequest::set_ConnectionType(int32 value)
0x4748  ret
```
