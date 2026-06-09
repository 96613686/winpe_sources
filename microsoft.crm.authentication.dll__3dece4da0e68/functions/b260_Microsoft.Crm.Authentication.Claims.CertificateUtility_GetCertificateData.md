# Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificateData

- ea: `0xb260`
- end: `0xb31a`
- name: `Microsoft.Crm.Authentication.Claims.CertificateUtility::GetCertificateData`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb000`

## callees

- `0xb260`

## string_xrefs

- `0xb293`: `StoreName`

## pseudocode

```c

```

## disassembly

```asm
0xb260  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xb265  ldc.i4.s 0x16
0xb267  ldstr    aTryingToGetCer// "Trying to get CertificateData for Certi"...
0xb26c  ldc.i4.1
0xb26d  newarr   [mscorlib]System.Object
0xb272  dup
0xb273  ldc.i4.0
0xb274  ldarg.0
0xb275  stelem.ref
0xb276  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb27b  ldc.i4.5
0xb27c  newarr   [mscorlib]System.String
0xb281  dup
0xb282  ldc.i4.0
0xb283  ldstr    aName// "Name"
0xb288  stelem.ref
0xb289  dup
0xb28a  ldc.i4.1
0xb28b  ldstr    aCertificatedat// "CertificateData"
0xb290  stelem.ref
0xb291  dup
0xb292  ldc.i4.2
0xb293  ldstr    aStorename// "StoreName"
0xb298  stelem.ref
0xb299  dup
0xb29a  ldc.i4.3
0xb29b  ldstr    aStorelocation// "StoreLocation"
0xb2a0  stelem.ref
0xb2a1  dup
0xb2a2  ldc.i4.4
0xb2a3  ldstr    aStorefindtype// "StoreFindType"
0xb2a8  stelem.ref
0xb2a9  stloc.0
0xb2aa  call     class [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.AuthManagementInfoProvider::get_Instance()
0xb2af  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xb2b4  ldarg.0
0xb2b5  ldloc.0
0xb2b6  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.IAuthManagementInfoProvider::GetCertificates(valuetype [mscorlib]System.Guid, string, string[])
0xb2bb  stloc.1
0xb2bc  ldloc.1
0xb2bd  brfalse.s loc_B2C7
0xb2bf  ldloc.1
0xb2c0  callvirt instance int32 class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Count()
0xb2c5  brtrue.s loc_B2EB
0xb2c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xb2cc  ldstr    aCertificatedat_0// "CertificateData for CertificateType: {0"...
0xb2d1  ldc.i4.1
0xb2d2  newarr   [mscorlib]System.Object
0xb2d7  dup
0xb2d8  ldc.i4.0
0xb2d9  ldarg.0
0xb2da  stelem.ref
0xb2db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xb2e0  ldc.i4   0x8005E239
0xb2e5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xb2ea  throw
0xb2eb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xb2f0  ldc.i4.s 0x16
0xb2f2  ldstr    aFoundCertifica// "Found CertificateData for CertificateTy"...
0xb2f7  ldc.i4.1
0xb2f8  newarr   [mscorlib]System.Object
0xb2fd  dup
0xb2fe  ldc.i4.0
0xb2ff  ldarg.0
0xb300  stelem.ref
0xb301  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb306  ldloc.1
0xb307  call     T0x2B00001B
0xb30c  stloc.2
0xb30d  ldloca.s 2
0xb30f  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Value()
0xb314  newobj   instance void [Microsoft.Crm.Admin.AdminService]Microsoft.Crm.Admin.AdminService.CertificateData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag)
0xb319  ret
```
