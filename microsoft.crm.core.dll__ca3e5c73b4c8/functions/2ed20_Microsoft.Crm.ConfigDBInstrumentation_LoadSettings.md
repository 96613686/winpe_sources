# Microsoft.Crm.ConfigDBInstrumentation::LoadSettings

- ea: `0x2ed20`
- end: `0x2ef40`
- name: `Microsoft.Crm.ConfigDBInstrumentation::LoadSettings`
- size: `544`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x13270`
- `0x2e9a0`
- `0x2fcc0`

## callees

- `0x2df80`
- `0x2ecf0`
- `0x2ed20`
- `0x337a0`
- `0x34780`

## string_xrefs

- `0x2ed85`: `/config/BeginTime`
- `0x2edc6`: `/config/Scope`
- `0x2ee0c`: `/config/PeriodInHours`
- `0x2ee7b`: `config`

## pseudocode

```c

```

## disassembly

```asm
0x2ed20  ldarg.0
0x2ed21  call     instance void Microsoft.Crm.ConfigDBInstrumentation::CreateXmlWriterSettings()
0x2ed26  ldarg.0
0x2ed27  call     string Microsoft.Crm.RegControl::get_CrmServerInstallKeyDir()
0x2ed2c  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x2ed31  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x2ed36  castclass [mscorlib]System.String
0x2ed3b  stfld    string Microsoft.Crm.ConfigDBInstrumentation::Directory
0x2ed40  ldarg.0
0x2ed41  ldarg.0
0x2ed42  ldfld    string Microsoft.Crm.ConfigDBInstrumentation::Directory
0x2ed47  ldstr    aTrace_0// "\\Trace\\"
0x2ed4c  ldarg.2
0x2ed4d  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ed52  stfld    string Microsoft.Crm.ConfigDBInstrumentation::InstrumentationFileName
0x2ed57  ldarg.0
0x2ed58  ldfld    string Microsoft.Crm.ConfigDBInstrumentation::Directory
0x2ed5d  ldstr    aTrace_0// "\\Trace\\"
0x2ed62  ldarg.1
0x2ed63  call     string [mscorlib]System.String::Concat(string, string, string)
0x2ed68  stloc.0
0x2ed69  ldloc.0
0x2ed6a  call     bool [mscorlib]System.IO.File::Exists(string)
0x2ed6f  brfalse  loc_2EE52
0x2ed74  ldloc.0
0x2ed75  ldc.i4.3
0x2ed76  ldc.i4.1
0x2ed77  newobj   instance void [mscorlib]System.IO.FileStream::.ctor(string, valuetype [mscorlib]System.IO.FileMode, valuetype [mscorlib]System.IO.FileAccess)
0x2ed7c  stloc.1
0x2ed7d  ldloc.1
0x2ed7e  call     class [System.Xml]System.Xml.XmlDocument Microsoft.Crm.SharedUtil::CreateXmlDocument(class [mscorlib]System.IO.Stream input)
0x2ed83  stloc.2
0x2ed84  ldloc.2
0x2ed85  ldstr    aConfigBegintim// "/config/BeginTime"
0x2ed8a  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2ed8f  stloc.3
0x2ed90  ldloc.3
0x2ed91  brfalse.s loc_2EDBA
0x2ed93  ldloc.3
0x2ed94  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2ed99  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ed9e  ldc.i4.s 0x10
0x2eda0  ldarg.0
0x2eda1  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.ConfigDBInstrumentation::InstrumentationBeginTimeUtc
0x2eda6  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x2edab  brtrue.s loc_2EDC5
0x2edad  ldarg.0
0x2edae  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2edb3  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.ConfigDBInstrumentation::InstrumentationBeginTimeUtc
0x2edb8  br.s     loc_2EDC5
0x2edba  ldarg.0
0x2edbb  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2edc0  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.ConfigDBInstrumentation::InstrumentationBeginTimeUtc
0x2edc5  ldloc.2
0x2edc6  ldstr    aConfigScope// "/config/Scope"
0x2edcb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2edd0  stloc.s  4
0x2edd2  ldloc.s  4
0x2edd4  brfalse.s loc_2EE04
0x2edd6  ldarg.0
0x2edd7  ldtoken  Microsoft.Crm.SharedDatabase.ConfigScope
0x2eddc  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x2ede1  ldloc.s  4
0x2ede3  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2ede8  ldc.i4.1
0x2ede9  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string, bool)
0x2edee  unbox.any Microsoft.Crm.SharedDatabase.ConfigScope
0x2edf3  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigDBInstrumentation::ConfigScope
0x2edf8  leave.s  loc_2EE0B
0x2edfa  pop
0x2edfb  ldarg.0
0x2edfc  ldc.i4.0
0x2edfd  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigDBInstrumentation::ConfigScope
0x2ee02  leave.s  loc_2EE0B
0x2ee04  ldarg.0
0x2ee05  ldc.i4.0
0x2ee06  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigDBInstrumentation::ConfigScope
0x2ee0b  ldloc.2
0x2ee0c  ldstr    aConfigPeriodin// "/config/PeriodInHours"
0x2ee11  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2ee16  stloc.s  5
0x2ee18  ldloc.s  5
0x2ee1a  brfalse.s loc_2EE3C
0x2ee1c  ldloc.s  5
0x2ee1e  callvirt instance string [System.Xml]System.Xml.XmlNode::get_InnerText()
0x2ee23  ldarg.0
0x2ee24  ldflda   int32 Microsoft.Crm.ConfigDBInstrumentation::InstrumentationPeriodInHours
0x2ee29  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x2ee2e  brtrue.s loc_2EE43
0x2ee30  ldarg.0
0x2ee31  ldc.i4.6
0x2ee32  stfld    int32 Microsoft.Crm.ConfigDBInstrumentation::InstrumentationPeriodInHours
0x2ee37  leave    loc_2EF3F
0x2ee3c  ldarg.0
0x2ee3d  ldc.i4.6
0x2ee3e  stfld    int32 Microsoft.Crm.ConfigDBInstrumentation::InstrumentationPeriodInHours
0x2ee43  leave    loc_2EF3F
0x2ee48  ldloc.1
0x2ee49  brfalse.s loc_2EE51
0x2ee4b  ldloc.1
0x2ee4c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ee51  endfinally
0x2ee52  ldarg.0
0x2ee53  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x2ee58  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.ConfigDBInstrumentation::InstrumentationBeginTimeUtc
0x2ee5d  ldarg.0
0x2ee5e  ldc.i4.0
0x2ee5f  stfld    valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigDBInstrumentation::ConfigScope
0x2ee64  ldarg.0
0x2ee65  ldc.i4.6
0x2ee66  stfld    int32 Microsoft.Crm.ConfigDBInstrumentation::InstrumentationPeriodInHours
0x2ee6b  ldloc.0
0x2ee6c  ldarg.0
0x2ee6d  ldfld    class [System.Xml]System.Xml.XmlWriterSettings Microsoft.Crm.ConfigDBInstrumentation::XmlSettings
0x2ee72  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(string, class [System.Xml]System.Xml.XmlWriterSettings)
0x2ee77  stloc.s  6
0x2ee79  ldloc.s  6
0x2ee7b  ldstr    aConfig// "config"
0x2ee80  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2ee85  ldloc.s  6
0x2ee87  ldstr    aBegintimeTheUt// "BeginTime - The UTC time when the instr"...
0x2ee8c  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteComment(string)
0x2ee91  ldloc.s  6
0x2ee93  ldstr    aBegintime// "BeginTime"
0x2ee98  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2ee9d  ldloc.s  6
0x2ee9f  ldarg.0
0x2eea0  ldflda   valuetype [mscorlib]System.DateTime Microsoft.Crm.ConfigDBInstrumentation::InstrumentationBeginTimeUtc
0x2eea5  call     instance string [mscorlib]System.DateTime::ToString()
0x2eeaa  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x2eeaf  ldloc.s  6
0x2eeb1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2eeb6  ldloc.s  6
0x2eeb8  ldstr    aScopeGeoSitewi// "Scope - Geo, SiteWide or ScaleGroup"
0x2eebd  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteComment(string)
0x2eec2  ldloc.s  6
0x2eec4  ldstr    aScope// "Scope"
0x2eec9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2eece  ldloc.s  6
0x2eed0  ldarg.0
0x2eed1  ldflda   valuetype Microsoft.Crm.SharedDatabase.ConfigScope Microsoft.Crm.ConfigDBInstrumentation::ConfigScope
0x2eed6  constrained. Microsoft.Crm.SharedDatabase.ConfigScope
0x2eedc  callvirt instance string [mscorlib]System.Object::ToString()
0x2eee1  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x2eee6  ldloc.s  6
0x2eee8  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2eeed  ldloc.s  6
0x2eeef  ldstr    aPeriodinhoursT// "PeriodInHours - The number of hours we "...
0x2eef4  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteComment(string)
0x2eef9  ldloc.s  6
0x2eefb  ldstr    aPeriodinhours// "PeriodInHours"
0x2ef00  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0x2ef05  ldloc.s  6
0x2ef07  ldarg.0
0x2ef08  ldflda   int32 Microsoft.Crm.ConfigDBInstrumentation::InstrumentationPeriodInHours
0x2ef0d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2ef12  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x2ef17  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteString(string)
0x2ef1c  ldloc.s  6
0x2ef1e  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2ef23  ldloc.s  6
0x2ef25  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0x2ef2a  ldloc.s  6
0x2ef2c  callvirt instance void [System.Xml]System.Xml.XmlWriter::Close()
0x2ef31  leave.s  loc_2EF3F
0x2ef33  ldloc.s  6
0x2ef35  brfalse.s loc_2EF3E
0x2ef37  ldloc.s  6
0x2ef39  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2ef3e  endfinally
0x2ef3f  ret
```
