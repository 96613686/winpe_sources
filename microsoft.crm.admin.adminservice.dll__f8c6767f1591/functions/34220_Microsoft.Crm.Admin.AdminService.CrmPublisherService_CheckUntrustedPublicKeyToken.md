# Microsoft.Crm.Admin.AdminService.CrmPublisherService::CheckUntrustedPublicKeyToken

- ea: `0x34220`
- end: `0x342cb`
- name: `Microsoft.Crm.Admin.AdminService.CrmPublisherService::CheckUntrustedPublicKeyToken`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x34650`

## callees

- `0x34220`
- `0x342d0`
- `0x347e0`
- `0x34870`

## string_xrefs

- `0x3423c`: `publicKeyToken`
- `0x34251`: `PublicKeyToken`
- `0x34227`: `RetrieveByPublicKeyTokenAndFullyQualifiedName: publicKeyToken = {0}`

## pseudocode

```c

```

## disassembly

```asm
0x34220  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x34225  ldc.i4.s 0x1D
0x34227  ldstr    aRetrievebypubl_0// "RetrieveByPublicKeyTokenAndFullyQualifi"...
0x3422c  ldc.i4.1
0x3422d  newarr   [mscorlib]System.Object
0x34232  dup
0x34233  ldc.i4.0
0x34234  ldarg.0
0x34235  stelem.ref
0x34236  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3423b  ldarg.0
0x3423c  ldstr    aPublickeytoken// "publicKeyToken"
0x34241  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x34246  ldarg.0
0x34247  ldstr    aFullyqualified// "fullyQualifiedName"
0x3424c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x34251  ldstr    aPublickeytoken_0// "PublicKeyToken"
0x34256  ldarg.0
0x34257  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection Microsoft.Crm.Admin.AdminService.CrmPublisherService::RetrieveFromPublisherData(string key, string value)
0x3425c  stloc.0
0x3425d  ldloc.0
0x3425e  brfalse.s loc_34268
0x34260  ldloc.0
0x34261  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0x34266  brtrue.s loc_34269
0x34268  ret
0x34269  ldloc.0
0x3426a  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x3426f  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x34274  stloc.1
0x34275  br.s     loc_342B1
0x34277  ldloca.s 1
0x34279  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x3427e  newobj   instance void Microsoft.Crm.Admin.AdminService.PublisherData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x34283  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.PluginTrustLevel Microsoft.Crm.Admin.AdminService.PublisherData::get_TrustLevel()
0x34288  ldc.i4.2
0x34289  bne.un.s loc_342AF
0x3428b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x34290  ldstr    aActionFailedFo// "Action failed for assembly '{0}': Publi"...
0x34295  ldc.i4.1
0x34296  newarr   [mscorlib]System.Object
0x3429b  dup
0x3429c  ldc.i4.0
0x3429d  ldarg.1
0x3429e  stelem.ref
0x3429f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x342a4  ldc.i4   0x80044170
0x342a9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x342ae  throw
0x342af  leave.s  loc_342CA
0x342b1  ldloca.s 1
0x342b3  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x342b8  brtrue.s loc_34277
0x342ba  leave.s  loc_342CA
0x342bc  ldloca.s 1
0x342be  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x342c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x342c9  endfinally
0x342ca  ret
```
