# Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FixPost

- ea: `0x20550`
- end: `0x2066c`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationDatabaseAccess::FixPost`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x201a0`

## callees

- `0x20550`

## string_xrefs

- `0x20564`: `Failed to parse as XML; Text {0} for PostId {1}, OriginalFullName {2}, DbConnectionString {3}; Exception {4}`
- `0x20615`: `UPDATE PostBase SET Text=@Text WHERE PostId=@PostId`

## pseudocode

```c

```

## disassembly

```asm
0x20550  ldarg.2
0x20551  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x20556  brfalse.s loc_20559
0x20558  ret
0x20559  nop
0x2055a  ldarg.1
0x2055b  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Parse(string)
0x20560  stloc.0
0x20561  leave.s  loc_205B4
0x20563  stloc.2
0x20564  ldstr    aFailedToParseA// "Failed to parse as XML; Text {0} for Po"...
0x20569  ldc.i4.5
0x2056a  newarr   [mscorlib]System.Object
0x2056f  dup
0x20570  ldc.i4.0
0x20571  ldarg.1
0x20572  dup
0x20573  brtrue.s loc_2057B
0x20575  pop
0x20576  ldsfld   string [mscorlib]System.String::Empty
0x2057b  stelem.ref
0x2057c  dup
0x2057d  ldc.i4.1
0x2057e  ldarg.0
0x2057f  box      [mscorlib]System.Guid
0x20584  stelem.ref
0x20585  dup
0x20586  ldc.i4.2
0x20587  ldarg.2
0x20588  dup
0x20589  brtrue.s loc_20591
0x2058b  pop
0x2058c  ldsfld   string [mscorlib]System.String::Empty
0x20591  stelem.ref
0x20592  dup
0x20593  ldc.i4.3
0x20594  ldarg.s  4
0x20596  callvirt instance string [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::get_ConnectionString()
0x2059b  dup
0x2059c  brtrue.s loc_205A4
0x2059e  pop
0x2059f  ldsfld   string [mscorlib]System.String::Empty
0x205a4  stelem.ref
0x205a5  dup
0x205a6  ldc.i4.4
0x205a7  ldloc.2
0x205a8  stelem.ref
0x205a9  call     string [mscorlib]System.String::Format(string, object[])
0x205ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x205b3  throw
0x205b4  ldc.i4.0
0x205b5  stloc.1
0x205b6  ldloc.0
0x205b7  ldstr    aP// "p"
0x205bc  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x205c1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XContainer::Descendants(class [System.Xml.Linq]System.Xml.Linq.XName)
0x205c6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x205cb  stloc.3
0x205cc  br.s     loc_205FC
0x205ce  ldloc.3
0x205cf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x205d4  stloc.s  4
0x205d6  ldloc.s  4
0x205d8  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x205dd  ldarg.2
0x205de  callvirt instance bool [mscorlib]System.String::Contains(string)
0x205e3  brfalse.s loc_205FC
0x205e5  ldloc.s  4
0x205e7  ldloc.s  4
0x205e9  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x205ee  ldarg.2
0x205ef  ldarg.3
0x205f0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x205f5  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::set_Value(string)
0x205fa  ldc.i4.1
0x205fb  stloc.1
0x205fc  ldloc.3
0x205fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20602  brtrue.s loc_205CE
0x20604  leave.s  loc_20610
0x20606  ldloc.3
0x20607  brfalse.s loc_2060F
0x20609  ldloc.3
0x2060a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2060f  endfinally
0x20610  ldloc.1
0x20611  brfalse.s loc_2066B
0x20613  ldarg.s  4
0x20615  ldstr    aUpdatePostbase// "UPDATE PostBase SET Text=@Text WHERE Po"...
0x2061a  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x2061f  stloc.s  5
0x20621  ldloc.0
0x20622  ldc.i4.1
0x20623  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNode::ToString(valuetype [System.Xml.Linq]System.Xml.Linq.SaveOptions)
0x20628  stloc.s  6
0x2062a  ldloc.s  5
0x2062c  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x20631  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x20636  dup
0x20637  ldstr    aText// "@Text"
0x2063c  ldloc.s  6
0x2063e  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20643  pop
0x20644  ldstr    aPostid// "@PostId"
0x20649  ldarg.0
0x2064a  box      [mscorlib]System.Guid
0x2064f  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x20654  pop
0x20655  ldloc.s  5
0x20657  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0x2065c  pop
0x2065d  leave.s  loc_2066B
0x2065f  ldloc.s  5
0x20661  brfalse.s loc_2066A
0x20663  ldloc.s  5
0x20665  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2066a  endfinally
0x2066b  ret
```
