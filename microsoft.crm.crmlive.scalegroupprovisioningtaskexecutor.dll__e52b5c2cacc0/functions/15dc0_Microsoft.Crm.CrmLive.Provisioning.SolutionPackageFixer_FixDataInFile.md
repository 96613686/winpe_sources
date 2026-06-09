# Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::FixDataInFile

- ea: `0x15dc0`
- end: `0x15e9e`
- name: `Microsoft.Crm.CrmLive.Provisioning.SolutionPackageFixer::FixDataInFile`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x15d50`

## callees

- `0x15a70`
- `0x15a90`
- `0x15ab0`
- `0x15dc0`

## string_xrefs

- `0x15e80`: `<field name="accessmode" value="4"`
- `0x15e85`: `<field name="accessmode" value="0"`

## pseudocode

```c

```

## disassembly

```asm
0x15dc0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ImportedRecord>::.ctor()
0x15dc5  stloc.0
0x15dc6  ldarg.0
0x15dc7  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Load(string)
0x15dcc  stloc.1
0x15dcd  ldloc.1
0x15dce  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x15dd3  ldstr    aRecord// "record"
0x15dd8  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15ddd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x15de2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x15de7  stloc.3
0x15de8  br.s     loc_15E5D
0x15dea  ldloc.3
0x15deb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x15df0  stloc.s  4
0x15df2  ldloc.s  4
0x15df4  ldstr    aId_0// "id"
0x15df9  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15dfe  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x15e03  brfalse.s loc_15E5D
0x15e05  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ImportedRecord::.ctor()
0x15e0a  stloc.s  5
0x15e0c  ldloc.s  5
0x15e0e  ldloc.s  4
0x15e10  ldstr    aId_0// "id"
0x15e15  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15e1a  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x15e1f  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x15e24  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x15e29  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ImportedRecord::set_RecordId(valuetype [mscorlib]System.Guid value)
0x15e2e  ldloc.s  5
0x15e30  ldloc.s  4
0x15e32  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XObject::get_Parent()
0x15e37  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XObject::get_Parent()
0x15e3c  ldstr    aName_0// "name"
0x15e41  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x15e46  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x15e4b  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x15e50  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.ImportedRecord::set_EntityName(string value)
0x15e55  ldloc.0
0x15e56  ldloc.s  5
0x15e58  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ImportedRecord>::Add(var<u1>)
0x15e5d  ldloc.3
0x15e5e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15e63  brtrue.s loc_15DEA
0x15e65  leave.s  loc_15E71
0x15e67  ldloc.3
0x15e68  brfalse.s loc_15E70
0x15e6a  ldloc.3
0x15e6b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15e70  endfinally
0x15e71  ldloc.1
0x15e72  ldarg.0
0x15e73  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XDocument::Save(string)
0x15e78  ldarg.0
0x15e79  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x15e7e  stloc.2
0x15e7f  ldloc.2
0x15e80  ldstr    aFieldNameAcces// "<field name=\"accessmode\" value=\"4\""
0x15e85  ldstr    aFieldNameAcces_0// "<field name=\"accessmode\" value=\"0\""
0x15e8a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x15e8f  stloc.2
0x15e90  ldarg.0
0x15e91  ldloc.2
0x15e92  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0x15e97  ldloc.0
0x15e98  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.CrmLive.Provisioning.ImportedRecord>::ToArray()
0x15e9d  ret
```
