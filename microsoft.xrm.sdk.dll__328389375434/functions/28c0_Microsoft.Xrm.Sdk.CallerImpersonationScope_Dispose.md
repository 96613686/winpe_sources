# Microsoft.Xrm.Sdk.CallerImpersonationScope::Dispose

- ea: `0x28c0`
- end: `0x2904`
- name: `Microsoft.Xrm.Sdk.CallerImpersonationScope::Dispose`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x28c0`

## string_xrefs

- `0x28df`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x28c0  ldarg.0
0x28c1  ldfld    bool Microsoft.Xrm.Sdk.CallerImpersonationScope::_disposed
0x28c6  brfalse.s loc_28C9
0x28c8  ret
0x28c9  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x28ce  brfalse.s loc_28FC
0x28d0  call     class [System.ServiceModel]System.ServiceModel.OperationContext [System.ServiceModel]System.ServiceModel.OperationContext::get_Current()
0x28d5  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_OutgoingMessageHeaders()
0x28da  ldstr    aCallerid// "CallerId"
0x28df  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x28e4  callvirt instance void [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::RemoveAll(string, string)
0x28e9  ldarg.0
0x28ea  ldfld    class [System.ServiceModel]System.ServiceModel.OperationContextScope Microsoft.Xrm.Sdk.CallerImpersonationScope::scope
0x28ef  brfalse.s loc_28FC
0x28f1  ldarg.0
0x28f2  ldfld    class [System.ServiceModel]System.ServiceModel.OperationContextScope Microsoft.Xrm.Sdk.CallerImpersonationScope::scope
0x28f7  callvirt instance void [System.ServiceModel]System.ServiceModel.OperationContextScope::Dispose()
0x28fc  ldarg.0
0x28fd  ldc.i4.1
0x28fe  stfld    bool Microsoft.Xrm.Sdk.CallerImpersonationScope::_disposed
0x2903  ret
```
