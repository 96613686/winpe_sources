# Microsoft.Crm.Sandbox.SandboxTrace::Trace

- ea: `0x1300`
- end: `0x1375`
- name: `Microsoft.Crm.Sandbox.SandboxTrace::Trace`
- size: `117`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1430`
- `0x1460`
- `0x14b0`
- `0x14e0`

## callees

- `0xd10`
- `0x1130`
- `0x1300`
- `0x14f0`
- `0x1740`

## string_xrefs

- `0x1335`: `_traceWriter`

## pseudocode

```c

```

## disassembly

```asm
0x1300  ldarg.2
0x1301  ldarg.3
0x1302  call     bool Microsoft.Crm.Sandbox.SandboxTrace::TraceEnabled(valuetype [System]System.Diagnostics.TraceLevel traceLevel, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory)
0x1307  brfalse.s loc_1374
0x1309  ldarg.1
0x130a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x130f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1314  brfalse.s loc_131D
0x1316  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxTrace::get_OrganizationId()
0x131b  starg.s  1
0x131d  ldarg.1
0x131e  ldarg.3
0x131f  ldarg.s  4
0x1321  callvirt instance var<u1> class [mscorlib]System.Func`1<string>::Invoke()
0x1326  ldnull
0x1327  ldloca.s 0
0x1329  ldloca.s 1
0x132b  call     void Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args, [out] string& newFormat, [out] object[]& newArgs)
0x1330  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x1335  ldstr    aTracewriter// "_traceWriter"
0x133a  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x133f  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x1344  ldarg.1
0x1345  ldarg.3
0x1346  ldarg.2
0x1347  ldc.i4.0
0x1348  ldloc.0
0x1349  ldloc.1
0x134a  callvirt instance void Microsoft.Crm.Sandbox.ISandboxTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x134f  ldarg.0
0x1350  brfalse.s loc_1374
0x1352  ldarg.1
0x1353  ldarg.3
0x1354  ldarg.0
0x1355  callvirt instance string [mscorlib]System.Object::ToString()
0x135a  ldnull
0x135b  ldloca.s 0
0x135d  ldloca.s 1
0x135f  call     void Microsoft.Crm.Sandbox.SandboxTrace::GetSandboxMessagePrefix(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args, [out] string& newFormat, [out] object[]& newArgs)
0x1364  ldsfld   class Microsoft.Crm.Sandbox.ISandboxTraceWriter Microsoft.Crm.Sandbox.SandboxTrace::_traceWriter
0x1369  ldarg.1
0x136a  ldarg.3
0x136b  ldarg.2
0x136c  ldc.i4.0
0x136d  ldloc.0
0x136e  ldloc.1
0x136f  callvirt instance void Microsoft.Crm.Sandbox.ISandboxTraceWriter::Write(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, valuetype [System]System.Diagnostics.TraceLevel traceLevel, int32 skipFrames, string format, object[] args)
0x1374  ret
```
