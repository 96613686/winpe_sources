# Microsoft.Crm.Sandbox.SandboxHost::SetPrivilegeUserGroupId

- ea: `0x48a0`
- end: `0x48bb`
- name: `Microsoft.Crm.Sandbox.SandboxHost::SetPrivilegeUserGroupId`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140`

## callees

- `0x4e40`
- `0x4e50`

## string_xrefs

- `0x48b0`: `PrivUserGroupSid`

## pseudocode

```c

```

## disassembly

```asm
0x48a0  ldarg.0
0x48a1  call     unsigned int8[] [Microsoft.Crm.ADUtility]Microsoft.Crm.SecurityUtils::GetSidFromAD(valuetype [mscorlib]System.Guid)
0x48a6  call     void Microsoft.Crm.Sandbox.SandboxHost::set_PrivUserGroupSid(unsigned int8[] value)
0x48ab  call     unsigned int8[] Microsoft.Crm.Sandbox.SandboxHost::get_PrivUserGroupSid()
0x48b0  ldstr    aPrivusergroups// "PrivUserGroupSid"
0x48b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x48ba  ret
```
