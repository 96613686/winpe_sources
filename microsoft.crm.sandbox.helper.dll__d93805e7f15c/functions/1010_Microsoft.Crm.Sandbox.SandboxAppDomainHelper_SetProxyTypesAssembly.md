# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::SetProxyTypesAssembly

- ea: `0x1010`
- end: `0x1053`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::SetProxyTypesAssembly`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x1010`

## pseudocode

```c

```

## disassembly

```asm
0x1010  ldarg.0
0x1011  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x1016  ldtoken  [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.ProxyTypesAssemblyAttribute
0x101b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1020  ldc.i4.0
0x1021  callvirt instance object[] [mscorlib]System.Reflection.Assembly::GetCustomAttributes(class [mscorlib]System.Type, bool)
0x1026  stloc.0
0x1027  ldloc.0
0x1028  brfalse.s loc_1052
0x102a  ldloc.0
0x102b  ldlen
0x102c  brfalse.s loc_1052
0x102e  ldarg.1
0x102f  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IProxyTypesAssemblyProvider
0x1034  dup
0x1035  brtrue.s loc_1047
0x1037  ldstr    aAssemblyprovid// "assemblyProvider"
0x103c  ldstr    aCrmSandboxInte_0// "CRM Sandbox Internal Error: assemblyPro"...
0x1041  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string, string)
0x1046  throw
0x1047  ldarg.0
0x1048  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x104d  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IProxyTypesAssemblyProvider::set_ProxyTypesAssembly(class [mscorlib]System.Reflection.Assembly)
0x1052  ret
```
