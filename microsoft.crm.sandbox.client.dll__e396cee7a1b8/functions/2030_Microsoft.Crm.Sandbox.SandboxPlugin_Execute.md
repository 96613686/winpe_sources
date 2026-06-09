# Microsoft.Crm.Sandbox.SandboxPlugin::Execute

- ea: `0x2030`
- end: `0x2076`
- name: `Microsoft.Crm.Sandbox.SandboxPlugin::Execute`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x480`
- `0x22d0`
- `0x22e0`
- `0x22f0`
- `0x2300`
- `0x2310`
- `0x2320`
- `0x2330`

## pseudocode

```c

```

## disassembly

```asm
0x2030  ldarg.1
0x2031  callvirt instance var<u1> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxClientBase`1<class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost>::get_Proxy()
0x2036  ldarg.2
0x2037  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo Microsoft.Crm.Sandbox.SandboxCallTracker::get_CallInfo()
0x203c  ldarg.3
0x203d  castclass [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext
0x2042  ldarg.0
0x2043  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginAssemblyId()
0x2048  ldarg.0
0x2049  call     instance int32 Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginAssemblyHashCode()
0x204e  ldarg.0
0x204f  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_AssemblyName()
0x2054  ldarg.0
0x2055  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginTypeId()
0x205a  ldarg.0
0x205b  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_TypeName()
0x2060  ldarg.0
0x2061  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginConfig()
0x2066  ldarg.0
0x2067  call     instance string Microsoft.Crm.Sandbox.SandboxCodeUnit::get_PluginSecureConfig()
0x206c  ldarg.s  4
0x206e  ldarg.s  5
0x2070  callvirt instance class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.ISandboxHost::ExecuteAndReturnTraceInfo(class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxCallInfo, class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxPluginExecutionContext, valuetype [mscorlib]System.Guid, int32, string, valuetype [mscorlib]System.Guid, string, string, string, string, bool)
0x2075  ret
```
