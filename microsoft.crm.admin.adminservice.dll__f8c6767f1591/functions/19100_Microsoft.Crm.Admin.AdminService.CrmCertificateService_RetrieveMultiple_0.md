# Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple_0

- ea: `0x19100`
- end: `0x1930b`
- name: `Microsoft.Crm.Admin.AdminService.CrmCertificateService::RetrieveMultiple_0`
- size: `523`
- prototype: ``
- caller_count: `8`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18860`
- `0x18c70`
- `0x18ce0`
- `0x18d90`
- `0x18e80`
- `0x18ef0`
- `0x18f30`
- `0x190f0`

## callees

- `0x19100`
- `0x19590`
- `0x19730`
- `0x197c0`
- `0x197e0`
- `0x19840`
- `0x19860`

## string_xrefs

- `0x1921f`: `D:\a\1\s\src\CrmLive\Admin\Certificates\CrmCertificateService.cs`
- `0x1923e`: `D:\a\1\s\src\CrmLive\Admin\Certificates\CrmCertificateService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x19100  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x19105  ldc.i4.s 0x14
0x19107  ldstr    aRetrieveMultip_0// "Retrieve multiple Certificates"
0x1910c  ldc.i4.0
0x1910d  newarr   [mscorlib]System.Object
0x19112  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19117  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x1911c  stloc.0
0x1911d  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x19122  stloc.1
0x19123  ldnull
0x19124  stloc.2
0x19125  ldarg.1
0x19126  brfalse  loc_1922C
0x1912b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::.ctor()
0x19130  stloc.3
0x19131  ldarg.1
0x19132  callvirt instance string[] Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateTypes()
0x19137  brfalse.s loc_1918A
0x19139  ldarg.1
0x1913a  callvirt instance string[] Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateTypes()
0x1913f  ldlen
0x19140  brfalse.s loc_1918A
0x19142  ldarg.1
0x19143  callvirt instance string[] Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateTypes()
0x19148  stloc.s  4
0x1914a  ldc.i4.0
0x1914b  stloc.s  5
0x1914d  br.s     loc_19182
0x1914f  ldloc.s  4
0x19151  ldloc.s  5
0x19153  ldelem.ref
0x19154  stloc.s  6
0x19156  ldloc.s  6
0x19158  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1915d  brtrue.s loc_1917C
0x1915f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x19164  stloc.s  7
0x19166  ldloc.s  7
0x19168  ldstr    aType// "Type"
0x1916d  ldloc.s  6
0x1916f  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x19174  ldloc.3
0x19175  ldloc.s  7
0x19177  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x1917c  ldloc.s  5
0x1917e  ldc.i4.1
0x1917f  add
0x19180  stloc.s  5
0x19182  ldloc.s  5
0x19184  ldloc.s  4
0x19186  ldlen
0x19187  conv.i4
0x19188  blt.s    loc_1914F
0x1918a  ldloc.3
0x1918b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x19190  ldc.i4.0
0x19191  bgt.s    loc_1919E
0x19193  ldloc.3
0x19194  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x19199  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>)
0x1919e  ldloc.3
0x1919f  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x191a4  stloc.s  8
0x191a6  br.s     loc_191EF
0x191a8  ldloca.s 8
0x191aa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x191af  stloc.s  9
0x191b1  ldarg.1
0x191b2  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_Name()
0x191b7  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x191bc  brtrue.s loc_191D0
0x191be  ldloc.s  9
0x191c0  ldstr    aName// "Name"
0x191c5  ldarg.1
0x191c6  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_Name()
0x191cb  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x191d0  ldarg.1
0x191d1  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_ParentId()
0x191d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x191db  brtrue.s loc_191EF
0x191dd  ldloc.s  9
0x191df  ldstr    aParentid// "ParentId"
0x191e4  ldarg.1
0x191e5  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_ParentId()
0x191ea  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x191ef  ldloca.s 8
0x191f1  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x191f6  brtrue.s loc_191A8
0x191f8  leave.s  loc_19208
0x191fa  ldloca.s 8
0x191fc  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x19202  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19207  endfinally
0x19208  ldloc.1
0x19209  ldstr    aCertificates// "Certificates"
0x1920e  ldnull
0x1920f  ldloc.3
0x19210  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::ToArray()
0x19215  ldc.i4   0x21B
0x1921a  ldstr    aRetrievemultip// "RetrieveMultiple"
0x1921f  ldstr    aDA1SSrcCrmlive_34// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Certi"...
0x19224  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x19229  stloc.2
0x1922a  br.s     loc_19249
0x1922c  ldloc.1
0x1922d  ldstr    aCertificates// "Certificates"
0x19232  ldnull
0x19233  ldnull
0x19234  ldc.i4   0x21F
0x19239  ldstr    aRetrievemultip// "RetrieveMultiple"
0x1923e  ldstr    aDA1SSrcCrmlive_34// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Certi"...
0x19243  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x19248  stloc.2
0x19249  ldloc.2
0x1924a  brfalse.s loc_192C0
0x1924c  ldloc.2
0x1924d  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x19252  stloc.s  0xA
0x19254  br.s     loc_192A7
0x19256  ldloca.s 0xA
0x19258  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x1925d  stloc.s  0xC
0x1925f  ldloca.s 0xC
0x19261  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0x19266  newobj   instance void Microsoft.Crm.Admin.AdminService.CertificateData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x1926b  stloc.s  0xB
0x1926d  ldarg.1
0x1926e  brfalse.s loc_1929E
0x19270  ldarg.1
0x19271  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateData()
0x19276  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1927b  brtrue.s loc_1929E
0x1927d  ldarg.1
0x1927e  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateData()
0x19283  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x19288  brtrue.s loc_192A7
0x1928a  ldloc.s  0xB
0x1928c  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateData::get_Certificate()
0x19291  ldarg.1
0x19292  callvirt instance string Microsoft.Crm.Admin.AdminService.CertificateFilter::get_CertificateData()
0x19297  callvirt instance bool [mscorlib]System.String::Equals(string)
0x1929c  brfalse.s loc_192A7
0x1929e  ldloc.0
0x1929f  ldloc.s  0xB
0x192a1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x192a6  pop
0x192a7  ldloca.s 0xA
0x192a9  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x192ae  brtrue.s loc_19256
0x192b0  leave.s  loc_192C0
0x192b2  ldloca.s 0xA
0x192b4  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x192ba  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x192bf  endfinally
0x192c0  ldloc.0
0x192c1  ldtoken  Microsoft.Crm.Admin.AdminService.CertificateData
0x192c6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x192cb  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x192d0  castclass class Microsoft.Crm.Admin.AdminService.CertificateData[]
0x192d5  stloc.s  0xD
0x192d7  leave.s  loc_19308
0x192d9  ldloc.1
0x192da  brfalse.s loc_192E2
0x192dc  ldloc.1
0x192dd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x192e2  endfinally
0x192e3  stloc.s  0xE
0x192e5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x192ea  ldc.i4.s 0x14
0x192ec  ldstr    aExceptionInRet_3// "Exception in retrieve multiple Certific"...
0x192f1  ldc.i4.1
0x192f2  newarr   [mscorlib]System.Object
0x192f7  dup
0x192f8  ldc.i4.0
0x192f9  ldloc.s  0xE
0x192fb  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19300  stelem.ref
0x19301  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x19306  rethrow
0x19308  ldloc.s  0xD
0x1930a  ret
```
