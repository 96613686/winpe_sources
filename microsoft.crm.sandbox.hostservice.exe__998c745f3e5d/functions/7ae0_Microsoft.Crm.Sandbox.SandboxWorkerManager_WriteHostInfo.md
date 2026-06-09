# Microsoft.Crm.Sandbox.SandboxWorkerManager::WriteHostInfo

- ea: `0x7ae0`
- end: `0x7de8`
- name: `Microsoft.Crm.Sandbox.SandboxWorkerManager::WriteHostInfo`
- size: `776`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0xf60`
- `0x7ae0`
- `0x9790`

## string_xrefs

- `0x7ae7`: `SandboxWorkerManager.WriteHostInfo: enter`
- `0x7d1e`: `WorkerProcessId`
- `0x7d2c`: `WorkerUri`
- `0x7dd0`: `SandboxWorkerManager.WriteHostInfo: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x7ae0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7ae5  ldc.i4.s 0x21
0x7ae7  ldstr    aSandboxworkerm_68// "SandboxWorkerManager.WriteHostInfo: ent"...
0x7aec  ldc.i4.0
0x7aed  newarr   [mscorlib]System.Object
0x7af2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7af7  ldsfld   object Microsoft.Crm.Sandbox.SandboxWorkerManager::_lockWriteHostInfo
0x7afc  stloc.0
0x7afd  ldc.i4.0
0x7afe  stloc.1
0x7aff  ldloc.0
0x7b00  ldloca.s 1
0x7b02  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x7b07  ldarg.0
0x7b08  castclass class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>
0x7b0d  stloc.2
0x7b0e  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x7b13  stloc.3
0x7b14  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x7b19  stloc.s  4
0x7b1b  ldloc.s  4
0x7b1d  ldc.i4.1
0x7b1e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x7b23  ldloc.s  4
0x7b25  ldc.i4.1
0x7b26  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0x7b2b  ldloc.s  4
0x7b2d  ldc.i4.1
0x7b2e  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x7b33  ldloc.3
0x7b34  ldloc.s  4
0x7b36  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0x7b3b  stloc.s  5
0x7b3d  ldloc.s  5
0x7b3f  ldstr    aSandboxhost// "SandboxHost"
0x7b44  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7b49  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x7b4e  stloc.s  6
0x7b50  ldloca.s 6
0x7b52  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToLocalTime()
0x7b57  stloc.s  7
0x7b59  ldloca.s 8
0x7b5b  ldstr    a077df9f2710d4b// "{077DF9F2-710D-4be3-B185-4AA068A16553}"
0x7b60  call     instance void [mscorlib]System.Guid::.ctor(string)
0x7b65  ldloc.s  5
0x7b67  ldstr    aFileversion// "FileVersion"
0x7b6c  ldloca.s 8
0x7b6e  constrained. [mscorlib]System.Guid
0x7b74  callvirt instance string [mscorlib]System.Object::ToString()
0x7b79  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7b7e  ldloc.s  5
0x7b80  ldstr    aMachine// "Machine"
0x7b85  call     string [mscorlib]System.Environment::get_MachineName()
0x7b8a  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7b8f  ldloc.s  5
0x7b91  ldstr    aProcessinfo// "ProcessInfo"
0x7b96  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_ProcessInfo()
0x7b9b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7ba0  ldloc.s  5
0x7ba2  ldstr    aFileguid// "FileGuid"
0x7ba7  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x7bac  stloc.s  9
0x7bae  ldloca.s 9
0x7bb0  ldstr    aD// "D"
0x7bb5  call     instance string [mscorlib]System.Guid::ToString(string)
0x7bba  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7bbf  ldloc.s  5
0x7bc1  ldstr    aUtctimestamp// "UtcTimeStamp"
0x7bc6  ldc.i4.7
0x7bc7  newarr   [mscorlib]System.Object
0x7bcc  dup
0x7bcd  ldc.i4.0
0x7bce  ldloca.s 6
0x7bd0  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x7bd5  box      [mscorlib]System.Int32
0x7bda  stelem.ref
0x7bdb  dup
0x7bdc  ldc.i4.1
0x7bdd  ldstr    asc_1B5EA// ":"
0x7be2  stelem.ref
0x7be3  dup
0x7be4  ldc.i4.2
0x7be5  ldloca.s 6
0x7be7  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x7bec  box      [mscorlib]System.Int32
0x7bf1  stelem.ref
0x7bf2  dup
0x7bf3  ldc.i4.3
0x7bf4  ldstr    asc_1B5EA// ":"
0x7bf9  stelem.ref
0x7bfa  dup
0x7bfb  ldc.i4.4
0x7bfc  ldloca.s 6
0x7bfe  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x7c03  box      [mscorlib]System.Int32
0x7c08  stelem.ref
0x7c09  dup
0x7c0a  ldc.i4.5
0x7c0b  ldstr    asc_1B5EA// ":"
0x7c10  stelem.ref
0x7c11  dup
0x7c12  ldc.i4.6
0x7c13  ldloca.s 6
0x7c15  call     instance int32 [mscorlib]System.DateTime::get_Millisecond()
0x7c1a  box      [mscorlib]System.Int32
0x7c1f  stelem.ref
0x7c20  call     string [mscorlib]System.String::Concat(object[])
0x7c25  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7c2a  ldloc.s  5
0x7c2c  ldstr    aUtcdate// "UtcDate"
0x7c31  ldloca.s 6
0x7c33  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x7c38  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7c3d  ldloc.s  5
0x7c3f  ldstr    aUtctime// "UtcTime"
0x7c44  ldloca.s 6
0x7c46  call     instance string [mscorlib]System.DateTime::ToLongTimeString()
0x7c4b  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7c50  ldloc.s  5
0x7c52  ldstr    aLocaldate// "LocalDate"
0x7c57  ldloca.s 7
0x7c59  call     instance string [mscorlib]System.DateTime::ToShortDateString()
0x7c5e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7c63  ldloc.s  5
0x7c65  ldstr    aLocaltime// "LocalTime"
0x7c6a  ldloca.s 7
0x7c6c  call     instance string [mscorlib]System.DateTime::ToLongTimeString()
0x7c71  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7c76  ldloc.s  5
0x7c78  ldstr    aOrganizationli// "OrganizationList"
0x7c7d  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7c82  ldloc.2
0x7c83  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::GetEnumerator()
0x7c88  stloc.s  0xA
0x7c8a  br       loc_7D5E
0x7c8f  ldloca.s 0xA
0x7c91  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::get_Current()
0x7c96  stloc.s  0xB
0x7c98  ldloca.s 0xB
0x7c9a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::get_Key()
0x7c9f  stloc.s  0xC
0x7ca1  ldloca.s 0xB
0x7ca3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::get_Value()
0x7ca8  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyCollection`1<class [System]System.Uri> Microsoft.Crm.Sandbox.OrganizationWorkerList::get_WorkersUri()
0x7cad  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System]System.Uri>::GetEnumerator()
0x7cb2  stloc.s  0xD
0x7cb4  br       loc_7D44
0x7cb9  ldloc.s  0xD
0x7cbb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System]System.Uri>::get_Current()
0x7cc0  stloc.s  0xE
0x7cc2  ldsfld   class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess> Microsoft.Crm.Sandbox.SandboxWorkerManager::_processPool
0x7cc7  ldloc.s  0xE
0x7cc9  ldloca.s 0xF
0x7ccb  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<class [System]System.Uri, class Microsoft.Crm.Sandbox.SandboxWorkerProcess>::TryGetValue(var<u1>, !!T0)
0x7cd0  pop
0x7cd1  ldstr    asc_1B658// "-"
0x7cd6  stloc.s  0x10
0x7cd8  ldloc.s  0xF
0x7cda  brfalse.s loc_7CF8
0x7cdc  ldloc.s  0xF
0x7cde  callvirt instance class [System]System.Diagnostics.Process Microsoft.Crm.Sandbox.SandboxWorkerProcess::get_WorkerProcess()
0x7ce3  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x7ce8  stloc.s  0x11
0x7cea  ldloca.s 0x11
0x7cec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7cf1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x7cf6  stloc.s  0x10
0x7cf8  ldloc.s  5
0x7cfa  ldstr    aOrganization// "Organization"
0x7cff  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x7d04  ldloc.s  5
0x7d06  ldstr    aId// "Id"
0x7d0b  ldloca.s 0xC
0x7d0d  ldstr    aD// "D"
0x7d12  call     instance string [mscorlib]System.Guid::ToString(string)
0x7d17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteAttributeString(string, string)
0x7d1c  ldloc.s  5
0x7d1e  ldstr    aWorkerprocessi_0// "WorkerProcessId"
0x7d23  ldloc.s  0x10
0x7d25  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7d2a  ldloc.s  5
0x7d2c  ldstr    aWorkeruri// "WorkerUri"
0x7d31  ldloc.s  0xE
0x7d33  callvirt instance string [mscorlib]System.Object::ToString()
0x7d38  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0x7d3d  ldloc.s  5
0x7d3f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7d44  ldloc.s  0xD
0x7d46  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7d4b  brtrue   loc_7CB9
0x7d50  leave.s  loc_7D5E
0x7d52  ldloc.s  0xD
0x7d54  brfalse.s loc_7D5D
0x7d56  ldloc.s  0xD
0x7d58  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d5d  endfinally
0x7d5e  ldloca.s 0xA
0x7d60  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>::MoveNext()
0x7d65  brtrue   loc_7C8F
0x7d6a  leave.s  loc_7D7A
0x7d6c  ldloca.s 0xA
0x7d6e  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Sandbox.OrganizationWorkerList>
0x7d74  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d79  endfinally
0x7d7a  ldloc.s  5
0x7d7c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7d81  ldloc.s  5
0x7d83  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x7d88  ldloc.s  5
0x7d8a  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x7d8f  leave.s  loc_7D9D
0x7d91  ldloc.s  5
0x7d93  brfalse.s loc_7D9C
0x7d95  ldloc.s  5
0x7d97  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7d9c  endfinally
0x7d9d  call     string [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxUtility::get_CrmServerInstallDirectory()
0x7da2  ldstr    aTraceSandboxho// "Trace\\SandboxHost.txt"
0x7da7  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7dac  ldloc.3
0x7dad  callvirt instance string [mscorlib]System.Object::ToString()
0x7db2  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x7db7  leave.s  loc_7DC3
0x7db9  ldloc.1
0x7dba  brfalse.s loc_7DC2
0x7dbc  ldloc.0
0x7dbd  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x7dc2  endfinally
0x7dc3  leave.s  loc_7DE7
0x7dc5  stloc.s  0x12
0x7dc7  ldloc.s  0x12
0x7dc9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x7dce  ldc.i4.s 0x21
0x7dd0  ldstr    aSandboxworkerm_69// "SandboxWorkerManager.WriteHostInfo: {0}"
0x7dd5  ldc.i4.1
0x7dd6  newarr   [mscorlib]System.Object
0x7ddb  dup
0x7ddc  ldc.i4.0
0x7ddd  ldloc.s  0x12
0x7ddf  stelem.ref
0x7de0  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7de5  leave.s  loc_7DE7
0x7de7  ret
```
