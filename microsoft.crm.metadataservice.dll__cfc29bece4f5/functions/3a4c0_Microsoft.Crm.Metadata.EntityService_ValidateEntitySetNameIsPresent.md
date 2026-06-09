# Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsPresent

- ea: `0x3a4c0`
- end: `0x3a529`
- name: `Microsoft.Crm.Metadata.EntityService::ValidateEntitySetNameIsPresent`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x39620`

## callees

- `0x3a4c0`
- `0x3d000`

## string_xrefs

- `0x3a4fb`: `EntitySetName cannot be updated for OOB entities`
- `0x3a518`: `EntitySetName cannot be updated for OOB entities`

## pseudocode

```c

```

## disassembly

```asm
0x3a4c0  ldarg.2
0x3a4c1  ldstr    aEntitysetname// "entitysetname"
0x3a4c6  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::IsPropertyNull(string)
0x3a4cb  brtrue.s loc_3A4DF
0x3a4cd  ldarg.2
0x3a4ce  ldstr    aEntitysetname// "entitysetname"
0x3a4d3  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x3a4d8  callvirt instance string [mscorlib]System.Object::ToString()
0x3a4dd  br.s     loc_3A4E0
0x3a4df  ldnull
0x3a4e0  stloc.0
0x3a4e1  ldloc.0
0x3a4e2  brfalse.s loc_3A50B
0x3a4e4  ldarg.1
0x3a4e5  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x3a4ea  brfalse.s loc_3A528
0x3a4ec  ldloc.0
0x3a4ed  ldarg.1
0x3a4ee  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x3a4f3  ldc.i4.5
0x3a4f4  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x3a4f9  brtrue.s loc_3A528
0x3a4fb  ldstr    aEntitysetnameC// "EntitySetName cannot be updated for OOB"...
0x3a500  ldc.i4   0x8004F663
0x3a505  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a50a  throw
0x3a50b  ldarg.1
0x3a50c  callvirt instance string Microsoft.Crm.Metadata.EntityUpdateInfo::get_EntitySetName()
0x3a511  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3a516  brtrue.s loc_3A528
0x3a518  ldstr    aEntitysetnameC// "EntitySetName cannot be updated for OOB"...
0x3a51d  ldc.i4   0x8004F663
0x3a522  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x3a527  throw
0x3a528  ret
```
