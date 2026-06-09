# Microsoft.Crm.Sandbox.AssemblyAuthenticationContextWrapper::AcquireToken

- ea: `0xd70`
- end: `0xde0`
- name: `Microsoft.Crm.Sandbox.AssemblyAuthenticationContextWrapper::AcquireToken`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xd70`

## string_xrefs

- `0xd8d`: `Error in AcquireToken: {0}`
- `0xdb2`: `PSS: Unhandled exception in AssemblyAuthenticationContextWrapper.AcquireToken: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xd70  ldc.i4.1
0xd71  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xd76  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xd7b  ldarg.0
0xd7c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IAssemblyAuthenticationContext Microsoft.Crm.Sandbox.AssemblyAuthenticationContextWrapper::_fulltrustedAuthenticationContext
0xd81  ldarg.1
0xd82  ldarg.2
0xd83  ldarg.3
0xd84  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IAssemblyAuthenticationContext::AcquireToken(string, string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AuthenticationType)
0xd89  stloc.0
0xd8a  leave.s  loc_DDE
0xd8c  stloc.1
0xd8d  ldstr    aErrorInAcquire// "Error in AcquireToken: {0}"
0xd92  ldloc.1
0xd93  callvirt instance string [mscorlib]System.Exception::get_Message()
0xd98  call     string [mscorlib]System.String::Format(string, object)
0xd9d  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0xda2  call     class [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Capture(class [mscorlib]System.Exception)
0xda7  callvirt instance void [mscorlib]System.Runtime.ExceptionServices.ExceptionDispatchInfo::Throw()
0xdac  leave.s  loc_DDC
0xdae  stloc.2
0xdaf  ldloc.2
0xdb0  ldc.i4.s 0x1F
0xdb2  ldstr    aPssUnhandledEx// "PSS: Unhandled exception in AssemblyAut"...
0xdb7  ldc.i4.2
0xdb8  newarr   [mscorlib]System.Object
0xdbd  dup
0xdbe  ldc.i4.0
0xdbf  ldloc.2
0xdc0  callvirt instance string [mscorlib]System.Exception::get_Message()
0xdc5  stelem.ref
0xdc6  dup
0xdc7  ldc.i4.1
0xdc8  ldloc.2
0xdc9  callvirt instance string [mscorlib]System.Object::ToString()
0xdce  stelem.ref
0xdcf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdd4  rethrow
0xdd6  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xddb  endfinally
0xddc  ldnull
0xddd  ret
0xdde  ldloc.0
0xddf  ret
```
