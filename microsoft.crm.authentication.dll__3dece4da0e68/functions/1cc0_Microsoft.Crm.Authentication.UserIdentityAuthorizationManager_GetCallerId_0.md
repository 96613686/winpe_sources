# Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerId_0

- ea: `0x1cc0`
- end: `0x1d71`
- name: `Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::GetCallerId_0`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3800`

## callees

- `0x1570`
- `0x1cc0`
- `0x2000`

## string_xrefs

- `0x1cd7`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1cef`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1d4c`: `http://schemas.microsoft.com/xrm/2011/Contracts`
- `0x1d64`: `http://schemas.microsoft.com/xrm/2011/Contracts`

## pseudocode

```c

```

## disassembly

```asm
0x1cc0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1cc5  stloc.0
0x1cc6  ldarg.0
0x1cc7  brfalse  loc_1D6F
0x1ccc  ldarg.0
0x1ccd  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1cd2  ldstr    aCallerobjectid// "CallerObjectId"
0x1cd7  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1cdc  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::FindHeader(string, string)
0x1ce1  ldc.i4.0
0x1ce2  blt.s    loc_1D41
0x1ce4  ldarg.0
0x1ce5  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1cea  ldstr    aCallerobjectid// "CallerObjectId"
0x1cef  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1cf4  callvirt T0x2B000008
0x1cf9  ldarg.1
0x1cfa  call     valuetype Microsoft.Crm.Authentication.CrmUserInfo Microsoft.Crm.Authentication.UserIdentityAuthorizationManager::RetrieveUserByObjectId(valuetype [mscorlib]System.Guid directoryObjectId, valuetype [mscorlib]System.Guid organizationId)
0x1cff  stloc.1
0x1d00  ldloca.s 1
0x1d02  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x1d07  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1d0c  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1d11  brfalse.s loc_1D1B
0x1d13  ldloca.s 1
0x1d15  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Authentication.CrmUserInfo::get_UserId()
0x1d1a  ret
0x1d1b  ldc.i4   0x191
0x1d20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1d25  ldstr    aCallerobjectid_0// "CallerObjectId should be Object Id of a"...
0x1d2a  ldc.i4.0
0x1d2b  newarr   [mscorlib]System.Object
0x1d30  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1d35  ldc.i4.0
0x1d36  newarr   [mscorlib]System.Object
0x1d3b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x1d40  throw
0x1d41  ldarg.0
0x1d42  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1d47  ldstr    aCallerid// "CallerId"
0x1d4c  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1d51  callvirt instance int32 [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders::FindHeader(string, string)
0x1d56  ldc.i4.0
0x1d57  blt.s    loc_1D6F
0x1d59  ldarg.0
0x1d5a  callvirt instance class [System.ServiceModel]System.ServiceModel.Channels.MessageHeaders [System.ServiceModel]System.ServiceModel.OperationContext::get_IncomingMessageHeaders()
0x1d5f  ldstr    aCallerid// "CallerId"
0x1d64  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/xrm/2011/C"...
0x1d69  callvirt T0x2B000008
0x1d6e  stloc.0
0x1d6f  ldloc.0
0x1d70  ret
```
