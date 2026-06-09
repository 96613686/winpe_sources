# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromLocalFile

- ea: `0x504b0`
- end: `0x506ff`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromLocalFile`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x503a0`

## callees

- `0x49510`
- `0x504b0`
- `0x507e0`
- `0x50900`
- `0x50a80`
- `0x50f60`
- `0x523d0`

## string_xrefs

- `0x50593`: `Build XmlDocument from XmlReader`
- `0x505ea`: `Build XmlDocument from XmlReader`
- `0x504b0`: `LoadCacheFromLocalFile`
- `0x504bf`: `ASP_BEGIN_MDCACHE_LOADFROMLOCALFILE`
- `0x506b1`: `LoadCacheFromLocalFile() got exception message: {0} Detais: {1}. To recover, Cache will be loaded from server`
- `0x506d8`: `ASP_END_MDCACHE_LOADFROMLOCALFILE`

## pseudocode

```c

```

## disassembly

```asm
0x504b0  ldstr    aLoadcachefroml// "LoadCacheFromLocalFile"
0x504b5  ldarg.3
0x504b6  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x504bb  dup
0x504bc  starg.s  3
0x504be  stloc.0
0x504bf  ldstr    aAspBeginMdcach_0// "ASP_BEGIN_MDCACHE_LOADFROMLOCALFILE"
0x504c4  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x504c9  ldarg.2
0x504ca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x504cf  stloc.1
0x504d0  ldc.i4.0
0x504d1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x504d6  ldsfld   string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::mutexName
0x504db  ldc.i4.1
0x504dc  newarr   [mscorlib]System.Object
0x504e1  dup
0x504e2  ldc.i4.0
0x504e3  ldloca.s 1
0x504e5  ldstr    aB// "B"
0x504ea  call     instance string [mscorlib]System.Guid::ToString(string)
0x504ef  stelem.ref
0x504f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x504f5  newobj   instance void [mscorlib]System.Threading.Mutex::.ctor(bool, string)
0x504fa  stloc.2
0x504fb  ldloc.2
0x504fc  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x50501  pop
0x50502  ldnull
0x50503  stloc.3
0x50504  ldarg.2
0x50505  ldnull
0x50506  call     string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::GetLocalFileName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] string languageCode)
0x5050b  stloc.s  4
0x5050d  ldloc.s  4
0x5050f  call     bool [mscorlib]System.IO.File::Exists(string)
0x50514  brfalse  loc_50681
0x50519  ldarg.2
0x5051a  isinst   [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx
0x5051f  stloc.s  5
0x50521  ldloc.s  5
0x50523  brfalse  loc_505D2
0x50528  ldloc.s  5
0x5052a  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x5052f  stloc.s  6
0x50531  ldloca.s 6
0x50533  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x50538  brfalse  loc_505D2
0x5053d  ldarg.2
0x5053e  ldloc.s  5
0x50540  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50545  stloc.s  6
0x50547  ldloca.s 6
0x50549  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x5054e  stloc.s  8
0x50550  ldloca.s 8
0x50552  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x50557  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5055c  call     string Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::GetLocalFileName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] string languageCode)
0x50561  stloc.s  7
0x50563  ldloc.s  7
0x50565  call     bool [mscorlib]System.IO.File::Exists(string)
0x5056a  brfalse.s loc_505D2
0x5056c  ldloc.s  7
0x5056e  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTime(string)
0x50573  ldloc.s  4
0x50575  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTime(string)
0x5057a  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5057f  brfalse.s loc_505D2
0x50581  ldloc.s  7
0x50583  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x50588  stloc.s  9
0x5058a  ldloc.s  9
0x5058c  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x50591  stloc.s  0xA
0x50593  ldstr    aBuildXmldocume// "Build XmlDocument from XmlReader"
0x50598  ldarg.3
0x50599  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5059e  stloc.s  0xB
0x505a0  ldloc.s  0xA
0x505a2  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [System.Xml]System.Xml.XmlReader)
0x505a7  stloc.3
0x505a8  leave.s  loc_505B6
0x505aa  ldloc.s  0xB
0x505ac  brfalse.s loc_505B5
0x505ae  ldloc.s  0xB
0x505b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x505b5  endfinally
0x505b6  leave.s  loc_505C4
0x505b8  ldloc.s  0xA
0x505ba  brfalse.s loc_505C3
0x505bc  ldloc.s  0xA
0x505be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x505c3  endfinally
0x505c4  leave.s  loc_505D2
0x505c6  ldloc.s  9
0x505c8  brfalse.s loc_505D1
0x505ca  ldloc.s  9
0x505cc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x505d1  endfinally
0x505d2  ldloc.3
0x505d3  brtrue   loc_50681
0x505d8  ldloc.s  4
0x505da  call     class [mscorlib]System.IO.FileStream [mscorlib]System.IO.File::OpenRead(string)
0x505df  stloc.s  0xC
0x505e1  ldloc.s  0xC
0x505e3  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.Stream)
0x505e8  stloc.s  0xD
0x505ea  ldstr    aBuildXmldocume// "Build XmlDocument from XmlReader"
0x505ef  ldarg.3
0x505f0  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x505f5  stloc.s  0xB
0x505f7  ldloc.s  0xD
0x505f9  call     class [System.Xml]System.Xml.XmlDocument [Microsoft.Crm.Core]Microsoft.Crm.SharedUtil::CreateXmlDocument(class [System.Xml]System.Xml.XmlReader)
0x505fe  stloc.3
0x505ff  leave.s  loc_5060D
0x50601  ldloc.s  0xB
0x50603  brfalse.s loc_5060C
0x50605  ldloc.s  0xB
0x50607  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5060c  endfinally
0x5060d  leave.s  loc_5061B
0x5060f  ldloc.s  0xD
0x50611  brfalse.s loc_5061A
0x50613  ldloc.s  0xD
0x50615  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5061a  endfinally
0x5061b  leave.s  loc_50629
0x5061d  ldloc.s  0xC
0x5061f  brfalse.s loc_50628
0x50621  ldloc.s  0xC
0x50623  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x50628  endfinally
0x50629  ldloc.s  5
0x5062b  brfalse.s loc_50681
0x5062d  ldloc.s  5
0x5062f  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50634  stloc.s  6
0x50636  ldloca.s 6
0x50638  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x5063d  brfalse.s loc_50681
0x5063f  ldloc.s  5
0x50641  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_OrganizationLanguageId()
0x50646  stloc.s  6
0x50648  ldloca.s 6
0x5064a  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x5064f  brfalse.s loc_50681
0x50651  ldloc.3
0x50652  ldloc.s  5
0x50654  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_OrganizationLanguageId()
0x50659  stloc.s  6
0x5065b  ldloca.s 6
0x5065d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x50662  ldloc.s  5
0x50664  callvirt instance valuetype [mscorlib]System.Nullable`1<int32> [Microsoft.Crm]Microsoft.Crm.IOrganizationContextEx::get_ClientUserUILanguageId()
0x50669  stloc.s  6
0x5066b  ldloca.s 6
0x5066d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x50672  ldarg.3
0x50673  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::RemoveExtraLanguages(class [System.Xml]System.Xml.XmlDocument document, int32 orgLanguageId, int32 clientLanguageId, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x50678  ldloc.3
0x50679  ldarg.2
0x5067a  ldarg.3
0x5067b  ldc.i4.1
0x5067c  call     void Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::WriteCacheToLocalFile(class [System.Xml]System.Xml.XmlDocument xmlCache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter, [opt] bool writeToLanguageSpecificFile)
0x50681  ldloc.3
0x50682  brfalse.s loc_506A8
0x50684  ldarg.0
0x50685  ldloc.3
0x50686  ldarg.1
0x50687  ldarg.3
0x50688  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromXml(class [System.Xml]System.Xml.XmlDocument xmlDocument, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5068d  stloc.s  0xE
0x5068f  ldloc.s  0xE
0x50691  brfalse.s loc_5069B
0x50693  ldloc.s  0xE
0x50695  ldc.i4.1
0x50696  callvirt instance void Microsoft.Crm.Metadata.DynamicMetadataCache::set_IsLoadedFromLocalFile(bool value)
0x5069b  ldnull
0x5069c  stloc.3
0x5069d  call     void [mscorlib]System.GC::Collect()
0x506a2  ldloc.s  0xE
0x506a4  stloc.s  0xF
0x506a6  leave.s  loc_506FC
0x506a8  leave.s  loc_506ED
0x506aa  stloc.s  0x10
0x506ac  ldloc.s  0x10
0x506ae  ldloc.1
0x506af  ldc.i4.s 0x19
0x506b1  ldstr    aLoadcachefroml_0// "LoadCacheFromLocalFile() got exception "...
0x506b6  ldc.i4.2
0x506b7  newarr   [mscorlib]System.Object
0x506bc  dup
0x506bd  ldc.i4.0
0x506be  ldloc.s  0x10
0x506c0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x506c5  stelem.ref
0x506c6  dup
0x506c7  ldc.i4.1
0x506c8  ldloc.s  0x10
0x506ca  stelem.ref
0x506cb  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x506d0  leave.s  loc_506ED
0x506d2  ldloc.2
0x506d3  callvirt instance void [mscorlib]System.Threading.Mutex::ReleaseMutex()
0x506d8  ldstr    aAspEndMdcacheL// "ASP_END_MDCACHE_LOADFROMLOCALFILE"
0x506dd  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x506e2  endfinally
0x506e3  ldloc.2
0x506e4  brfalse.s loc_506EC
0x506e6  ldloc.2
0x506e7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x506ec  endfinally
0x506ed  ldnull
0x506ee  stloc.s  0xF
0x506f0  leave.s  loc_506FC
0x506f2  ldloc.0
0x506f3  brfalse.s loc_506FB
0x506f5  ldloc.0
0x506f6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x506fb  endfinally
0x506fc  ldloc.s  0xF
0x506fe  ret
```
