# <>c__DisplayClass17_0::<WriteTrace>b__0

- ea: `0xafe0`
- end: `0xb0ef`
- name: `<>c__DisplayClass17_0::<WriteTrace>b__0`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0xafe0`

## string_xrefs

- `0xb0e3`: `SandboxTracker.WriteTrace: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xafe0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0xafe5  stloc.0
0xafe6  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0xafeb  stloc.1
0xafec  ldloc.1
0xafed  ldc.i4.1
0xafee  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0xaff3  ldloc.1
0xaff4  ldc.i4.1
0xaff5  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_ConformanceLevel(valuetype [System.Xml]System.Xml.ConformanceLevel)
0xaffa  ldloc.1
0xaffb  ldc.i4.1
0xaffc  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0xb001  ldloc.0
0xb002  ldloc.1
0xb003  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(class [mscorlib]System.Text.StringBuilder, class [System.Xml]System.Xml.XmlWriterSettings)
0xb008  stloc.2
0xb009  ldloc.2
0xb00a  ldarg.0
0xb00b  ldfld    string <>c__DisplayClass17_0::traceType
0xb010  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xb015  ldloc.2
0xb016  ldstr    aTrackingid// "TrackingID"
0xb01b  ldarg.0
0xb01c  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb021  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_trackingIdText
0xb026  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb02b  ldloc.2
0xb02c  ldstr    aFunction// "Function"
0xb031  ldarg.0
0xb032  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb037  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_function
0xb03c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb041  ldarg.0
0xb042  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb047  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_origin
0xb04c  brfalse.s loc_B064
0xb04e  ldloc.2
0xb04f  ldstr    aOrigin// "Origin"
0xb054  ldarg.0
0xb055  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb05a  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_origin
0xb05f  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb064  ldarg.0
0xb065  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb06a  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_destination
0xb06f  brfalse.s loc_B087
0xb071  ldloc.2
0xb072  ldstr    aDestination// "Destination"
0xb077  ldarg.0
0xb078  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb07d  ldfld    string Microsoft.Crm.Sandbox.SandboxTracker::_destination
0xb082  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb087  ldloc.2
0xb088  ldstr    aAdditionaldata// "AdditionalData"
0xb08d  ldstr    asc_107B8// ";"
0xb092  ldarg.0
0xb093  ldfld    class Microsoft.Crm.Sandbox.SandboxTracker <>c__DisplayClass17_0::<>4__this
0xb098  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Sandbox.SandboxTracker::_additionalData
0xb09d  ldsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__17_1
0xb0a2  dup
0xb0a3  brtrue.s loc_B0BC
0xb0a5  pop
0xb0a6  ldsfld   class <>c <>c::<>9
0xb0ab  ldftn    instance string <>c::<WriteTrace>b__17_1(valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string> x)
0xb0b1  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string>::.ctor(object, native int)
0xb0b6  dup
0xb0b7  stsfld   class [mscorlib]System.Func`2<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>, string> <>c::<>9__17_1
0xb0bc  call     T0x2B000022
0xb0c1  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0xb0c6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xb0cb  ldloc.2
0xb0cc  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xb0d1  ldloc.2
0xb0d2  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0xb0d7  leave.s  loc_B0E3
0xb0d9  ldloc.2
0xb0da  brfalse.s loc_B0E2
0xb0dc  ldloc.2
0xb0dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb0e2  endfinally
0xb0e3  ldstr    aSandboxtracker_2// "SandboxTracker.WriteTrace: {0}"
0xb0e8  ldloc.0
0xb0e9  call     string [mscorlib]System.String::Format(string, object)
0xb0ee  ret
```
