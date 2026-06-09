# Microsoft.Crm.Sandbox.SandboxAppDomain::CreateHelperInPartialTrustAppDomain

- ea: `0x1750`
- end: `0x177d`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomain::CreateHelperInPartialTrustAppDomain`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xef0`
- `0xfa0`

## pseudocode

```c

```

## disassembly

```asm
0x1750  ldtoken  [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper
0x1755  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x175a  stloc.0
0x175b  ldarg.0
0x175c  ldloc.0
0x175d  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x1762  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1767  ldloc.0
0x1768  callvirt instance string [mscorlib]System.Type::get_FullName()
0x176d  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstanceFrom(class [mscorlib]System.AppDomain, string, string)
0x1772  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0x1777  castclass [Microsoft.Crm.Sandbox.Helper]Microsoft.Crm.Sandbox.SandboxAppDomainHelper
0x177c  ret
```
