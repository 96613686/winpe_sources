# Microsoft.Crm.Sandbox.SandboxAppDomainHelper::CreateSandboxCodeUnit

- ea: `0x720`
- end: `0x7a6`
- name: `Microsoft.Crm.Sandbox.SandboxAppDomainHelper::CreateSandboxCodeUnit`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7b0`
- `0x1240`

## callees

- `0x720`
- `0x1990`

## string_xrefs

- `0x728`: `SandboxAppDomainHelper.CreateSandboxCodeUnit: enter`
- `0x777`: `SandboxAppDomainHelper.CreateSandboxCodeUnit: exception: `

## pseudocode

```c

```

## disassembly

```asm
0x720  ldnull
0x721  stloc.0
0x722  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x727  ldc.i4.3
0x728  ldstr    aSandboxappdoma_9// "SandboxAppDomainHelper.CreateSandboxCod"...
0x72d  ldnull
0x72e  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x733  ldc.i4.1
0x734  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x739  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0x73e  ldarg.1
0x73f  ldnull
0x740  call     bool [mscorlib]System.Reflection.ConstructorInfo::op_Inequality(class [mscorlib]System.Reflection.ConstructorInfo, class [mscorlib]System.Reflection.ConstructorInfo)
0x745  brfalse.s loc_751
0x747  ldarg.1
0x748  ldarg.2
0x749  callvirt instance object [mscorlib]System.Reflection.ConstructorInfo::Invoke(object[])
0x74e  stloc.0
0x74f  br.s     loc_75E
0x751  ldarg.0
0x752  ldfld    class [mscorlib]System.Reflection.Assembly Microsoft.Crm.Sandbox.SandboxAppDomainHelper::_loadedAssembly
0x757  ldarg.3
0x758  callvirt instance object [mscorlib]System.Reflection.Assembly::CreateInstance(string)
0x75d  stloc.0
0x75e  leave.s  loc_766
0x760  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x765  endfinally
0x766  leave.s  loc_7A4
0x768  stloc.1
0x769  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x76e  ldc.i4.1
0x76f  ldc.i4.4
0x770  newarr   [mscorlib]System.Object
0x775  dup
0x776  ldc.i4.0
0x777  ldstr    aSandboxappdoma_10// "SandboxAppDomainHelper.CreateSandboxCod"...
0x77c  stelem.ref
0x77d  dup
0x77e  ldc.i4.1
0x77f  ldloc.1
0x780  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x785  stelem.ref
0x786  dup
0x787  ldc.i4.2
0x788  ldstr    asc_38FC// ": "
0x78d  stelem.ref
0x78e  dup
0x78f  ldc.i4.3
0x790  ldloc.1
0x791  callvirt instance string [mscorlib]System.Object::ToString()
0x796  stelem.ref
0x797  call     string [mscorlib]System.String::Concat(object[])
0x79c  ldnull
0x79d  call     void Microsoft.Crm.Sandbox.SandboxRestrictedTrace::Trace(valuetype [mscorlib]System.Guid orgId, valuetype [System]System.Diagnostics.TraceLevel traceLevel, string message, [opt] string traceCategory)
0x7a2  rethrow
0x7a4  ldloc.0
0x7a5  ret
```
