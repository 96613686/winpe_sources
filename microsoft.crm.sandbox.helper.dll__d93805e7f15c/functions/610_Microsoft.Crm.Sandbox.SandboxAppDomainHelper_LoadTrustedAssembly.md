# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadTrustedAssembly

- ea: `0x610`
- end: `0x717`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::LoadTrustedAssembly`
- size: `263`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1f0`

## callees

- `0x340`
- `0x610`
- `0x1990`

## string_xrefs

- `0x691`: `{0}.dll`

## pseudocode

```c

```

## disassembly

```asm
0x610  call     class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.Crm.Sandbox.SandboxAppDomainHelper::get_TrustedAssemblies()
0x615  ldarg.0
0x616  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x61b  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<string>::Contains(var<u1>)
0x620  brtrue.s loc_629
0x622  ldnull
0x623  stloc.0
0x624  leave    loc_715
0x629  nop
0x62a  ldc.i4.0
0x62b  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x630  dup
0x631  ldc.i4.s 0x20
0x633  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x638  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x63d  pop
0x63e  ldc.i4.1
0x63f  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x644  stloc.1
0x645  dup
0x646  ldloc.1
0x647  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x64c  pop
0x64d  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x652  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x657  stloc.2
0x658  ldloc.2
0x659  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x65e  dup
0x65f  ldarg.0
0x660  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x665  callvirt instance void [mscorlib]System.Reflection.AssemblyName::set_Name(string)
0x66a  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x66f  ldarg.0
0x670  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x675  call     bool [mscorlib]System.String::op_Equality(string, string)
0x67a  brfalse.s loc_6CC
0x67c  ldloc.2
0x67d  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x682  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x687  callvirt instance string [mscorlib]System.IO.FileInfo::get_DirectoryName()
0x68c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x691  ldstr    a0Dll// "{0}.dll"
0x696  ldc.i4.1
0x697  newarr   [mscorlib]System.Object
0x69c  dup
0x69d  ldc.i4.0
0x69e  ldarg.0
0x69f  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x6a4  stelem.ref
0x6a5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6aa  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x6af  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x6b4  stloc.3
0x6b5  ldloc.3
0x6b6  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x6bb  ldarg.0
0x6bc  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_FullName()
0x6c1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6c6  brfalse.s loc_6CC
0x6c8  ldloc.3
0x6c9  stloc.0
0x6ca  leave.s  loc_715
0x6cc  ldnull
0x6cd  stloc.0
0x6ce  leave.s  loc_715
0x6d0  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x6d5  endfinally
0x6d6  stloc.s  4
0x6d8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x6dd  ldc.i4.1
0x6de  ldc.i4.4
0x6df  newarr   [mscorlib]System.Object
0x6e4  dup
0x6e5  ldc.i4.0
0x6e6  ldstr    aSandboxappdoma_8// "SandboxAppDomainHelper.LoadSandboxAssem"...
0x6eb  stelem.ref
0x6ec  dup
0x6ed  ldc.i4.1
0x6ee  ldloc.s  4
0x6f0  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x6f5  stelem.ref
0x6f6  dup
0x6f7  ldc.i4.2
0x6f8  ldstr    asc_38FC// ": "
0x6fd  stelem.ref
0x6fe  dup
0x6ff  ldc.i4.3
0x700  ldloc.s  4
0x702  callvirt instance string [mscorlib]System.Object::ToString()
0x707  stelem.ref
0x708  call     string [mscorlib]System.String::Concat(object[])
0x70d  ldnull
0x70e  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x713  rethrow
0x715  ldloc.0
0x716  ret
```
