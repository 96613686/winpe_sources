# Microsoft.Crm.Sandbox.SandboxSdkListener::GetPluginExecutionIdFromCallInfo

- ea: `0x53f0`
- end: `0x541f`
- name: `Microsoft.Crm.Sandbox.SandboxSdkListener::GetPluginExecutionIdFromCallInfo`
- size: `47`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3ca0`
- `0x4000`
- `0x4360`
- `0x4680`

## callees

- `0x53f0`

## pseudocode

```c

```

## disassembly

```asm
0x53f0  ldarg.1
0x53f1  brfalse.s loc_5419
0x53f3  ldarg.1
0x53f4  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x53f9  brfalse.s loc_5419
0x53fb  ldarg.1
0x53fc  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5401  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5406  brfalse.s loc_5419
0x5408  ldarg.1
0x5409  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x540e  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_ParentCallInfo()
0x5413  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo::get_Id()
0x5418  ret
0x5419  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x541e  ret
```
