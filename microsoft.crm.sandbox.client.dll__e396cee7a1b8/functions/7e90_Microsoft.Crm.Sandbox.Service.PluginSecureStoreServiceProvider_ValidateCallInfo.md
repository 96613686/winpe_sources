# Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateCallInfo

- ea: `0x7e90`
- end: `0x7ec1`
- name: `Microsoft.Crm.Sandbox.Service.PluginSecureStoreServiceProvider::ValidateCallInfo`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x7d10`
- `0x7ed0`

## pseudocode

```c

```

## disassembly

```asm
0x7e90  ldarg.1
0x7e91  ldstr    aCallinfo// "callInfo"
0x7e96  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7e9b  ldarg.1
0x7e9c  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7ea1  ldstr    aCallinfoParent// "callInfo.ParentCallInfo"
0x7ea6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7eab  ldarg.1
0x7eac  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7eb1  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x7eb6  ldstr    aCallinfoParent_0// "callInfo.ParentCallInfo.ParentCallInfo"
0x7ebb  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x7ec0  ret
```
