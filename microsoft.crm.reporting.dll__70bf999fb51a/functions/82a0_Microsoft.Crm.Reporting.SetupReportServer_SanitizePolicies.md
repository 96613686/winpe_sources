# Microsoft.Crm.Reporting.SetupReportServer::SanitizePolicies

- ea: `0x82a0`
- end: `0x833b`
- name: `Microsoft.Crm.Reporting.SetupReportServer::SanitizePolicies`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x7af0`

## callees

- `0x300`
- `0x4860`
- `0x82a0`

## string_xrefs

- `0x82dc`: `Ignoring SoapException returned from attempting to set policies for user/group {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x82a0  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x82a5  stloc.0
0x82a6  ldc.i4.0
0x82a7  stloc.2
0x82a8  br.s     loc_8302
0x82aa  ldc.i4.1
0x82ab  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy
0x82b0  stloc.3
0x82b1  ldloc.3
0x82b2  ldc.i4.0
0x82b3  ldarg.2
0x82b4  ldloc.2
0x82b5  ldelem.ref
0x82b6  stelem.ref
0x82b7  ldarg.0
0x82b8  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x82bd  ldarg.1
0x82be  ldloc.3
0x82bf  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetPolicies(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy[] Policies)
0x82c4  ldloc.0
0x82c5  ldloc.2
0x82c6  box      [mscorlib]System.Int32
0x82cb  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x82d0  pop
0x82d1  leave.s  loc_82FE
0x82d3  stloc.s  4
0x82d5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x82da  ldc.i4.s 0x20
0x82dc  ldstr    aIgnoringSoapex// "Ignoring SoapException returned from at"...
0x82e1  ldc.i4.2
0x82e2  newarr   [mscorlib]System.Object
0x82e7  dup
0x82e8  ldc.i4.0
0x82e9  ldloc.3
0x82ea  ldc.i4.0
0x82eb  ldelem.ref
0x82ec  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy::get_GroupUserName()
0x82f1  stelem.ref
0x82f2  dup
0x82f3  ldc.i4.1
0x82f4  ldloc.s  4
0x82f6  stelem.ref
0x82f7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x82fc  leave.s  loc_82FE
0x82fe  ldloc.2
0x82ff  ldc.i4.1
0x8300  add
0x8301  stloc.2
0x8302  ldloc.2
0x8303  ldarg.2
0x8304  ldlen
0x8305  conv.i4
0x8306  blt.s    loc_82AA
0x8308  ldloc.0
0x8309  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x830e  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.Policy
0x8313  stloc.1
0x8314  ldc.i4.0
0x8315  stloc.s  5
0x8317  br.s     loc_8332
0x8319  ldloc.1
0x831a  ldloc.s  5
0x831c  ldarg.2
0x831d  ldloc.0
0x831e  ldloc.s  5
0x8320  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x8325  unbox.any [mscorlib]System.Int32
0x832a  ldelem.ref
0x832b  stelem.ref
0x832c  ldloc.s  5
0x832e  ldc.i4.1
0x832f  add
0x8330  stloc.s  5
0x8332  ldloc.s  5
0x8334  ldloc.1
0x8335  ldlen
0x8336  conv.i4
0x8337  blt.s    loc_8319
0x8339  ldloc.1
0x833a  ret
```
