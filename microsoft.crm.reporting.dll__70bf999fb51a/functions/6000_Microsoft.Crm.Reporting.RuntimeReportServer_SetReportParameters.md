# Microsoft.Crm.Reporting.RuntimeReportServer::SetReportParameters

- ea: `0x6000`
- end: `0x633a`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::SetReportParameters`
- size: `826`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x290`
- `0x2a0`
- `0x4860`
- `0x4970`
- `0x6000`
- `0x6880`
- `0x6bf0`
- `0x6d70`

## string_xrefs

- `0x6068`: `Calling ReportingService.GetItemParameters on: {0}.`
- `0x6224`: `Calling ReportingService.GetItemParameters on: {0}.`
- `0x60c8`: `GetItemParameters`
- `0x6251`: `GetItemParameters`
- `0x62ea`: `Calling ReportingService.SetItemParameters on: {0}.`
- `0x6312`: `SetItemParameters`

## pseudocode

```c

```

## disassembly

```asm
0x6000  ldarg.2
0x6001  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6006  brfalse.s loc_601B
0x6008  ldarg.3
0x6009  brfalse.s loc_6014
0x600b  ldarg.3
0x600c  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x6011  ldc.i4.0
0x6012  bgt.s    loc_601B
0x6014  ldc.i4.0
0x6015  newarr   [mscorlib]System.String
0x601a  ret
0x601b  ldarg.1
0x601c  ldstr    aReportnameonsr_0// "reportNameOnSrs"
0x6021  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x6026  ldarg.0
0x6027  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x602c  ldarg.1
0x602d  ldarg.s  4
0x602f  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::GetItemPath(string, bool)
0x6034  stloc.0
0x6035  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x603a  stloc.1
0x603b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::.ctor()
0x6040  stloc.2
0x6041  ldarg.2
0x6042  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x6047  brtrue.s loc_6055
0x6049  ldloc.2
0x604a  ldarg.2
0x604b  call     class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Microsoft.Crm.Reporting.RuntimeReportServer::DeserializeCrmParameterValues(string parametersXml)
0x6050  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x6055  ldarg.3
0x6056  brfalse.s loc_605F
0x6058  ldloc.2
0x6059  ldarg.3
0x605a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x605f  ldnull
0x6060  stloc.3
0x6061  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6066  ldc.i4.s 0x20
0x6068  ldstr    aCallingReporti_9// "Calling ReportingService.GetItemParamet"...
0x606d  ldc.i4.1
0x606e  newarr   [mscorlib]System.Object
0x6073  dup
0x6074  ldc.i4.0
0x6075  ldloc.0
0x6076  stelem.ref
0x6077  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x607c  ldarg.0
0x607d  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6082  ldloc.0
0x6083  ldnull
0x6084  ldc.i4.1
0x6085  ldloc.2
0x6086  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::ToArray()
0x608b  ldnull
0x608c  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6091  stloc.3
0x6092  leave.s  loc_60DA
0x6094  stloc.s  6
0x6096  ldloc.s  6
0x6098  isinst   [System.Web.Services]System.Web.Services.Protocols.SoapException
0x609d  stloc.s  7
0x609f  ldloc.s  7
0x60a1  brfalse.s loc_60C5
0x60a3  ldloc.s  7
0x60a5  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Web.Services]System.Web.Services.Protocols.SoapException::get_Detail()
0x60aa  ldstr    aErrorcode// "ErrorCode"
0x60af  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlNode::get_Item(string)
0x60b4  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x60b9  ldstr    aRsreportparame// "rsReportParameterTypeMismatch"
0x60be  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x60c3  brfalse.s loc_60D8
0x60c5  ldarg.0
0x60c6  ldloc.s  6
0x60c8  ldstr    aGetitemparamet// "GetItemParameters"
0x60cd  ldc.i4   0x80048323
0x60d2  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x60d7  throw
0x60d8  leave.s  loc_60DA
0x60da  ldloc.2
0x60db  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x60e0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::.ctor(int32)
0x60e5  stloc.s  4
0x60e7  ldloc.2
0x60e8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x60ed  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x60f2  stloc.s  5
0x60f4  ldloc.3
0x60f5  brfalse  loc_619D
0x60fa  ldloc.3
0x60fb  ldlen
0x60fc  conv.i4
0x60fd  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor(int32)
0x6102  stloc.s  8
0x6104  ldloc.3
0x6105  stloc.s  9
0x6107  ldc.i4.0
0x6108  stloc.s  0xA
0x610a  br.s     loc_6129
0x610c  ldloc.s  9
0x610e  ldloc.s  0xA
0x6110  ldelem.ref
0x6111  stloc.s  0xB
0x6113  ldloc.s  8
0x6115  ldloc.s  0xB
0x6117  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Name()
0x611c  ldloc.s  0xB
0x611e  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x6123  ldloc.s  0xA
0x6125  ldc.i4.1
0x6126  add
0x6127  stloc.s  0xA
0x6129  ldloc.s  0xA
0x612b  ldloc.s  9
0x612d  ldlen
0x612e  conv.i4
0x612f  blt.s    loc_610C
0x6131  ldloc.2
0x6132  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::GetEnumerator()
0x6137  stloc.s  0xC
0x6139  br.s     loc_6184
0x613b  ldloca.s 0xC
0x613d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Current()
0x6142  stloc.s  0xD
0x6144  ldloc.s  8
0x6146  ldloc.s  0xD
0x6148  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Name()
0x614d  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x6152  castclass [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter
0x6157  stloc.s  0xE
0x6159  ldloc.s  0xD
0x615b  ldloc.s  0xE
0x615d  call     bool Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue pv, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter rp)
0x6162  brfalse.s loc_6176
0x6164  ldloc.s  4
0x6166  ldloc.s  0xD
0x6168  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Name()
0x616d  ldloc.s  0xD
0x616f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::Add(var<u1>, !!T0)
0x6174  br.s     loc_6184
0x6176  ldloc.s  5
0x6178  ldloc.s  0xE
0x617a  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Prompt()
0x617f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6184  ldloca.s 0xC
0x6186  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::MoveNext()
0x618b  brtrue.s loc_613B
0x618d  leave.s  loc_61F1
0x618f  ldloca.s 0xC
0x6191  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>
0x6197  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x619c  endfinally
0x619d  ldloc.2
0x619e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::GetEnumerator()
0x61a3  stloc.s  0xC
0x61a5  br.s     loc_61D8
0x61a7  ldloca.s 0xC
0x61a9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Current()
0x61ae  stloc.s  0xF
0x61b0  ldarg.0
0x61b1  ldloc.s  0xF
0x61b3  ldloc.0
0x61b4  ldloca.s 0x10
0x61b6  call     instance bool Microsoft.Crm.Reporting.RuntimeReportServer::IsParameterValid(class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue pv, string reportPath, [out] string& prompt)
0x61bb  brfalse.s loc_61CF
0x61bd  ldloc.s  4
0x61bf  ldloc.s  0xF
0x61c1  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Name()
0x61c6  ldloc.s  0xF
0x61c8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::Add(var<u1>, !!T0)
0x61cd  br.s     loc_61D8
0x61cf  ldloc.s  5
0x61d1  ldloc.s  0x10
0x61d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x61d8  ldloca.s 0xC
0x61da  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::MoveNext()
0x61df  brtrue.s loc_61A7
0x61e1  leave.s  loc_61F1
0x61e3  ldloca.s 0xC
0x61e5  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>
0x61eb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x61f0  endfinally
0x61f1  ldloc.s  4
0x61f3  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x61f8  ldloc.2
0x61f9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x61fe  bgt.s    loc_6261
0x6200  ldloc.s  4
0x6202  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Count()
0x6207  newarr   [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue
0x620c  stloc.s  0x11
0x620e  ldloc.s  4
0x6210  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::get_Values()
0x6215  ldloc.s  0x11
0x6217  ldc.i4.0
0x6218  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::CopyTo(var<u1>[], void)
0x621d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6222  ldc.i4.s 0x20
0x6224  ldstr    aCallingReporti_9// "Calling ReportingService.GetItemParamet"...
0x6229  ldc.i4.1
0x622a  newarr   [mscorlib]System.Object
0x622f  dup
0x6230  ldc.i4.0
0x6231  ldloc.0
0x6232  stelem.ref
0x6233  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x6238  ldarg.0
0x6239  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x623e  ldloc.0
0x623f  ldnull
0x6240  ldc.i4.1
0x6241  ldloc.s  0x11
0x6243  ldnull
0x6244  callvirt instance class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Microsoft.Crm.Reporting.IReportingService::GetItemParameters(string ItemPath, string HistoryID, bool ForRendering, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue[] Values, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.DataSourceCredentials[] Credentials)
0x6249  stloc.3
0x624a  leave.s  loc_6261
0x624c  stloc.s  0x12
0x624e  ldarg.0
0x624f  ldloc.s  0x12
0x6251  ldstr    aGetitemparamet// "GetItemParameters"
0x6256  ldc.i4   0x80048323
0x625b  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
0x6260  throw
0x6261  ldloc.3
0x6262  stloc.s  9
0x6264  ldc.i4.0
0x6265  stloc.s  0xA
0x6267  br.s     loc_62DB
0x6269  ldloc.s  9
0x626b  ldloc.s  0xA
0x626d  ldelem.ref
0x626e  stloc.s  0x13
0x6270  ldnull
0x6271  stloc.s  0x14
0x6273  ldloc.s  4
0x6275  ldloc.s  0x13
0x6277  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Name()
0x627c  ldloca.s 0x14
0x627e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue>::TryGetValue(var<u1>, !!T0)
0x6283  brfalse.s loc_62D5
0x6285  ldloc.s  0x14
0x6287  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Value()
0x628c  brtrue.s loc_62B3
0x628e  ldloc.s  0x13
0x6290  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_ParameterTypeName()
0x6295  ldstr    aString// "String"
0x629a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x629f  brfalse.s loc_62B3
0x62a1  ldloc.s  0x13
0x62a3  callvirt instance bool [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_NullableSpecified()
0x62a8  brfalse.s loc_62B3
0x62aa  ldloc.s  0x13
0x62ac  callvirt instance bool [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::get_Nullable()
0x62b1  brfalse.s loc_62BC
0x62b3  ldloc.s  0x14
0x62b5  callvirt instance string [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ParameterValue::get_Value()
0x62ba  br.s     loc_62C1
0x62bc  ldsfld   string [mscorlib]System.String::Empty
0x62c1  stloc.s  0x15
0x62c3  ldloc.s  0x13
0x62c5  ldc.i4.1
0x62c6  newarr   [mscorlib]System.String
0x62cb  dup
0x62cc  ldc.i4.0
0x62cd  ldloc.s  0x15
0x62cf  stelem.ref
0x62d0  callvirt instance void [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter::set_DefaultValues(string[])
0x62d5  ldloc.s  0xA
0x62d7  ldc.i4.1
0x62d8  add
0x62d9  stloc.s  0xA
0x62db  ldloc.s  0xA
0x62dd  ldloc.s  9
0x62df  ldlen
0x62e0  conv.i4
0x62e1  blt.s    loc_6269
0x62e3  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x62e8  ldc.i4.s 0x20
0x62ea  ldstr    aCallingReporti_10// "Calling ReportingService.SetItemParamet"...
0x62ef  ldc.i4.1
0x62f0  newarr   [mscorlib]System.Object
0x62f5  dup
0x62f6  ldc.i4.0
0x62f7  ldloc.0
0x62f8  stelem.ref
0x62f9  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x62fe  ldarg.0
0x62ff  call     instance class Microsoft.Crm.Reporting.IReportingService Microsoft.Crm.Reporting.ReportServer::get_ReportingService()
0x6304  ldloc.0
0x6305  ldloc.3
0x6306  callvirt instance void Microsoft.Crm.Reporting.IReportingService::SetItemParameters(string ItemPath, class [Microsoft.Crm.ReportingServices]Microsoft.Crm.ReportingServices2010.ItemParameter[] Parameters)
0x630b  leave.s  loc_6322
0x630d  stloc.s  0x16
0x630f  ldarg.0
0x6310  ldloc.s  0x16
0x6312  ldstr    aSetitemparamet// "SetItemParameters"
0x6317  ldc.i4   0x80048324
0x631c  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmReportingException Microsoft.Crm.Reporting.ReportServer::CreateCrmReportingException(class [mscorlib]System.Exception innerException, string methodName, int32 errorCode)
  ... truncated ...
```
