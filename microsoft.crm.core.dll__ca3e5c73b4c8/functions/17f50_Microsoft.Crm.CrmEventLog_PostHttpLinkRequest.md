# Microsoft.Crm.CrmEventLog::PostHttpLinkRequest

- ea: `0x17f50`
- end: `0x180f3`
- name: `Microsoft.Crm.CrmEventLog::PostHttpLinkRequest`
- size: `419`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x17f50`
- `0x34780`

## string_xrefs

- `0x17f55`: `EventHotLinks`
- `0x17fd5`: `SYSTEM\CurrentControlSet\Services\Eventlog\Application\{0}`
- `0x1805f`: `EventHotLinksUrl`
- `0x18064`: `http://www.microsoft.com/products/ee/transform.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x17f50  ldc.i4.0
0x17f51  stloc.0
0x17f52  ldloc.0
0x17f53  brtrue.s loc_17F72
0x17f55  ldstr    aEventhotlinks// "EventHotLinks"
0x17f5a  ldc.i4.0
0x17f5b  box      [mscorlib]System.Int32
0x17f60  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x17f65  unbox.any [mscorlib]System.Int32
0x17f6a  stloc.s  7
0x17f6c  ldloc.s  7
0x17f6e  ldc.i4.0
0x17f6f  cgt.un
0x17f71  stloc.0
0x17f72  ldloc.0
0x17f73  brtrue.s loc_17F76
0x17f75  ret
0x17f76  ldnull
0x17f77  stloc.1
0x17f78  ldc.i4.0
0x17f79  stloc.2
0x17f7a  ldarg.1
0x17f7b  ldc.i4.1
0x17f7c  sub
0x17f7d  switch   loc_17FB4, loc_17FAA, loc_17FBE, loc_17FA0
0x17f92  ldarg.1
0x17f93  ldc.i4.8
0x17f94  bne.un.s loc_17FBE
0x17f96  ldstr    aInformation// "Information"
0x17f9b  stloc.1
0x17f9c  ldc.i4.0
0x17f9d  stloc.2
0x17f9e  br.s     loc_17FC9
0x17fa0  ldstr    aInformation// "Information"
0x17fa5  stloc.1
0x17fa6  ldc.i4.4
0x17fa7  stloc.2
0x17fa8  br.s     loc_17FC9
0x17faa  ldstr    aWarning// "Warning"
0x17faf  stloc.1
0x17fb0  ldc.i4.2
0x17fb1  stloc.2
0x17fb2  br.s     loc_17FC9
0x17fb4  ldstr    aError// "Error"
0x17fb9  stloc.1
0x17fba  ldc.i4.1
0x17fbb  stloc.2
0x17fbc  br.s     loc_17FC9
0x17fbe  ldstr    aEventtype// "eventType"
0x17fc3  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x17fc8  throw
0x17fc9  ldnull
0x17fca  stloc.3
0x17fcb  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x17fd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17fd5  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services\\Ev"...
0x17fda  ldc.i4.1
0x17fdb  newarr   [mscorlib]System.Object
0x17fe0  dup
0x17fe1  ldc.i4.0
0x17fe2  ldarg.0
0x17fe3  stelem.ref
0x17fe4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x17fe9  ldc.i4.0
0x17fea  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string, bool)
0x17fef  stloc.s  8
0x17ff1  ldloc.s  8
0x17ff3  brtrue.s loc_17FFA
0x17ff5  leave    loc_180F2
0x17ffa  ldloc.s  8
0x17ffc  stloc.s  9
0x17ffe  ldloc.s  8
0x18000  ldstr    aEventmessagefi// "EventMessageFile"
0x18005  ldnull
0x18006  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string, object)
0x1800b  castclass [mscorlib]System.String
0x18010  stloc.3
0x18011  leave.s  loc_1801F
0x18013  ldloc.s  9
0x18015  brfalse.s loc_1801E
0x18017  ldloc.s  9
0x18019  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1801e  endfinally
0x1801f  leave.s  loc_18027
0x18021  pop
0x18022  leave    loc_180F2
0x18027  ldloc.3
0x18028  brtrue.s loc_1802B
0x1802a  ret
0x1802b  ldnull
0x1802c  stloc.s  4
0x1802e  ldloc.3
0x1802f  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x18034  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_FileVersion()
0x18039  stloc.s  4
0x1803b  leave.s  loc_18049
0x1803d  pop
0x1803e  leave    loc_180F2
0x18043  pop
0x18044  leave    loc_180F2
0x18049  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x1804e  callvirt instance class [mscorlib]System.Reflection.AssemblyName [mscorlib]System.Reflection.Assembly::GetName()
0x18053  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0x18058  callvirt instance string [mscorlib]System.Object::ToString()
0x1805d  stloc.s  5
0x1805f  ldstr    aEventhotlinksu// "EventHotLinksUrl"
0x18064  ldstr    aHttpWwwMicroso// "http://www.microsoft.com/products/ee/tr"...
0x18069  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x1806e  castclass [mscorlib]System.String
0x18073  stloc.s  6
0x18075  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1807a  ldstr    a0Evtsrc1Evtcat// "{0}?EvtSrc={1}&EvtCat=None&EvtID={2}&Ev"...
0x1807f  ldc.i4.s 0xA
0x18081  newarr   [mscorlib]System.Object
0x18086  dup
0x18087  ldc.i4.0
0x18088  ldloc.s  6
0x1808a  stelem.ref
0x1808b  dup
0x1808c  ldc.i4.1
0x1808d  ldarg.0
0x1808e  stelem.ref
0x1808f  dup
0x18090  ldc.i4.2
0x18091  ldarg.2
0x18092  conv.u4
0x18093  ldc.i4   0xFFFF
0x18098  and
0x18099  box      [mscorlib]System.UInt32
0x1809e  stelem.ref
0x1809f  dup
0x180a0  ldc.i4.3
0x180a1  ldloc.1
0x180a2  stelem.ref
0x180a3  dup
0x180a4  ldc.i4.4
0x180a5  ldloc.2
0x180a6  box      [mscorlib]System.Int32
0x180ab  stelem.ref
0x180ac  dup
0x180ad  ldc.i4.5
0x180ae  ldstr    aMicrosoft20cor// "Microsoft%20Corporation"
0x180b3  stelem.ref
0x180b4  dup
0x180b5  ldc.i4.6
0x180b6  ldstr    aMicrosoftC2Ae2// "Microsoft%c2%ae%20Business%20Solutions%"...
0x180bb  stelem.ref
0x180bc  dup
0x180bd  ldc.i4.7
0x180be  ldloc.s  5
0x180c0  stelem.ref
0x180c1  dup
0x180c2  ldc.i4.8
0x180c3  ldloc.3
0x180c4  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x180c9  stelem.ref
0x180ca  dup
0x180cb  ldc.i4.s 9
0x180cd  ldloc.s  4
0x180cf  stelem.ref
0x180d0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x180d5  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(string)
0x180da  castclass [System]System.Net.HttpWebRequest
0x180df  ldnull
0x180e0  ldftn    void Microsoft.Crm.CrmEventLog::RespCallback(class [mscorlib]System.IAsyncResult asynchronousResult)
0x180e6  newobj   instance void [mscorlib]System.AsyncCallback::.ctor(object, native int)
0x180eb  ldnull
0x180ec  callvirt instance class [mscorlib]System.IAsyncResult [System]System.Net.WebRequest::BeginGetResponse(class [mscorlib]System.AsyncCallback, object)
0x180f1  pop
0x180f2  ret
```
