# Microsoft.Crm.Caching.OrganizationCache::ExamineOrganizationsInCache

- ea: `0x96ec0`
- end: `0x96f80`
- name: `Microsoft.Crm.Caching.OrganizationCache::ExamineOrganizationsInCache`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xae1f0`

## callees

- `0x7b680`
- `0x96ec0`

## string_xrefs

- `0x96ef2`: `OrganizationSettingsCache`
- `0x96f63`: `Examination of Organization Cache failed with exception - {0}`

## pseudocode

```c

```

## disassembly

```asm
0x96ec0  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96ec5  callvirt instance class [Microsoft.Crm]Microsoft.Crm.ICrmCache`1<var<u1>> class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::get_InnerCache()
0x96eca  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [mscorlib]System.Collections.DictionaryEntry> class [Microsoft.Crm]Microsoft.Crm.ICrmCache`1<class Microsoft.Crm.Caching.IOrganizationSettings>::DumpContentsNoLock()
0x96ecf  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Caching.IOrganizationSettings>::.ctor()
0x96ed4  stloc.0
0x96ed5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::GetEnumerator()
0x96eda  stloc.1
0x96edb  br.s     loc_96F29
0x96edd  ldloc.1
0x96ede  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.DictionaryEntry>::get_Current()
0x96ee3  stloc.2
0x96ee4  ldloca.s 2
0x96ee6  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Key()
0x96eeb  callvirt instance string [mscorlib]System.Object::ToString()
0x96ef0  stloc.3
0x96ef1  ldloc.3
0x96ef2  ldstr    aOrganizationse_0// "OrganizationSettingsCache"
0x96ef7  call     instance int32 [mscorlib]System.String::get_Length()
0x96efc  callvirt instance string [mscorlib]System.String::Substring(int32)
0x96f01  stloc.3
0x96f02  ldsfld   class Microsoft.Crm.Caching.OrganizationCache Microsoft.Crm.Caching.OrganizationCache::_innerCache
0x96f07  ldloc.3
0x96f08  callvirt instance bool class Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class Microsoft.Crm.Caching.IOrganizationSettings>::IsCacheKeyForNonDependencyNode(string)
0x96f0d  brfalse.s loc_96F29
0x96f0f  ldloca.s 2
0x96f11  call     instance object [mscorlib]System.Collections.DictionaryEntry::get_Value()
0x96f16  isinst   Microsoft.Crm.Caching.IOrganizationSettings
0x96f1b  stloc.s  4
0x96f1d  ldloc.s  4
0x96f1f  brfalse.s loc_96F29
0x96f21  ldloc.0
0x96f22  ldloc.s  4
0x96f24  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Caching.IOrganizationSettings>::Add(var<u1>)
0x96f29  ldloc.1
0x96f2a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x96f2f  brtrue.s loc_96EDD
0x96f31  leave.s  loc_96F3D
0x96f33  ldloc.1
0x96f34  brfalse.s loc_96F3C
0x96f36  ldloc.1
0x96f37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x96f3c  endfinally
0x96f3d  nop
0x96f3e  ldsfld   class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Caching.ActiveOrganizationExaminationEventArgs> Microsoft.Crm.Caching.OrganizationCache::ActiveOrganizationExaminationCompleted
0x96f43  brfalse.s loc_96F56
0x96f45  ldsfld   class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Caching.ActiveOrganizationExaminationEventArgs> Microsoft.Crm.Caching.OrganizationCache::ActiveOrganizationExaminationCompleted
0x96f4a  ldnull
0x96f4b  ldloc.0
0x96f4c  newobj   instance void Microsoft.Crm.Caching.ActiveOrganizationExaminationEventArgs::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.Crm.Caching.IOrganizationSettings> activeOrganizations)
0x96f51  callvirt instance void class [mscorlib]System.EventHandler`1<class Microsoft.Crm.Caching.ActiveOrganizationExaminationEventArgs>::Invoke(object, var<u1>)
0x96f56  leave.s  loc_96F7F
0x96f58  stloc.s  5
0x96f5a  ldloc.s  5
0x96f5c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x96f61  ldc.i4.s 0x14
0x96f63  ldstr    aExaminationOfO// "Examination of Organization Cache faile"...
0x96f68  ldc.i4.1
0x96f69  newarr   [mscorlib]System.Object
0x96f6e  dup
0x96f6f  ldc.i4.0
0x96f70  ldloc.s  5
0x96f72  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x96f77  stelem.ref
0x96f78  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x96f7d  leave.s  loc_96F7F
0x96f7f  ret
```
