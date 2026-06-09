# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::WriteCacheToLocalFile

- ea: `0x507e0`
- end: `0x508fc`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::WriteCacheToLocalFile`
- size: `284`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x504b0`
- `0x509a0`

## callees

- `0x507e0`
- `0x50900`
- `0x50960`
- `0x523d0`
- `0x6f580`

## string_xrefs

- `0x507e0`: `WriteCacheToLocalFile`
- `0x507ec`: `ASP_BEGIN_MDCACHE_WRITEFILE`
- `0x508d2`: `ASP_END_MDCACHE_WRITEFILE`

## pseudocode

```c

```

## disassembly

```asm
0x507e0  ldstr    aWritecachetolo// "WriteCacheToLocalFile"
0x507e5  ldarg.2
0x507e6  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x507eb  stloc.0
0x507ec  ldstr    aAspBeginMdcach_2// "ASP_BEGIN_MDCACHE_WRITEFILE"
0x507f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x507f6  ldarg.1
0x507f7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x507fc  stloc.1
0x507fd  ldnull
0x507fe  stloc.2
0x507ff  ldarg.3
0x50800  brfalse.s loc_5083F
0x50802  ldarg.1
0x50803  isinst   [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx
0x50808  stloc.s  4
0x5080a  ldloc.s  4
0x5080c  brfalse.s loc_5083F
0x5080e  ldloc.s  4
0x50810  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50815  stloc.s  5
0x50817  ldloca.s 5
0x50819  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x5081e  brfalse.s loc_5083F
0x50820  ldloc.s  4
0x50822  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50827  stloc.s  5
0x50829  ldloca.s 5
0x5082b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x50830  stloc.s  6
0x50832  ldloca.s 6
0x50834  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50839  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5083e  stloc.2
0x5083f  ldarg.1
0x50840  ldloc.2
0x50841  call     string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::GetLocalFileName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] string languageCode)
0x50846  stloc.3
0x50847  ldarg.1
0x50848  call     string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::GetLocalDirectoryName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5084d  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x50852  brtrue.s loc_50860
0x50854  ldarg.1
0x50855  call     string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::GetLocalDirectoryName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x5085a  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::CreateDirectory(string)
0x5085f  pop
0x50860  ldc.i4.0
0x50861  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50866  ldsfld   string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::mutexName
0x5086b  ldc.i4.1
0x5086c  newarr   [mscorlib]System.Object
0x50871  dup
0x50872  ldc.i4.0
0x50873  ldloca.s 1
0x50875  ldstr    aB// "B"
0x5087a  call     instance string [mscorlib]System.Guid::ToString(string)
0x5087f  stelem.ref
0x50880  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x50885  newobj   instance void [mscorlib]System.Threading.Mutex::.ctor(bool, string)
0x5088a  stloc.s  7
0x5088c  ldloc.s  7
0x5088e  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x50893  pop
0x50894  ldloc.3
0x50895  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x5089a  call     class [System.Xml]System.Xml.XmlWriter Microsoft.Crm.Metadata.XmlUtil::CreateXmlWriter(string fileName, class [mscorlib]System.Text.Encoding encoding)
0x5089f  stloc.s  8
0x508a1  ldarg.0
0x508a2  ldloc.s  8
0x508a4  callvirt instance void [System.Xml]System.Xml.XmlDocument::Save(class [System.Xml]System.Xml.XmlWriter)
0x508a9  ldloc.s  8
0x508ab  callvirt instance void [System.Xml]System.Xml.XmlWriter::Flush()
0x508b0  leave.s  loc_508D2
0x508b2  ldloc.s  8
0x508b4  brfalse.s loc_508BD
0x508b6  ldloc.s  8
0x508b8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x508bd  endfinally
0x508be  ldloc.s  7
0x508c0  callvirt instance void [mscorlib]System.Threading.Mutex::ReleaseMutex()
0x508c5  endfinally
0x508c6  ldloc.s  7
0x508c8  brfalse.s loc_508D1
0x508ca  ldloc.s  7
0x508cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x508d1  endfinally
0x508d2  ldstr    aAspEndMdcacheW// "ASP_END_MDCACHE_WRITEFILE"
0x508d7  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x508dc  ldloc.1
0x508dd  ldc.i4.s 0x19
0x508df  ldstr    aWroteMetadataT// "Wrote Metadata to local file."
0x508e4  ldc.i4.0
0x508e5  newarr   [mscorlib]System.Object
0x508ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x508ef  leave.s  loc_508FB
0x508f1  ldloc.0
0x508f2  brfalse.s loc_508FA
0x508f4  ldloc.0
0x508f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x508fa  endfinally
0x508fb  ret
```
