# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetUserType_0

- ea: `0x1e30`
- end: `0x1e65`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetUserType_0`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3800`
- `0x3ae0`

## callees

- `0x1e30`

## string_xrefs

- `0x1e40`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1e58`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x1e30  ldc.i4.0
0x1e31  stloc.0
0x1e32  ldarg.0
0x1e33  brfalse.s loc_1E63
0x1e35  ldarg.0
0x1e36  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1e3b  ldstr    aUsertype// "UserType"
0x1e40  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1e45  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::FindHeader(string, string)
0x1e4a  ldc.i4.0
0x1e4b  blt.s    loc_1E63
0x1e4d  ldarg.0
0x1e4e  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1e53  ldstr    aUsertype// "UserType"
0x1e58  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1e5d  callvirt T0x2B000009
0x1e62  stloc.0
0x1e63  ldloc.0
0x1e64  ret
```
