# <>c__DisplayClass47_1::<LoadOrgSettings>b__1

- ea: `0xab6f0`
- end: `0xab77c`
- name: `<>c__DisplayClass47_1::<LoadOrgSettings>b__1`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x19b60`
- `0x19b80`
- `0x4c280`
- `0x51f10`
- `0xab6f0`

## string_xrefs

- `0xab710`: `The fillable description created for the organization should be OrganizationDescription inheriting object`
- `0xab73e`: `SiteMapXml`
- `0xab75b`: `SiteMapXml`

## pseudocode

```c

```

## disassembly

```asm
0xab6f0  br.s     loc_AB770
0xab6f2  ldarg.0
0xab6f3  ldfld    class <>c__DisplayClass47_0 <>c__DisplayClass47_1::CS$<>8__locals1
0xab6f8  ldfld    class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader <>c__DisplayClass47_0::<>4__this
0xab6fd  ldstr    aOrganization// "Organization"
0xab702  callvirt instance class Microsoft.Crm.Metadata.IFillableMetadataDescription Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFillableDescription(string name)
0xab707  isinst   Microsoft.Crm.Metadata.OrganizationDescription
0xab70c  stloc.0
0xab70d  ldloc.0
0xab70e  brtrue.s loc_AB720
0xab710  ldstr    aTheFillableDes// "The fillable description created for th"...
0xab715  ldc.i4   0x80040216
0xab71a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xab71f  throw
0xab720  ldarg.0
0xab721  ldfld    class <>c__DisplayClass47_0 <>c__DisplayClass47_1::CS$<>8__locals1
0xab726  ldfld    class Microsoft.Crm.Metadata.IMetadataContainer <>c__DisplayClass47_0::container
0xab72b  ldarg.1
0xab72c  ldarg.0
0xab72d  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> <>c__DisplayClass47_1::enabledMuiLanguages
0xab732  ldloc.0
0xab733  newobj   instance void Microsoft.Crm.Metadata.Organization::.ctor(class [System.Data]System.Data.IDataReader reader, class [mscorlib]System.Collections.Generic.IEnumerable`1<int32> enabledMuiLanguages, class Microsoft.Crm.Metadata.OrganizationDescription descriptionToUse)
0xab738  callvirt instance void Microsoft.Crm.Metadata.IMetadataContainer::set_OrganizationSettings(class Microsoft.Crm.Metadata.Organization value)
0xab73d  ldarg.1
0xab73e  ldstr    aSitemapxml// "SiteMapXml"
0xab743  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xab748  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xab74d  beq.s    loc_AB77B
0xab74f  ldarg.0
0xab750  ldfld    class <>c__DisplayClass47_0 <>c__DisplayClass47_1::CS$<>8__locals1
0xab755  ldfld    class Microsoft.Crm.Metadata.IMetadataContainer <>c__DisplayClass47_0::container
0xab75a  ldarg.1
0xab75b  ldstr    aSitemapxml// "SiteMapXml"
0xab760  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xab765  castclass [mscorlib]System.String
0xab76a  callvirt instance void Microsoft.Crm.Metadata.IMetadataContainer::set_SiteMapXml(string value)
0xab76f  ret
0xab770  ldarg.1
0xab771  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xab776  brtrue   loc_AB6F2
0xab77b  ret
```
