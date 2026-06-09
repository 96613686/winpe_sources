# Microsoft.Crm.Sandbox.SandboxHostSids::AddSid

- ea: `0x1bf0`
- end: `0x1d3c`
- name: `Microsoft.Crm.Sandbox.SandboxHostSids::AddSid`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x83d0`

## callees

- `0x1bf0`
- `0x8d40`
- `0x8d90`

## string_xrefs

- `0x1bf1`: `hostSidSddlForm`
- `0x1c2a`: `sidEntry`
- `0x1c3b`: `currentHostSidSddlForm`
- `0x1c56`: `SandboxHostSids.AddSid: Sandbox Host SID has changed: {0}; previous: {1}; new: {2}`
- `0x1cc3`: `SandboxHostSids.AddSid: {0}; hostSidSddlForm: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1bf0  ldarg.0
0x1bf1  ldstr    aHostsidsddlfor// "hostSidSddlForm"
0x1bf6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1bfb  ldarg.1
0x1bfc  ldstr    aMachinename// "machineName"
0x1c01  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1c06  ldarg.1
0x1c07  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1c0c  starg.s  1
0x1c0e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1c13  ldarg.1
0x1c14  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::ContainsKey(var<u1>)
0x1c19  brfalse  loc_1CBC
0x1c1e  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1c23  ldarg.1
0x1c24  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::get_Item(void)
0x1c29  dup
0x1c2a  ldstr    aSidentry// "sidEntry"
0x1c2f  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1c34  callvirt instance string SidEntry::get_AccountName()
0x1c39  stloc.1
0x1c3a  ldloc.1
0x1c3b  ldstr    aCurrenthostsid// "currentHostSidSddlForm"
0x1c40  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1c45  ldloc.1
0x1c46  ldarg.0
0x1c47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c4c  brfalse.s loc_1C4F
0x1c4e  ret
0x1c4f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1c54  ldc.i4.s 0x26
0x1c56  ldstr    aSandboxhostsid// "SandboxHostSids.AddSid: Sandbox Host SI"...
0x1c5b  ldc.i4.3
0x1c5c  newarr   [mscorlib]System.Object
0x1c61  dup
0x1c62  ldc.i4.0
0x1c63  ldarg.1
0x1c64  stelem.ref
0x1c65  dup
0x1c66  ldc.i4.1
0x1c67  ldloc.1
0x1c68  stelem.ref
0x1c69  dup
0x1c6a  ldc.i4.2
0x1c6b  ldarg.0
0x1c6c  stelem.ref
0x1c6d  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c72  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1c77  ldarg.1
0x1c78  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::Remove(var<u1>)
0x1c7d  pop
0x1c7e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::.ctor()
0x1c83  stloc.2
0x1c84  ldloc.2
0x1c85  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_EventSource()
0x1c8a  ldc.i4.2
0x1c8b  ldc.i4   0x80004F1C
0x1c90  conv.u8
0x1c91  ldc.i4.4
0x1c92  newarr   [mscorlib]System.Object
0x1c97  dup
0x1c98  ldc.i4.0
0x1c99  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x1c9e  stelem.ref
0x1c9f  dup
0x1ca0  ldc.i4.1
0x1ca1  ldarg.1
0x1ca2  stelem.ref
0x1ca3  dup
0x1ca4  ldc.i4.2
0x1ca5  ldloc.1
0x1ca6  stelem.ref
0x1ca7  dup
0x1ca8  ldc.i4.3
0x1ca9  ldarg.0
0x1caa  stelem.ref
0x1cab  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmEventLog::WriteEntry(string, valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x1cb0  leave.s  loc_1CBC
0x1cb2  ldloc.2
0x1cb3  brfalse.s loc_1CBB
0x1cb5  ldloc.2
0x1cb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cbb  endfinally
0x1cbc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1cc1  ldc.i4.s 0x26
0x1cc3  ldstr    aSandboxhostsid_0// "SandboxHostSids.AddSid: {0}; hostSidSdd"...
0x1cc8  ldc.i4.2
0x1cc9  newarr   [mscorlib]System.Object
0x1cce  dup
0x1ccf  ldc.i4.0
0x1cd0  ldarg.1
0x1cd1  stelem.ref
0x1cd2  dup
0x1cd3  ldc.i4.1
0x1cd4  ldarg.0
0x1cd5  stelem.ref
0x1cd6  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1cdb  ldarg.0
0x1cdc  ldc.i4.1
0x1cdd  newarr   [mscorlib]System.Char
0x1ce2  dup
0x1ce3  ldc.i4.0
0x1ce4  ldc.i4.s 0x3B
0x1ce6  stelem.i2
0x1ce7  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1cec  dup
0x1ced  ldlen
0x1cee  conv.i4
0x1cef  ldc.i4.2
0x1cf0  ceq
0x1cf2  ldstr    aPartsLength2// "parts.Length != 2"
0x1cf7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x1cfc  dup
0x1cfd  ldc.i4.0
0x1cfe  ldelem.ref
0x1cff  ldstr    aParts0// "parts[0]"
0x1d04  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1d09  dup
0x1d0a  ldc.i4.1
0x1d0b  ldelem.ref
0x1d0c  ldstr    aParts1// "parts[1]"
0x1d11  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1d16  ldc.i4.1
0x1d17  ldelem.ref
0x1d18  newobj   instance void [mscorlib]System.Security.Principal.SecurityIdentifier::.ctor(string)
0x1d1d  stloc.0
0x1d1e  ldloc.0
0x1d1f  ldstr    aSid// "sid"
0x1d24  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1d29  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry> Microsoft.Crm.Sandbox.SandboxHostSids::_sids
0x1d2e  ldarg.1
0x1d2f  ldloc.0
0x1d30  ldarg.0
0x1d31  newobj   instance void SidEntry::.ctor(class [mscorlib]System.Security.Principal.SecurityIdentifier sid, string accountName)
0x1d36  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class SidEntry>::set_Item(var<u1>, !!T0)
0x1d3b  ret
```
