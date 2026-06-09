# Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::WriteWorkerExecutionRecord

- ea: `0x82a0`
- end: `0x868b`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::WriteWorkerExecutionRecord`
- size: `1003`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1420`
- `0x14d0`
- `0x30f0`
- `0x3440`
- `0x6ba0`
- `0x6bc0`
- `0x6cd0`
- `0x6cf0`
- `0x6d10`
- `0x81a0`
- `0x8200`
- `0x8220`
- `0x82a0`

## string_xrefs

- `0x82a7`: `WriteWorkerExecutionRecord: enter`
- `0x8488`: `CrashPluginId`
- `0x84a8`: `ProcessId`
- `0x84d8`: `PluginExecutionRecords`
- `0x84ff`: `PluginExecutionRecord`
- `0x850b`: `PluginTypeId`
- `0x861a`: `WriteWorkerExecutionRecord: fileName: {0}`
- `0x8646`: `WriteWorkerExecutionRecord: filePath: {0}`
- `0x8673`: `WriteWorkerExecutionRecord: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x82a0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x82a5  ldc.i4.s 0x21
0x82a7  ldstr    aWriteworkerexe// "WriteWorkerExecutionRecord: enter"
0x82ac  ldc.i4.0
0x82ad  newarr   [mscorlib]System.Object
0x82b2  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x82b7  ldc.i4.6
0x82b8  ldc.i4.0
0x82b9  call     T0x2B000008
0x82be  ldc.i4.0
0x82bf  bgt.s    loc_82C2
0x82c1  ret
0x82c2  nop
0x82c3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x82c8  stloc.0
0x82c9  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x82ce  stloc.1
0x82cf  ldloc.1
0x82d0  ldc.i4.1
0x82d1  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x82d6  ldloc.1
0x82d7  ldc.i4.1
0x82d8  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x82dd  ldloc.1
0x82de  ldc.i4.1
0x82df  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x82e4  ldloc.0
0x82e5  ldloc.1
0x82e6  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x82eb  stloc.s  4
0x82ed  ldloc.s  4
0x82ef  ldstr    aSandboxwxr// "SandboxWXR"
0x82f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x82f9  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x82fe  stloc.s  5
0x8300  ldloca.s 5
0x8302  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x8307  stloc.s  6
0x8309  ldloca.s 7
0x830b  ldstr    aAfbedd383ef541// "{AFBEDD38-3EF5-4153-B09F-D02D6C7EACC5}"
0x8310  call     instance void [mscorlib]System.Guid::.ctor(string)
0x8315  ldloc.s  4
0x8317  ldstr    aHeader// "Header"
0x831c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8321  ldloc.s  4
0x8323  ldstr    aFileversion// "FileVersion"
0x8328  ldloca.s 7
0x832a  constrained. [mscorlib]System.Guid
0x8330  callvirt instance string [mscorlib]System.Object::ToString()
0x8335  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x833a  ldloc.s  4
0x833c  ldstr    aMachine// "Machine"
0x8341  call     string [mscorlib]System.Environment::get_MachineName()
0x8346  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x834b  ldloc.s  4
0x834d  ldstr    aProcessinfo// "ProcessInfo"
0x8352  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x8357  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x835c  ldloc.s  4
0x835e  ldstr    aFileguid// "FileGuid"
0x8363  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x8368  stloc.s  8
0x836a  ldloca.s 8
0x836c  ldstr    aD// "D"
0x8371  call     instance string [mscorlib]System.Guid::ToString(string)
0x8376  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x837b  ldloc.s  4
0x837d  ldstr    aUtctimestamp// "UtcTimeStamp"
0x8382  ldc.i4.7
0x8383  newarr   [mscorlib]System.Object
0x8388  dup
0x8389  ldc.i4.0
0x838a  ldloca.s 5
0x838c  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x8391  box      [mscorlib]System.Int32
0x8396  stelem.ref
0x8397  dup
0x8398  ldc.i4.1
0x8399  ldstr    asc_1122C// ":"
0x839e  stelem.ref
0x839f  dup
0x83a0  ldc.i4.2
0x83a1  ldloca.s 5
0x83a3  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x83a8  box      [mscorlib]System.Int32
0x83ad  stelem.ref
0x83ae  dup
0x83af  ldc.i4.3
0x83b0  ldstr    asc_1122C// ":"
0x83b5  stelem.ref
0x83b6  dup
0x83b7  ldc.i4.4
0x83b8  ldloca.s 5
0x83ba  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x83bf  box      [mscorlib]System.Int32
0x83c4  stelem.ref
0x83c5  dup
0x83c6  ldc.i4.5
0x83c7  ldstr    asc_1122C// ":"
0x83cc  stelem.ref
0x83cd  dup
0x83ce  ldc.i4.6
0x83cf  ldloca.s 5
0x83d1  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0x83d6  box      [mscorlib]System.Int32
0x83db  stelem.ref
0x83dc  call     string [mscorlib]System.String::Concat(object[])
0x83e1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x83e6  ldloc.s  4
0x83e8  ldstr    aUtcdate// "UtcDate"
0x83ed  ldloca.s 5
0x83ef  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x83f4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x83f9  ldloc.s  4
0x83fb  ldstr    aUtctime// "UtcTime"
0x8400  ldloca.s 5
0x8402  call     instance string [mscorlib]System.DateTime::ToLongTimeString()
0x8407  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x840c  ldloc.s  4
0x840e  ldstr    aLocaldate// "LocalDate"
0x8413  ldloca.s 6
0x8415  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x841a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x841f  ldloc.s  4
0x8421  ldstr    aLocaltime// "LocalTime"
0x8426  ldloca.s 6
0x8428  call     instance string [mscorlib]System.DateTime::ToLongTimeString()
0x842d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8432  ldloc.s  4
0x8434  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x8439  ldloc.s  4
0x843b  ldstr    aSandboxworkere// "SandboxWorkerExecutionRecord"
0x8440  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8445  ldloc.s  4
0x8447  ldstr    aOrganizationid_0// "OrganizationId"
0x844c  ldarg.0
0x844d  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_OrganizationId()
0x8452  stloc.s  8
0x8454  ldloca.s 8
0x8456  ldstr    aD// "D"
0x845b  call     instance string [mscorlib]System.Guid::ToString(string)
0x8460  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8465  ldloc.s  4
0x8467  ldstr    aExitreason// "ExitReason"
0x846c  ldarg.0
0x846d  call     instance valuetype Microsoft.Crm.Sandbox.SandboxWorkerExitReason Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_ExitReason()
0x8472  stloc.s  9
0x8474  ldloca.s 9
0x8476  constrained. Microsoft.Crm.Sandbox.SandboxWorkerExitReason
0x847c  callvirt instance string [mscorlib]System.Object::ToString()
0x8481  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x8486  ldloc.s  4
0x8488  ldstr    aCrashpluginid// "CrashPluginId"
0x848d  ldarg.0
0x848e  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::get_CrashPluginId()
0x8493  stloc.s  8
0x8495  ldloca.s 8
0x8497  ldstr    aD// "D"
0x849c  call     instance string [mscorlib]System.Guid::ToString(string)
0x84a1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x84a6  ldloc.s  4
0x84a8  ldstr    aProcessid// "ProcessId"
0x84ad  ldarga.s 2
0x84af  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84b4  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x84b9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x84be  ldloc.s  4
0x84c0  ldstr    aWorkerlifetime// "WorkerLifetime"
0x84c5  ldarga.s 5
0x84c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x84cc  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x84d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x84d6  ldloc.s  4
0x84d8  ldstr    aPluginexecutio// "PluginExecutionRecords"
0x84dd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x84e2  ldarg.0
0x84e3  ldfld    class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord> Microsoft.Crm.Sandbox.SandboxWorkerExecutionRecord::_pluginExecutionRecords
0x84e8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::GetEnumerator()
0x84ed  stloc.s  0xA
0x84ef  br       loc_85B5
0x84f4  ldloc.s  0xA
0x84f6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord>::get_Current()
0x84fb  stloc.s  0xB
0x84fd  ldloc.s  4
0x84ff  ldstr    aPluginexecutio_0// "PluginExecutionRecord"
0x8504  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x8509  ldloc.s  4
0x850b  ldstr    aPlugintypeid// "PluginTypeId"
0x8510  ldloc.s  0xB
0x8512  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_PluginTypeId()
0x8517  stloc.s  8
0x8519  ldloca.s 8
0x851b  ldstr    aD// "D"
0x8520  call     instance string [mscorlib]System.Guid::ToString(string)
0x8525  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x852a  ldloc.s  4
0x852c  ldstr    aNumberofreques// "NumberOfRequests"
0x8531  ldloc.s  0xB
0x8533  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfRequests()
0x8538  stloc.s  0xC
0x853a  ldloca.s 0xC
0x853c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8541  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x8546  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x854b  ldloc.s  4
0x854d  ldstr    aNumberofbadreq// "NumberOfBadRequests"
0x8552  ldloc.s  0xB
0x8554  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_NumberOfBadRequests()
0x8559  stloc.s  0xC
0x855b  ldloca.s 0xC
0x855d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8562  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x8567  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x856c  ldloc.s  4
0x856e  ldstr    aTotalrequestti// "TotalRequestTimeInMSec"
0x8573  ldloc.s  0xB
0x8575  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxRequestCounter::get_TotalRequestTimeInMSec()
0x857a  stloc.s  0xC
0x857c  ldloca.s 0xC
0x857e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x8583  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x8588  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x858d  ldloc.s  4
0x858f  ldstr    aContribution// "Contribution"
0x8594  ldloc.s  0xB
0x8596  callvirt instance int64 Microsoft.Crm.Sandbox.SandboxPluginExecutionRecord::get_Contribution()
0x859b  stloc.s  0xC
0x859d  ldloca.s 0xC
0x859f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85a4  call     instance string [mscorlib]System.Int64::ToString(class [mscorlib]System.IFormatProvider)
0x85a9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x85ae  ldloc.s  4
0x85b0  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x85b5  ldloc.s  0xA
0x85b7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x85bc  brtrue   loc_84F4
0x85c1  leave.s  loc_85CF
0x85c3  ldloc.s  0xA
0x85c5  brfalse.s loc_85CE
0x85c7  ldloc.s  0xA
0x85c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85ce  endfinally
0x85cf  ldloc.s  4
0x85d1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x85d6  ldloc.s  4
0x85d8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x85dd  ldloc.s  4
0x85df  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x85e4  ldloc.s  4
0x85e6  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x85eb  leave.s  loc_85F9
0x85ed  ldloc.s  4
0x85ef  brfalse.s loc_85F8
0x85f1  ldloc.s  4
0x85f3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x85f8  endfinally
0x85f9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x85fe  ldstr    aSandboxwxr0Txt// "SandboxWXR.{0}.txt"
0x8603  ldc.i4.1
0x8604  newarr   [mscorlib]System.Object
0x8609  dup
0x860a  ldc.i4.0
0x860b  ldarg.1
0x860c  stelem.ref
0x860d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x8612  stloc.2
0x8613  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8618  ldc.i4.s 0x21
0x861a  ldstr    aWriteworkerexe_0// "WriteWorkerExecutionRecord: fileName: {"...
0x861f  ldc.i4.1
0x8620  newarr   [mscorlib]System.Object
0x8625  dup
0x8626  ldc.i4.0
0x8627  ldloc.2
0x8628  stelem.ref
0x8629  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x862e  call     string Microsoft.Crm.Sandbox.SandboxUtility::get_CrmServerInstallDirectory()
0x8633  ldstr    aTrace// "Trace"
0x8638  ldloc.2
0x8639  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x863e  stloc.3
0x863f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8644  ldc.i4.s 0x21
0x8646  ldstr    aWriteworkerexe_1// "WriteWorkerExecutionRecord: filePath: {"...
0x864b  ldc.i4.1
0x864c  newarr   [mscorlib]System.Object
0x8651  dup
0x8652  ldc.i4.0
0x8653  ldloc.3
0x8654  stelem.ref
0x8655  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x865a  ldloc.3
0x865b  ldloc.0
0x865c  callvirt instance string [mscorlib]System.Object::ToString()
0x8661  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x8666  leave.s  loc_868A
0x8668  stloc.s  0xD
0x866a  ldloc.s  0xD
0x866c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x8671  ldc.i4.s 0x21
  ... truncated ...
```
