# Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogOrganizationSuccess

- ea: `0x5dc0`
- end: `0x5e19`
- name: `Microsoft.Crm.Asynchronous.AsyncEventLogHelper::LogOrganizationSuccess`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x103c0`

## callees

- `0x5dc0`

## string_xrefs

- `0x5dfa`: `Recovered from failure accessing organization {0}. `

## pseudocode

```c

```

## disassembly

```asm
0x5dc0  ldarg.1
0x5dc1  ldc.i4.0
0x5dc2  callvirt instance bool [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::SetErrorFlag(bool)
0x5dc7  brfalse.s loc_5E18
0x5dc9  ldarg.0
0x5dca  ldc.i4.4
0x5dcb  ldc.i4   0x40004408
0x5dd0  conv.i8
0x5dd1  ldc.i4.2
0x5dd2  newarr   [mscorlib]System.Object
0x5dd7  dup
0x5dd8  ldc.i4.0
0x5dd9  call     string [mscorlib]System.Environment::get_MachineName()
0x5dde  stelem.ref
0x5ddf  dup
0x5de0  ldc.i4.1
0x5de1  ldarg.1
0x5de2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5de7  box      [mscorlib]System.Guid
0x5dec  stelem.ref
0x5ded  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.ICrmEventLog::WriteEntry(valuetype [System]System.Diagnostics.EventLogEntryType, int64, object[])
0x5df2  ldarg.1
0x5df3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5df8  ldc.i4.s 0x15
0x5dfa  ldstr    aRecoveredFromF// "Recovered from failure accessing organi"...
0x5dff  ldc.i4.1
0x5e00  newarr   [mscorlib]System.Object
0x5e05  dup
0x5e06  ldc.i4.0
0x5e07  ldarg.1
0x5e08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Workflow]Microsoft.Crm.Asynchronous.IOrganizationConfiguration::get_OrganizationId()
0x5e0d  box      [mscorlib]System.Guid
0x5e12  stelem.ref
0x5e13  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5e18  ret
```
