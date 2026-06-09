# Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::CreateRole

- ea: `0x8510`
- end: `0x85c4`
- name: `Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::CreateRole`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x120`
- `0x140`
- `0x4960`
- `0x8510`

## string_xrefs

- `0x855e`: `Calling ReportingService.CreateRole to create role {0}`
- `0x85a7`: `rsRoleAlreadyExists`
- `0x85b6`: `CreateRole`

## pseudocode

```c

```

## disassembly

```asm
0x8510  ldarg.3
0x8511  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::get_Count()
0x8516  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.Task
0x851b  stloc.0
0x851c  ldc.i4.0
0x851d  stloc.1
0x851e  br.s     loc_854E
0x8520  ldarg.3
0x8521  ldloc.1
0x8522  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Reporting.CrmTask>::get_Item(!!T0)
0x8527  stloc.2
0x8528  newobj   instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.Task::.ctor()
0x852d  stloc.3
0x852e  ldloc.3
0x852f  ldloc.2
0x8530  callvirt instance string Microsoft.Crm.Reporting.CrmTask::get_TaskId()
0x8535  stfld    string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.Task::TaskID
0x853a  ldloc.3
0x853b  ldloc.2
0x853c  callvirt instance string Microsoft.Crm.Reporting.CrmTask::get_Name()
0x8541  stfld    string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.Task::Name
0x8546  ldloc.0
0x8547  ldloc.1
0x8548  ldloc.3
0x8549  stelem.ref
0x854a  ldloc.1
0x854b  ldc.i4.1
0x854c  add
0x854d  stloc.1
0x854e  ldloc.1
0x854f  ldarg.3
0x8550  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.Crm.Reporting.CrmTask>::get_Count()
0x8555  blt.s    loc_8520
0x8557  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x855c  ldc.i4.s 0x20
0x855e  ldstr    aCallingReporti_21// "Calling ReportingService.CreateRole to "...
0x8563  ldc.i4.1
0x8564  newarr   [mscorlib]System.Object
0x8569  dup
0x856a  ldc.i4.0
0x856b  ldarg.1
0x856c  stelem.ref
0x856d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x8572  ldarg.0
0x8573  ldfld    class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService Microsoft.Crm.Reporting.WorkgroupEditionSetupReportServer::_rs2000
0x8578  ldarg.1
0x8579  ldarg.2
0x857a  ldloc.0
0x857b  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.ReportingService::CreateRole(string, string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices.Task[])
0x8580  leave.s  loc_85C3
0x8582  stloc.s  4
0x8584  ldloc.s  4
0x8586  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x858b  stloc.s  5
0x858d  ldloc.s  5
0x858f  brfalse.s loc_85B3
0x8591  ldloc.s  5
0x8593  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x8598  ldstr    aErrorcode// "ErrorCode"
0x859d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x85a2  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x85a7  ldstr    aRsrolealreadye// "rsRoleAlreadyExists"
0x85ac  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x85b1  brfalse.s loc_85C1
0x85b3  ldarg.0
0x85b4  ldloc.s  4
0x85b6  ldstr    aCreaterole// "CreateRole"
0x85bb  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName)
0x85c0  throw
0x85c1  leave.s  loc_85C3
0x85c3  ret
```
