# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::UnhandledExceptionHandler

- ea: `0x3a0`
- end: `0x4a6`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::UnhandledExceptionHandler`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x3a0`
- `0x1990`

## string_xrefs

- `0x481`: `SandboxAppDomainHelper.UnhandledExceptionHandler: Exception inside UnhandledExceptionHandler: {0}.  Original Exception: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.1
0x3a1  callvirt instance object [mscorlib]System.UnhandledExceptionEventArgs::get_ExceptionObject()
0x3a6  isinst   [mscorlib]System.Exception
0x3ab  stloc.0
0x3ac  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3b1  ldc.i4.1
0x3b2  ldstr    aSandboxappdoma_0// "SandboxAppDomainHelper.UnhandledExcepti"...
0x3b7  ldnull
0x3b8  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x3bd  ldloc.0
0x3be  brtrue.s loc_3C1
0x3c0  ret
0x3c1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3c6  ldc.i4.1
0x3c7  ldstr    aSandboxappdoma_1// "SandboxAppDomainHelper.UnhandledExcepti"...
0x3cc  ldloc.0
0x3cd  call     string [mscorlib]System.String::Format(string, object)
0x3d2  ldnull
0x3d3  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x3d8  ldloc.0
0x3d9  stsfld   class [mscorlib]System.Exception Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_crashException
0x3de  ldsfld   class [mscorlib]System.Threading.ManualResetEvent Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_crashEvent
0x3e3  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0x3e8  pop
0x3e9  ldloc.0
0x3ea  callvirt instance class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Exception::get_TargetSite()
0x3ef  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.MemberInfo::get_DeclaringType()
0x3f4  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x3f9  call     string [mscorlib]System.Environment::get_NewLine()
0x3fe  call     string [mscorlib]System.String::Concat(object, object)
0x403  stloc.1
0x404  ldloc.1
0x405  ldloc.0
0x406  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x40b  call     string [mscorlib]System.Environment::get_NewLine()
0x410  call     string [mscorlib]System.String::Concat(string, string, string)
0x415  stloc.1
0x416  ldloc.1
0x417  ldc.i4.0
0x418  ldloc.1
0x419  callvirt instance int32 [mscorlib]System.String::get_Length()
0x41e  ldc.i4   0x800
0x423  call     int32 [mscorlib]System.Math::Min(int32, int32)
0x428  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x42d  stloc.1
0x42e  ldc.i4.0
0x42f  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x434  dup
0x435  ldc.i4.2
0x436  newobj   instance void [mscorlib]System.Security.Permissions.SecurityPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.SecurityPermissionFlag)
0x43b  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x440  pop
0x441  ldc.i4.0
0x442  newobj   instance void [mscorlib]System.Security.Permissions.FileIOPermission::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x447  stloc.2
0x448  ldloc.2
0x449  ldc.i4.2
0x44a  callvirt instance void [mscorlib]System.Security.Permissions.FileIOPermission::set_AllLocalFiles(valuetype [mscorlib]System.Security.Permissions.FileIOPermissionAccess)
0x44f  dup
0x450  ldloc.2
0x451  callvirt instance class [mscorlib]System.Security.IPermission [mscorlib]System.Security.PermissionSet::AddPermission(class [mscorlib]System.Security.IPermission)
0x456  pop
0x457  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x45c  ldsfld   string Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_crashFile
0x461  ldloc.1
0x462  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x467  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x46c  ldc.i4.2
0x46d  ldstr    aSandboxappdoma_2// "SandboxAppDomainHelper.UnhandledExcepti"...
0x472  ldnull
0x473  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x478  leave.s  loc_4A5
0x47a  stloc.3
0x47b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x480  ldc.i4.1
0x481  ldstr    aSandboxappdoma_3// "SandboxAppDomainHelper.UnhandledExcepti"...
0x486  ldloc.3
0x487  callvirt instance string [mscorlib]System.Object::ToString()
0x48c  ldloc.0
0x48d  callvirt instance string [mscorlib]System.Object::ToString()
0x492  call     string [mscorlib]System.String::Format(string, object, object)
0x497  ldnull
0x498  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x49d  leave.s  loc_4A5
0x49f  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x4a4  endfinally
0x4a5  ret
```
