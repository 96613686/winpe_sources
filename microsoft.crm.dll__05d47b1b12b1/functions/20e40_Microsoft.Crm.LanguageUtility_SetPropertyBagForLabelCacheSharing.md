# Microsoft.Crm.LanguageUtility::SetPropertyBagForLabelCacheSharing

- ea: `0x20e40`
- end: `0x20e92`
- name: `Microsoft.Crm.LanguageUtility::SetPropertyBagForLabelCacheSharing`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x20d10`

## string_xrefs

- `0x20e63`: `LabelCacheSharingEnabled`
- `0x20e76`: `OrganizationLanguagePack: LabelCacheSharingEnabled set to {0} in database`

## pseudocode

```c

```

## disassembly

```asm
0x20e40  ldarg.0
0x20e41  ldarg.1
0x20e42  ldarg.2
0x20e43  ldarg.3
0x20e44  call     bool Microsoft.Crm.LanguageUtility::IsValidMuiPackVersion(string versionInFileValue, string versionInDbValue, string versionOfCrmValue, valuetype [mscorlib]System.Guid organizationId)
0x20e49  stloc.0
0x20e4a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x20e4f  stloc.1
0x20e50  ldloc.1
0x20e51  ldstr    aLanguageid_0// "LanguageId"
0x20e56  ldarg.s  4
0x20e58  box      [mscorlib]System.Int32
0x20e5d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x20e62  ldloc.1
0x20e63  ldstr    aLabelcacheshar// "LabelCacheSharingEnabled"
0x20e68  ldloc.0
0x20e69  box      [mscorlib]System.Boolean
0x20e6e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::SetValue(string, object)
0x20e73  ldarg.3
0x20e74  ldc.i4.s 0x1A
0x20e76  ldstr    aOrganizationla// "OrganizationLanguagePack: LabelCacheSha"...
0x20e7b  ldc.i4.1
0x20e7c  newarr   [mscorlib]System.Object
0x20e81  dup
0x20e82  ldc.i4.0
0x20e83  ldloca.s 0
0x20e85  call     instance string [mscorlib]System.Boolean::ToString()
0x20e8a  stelem.ref
0x20e8b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20e90  ldloc.1
0x20e91  ret
```
