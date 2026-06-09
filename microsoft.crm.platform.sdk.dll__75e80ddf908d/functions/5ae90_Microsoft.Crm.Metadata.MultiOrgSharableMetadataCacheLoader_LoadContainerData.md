# Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadContainerData

- ea: `0x5ae90`
- end: `0x5afda`
- name: `Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadContainerData`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5a7d0`

## callees

- `0x50cf0`
- `0x50d30`
- `0x51350`
- `0x51f70`
- `0x51f90`
- `0x51fb0`
- `0x52020`
- `0x523d0`
- `0x52880`
- `0x528a0`
- `0x5ae90`
- `0x5afe0`
- `0x5b300`

## string_xrefs

- `0x5aecb`: `Privilege`
- `0x5af7f`: `Could not load metadata cache due to frequent MD changes`
- `0x5af8f`: `Could not load metadata cache due to frequent MD changes`

## pseudocode

```c

```

## disassembly

```asm
0x5ae90  ldstr    aLoadcontainerd// "LoadContainerData"
0x5ae95  ldarg.s  7
0x5ae97  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5ae9c  dup
0x5ae9d  starg.s  7
0x5ae9f  stloc.0
0x5aea0  ldc.i4.0
0x5aea1  stloc.3
0x5aea2  ldarg.0
0x5aea3  ldarg.3
0x5aea4  ldarg.s  7
0x5aea6  call     instance class Microsoft.Crm.Metadata.MetadataTimestamp Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::GenerateTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5aeab  stloc.1
0x5aeac  ldarg.s  6
0x5aeae  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class TableFillPropertiesMultiOrg>::GetEnumerator()
0x5aeb3  stloc.s  4
0x5aeb5  br.s     loc_5AF27
0x5aeb7  ldloca.s 4
0x5aeb9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TableFillPropertiesMultiOrg>::get_Current()
0x5aebe  stloc.s  5
0x5aec0  ldloc.s  5
0x5aec2  callvirt instance string Microsoft.Crm.Metadata.TableFillProperties::get_MetadataEntityName()
0x5aec7  stloc.s  6
0x5aec9  ldloc.s  6
0x5aecb  ldstr    aPrivilege// "Privilege"
0x5aed0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5aed5  brtrue.s loc_5AEE7
0x5aed7  ldloc.s  6
0x5aed9  ldstr    aAttributepickl// "AttributePicklistValue"
0x5aede  call     bool [mscorlib]System.String::op_Equality(string, string)
0x5aee3  brtrue.s loc_5AEF9
0x5aee5  br.s     loc_5AF11
0x5aee7  ldarg.0
0x5aee8  ldarg.1
0x5aee9  ldarg.3
0x5aeea  ldarg.s  4
0x5aeec  ldarg.s  5
0x5aeee  ldloc.s  5
0x5aef0  ldarg.s  7
0x5aef2  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadPrivileges(bool isSystemDataLoaded, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class Microsoft.Crm.Metadata.MetadataContainer systemContainer, class Microsoft.Crm.Metadata.MetadataContainer aggregateContainer, class TableFillPropertiesMultiOrg properties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5aef7  br.s     loc_5AF27
0x5aef9  ldarg.0
0x5aefa  ldarg.0
0x5aefb  call     instance class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_MetadataForMetadata()
0x5af00  ldarg.2
0x5af01  ldarg.3
0x5af02  ldarg.s  4
0x5af04  ldarg.s  5
0x5af06  ldloc.s  5
0x5af08  ldarg.s  7
0x5af0a  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadDescriptions(class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata, bool isSystemDataLoaded, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class Microsoft.Crm.Metadata.MetadataContainer systemContainer, class Microsoft.Crm.Metadata.MetadataContainer aggregateContainer, class TableFillPropertiesMultiOrg properties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5af0f  br.s     loc_5AF27
0x5af11  ldarg.0
0x5af12  ldarg.0
0x5af13  call     instance class Microsoft.Crm.Metadata.MetadataForMetadata Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_MetadataForMetadata()
0x5af18  ldarg.1
0x5af19  ldarg.3
0x5af1a  ldarg.s  4
0x5af1c  ldarg.s  5
0x5af1e  ldloc.s  5
0x5af20  ldarg.s  7
0x5af22  call     instance void Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadDescriptions(class Microsoft.Crm.Metadata.MetadataForMetadata metadataForMetadata, bool isSystemDataLoaded, class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class Microsoft.Crm.Metadata.MetadataContainer systemContainer, class Microsoft.Crm.Metadata.MetadataContainer aggregateContainer, class TableFillPropertiesMultiOrg properties, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5af27  ldloca.s 4
0x5af29  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TableFillPropertiesMultiOrg>::MoveNext()
0x5af2e  brtrue.s loc_5AEB7
0x5af30  leave.s  loc_5AF40
0x5af32  ldloca.s 4
0x5af34  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class TableFillPropertiesMultiOrg>
0x5af3a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5af3f  endfinally
0x5af40  ldarg.0
0x5af41  ldarg.3
0x5af42  ldarg.s  7
0x5af44  call     instance class Microsoft.Crm.Metadata.MetadataTimestamp Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::GenerateTimestamp(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess crmSqlDataAccesser, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5af49  stloc.2
0x5af4a  ldloc.3
0x5af4b  ldc.i4.1
0x5af4c  add
0x5af4d  stloc.3
0x5af4e  ldloc.1
0x5af4f  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5af54  ldloc.2
0x5af55  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5af5a  beq.s    loc_5AF63
0x5af5c  ldloc.3
0x5af5d  ldc.i4.5
0x5af5e  ble      loc_5AEA2
0x5af63  ldloc.1
0x5af64  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5af69  ldloc.2
0x5af6a  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5af6f  beq.s    loc_5AF9A
0x5af71  ldnull
0x5af72  ldarg.0
0x5af73  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::get_OrganizationContext()
0x5af78  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x5af7d  ldc.i4.s 0x14
0x5af7f  ldstr    aCouldNotLoadMe// "Could not load metadata cache due to fr"...
0x5af84  ldc.i4.0
0x5af85  newarr   [mscorlib]System.Object
0x5af8a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5af8f  ldstr    aCouldNotLoadMe// "Could not load metadata cache due to fr"...
0x5af94  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x5af99  throw
0x5af9a  ldarg.s  5
0x5af9c  ldloc.2
0x5af9d  callvirt instance string Microsoft.Crm.Metadata.MetadataTimestamp::get_CalculatedTimestamp()
0x5afa2  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::set_Timestamp(string value)
0x5afa7  ldarg.s  5
0x5afa9  ldloc.2
0x5afaa  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MinActiveRowVersion()
0x5afaf  ldloc.2
0x5afb0  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5afb5  blt.s    loc_5AFBF
0x5afb7  ldloc.2
0x5afb8  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MaximumSqlTimestamp()
0x5afbd  br.s     loc_5AFC8
0x5afbf  ldloc.2
0x5afc0  callvirt instance int64 Microsoft.Crm.Metadata.MetadataTimestamp::get_MinActiveRowVersion()
0x5afc5  ldc.i4.1
0x5afc6  conv.i8
0x5afc7  sub
0x5afc8  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::set_MinActiveRowVersion(int64 value)
0x5afcd  leave.s  loc_5AFD9
0x5afcf  ldloc.0
0x5afd0  brfalse.s loc_5AFD8
0x5afd2  ldloc.0
0x5afd3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5afd8  endfinally
0x5afd9  ret
```
