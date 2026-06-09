# Microsoft.Crm.Entities.CommunicationActivity::Merge

- ea: `0x800`
- end: `0xa08`
- name: `Microsoft.Crm.Entities.CommunicationActivity::Merge`
- size: `520`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x100`
- `0x800`
- `0xc50`
- `0xc60`
- `0xc90`
- `0xd80`

## pseudocode

```c

```

## disassembly

```asm
0x800  ldarg.0
0x801  ldarg.1
0x802  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Merge(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x807  castclass Microsoft.Crm.Entities.CommunicationActivity
0x80c  stloc.0
0x80d  ldarg.1
0x80e  castclass Microsoft.Crm.Entities.CommunicationActivity
0x813  stloc.1
0x814  ldarg.0
0x815  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x81a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x81f  stloc.2
0x820  br       loc_8FB
0x825  ldloc.2
0x826  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x82b  castclass Microsoft.Crm.Entities.PartyMappingItem
0x830  stloc.3
0x831  ldloc.1
0x832  callvirt instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x837  ldloc.3
0x838  callvirt instance valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x83d  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(valuetype Microsoft.Crm.Entities.ParticipationType type)
0x842  dup
0x843  brtrue.s loc_855
0x845  ldstr    aOneActivityDoe// "One Activity does not have party mappin"...
0x84a  ldc.i4   0x80043515
0x84f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x854  throw
0x855  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x85a  brtrue   loc_8FB
0x85f  ldloc.0
0x860  callvirt instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x865  ldloc.3
0x866  callvirt instance valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x86b  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(valuetype Microsoft.Crm.Entities.ParticipationType type)
0x870  stloc.s  4
0x872  ldloc.s  4
0x874  brtrue.s loc_886
0x876  ldstr    aMergedActivity// "Merged Activity does not have party map"...
0x87b  ldc.i4   0x80043515
0x880  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x885  throw
0x886  ldloc.s  4
0x888  ldstr    aActivityparty// "ActivityParty"
0x88d  ldarg.0
0x88e  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_OrganizationId()
0x893  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x898  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x89d  ldloc.3
0x89e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x8a3  brfalse.s loc_8FB
0x8a5  ldloc.3
0x8a6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x8ab  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x8b0  stloc.s  5
0x8b2  br.s     loc_8DB
0x8b4  ldloc.s  5
0x8b6  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8bb  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8c0  stloc.s  6
0x8c2  ldloc.s  4
0x8c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x8c9  ldloc.s  6
0x8cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone()
0x8d0  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x8d5  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x8da  pop
0x8db  ldloc.s  5
0x8dd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8e2  brtrue.s loc_8B4
0x8e4  leave.s  loc_8FB
0x8e6  ldloc.s  5
0x8e8  isinst   [mscorlib]System.IDisposable
0x8ed  stloc.s  7
0x8ef  ldloc.s  7
0x8f1  brfalse.s loc_8FA
0x8f3  ldloc.s  7
0x8f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8fa  endfinally
0x8fb  ldloc.2
0x8fc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x901  brtrue   loc_825
0x906  leave.s  loc_91C
0x908  ldloc.2
0x909  isinst   [mscorlib]System.IDisposable
0x90e  stloc.s  7
0x910  ldloc.s  7
0x912  brfalse.s loc_91B
0x914  ldloc.s  7
0x916  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x91b  endfinally
0x91c  ldloc.1
0x91d  callvirt instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x922  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x927  stloc.2
0x928  br       loc_9E5
0x92d  ldloc.2
0x92e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x933  castclass Microsoft.Crm.Entities.PartyMappingItem
0x938  stloc.s  8
0x93a  ldloc.s  8
0x93c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x941  brfalse  loc_9E5
0x946  ldloc.0
0x947  callvirt instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x94c  ldloc.s  8
0x94e  callvirt instance valuetype Microsoft.Crm.Entities.ParticipationType Microsoft.Crm.Entities.PartyMappingItem::get_Type()
0x953  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(valuetype Microsoft.Crm.Entities.ParticipationType type)
0x958  stloc.s  9
0x95a  ldloc.s  9
0x95c  brtrue.s loc_96E
0x95e  ldstr    aMergedActivity// "Merged Activity does not have party map"...
0x963  ldc.i4   0x80043515
0x968  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x96d  throw
0x96e  ldloc.s  9
0x970  ldstr    aActivityparty// "ActivityParty"
0x975  ldarg.0
0x976  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_OrganizationId()
0x97b  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x980  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x985  ldloc.s  8
0x987  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x98c  brfalse.s loc_9E5
0x98e  ldloc.s  8
0x990  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x995  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x99a  stloc.s  5
0x99c  br.s     loc_9C5
0x99e  ldloc.s  5
0x9a0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9a5  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x9aa  stloc.s  0xA
0x9ac  ldloc.s  9
0x9ae  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x9b3  ldloc.s  0xA
0x9b5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::Clone()
0x9ba  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x9bf  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x9c4  pop
0x9c5  ldloc.s  5
0x9c7  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9cc  brtrue.s loc_99E
0x9ce  leave.s  loc_9E5
0x9d0  ldloc.s  5
0x9d2  isinst   [mscorlib]System.IDisposable
0x9d7  stloc.s  7
0x9d9  ldloc.s  7
0x9db  brfalse.s loc_9E4
0x9dd  ldloc.s  7
0x9df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e4  endfinally
0x9e5  ldloc.2
0x9e6  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9eb  brtrue   loc_92D
0x9f0  leave.s  loc_A06
0x9f2  ldloc.2
0x9f3  isinst   [mscorlib]System.IDisposable
0x9f8  stloc.s  7
0x9fa  ldloc.s  7
0x9fc  brfalse.s loc_A05
0x9fe  ldloc.s  7
0xa00  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa05  endfinally
0xa06  ldloc.0
0xa07  ret
```
