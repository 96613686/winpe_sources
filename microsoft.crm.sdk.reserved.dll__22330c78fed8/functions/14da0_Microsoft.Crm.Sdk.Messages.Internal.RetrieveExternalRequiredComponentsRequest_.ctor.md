# Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::.ctor

- ea: `0x14da0`
- end: `0x14dcf`
- name: `Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::.ctor`
- size: `47`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14c90`
- `0x14ce0`
- `0x14d30`

## string_xrefs

- `0x14da7`: `RetrieveExternalRequiredComponents`

## pseudocode

```c

```

## disassembly

```asm
0x14da0  ldarg.0
0x14da1  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::.ctor()
0x14da6  ldarg.0
0x14da7  ldstr    aRetrieveextern_0// "RetrieveExternalRequiredComponents"
0x14dac  call     instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest::set_RequestName(string)
0x14db1  ldarg.0
0x14db2  ldloca.s 0
0x14db4  initobj  [mscorlib]System.Guid
0x14dba  ldloc.0
0x14dbb  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::set_ComponentId(valuetype [mscorlib]System.Guid value)
0x14dc0  ldarg.0
0x14dc1  ldc.i4.0
0x14dc2  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::set_ComponentType(int32 value)
0x14dc7  ldarg.0
0x14dc8  ldc.i4.0
0x14dc9  call     instance void Microsoft.Crm.Sdk.Messages.Internal.RetrieveExternalRequiredComponentsRequest::set_IncludeSubcomponents(bool value)
0x14dce  ret
```
