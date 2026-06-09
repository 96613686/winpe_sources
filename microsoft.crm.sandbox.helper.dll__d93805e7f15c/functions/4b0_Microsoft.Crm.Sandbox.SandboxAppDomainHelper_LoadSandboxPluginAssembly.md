# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadSandboxPluginAssembly

- ea: `0x4b0`
- end: `0x508`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadSandboxPluginAssembly`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x4b0`

## pseudocode

```c

```

## disassembly

```asm
0x4b0  ldc.i4.1
0x4b1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x4b6  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x4bb  ldarg.0
0x4bc  ldstr    aMicrosoftCrmSa// "Microsoft.Crm.Sandbox"
0x4c1  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x4c6  stfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x4cb  ldarg.0
0x4cc  ldarg.0
0x4cd  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x4d2  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x4d7  stfld    class [mscorlib]System.Reflection.AssemblyName Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_assemblyName
0x4dc  ldarg.0
0x4dd  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x4e2  callvirt instance class [mscorlib]System.Security.Policy.Evidence [mscorlib]System.Reflection.Assembly::get_Evidence()
0x4e7  brfalse.s loc_4FF
0x4e9  ldarg.0
0x4ea  ldarg.0
0x4eb  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x4f0  callvirt instance class [mscorlib]System.Security.Policy.Evidence [mscorlib]System.Reflection.Assembly::get_Evidence()
0x4f5  callvirt T0x2B000001
0x4fa  stfld    class [mscorlib]System.Security.Policy.StrongName Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_strongName
0x4ff  leave.s  loc_507
0x501  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x506  endfinally
0x507  ret
```
