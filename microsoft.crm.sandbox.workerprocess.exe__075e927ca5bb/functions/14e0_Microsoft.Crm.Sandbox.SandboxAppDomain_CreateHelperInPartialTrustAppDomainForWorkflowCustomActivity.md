# Microsoft.Crm.Sandbox.SandboxAppDomain::CreateHelperInPartialTrustAppDomainForWorkflowCustomActivity

- ea: `0x14e0`
- end: `0x1512`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::CreateHelperInPartialTrustAppDomainForWorkflowCustomActivity`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x32d0`

## pseudocode

```c

```

## disassembly

```asm
0x14e0  ldtoken  Microsoft.Crm.Sandbox.SandboxWorkflowCustomActivityAppDomainHelper
0x14e5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14ea  stloc.0
0x14eb  ldarg.0
0x14ec  ldfld    class [mscorlib]System.AppDomain Microsoft.Crm.Sandbox.SandboxAppDomain::_restrictedAppDomain
0x14f1  ldloc.0
0x14f2  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x14f7  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x14fc  ldloc.0
0x14fd  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1502  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstanceFrom(class [mscorlib]System.AppDomain, string, string)
0x1507  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x150c  castclass Microsoft.Crm.Sandbox.SandboxWorkflowCustomActivityAppDomainHelper
0x1511  ret
```
