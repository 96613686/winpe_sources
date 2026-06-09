# Microsoft.Crm.ObjectModel.PagingExtension::DeserializePagingCookie

- ea: `0xe48e0`
- end: `0xe4af3`
- name: `Microsoft.Crm.ObjectModel.PagingExtension::DeserializePagingCookie`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xe3750`

## callees

- `0xe4680`
- `0xe46c0`
- `0xe46e0`
- `0xe4700`
- `0xe4720`
- `0xe48e0`
- `0xe4b00`

## string_xrefs

- `0xe4932`: `Malformed XML Passed to in the Paging Cookie. We expect entity platform name to be same as passed in RetrieveEntityChanges API`
- `0xe494b`: `Malformed XML Passed to in the Paging Cookie. We expect at most four attributes (minTimestamp, maxTimestamp, lastSyncedTimestamp and syncstate)`
- `0xe49a7`: `Malformed XML Passed to in the Paging Cookie. Value for attribute minTimestamp should be greater than equal to 0`
- `0xe49ea`: `Malformed XML Passed to in the Paging Cookie. Value for attribute maxTimestamp should be greater than 0`
- `0xe4a2d`: `Malformed XML Passed to in the Paging Cookie. Value for attribute lastSyncedTimestamp should be greater than equal to 0`
- `0xe4ad6`: `Malformed XML in the Paging Cookie`

## pseudocode

```c

```

## disassembly

```asm
0xe48e0  ldc.i4.0
0xe48e1  stloc.0
0xe48e2  ldnull
0xe48e3  stloc.1
0xe48e4  ldarg.0
0xe48e5  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PagingCookie()
0xe48ea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xe48ef  brtrue   loc_E4AF1
0xe48f4  newobj   instance void Microsoft.Crm.ObjectModel.PagingCookieParameters::.ctor()
0xe48f9  stloc.1
0xe48fa  ldarg.0
0xe48fb  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.PagingInfo::get_PagingCookie()
0xe4900  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0xe4905  stloc.2
0xe4906  ldloc.2
0xe4907  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe490c  pop
0xe490d  br       loc_E4A60
0xe4912  ldloc.2
0xe4913  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xe4918  ldc.i4.s 0xF
0xe491a  beq      loc_E4A60
0xe491f  ldloc.2
0xe4920  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xe4925  ldarg.1
0xe4926  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0xe492b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xe4930  brfalse.s loc_E4942
0xe4932  ldstr    aMalformedXmlPa// "Malformed XML Passed to in the Paging C"...
0xe4937  ldc.i4   0x80040201
0xe493c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe4941  throw
0xe4942  ldloc.2
0xe4943  callvirt instance int32 [System.Xml]System.Xml.XmlReader::get_AttributeCount()
0xe4948  ldc.i4.4
0xe4949  beq.s    loc_E495B
0xe494b  ldstr    aMalformedXmlPa_0// "Malformed XML Passed to in the Paging C"...
0xe4950  ldc.i4   0x80040201
0xe4955  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe495a  throw
0xe495b  ldloc.2
0xe495c  ldstr    aMintimestamp// "minTimestamp"
0xe4961  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xe4966  stloc.3
0xe4967  ldloc.2
0xe4968  ldstr    aMaxtimestamp// "maxTimestamp"
0xe496d  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xe4972  stloc.s  4
0xe4974  ldloc.2
0xe4975  ldstr    aLastsyncedtime// "lastSyncedTimestamp"
0xe497a  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xe497f  stloc.s  5
0xe4981  ldc.i4.m1
0xe4982  conv.i8
0xe4983  stloc.s  6
0xe4985  ldloc.3
0xe4986  brfalse.s loc_E49A2
0xe4988  ldloc.3
0xe4989  ldloca.s 6
0xe498b  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0xe4990  brfalse.s loc_E49A2
0xe4992  ldloc.s  6
0xe4994  ldc.i4.0
0xe4995  conv.i8
0xe4996  blt.s    loc_E49A2
0xe4998  ldloc.1
0xe4999  ldloc.s  6
0xe499b  callvirt instance void Microsoft.Crm.ObjectModel.PagingCookieParameters::set_MinTimestamp(int64 value)
0xe49a0  br.s     loc_E49C2
0xe49a2  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe49a7  ldstr    aMalformedXmlPa_1// "Malformed XML Passed to in the Paging C"...
0xe49ac  ldc.i4.0
0xe49ad  newarr   [mscorlib]System.Object
0xe49b2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe49b7  ldc.i4   0x80040201
0xe49bc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe49c1  throw
0xe49c2  ldc.i4.m1
0xe49c3  conv.i8
0xe49c4  stloc.s  7
0xe49c6  ldloc.s  4
0xe49c8  brfalse.s loc_E49E5
0xe49ca  ldloc.s  4
0xe49cc  ldloca.s 7
0xe49ce  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0xe49d3  brfalse.s loc_E49E5
0xe49d5  ldloc.s  7
0xe49d7  ldc.i4.0
0xe49d8  conv.i8
0xe49d9  ble.s    loc_E49E5
0xe49db  ldloc.1
0xe49dc  ldloc.s  7
0xe49de  callvirt instance void Microsoft.Crm.ObjectModel.PagingCookieParameters::set_MaxTimestamp(int64 value)
0xe49e3  br.s     loc_E4A05
0xe49e5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe49ea  ldstr    aMalformedXmlPa_2// "Malformed XML Passed to in the Paging C"...
0xe49ef  ldc.i4.0
0xe49f0  newarr   [mscorlib]System.Object
0xe49f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe49fa  ldc.i4   0x80040201
0xe49ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe4a04  throw
0xe4a05  ldc.i4.m1
0xe4a06  conv.i8
0xe4a07  stloc.s  8
0xe4a09  ldloc.s  5
0xe4a0b  brfalse.s loc_E4A28
0xe4a0d  ldloc.s  5
0xe4a0f  ldloca.s 8
0xe4a11  call     bool [mscorlib]System.Int64::TryParse(string, int64&)
0xe4a16  brfalse.s loc_E4A28
0xe4a18  ldloc.s  8
0xe4a1a  ldc.i4.0
0xe4a1b  conv.i8
0xe4a1c  blt.s    loc_E4A28
0xe4a1e  ldloc.1
0xe4a1f  ldloc.s  8
0xe4a21  callvirt instance void Microsoft.Crm.ObjectModel.PagingCookieParameters::set_LastSyncedTimestamp(int64 value)
0xe4a26  br.s     loc_E4A48
0xe4a28  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe4a2d  ldstr    aMalformedXmlPa_3// "Malformed XML Passed to in the Paging C"...
0xe4a32  ldc.i4.0
0xe4a33  newarr   [mscorlib]System.Object
0xe4a38  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe4a3d  ldc.i4   0x80040201
0xe4a42  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe4a47  throw
0xe4a48  ldloc.1
0xe4a49  ldloc.2
0xe4a4a  ldstr    aSyncstate// "syncState"
0xe4a4f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xe4a54  call     int32 Microsoft.Crm.ObjectModel.PagingExtension::GetSyncStateValue(string syncState)
0xe4a59  callvirt instance void Microsoft.Crm.ObjectModel.PagingCookieParameters::set_SyncStateValue(valuetype Microsoft.Crm.ObjectModel.SyncState value)
0xe4a5e  ldc.i4.1
0xe4a5f  stloc.0
0xe4a60  ldloc.2
0xe4a61  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xe4a66  brtrue   loc_E4912
0xe4a6b  leave.s  loc_E4A77
0xe4a6d  ldloc.2
0xe4a6e  brfalse.s loc_E4A76
0xe4a70  ldloc.2
0xe4a71  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe4a76  endfinally
0xe4a77  leave.s  loc_E4ACE
0xe4a79  stloc.s  9
0xe4a7b  ldloc.s  9
0xe4a7d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe4a82  ldc.i4.s 0x14
0xe4a84  ldstr    a0_0// "{0}"
0xe4a89  ldc.i4.1
0xe4a8a  newarr   [mscorlib]System.Object
0xe4a8f  dup
0xe4a90  ldc.i4.0
0xe4a91  ldloc.s  9
0xe4a93  stelem.ref
0xe4a94  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe4a99  ldc.i4.0
0xe4a9a  stloc.0
0xe4a9b  leave.s  loc_E4ACE
0xe4a9d  stloc.s  0xA
0xe4a9f  ldloc.s  0xA
0xe4aa1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xe4aa6  ldc.i4.s 0x14
0xe4aa8  ldstr    a0_0// "{0}"
0xe4aad  ldc.i4.1
0xe4aae  newarr   [mscorlib]System.Object
0xe4ab3  dup
0xe4ab4  ldc.i4.0
0xe4ab5  ldloc.s  0xA
0xe4ab7  stelem.ref
0xe4ab8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xe4abd  ldc.i4   0x8004112A
0xe4ac2  ldc.i4.0
0xe4ac3  newarr   [mscorlib]System.Object
0xe4ac8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0xe4acd  throw
0xe4ace  ldloc.0
0xe4acf  brtrue.s loc_E4AF1
0xe4ad1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xe4ad6  ldstr    aMalformedXmlIn// "Malformed XML in the Paging Cookie"
0xe4adb  ldc.i4.0
0xe4adc  newarr   [mscorlib]System.Object
0xe4ae1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe4ae6  ldc.i4   0x80040201
0xe4aeb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xe4af0  throw
0xe4af1  ldloc.1
0xe4af2  ret
```
