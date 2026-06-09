# Microsoft.Crm.ServiceBus.RouterService::AuthenticateCaller

- ea: `0x42f0`
- end: `0x433c`
- name: `Microsoft.Crm.ServiceBus.RouterService::AuthenticateCaller`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x3ff0`
- `0x4090`

## callees

- `0x42f0`
- `0x4340`

## pseudocode

```c

```

## disassembly

```asm
0x42f0  call     class [System.ServiceModel]System.ServiceModel.ServiceSecurityContext [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_Current()
0x42f5  callvirt instance class [mscorlib]System.Security.Principal.WindowsIdentity [System.ServiceModel]System.ServiceModel.ServiceSecurityContext::get_WindowsIdentity()
0x42fa  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x42ff  stloc.0
0x4300  ldloc.0
0x4301  ldc.i4.s 0x16
0x4303  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x4308  brtrue.s loc_4314
0x430a  ldloc.0
0x430b  ldc.i4.s 0x18
0x430d  callvirt instance bool [mscorlib]System.Security.Principal.SecurityIdentifier::IsWellKnown(valuetype [mscorlib]System.Security.Principal.WellKnownSidType)
0x4312  brfalse.s loc_4315
0x4314  ret
0x4315  ldarg.0
0x4316  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.ServiceBus.RouterService::RetrievePrivilegeUserGroupId()
0x431b  stloc.1
0x431c  ldloc.0
0x431d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetGuidFromSid(class [mscorlib]System.Security.Principal.SecurityIdentifier)
0x4322  ldloc.1
0x4323  call     bool [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::CheckMembership(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4328  brtrue.s loc_433B
0x432a  ldc.i4   0x80048405
0x432f  ldc.i4.0
0x4330  newarr   [mscorlib]System.Object
0x4335  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x433a  throw
0x433b  ret
```
