# Microsoft.Crm.Authentication.Claims.CertificateUtility::get_DecryptionCertificates

- ea: `0xb190`
- end: `0xb257`
- name: `Microsoft.Crm.Authentication.Claims.CertificateUtility::get_DecryptionCertificates`
- size: `199`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb010`

## callees

- `0xb190`

## string_xrefs

- `0xb1a8`: `StoreName`

## pseudocode

```c

```

## disassembly

```asm
0xb190  ldc.i4.5
0xb191  newarr   [mscorlib]System.String
0xb196  dup
0xb197  ldc.i4.0
0xb198  ldstr    aName// "Name"
0xb19d  stelem.ref
0xb19e  dup
0xb19f  ldc.i4.1
0xb1a0  ldstr    aCertificatedat// "CertificateData"
0xb1a5  stelem.ref
0xb1a6  dup
0xb1a7  ldc.i4.2
0xb1a8  ldstr    aStorename// "StoreName"
0xb1ad  stelem.ref
0xb1ae  dup
0xb1af  ldc.i4.3
0xb1b0  ldstr    aStorelocation// "StoreLocation"
0xb1b5  stelem.ref
0xb1b6  dup
0xb1b7  ldc.i4.4
0xb1b8  ldstr    aStorefindtype// "StoreFindType"
0xb1bd  stelem.ref
0xb1be  stloc.0
0xb1bf  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0xb1c4  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb1c9  ldstr    aSecondaryencry// "SecondaryEncrypting"
0xb1ce  ldloc.0
0xb1cf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetCertificates(valuetype [mscorlib]System.Guid, string, string[])
0xb1d4  stloc.1
0xb1d5  call     class [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.ServerInfoProvider::get_Instance()
0xb1da  ldc.i4.0
0xb1db  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles [Microsoft.Crm.Core]Microsoft.Crm.IServerInfoProvider::GetServerRoles(bool)
0xb1e0  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0xb1e5  ldc.i4.8
0xb1e6  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0xb1eb  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0xb1f0  brtrue.s loc_B1F4
0xb1f2  ldloc.1
0xb1f3  ret
0xb1f4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0xb1f9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb1fe  ldstr    aAlternativeenc// "AlternativeEncrypting"
0xb203  ldloc.0
0xb204  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetCertificates(valuetype [mscorlib]System.Guid, string, string[])
0xb209  stloc.2
0xb20a  ldloc.2
0xb20b  brfalse.s loc_B255
0xb20d  ldloc.1
0xb20e  brtrue.s loc_B216
0xb210  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::.ctor()
0xb215  stloc.1
0xb216  ldloc.2
0xb217  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0xb21c  stloc.3
0xb21d  br.s     loc_B23C
0xb21f  ldloca.s 3
0xb221  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0xb226  stloc.s  4
0xb228  ldloc.1
0xb229  ldloca.s 4
0xb22b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Key()
0xb230  ldloca.s 4
0xb232  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0xb237  callvirt instance void class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::Add(var<u1>, !!T0)
0xb23c  ldloca.s 3
0xb23e  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0xb243  brtrue.s loc_B21F
0xb245  leave.s  loc_B255
0xb247  ldloca.s 3
0xb249  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0xb24f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb254  endfinally
0xb255  ldloc.1
0xb256  ret
```
