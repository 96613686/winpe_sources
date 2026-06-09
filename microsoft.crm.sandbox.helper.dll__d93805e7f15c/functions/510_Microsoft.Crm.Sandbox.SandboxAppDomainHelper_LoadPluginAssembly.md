# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadPluginAssembly

- ea: `0x510`
- end: `0x607`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadPluginAssembly`
- size: `247`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x510`
- `0x1990`

## string_xrefs

- `0x516`: `SandboxAppDomainHelper.LoadPluginAssembly: enter`
- `0x524`: `SandboxAppDomainHelper.LoadPluginAssembly: CRM Sandbox Internal Error: assemblyContents is null`
- `0x53d`: `SandboxAppDomainHelper.LoadPluginAssembly: CRM Sandbox Internal Error: _loadedAssembly is null`
- `0x5d3`: `SandboxAppDomainHelper.LoadPluginAssembly: exception: `

## pseudocode

```c

```

## disassembly

```asm
0x510  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x515  ldc.i4.3
0x516  ldstr    aSandboxappdoma_4// "SandboxAppDomainHelper.LoadPluginAssemb"...
0x51b  ldnull
0x51c  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x521  ldarg.1
0x522  brtrue.s loc_52F
0x524  ldstr    aSandboxappdoma_5// "SandboxAppDomainHelper.LoadPluginAssemb"...
0x529  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x52e  throw
0x52f  ldarg.0
0x530  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x535  ldnull
0x536  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0x53b  brfalse.s loc_548
0x53d  ldstr    aSandboxappdoma_6// "SandboxAppDomainHelper.LoadPluginAssemb"...
0x542  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x547  throw
0x548  nop
0x549  ldc.i4.0
0x54a  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x54f  dup
0x550  ldc.i4.s 0x20
0x552  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x557  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x55c  pop
0x55d  ldc.i4.0
0x55e  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x563  stloc.0
0x564  ldloc.0
0x565  ldc.i4.8
0x566  callvirt instance void [mscorlib]System.Security.Permissions.FileIOPermission::set_AllLocalFiles(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess)
0x56b  dup
0x56c  ldloc.0
0x56d  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x572  pop
0x573  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x578  ldarg.0
0x579  ldarg.1
0x57a  ldarg.2
0x57b  ldc.i4.0
0x57c  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(unsigned int8[], unsigned int8[], valuetype [mscorlib]System.Security.SecurityContextSource)
0x581  stfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x586  ldarg.0
0x587  ldarg.0
0x588  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x58d  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x592  stfld    class [mscorlib]System.Reflection.AssemblyName Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_assemblyName
0x597  ldarg.0
0x598  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x59d  callvirt instance class [mscorlib]System.Security.Policy.Evidence [mscorlib]System.Reflection.Assembly::get_Evidence()
0x5a2  brfalse.s loc_5BA
0x5a4  ldarg.0
0x5a5  ldarg.0
0x5a6  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x5ab  callvirt instance class [mscorlib]System.Security.Policy.Evidence [mscorlib]System.Reflection.Assembly::get_Evidence()
0x5b0  callvirt T0x2B000001
0x5b5  stfld    class [mscorlib]System.Security.Policy.StrongName Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_strongName
0x5ba  leave.s  loc_5C2
0x5bc  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x5c1  endfinally
0x5c2  leave.s  loc_600
0x5c4  stloc.1
0x5c5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5ca  ldc.i4.1
0x5cb  ldc.i4.4
0x5cc  newarr   [mscorlib]System.Object
0x5d1  dup
0x5d2  ldc.i4.0
0x5d3  ldstr    aSandboxappdoma_7// "SandboxAppDomainHelper.LoadPluginAssemb"...
0x5d8  stelem.ref
0x5d9  dup
0x5da  ldc.i4.1
0x5db  ldloc.1
0x5dc  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x5e1  stelem.ref
0x5e2  dup
0x5e3  ldc.i4.2
0x5e4  ldstr    asc_38FC// ": "
0x5e9  stelem.ref
0x5ea  dup
0x5eb  ldc.i4.3
0x5ec  ldloc.1
0x5ed  callvirt instance string [mscorlib]System.Object::ToString()
0x5f2  stelem.ref
0x5f3  call     string [mscorlib]System.String::Concat(object[])
0x5f8  ldnull
0x5f9  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x5fe  rethrow
0x600  ldarg.0
0x601  ldfld    class [mscorlib]System.Reflection.AssemblyName Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_assemblyName
0x606  ret
```
