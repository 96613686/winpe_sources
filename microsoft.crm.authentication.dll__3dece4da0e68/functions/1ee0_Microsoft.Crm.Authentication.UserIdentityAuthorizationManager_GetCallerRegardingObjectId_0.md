# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerRegardingObjectId_0

- ea: `0x1ee0`
- end: `0x1f19`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerRegardingObjectId_0`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3800`
- `0x3ae0`

## callees

- `0x1ee0`

## string_xrefs

- `0x1ef4`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1f0c`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x1ee0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1ee5  stloc.0
0x1ee6  ldarg.0
0x1ee7  brfalse.s loc_1F17
0x1ee9  ldarg.0
0x1eea  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1eef  ldstr    aCallerregardin// "CallerRegardingObjectId"
0x1ef4  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1ef9  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::FindHeader(string, string)
0x1efe  ldc.i4.0
0x1eff  blt.s    loc_1F17
0x1f01  ldarg.0
0x1f02  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1f07  ldstr    aCallerregardin// "CallerRegardingObjectId"
0x1f0c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1f11  callvirt T0x2B000008
0x1f16  stloc.0
0x1f17  ldloc.0
0x1f18  ret
```
