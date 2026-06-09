# <>c__DisplayClass10_0::<LoadPrivileges>b__0

- ea: `0xac280`
- end: `0xac315`
- name: `<>c__DisplayClass10_0::<LoadPrivileges>b__0`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation`

## callees

- `0x4d560`
- `0x51f10`
- `0x539e0`
- `0xac280`

## string_xrefs

- `0xac28b`: `Privilege`
- `0xac29e`: `The fillable description created for a privilege should be a PrivilegeDescription-inheriting object`

## pseudocode

```c

```

## disassembly

```asm
0xac280  br       loc_AC309
0xac285  ldarg.0
0xac286  ldfld    class Microsoft.Crm.Metadata.MultiOrgSharableMetadataCacheLoader <>c__DisplayClass10_0::<>4__this
0xac28b  ldstr    aPrivilege// "Privilege"
0xac290  callvirt instance class Microsoft.Crm.Metadata.IFillableMetadataDescription Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::CreateFillableDescription(string name)
0xac295  isinst   Microsoft.Crm.Metadata.PrivilegeDescription
0xac29a  stloc.0
0xac29b  ldloc.0
0xac29c  brtrue.s loc_AC2AE
0xac29e  ldstr    aTheFillableDes_0// "The fillable description created for a "...
0xac2a3  ldc.i4   0x80040216
0xac2a8  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0xac2ad  throw
0xac2ae  ldarg.1
0xac2af  ldloc.0
0xac2b0  newobj   instance void Microsoft.Crm.Metadata.Privilege::.ctor(class [System.Data]System.Data.IDataReader reader, class Microsoft.Crm.Metadata.PrivilegeDescription descriptionToUse)
0xac2b5  stloc.1
0xac2b6  ldarg.0
0xac2b7  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::aggregateContainer
0xac2bc  ldloc.1
0xac2bd  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::AddPrivilege(class Microsoft.Crm.Metadata.Privilege privilege)
0xac2c2  ldarg.1
0xac2c3  ldstr    aObjecttypecode// "ObjectTypeCode"
0xac2c8  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac2cd  unbox.any [mscorlib]System.Int32
0xac2d2  stloc.2
0xac2d3  ldarg.1
0xac2d4  ldstr    aIscustomentity_0// "IsCustomEntity"
0xac2d9  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac2de  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0xac2e3  beq.s    loc_AC2F7
0xac2e5  ldarg.1
0xac2e6  ldstr    aIscustomentity_0// "IsCustomEntity"
0xac2eb  callvirt instance object [System.Data]System.Data.IDataRecord::get_Item(string)
0xac2f0  unbox.any [mscorlib]System.Boolean
0xac2f5  br.s     loc_AC2F8
0xac2f7  ldc.i4.1
0xac2f8  brfalse.s loc_AC2FD
0xac2fa  ldloc.2
0xac2fb  brtrue.s loc_AC309
0xac2fd  ldarg.0
0xac2fe  ldfld    class Microsoft.Crm.Metadata.MetadataContainer <>c__DisplayClass10_0::systemContainer
0xac303  ldloc.1
0xac304  callvirt instance void Microsoft.Crm.Metadata.MetadataContainer::AddPrivilege(class Microsoft.Crm.Metadata.Privilege privilege)
0xac309  ldarg.1
0xac30a  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xac30f  brtrue   loc_AC285
0xac314  ret
```
