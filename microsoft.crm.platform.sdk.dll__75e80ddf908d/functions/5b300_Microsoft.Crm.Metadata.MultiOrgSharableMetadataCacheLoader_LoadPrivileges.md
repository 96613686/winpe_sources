# Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadPrivileges

- ea: `0x5b300`
- end: `0x5b412`
- name: `Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader::LoadPrivileges`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5ae90`

## callees

- `0x523d0`
- `0x528b0`
- `0x529d0`
- `0x52d80`
- `0x539e0`
- `0x5b300`
- `0xabc70`
- `0xabd70`
- `0xabef0`
- `0xabf10`
- `0xac270`

## string_xrefs

- `0x5b33b`: `Privilege`
- `0x5b352`: `Privilege`
- `0x5b3bd`: `Privilege`
- `0x5b3d9`: `Privilege`
- `0x5b31c`: `LoadPrivileges`

## pseudocode

```c

```

## disassembly

```asm
0x5b300  newobj   instance void <>c__DisplayClass10_0::.ctor()
0x5b305  stloc.0
0x5b306  ldloc.0
0x5b307  ldarg.0
0x5b308  stfld    class Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader <>c__DisplayClass10_0::<>4__this
0x5b30d  ldloc.0
0x5b30e  ldarg.s  4
0x5b310  stfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::aggregateContainer
0x5b315  ldloc.0
0x5b316  ldarg.3
0x5b317  stfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::systemContainer
0x5b31c  ldstr    aLoadprivileges// "LoadPrivileges"
0x5b321  ldarg.s  6
0x5b323  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x5b328  dup
0x5b329  starg.s  6
0x5b32b  stloc.1
0x5b32c  ldarg.1
0x5b32d  brfalse.s loc_5B39E
0x5b32f  ldloc.0
0x5b330  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::aggregateContainer
0x5b335  ldloc.0
0x5b336  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::systemContainer
0x5b33b  ldstr    aPrivilege// "Privilege"
0x5b340  callvirt instance int32 Microsoft.Crm.Metadata.MetadataContainer::GetSize(string name)
0x5b345  ldarg.s  5
0x5b347  callvirt instance class MultiOrgSharableSelectConditions TableFillPropertiesMultiOrg::get_SelectConditions()
0x5b34c  callvirt instance int32 MultiOrgSharableSelectConditions::get_CountOnlyPublishedNoSystemRows()
0x5b351  add
0x5b352  ldstr    aPrivilege// "Privilege"
0x5b357  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::InitializeSize(int32 size, string name)
0x5b35c  ldloc.0
0x5b35d  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::systemContainer
0x5b362  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege> Microsoft.Crm.Metadata.MetadataContainer::get_Privileges()
0x5b367  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Metadata.Privilege>::GetEnumerator()
0x5b36c  stloc.3
0x5b36d  br.s     loc_5B385
0x5b36f  ldloca.s 3
0x5b371  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>::get_Current()
0x5b376  stloc.s  4
0x5b378  ldloc.0
0x5b379  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::aggregateContainer
0x5b37e  ldloc.s  4
0x5b380  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::AddPrivilege(class Microsoft.Crm.Metadata.Privilege privilege)
0x5b385  ldloca.s 3
0x5b387  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>::MoveNext()
0x5b38c  brtrue.s loc_5B36F
0x5b38e  leave.s  loc_5B3E3
0x5b390  ldloca.s 3
0x5b392  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Metadata.Privilege>
0x5b398  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b39d  endfinally
0x5b39e  ldloc.0
0x5b39f  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::aggregateContainer
0x5b3a4  ldarg.s  5
0x5b3a6  callvirt instance class MultiOrgSharableSelectConditions TableFillPropertiesMultiOrg::get_SelectConditions()
0x5b3ab  callvirt instance int32 MultiOrgSharableSelectConditions::get_CountOnlySystemRows()
0x5b3b0  ldarg.s  5
0x5b3b2  callvirt instance class MultiOrgSharableSelectConditions TableFillPropertiesMultiOrg::get_SelectConditions()
0x5b3b7  callvirt instance int32 MultiOrgSharableSelectConditions::get_CountOnlyPublishedNoSystemRows()
0x5b3bc  add
0x5b3bd  ldstr    aPrivilege// "Privilege"
0x5b3c2  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::InitializeSize(int32 size, string name)
0x5b3c7  ldloc.0
0x5b3c8  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::systemContainer
0x5b3cd  ldarg.s  5
0x5b3cf  callvirt instance class MultiOrgSharableSelectConditions TableFillPropertiesMultiOrg::get_SelectConditions()
0x5b3d4  callvirt instance int32 MultiOrgSharableSelectConditions::get_CountOnlySystemRows()
0x5b3d9  ldstr    aPrivilege// "Privilege"
0x5b3de  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::InitializeSize(int32 size, string name)
0x5b3e3  ldarg.s  5
0x5b3e5  ldarg.1
0x5b3e6  callvirt instance string TableFillPropertiesMultiOrg::BuildSelectCommandText(bool isSystemDataLoaded)
0x5b3eb  stloc.2
0x5b3ec  ldarg.2
0x5b3ed  ldloc.2
0x5b3ee  ldc.i4.1
0x5b3ef  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x5b3f4  ldloc.0
0x5b3f5  ldftn    instance void <>c__DisplayClass10_0::<LoadPrivileges>b__0(class [System.Data]System.Data.IDataReader reader)
0x5b3fb  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x5b400  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0x5b405  leave.s  loc_5B411
0x5b407  ldloc.1
0x5b408  brfalse.s loc_5B410
0x5b40a  ldloc.1
0x5b40b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b410  endfinally
0x5b411  ret
```
