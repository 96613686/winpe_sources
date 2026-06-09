# Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::ParseSyncInfo

- ea: `0x529f0`
- end: `0x52acd`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::ParseSyncInfo`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5b270`

## callees

- `0x528e0`
- `0x52900`
- `0x52920`
- `0x52960`
- `0x529f0`

## string_xrefs

- `0x52a42`: `update_count`
- `0x52a4f`: `delete_count`

## pseudocode

```c

```

## disassembly

```asm
0x529f0  ldarg.1
0x529f1  ldarg.2
0x529f2  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::set_EntityName(string value)
0x529f7  ldarg.0
0x529f8  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0x529fd  stloc.0
0x529fe  br       loc_52AB5
0x52a03  ldloc.0
0x52a04  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x52a09  stloc.1
0x52a0a  ldloc.1
0x52a0b  ldc.i4.1
0x52a0c  bne.un   loc_52AB5
0x52a11  ldloc.0
0x52a12  ldstr    aName_0// "name"
0x52a17  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x52a1c  stloc.2
0x52a1d  ldloc.2
0x52a1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52a23  brtrue   loc_52AB5
0x52a28  ldloc.2
0x52a29  ldarg.2
0x52a2a  ldc.i4.5
0x52a2b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x52a30  brtrue   loc_52AB5
0x52a35  ldloc.0
0x52a36  ldstr    aInsertCount// "insert_count"
0x52a3b  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x52a40  stloc.3
0x52a41  ldloc.0
0x52a42  ldstr    aUpdateCount// "update_count"
0x52a47  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x52a4c  stloc.s  4
0x52a4e  ldloc.0
0x52a4f  ldstr    aDeleteCount// "delete_count"
0x52a54  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x52a59  stloc.s  5
0x52a5b  ldarg.1
0x52a5c  ldloc.3
0x52a5d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52a62  brtrue.s loc_52A71
0x52a64  ldloc.3
0x52a65  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a6a  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x52a6f  br.s     loc_52A72
0x52a71  ldc.i4.0
0x52a72  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::set_InsertCount(int32 value)
0x52a77  ldarg.1
0x52a78  ldloc.s  4
0x52a7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52a7f  brtrue.s loc_52A8F
0x52a81  ldloc.s  4
0x52a83  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52a88  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x52a8d  br.s     loc_52A90
0x52a8f  ldc.i4.0
0x52a90  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::set_UpdateCount(int32 value)
0x52a95  ldarg.1
0x52a96  ldloc.s  5
0x52a98  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x52a9d  brtrue.s loc_52AAD
0x52a9f  ldloc.s  5
0x52aa1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x52aa6  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x52aab  br.s     loc_52AAE
0x52aad  ldc.i4.0
0x52aae  callvirt instance void Microsoft.Crm.Asynchronous.EmailConnector.CrmSyncInfo::set_DeleteCount(int32 value)
0x52ab3  leave.s  loc_52ACC
0x52ab5  ldloc.0
0x52ab6  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x52abb  brtrue   loc_52A03
0x52ac0  leave.s  loc_52ACC
0x52ac2  ldloc.0
0x52ac3  brfalse.s loc_52ACB
0x52ac5  ldloc.0
0x52ac6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x52acb  endfinally
0x52acc  ret
```
