# Microsoft.Crm.Sandbox.SandboxAssemblyCache::DeleteDirectory

- ea: `0x2670`
- end: `0x2703`
- name: `Microsoft.Crm.Sandbox.SandboxAssemblyCache::DeleteDirectory`
- size: `147`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x36a0`

## callees

- `0x2670`

## string_xrefs

- `0x2683`: `SandboxAssemblyCache.DeleteDirectory: OK`
- `0x26b5`: `SandboxAssemblyCache.DeleteDirectory: EXCEPTION {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2670  ldarg.0
0x2671  ldfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x2676  call     void [mscorlib]System.IO.Directory::Delete(string)
0x267b  ldarg.0
0x267c  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x2681  ldc.i4.s 0x22
0x2683  ldstr    aSandboxassembl_2// "SandboxAssemblyCache.DeleteDirectory: O"...
0x2688  ldc.i4.0
0x2689  newarr   [mscorlib]System.Object
0x268e  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2693  leave.s  loc_2702
0x2695  stloc.0
0x2696  ldloc.0
0x2697  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x269c  ldstr    asc_12434// ": "
0x26a1  ldloc.0
0x26a2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x26a7  call     string [mscorlib]System.String::Concat(object, object, object)
0x26ac  stloc.1
0x26ad  ldarg.0
0x26ae  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxAssemblyCache::_organizationId
0x26b3  ldc.i4.s 0x22
0x26b5  ldstr    aSandboxassembl_3// "SandboxAssemblyCache.DeleteDirectory: E"...
0x26ba  ldc.i4.1
0x26bb  newarr   [mscorlib]System.Object
0x26c0  dup
0x26c1  ldc.i4.0
0x26c2  ldloc.1
0x26c3  stelem.ref
0x26c4  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x26c9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x26ce  stloc.2
0x26cf  ldloc.2
0x26d0  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x26d5  ldc.i4.2
0x26d6  ldc.i4   0xC0004F0F
0x26db  conv.u8
0x26dc  ldc.i4.2
0x26dd  newarr   [mscorlib]System.Object
0x26e2  dup
0x26e3  ldc.i4.0
0x26e4  ldarg.0
0x26e5  ldfld    string Microsoft.Crm.Sandbox.SandboxAssemblyCache::_cachePath
0x26ea  stelem.ref
0x26eb  dup
0x26ec  ldc.i4.1
0x26ed  ldloc.1
0x26ee  stelem.ref
0x26ef  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x26f4  leave.s  loc_2700
0x26f6  ldloc.2
0x26f7  brfalse.s loc_26FF
0x26f9  ldloc.2
0x26fa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x26ff  endfinally
0x2700  leave.s  loc_2702
0x2702  ret
```
