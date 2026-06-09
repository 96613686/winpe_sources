# Microsoft.Crm.Reporting.SetupReportServer::CreateRole

- ea: `0x7980`
- end: `0x7a18`
- name: `Microsoft.Crm.Reporting.SetupReportServer::CreateRole`
- size: `152`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7cc0`
- `0x7dc0`

## callees

- `0x140`
- `0x320`
- `0x4860`
- `0x4960`
- `0x7980`

## string_xrefs

- `0x79b5`: `Calling ReportingService.CreateRole to create role {0}`
- `0x79fc`: `rsRoleAlreadyExists`
- `0x7a0a`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x7980  ldarg.3
0x7981  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::get_Count()
0x7986  newarr   [mscorlib]System.String
0x798b  stloc.0
0x798c  ldc.i4.0
0x798d  stloc.1
0x798e  br.s     loc_79A5
0x7990  ldarg.3
0x7991  ldloc.1
0x7992  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask>::get_Item(!!T0)
0x7997  stloc.2
0x7998  ldloc.0
0x7999  ldloc.1
0x799a  ldloc.2
0x799b  callvirt instance string Microsoft.Crm.Reporting.CrmTask::get_TaskId()
0x79a0  stelem.ref
0x79a1  ldloc.1
0x79a2  ldc.i4.1
0x79a3  add
0x79a4  stloc.1
0x79a5  ldloc.1
0x79a6  ldarg.3
0x79a7  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::get_Count()
0x79ac  blt.s    loc_7990
0x79ae  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x79b3  ldc.i4.s 0x20
0x79b5  ldstr    aCallingReporti_21// "Calling ReportingService.CreateRole to "...
0x79ba  ldc.i4.1
0x79bb  newarr   [mscorlib]System.Object
0x79c0  dup
0x79c1  ldc.i4.0
0x79c2  ldarg.1
0x79c3  stelem.ref
0x79c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x79c9  ldarg.0
0x79ca  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x79cf  ldarg.1
0x79d0  ldarg.2
0x79d1  ldloc.0
0x79d2  callvirt instance void Microsoft.Crm.Reporting.IReportingService::CreateRole(string Name, string Description, string[] TaskIDs)
0x79d7  leave.s  loc_7A17
0x79d9  stloc.3
0x79da  ldloc.3
0x79db  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x79e0  stloc.s  4
0x79e2  ldloc.s  4
0x79e4  brfalse.s loc_7A08
0x79e6  ldloc.s  4
0x79e8  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x79ed  ldstr    aErrorcode// "ErrorCode"
0x79f2  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x79f7  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x79fc  ldstr    aRsrolealreadye// "rsRoleAlreadyExists"
0x7a01  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x7a06  brfalse.s loc_7A15
0x7a08  ldarg.0
0x7a09  ldloc.3
0x7a0a  ldstr    aCreaterole// "CreateRole"
0x7a0f  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x7a14  throw
0x7a15  leave.s  loc_7A17
0x7a17  ret
```
