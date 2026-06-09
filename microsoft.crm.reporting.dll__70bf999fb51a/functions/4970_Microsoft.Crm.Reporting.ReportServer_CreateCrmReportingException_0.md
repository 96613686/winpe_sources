# Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException_0

- ea: `0x4970`
- end: `0x4a16`
- name: `Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException_0`
- size: `166`
- prototype: ``
- caller_count: `22`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4960`
- `0x4a20`
- `0x4ab0`
- `0x4d00`
- `0x4dc0`
- `0x4f30`
- `0x5980`
- `0x5bf0`
- `0x5e70`
- `0x6000`
- `0x6340`
- `0x6460`
- `0x66c0`
- `0x6700`
- `0x6d10`
- `0x6d70`
- `0x6e70`
- `0x6f70`
- `0x70a0`
- `0x7130`
- `0x72d0`
- `0x77e0`

## callees

- `0x1c0`
- `0x47d0`
- `0x4860`
- `0x4970`
- `0x4fe0`

## pseudocode

```c

```

## disassembly

```asm
0x4970  ldarg.1
0x4971  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x4976  stloc.0
0x4977  ldloc.0
0x4978  brtrue.s loc_4982
0x497a  ldarg.1
0x497b  callvirt instance string [mscorlib]System.Exception::get_Message()
0x4980  br.s     loc_4997
0x4982  ldloc.0
0x4983  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x4988  ldstr    aMessage// "Message"
0x498d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x4992  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x4997  stloc.1
0x4998  ldarg.0
0x4999  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x499e  brfalse.s loc_49AD
0x49a0  ldarg.0
0x49a1  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x49a6  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x49ab  brtrue.s loc_49B4
0x49ad  ldstr    aNotfound// "[NotFound]"
0x49b2  br.s     loc_49BF
0x49b4  ldarg.0
0x49b5  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x49ba  callvirt instance string Microsoft.Crm.Reporting.IReportingService::get_Url()
0x49bf  stloc.2
0x49c0  ldarg.0
0x49c1  call     instance bool Microsoft.Crm.Reporting.ReportServer::get_LogErrorsToEventLog()
0x49c6  brfalse.s loc_49F7
0x49c8  ldloc.0
0x49c9  brtrue.s loc_49D3
0x49cb  ldc.i4   0xC0004E00
0x49d0  conv.u8
0x49d1  br.s     loc_49D9
0x49d3  ldc.i4   0xC0004E01
0x49d8  conv.u8
0x49d9  stloc.3
0x49da  ldstr    aMscrmreporting// "MSCRMReporting"
0x49df  ldloc.3
0x49e0  ldc.i4.3
0x49e1  newarr   [mscorlib]System.String
0x49e6  dup
0x49e7  ldc.i4.0
0x49e8  ldarg.2
0x49e9  stelem.ref
0x49ea  dup
0x49eb  ldc.i4.1
0x49ec  ldloc.2
0x49ed  stelem.ref
0x49ee  dup
0x49ef  ldc.i4.2
0x49f0  ldloc.1
0x49f1  stelem.ref
0x49f2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::WriteEventError(string, int64, string[])
0x49f7  ldarg.3
0x49f8  call     bool Microsoft.Crm.Reporting.SRSReportUtility::IsSafeToShowSrsErrors(int32 errorCode)
0x49fd  brfalse.s loc_4A08
0x49ff  ldloc.1
0x4a00  ldarg.1
0x4a01  ldarg.3
0x4a02  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(string, class [mscorlib]System.Exception, int32)
0x4a07  ret
0x4a08  ldarg.1
0x4a09  ldarg.3
0x4a0a  ldc.i4.0
0x4a0b  newarr   [mscorlib]System.Object
0x4a10  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException::.ctor(class [mscorlib]System.Exception, int32, object[])
0x4a15  ret
```
