# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie

- ea: `0x202c0`
- end: `0x20351`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::DeserializePagingCookie`
- size: `145`
- prototype: ``
- caller_count: `8`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14e10`
- `0x1eb40`
- `0x20290`
- `0x20360`
- `0x203a0`
- `0x21200`
- `0x212a0`
- `0x21330`

## callees

- `0x1d510`
- `0x202c0`

## string_xrefs

- `0x20344`: `Malformed XML`

## pseudocode

```c

```

## disassembly

```asm
0x202c0  ldarg.0
0x202c1  call     class [System.Xml]System.Xml.XmlReader [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlReader(string)
0x202c6  stloc.0
0x202c7  ldloc.0
0x202c8  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x202cd  pop
0x202ce  ldloc.0
0x202cf  ldstr    aPagenumber// "pagenumber"
0x202d4  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x202d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x202de  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x202e3  ldloc.0
0x202e4  ldstr    aPagingcookie// "pagingcookie"
0x202e9  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x202ee  stloc.1
0x202ef  dup
0x202f0  ldstr    aPagenumber_0// "pageNumber"
0x202f5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x202fa  ldloc.0
0x202fb  ldstr    aIstracking// "istracking"
0x20300  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x20305  stloc.2
0x20306  ldloc.1
0x20307  ldloc.2
0x20308  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2030d  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x20312  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmODataPagingCookie::.ctor(int32 pageNumber, string pagingCookie, bool isTracking)
0x20317  stloc.3
0x20318  leave.s  loc_2034F
0x2031a  ldloc.0
0x2031b  brfalse.s loc_20323
0x2031d  ldloc.0
0x2031e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20323  endfinally
0x20324  stloc.s  4
0x20326  ldloc.s  4
0x20328  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2032d  ldc.i4.s 0x14
0x2032f  ldstr    a0_0// "{0}"
0x20334  ldc.i4.1
0x20335  newarr   [mscorlib]System.Object
0x2033a  dup
0x2033b  ldc.i4.0
0x2033c  ldloc.s  4
0x2033e  stelem.ref
0x2033f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20344  ldstr    aMalformedXml// "Malformed XML"
0x20349  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2034e  throw
0x2034f  ldloc.3
0x20350  ret
```
