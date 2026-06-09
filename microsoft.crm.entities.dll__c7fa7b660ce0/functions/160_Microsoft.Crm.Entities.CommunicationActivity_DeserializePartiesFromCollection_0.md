# Microsoft.Crm.Entities.CommunicationActivity::DeserializePartiesFromCollection_0

- ea: `0x160`
- end: `0x24f`
- name: `Microsoft.Crm.Entities.CommunicationActivity::DeserializePartiesFromCollection_0`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x150`

## callees

- `0x100`
- `0x160`
- `0xc50`
- `0xc60`
- `0xd80`

## string_xrefs

- `0x16b`: `Invalid startIndex or Length passed to DeserializePartiesFromCollection`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.1
0x161  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x166  ldarg.2
0x167  ldarg.3
0x168  add
0x169  bge.s    loc_176
0x16b  ldstr    aInvalidStartin// "Invalid startIndex or Length passed to "...
0x170  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x175  throw
0x176  ldarg.0
0x177  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x17c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x181  stloc.0
0x182  br.s     loc_1BB
0x184  ldloc.0
0x185  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x18a  castclass Microsoft.Crm.Entities.PartyMappingItem
0x18f  stloc.1
0x190  ldloc.1
0x191  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x196  brtrue.s loc_1B0
0x198  ldloc.1
0x199  ldstr    aActivityparty// "ActivityParty"
0x19e  ldarg.0
0x19f  call     instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_OrganizationId()
0x1a4  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x1a9  callvirt instance void Microsoft.Crm.Entities.PartyMappingItem::set_Parties(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection value)
0x1ae  br.s     loc_1BB
0x1b0  ldloc.1
0x1b1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x1b6  callvirt instance void [mscorlib]System.Collections.CollectionBase::Clear()
0x1bb  ldloc.0
0x1bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c1  brtrue.s loc_184
0x1c3  leave.s  loc_1D6
0x1c5  ldloc.0
0x1c6  isinst   [mscorlib]System.IDisposable
0x1cb  stloc.2
0x1cc  ldloc.2
0x1cd  brfalse.s loc_1D5
0x1cf  ldloc.2
0x1d0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1d5  endfinally
0x1d6  ldarg.2
0x1d7  stloc.3
0x1d8  br.s     loc_248
0x1da  ldarg.1
0x1db  ldloc.3
0x1dc  callvirt instance object [mscorlib]System.Collections.IList::get_Item(int32)
0x1e1  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x1e6  stloc.s  4
0x1e8  ldloc.s  4
0x1ea  ldstr    aParticipationt// "participationtypemask"
0x1ef  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1f4  brfalse.s loc_229
0x1f6  ldarg.0
0x1f7  call     instance class Microsoft.Crm.Entities.PartyMappingCollection Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x1fc  ldloc.s  4
0x1fe  ldstr    aParticipationt// "participationtypemask"
0x203  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x208  unbox.any Microsoft.Crm.Entities.ParticipationType
0x20d  callvirt instance class Microsoft.Crm.Entities.PartyMappingItem Microsoft.Crm.Entities.PartyMappingCollection::Find(valuetype Microsoft.Crm.Entities.ParticipationType type)
0x212  stloc.s  5
0x214  ldloc.s  5
0x216  brfalse.s loc_244
0x218  ldloc.s  5
0x21a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Entities.PartyMappingItem::get_Parties()
0x21f  ldloc.s  4
0x221  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x226  pop
0x227  br.s     loc_244
0x229  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22e  ldstr    aNoParticipatio// "No participationtypemask in the party"
0x233  ldc.i4.0
0x234  newarr   [mscorlib]System.Object
0x239  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x23e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmInvalidOperationException::.ctor(string)
0x243  throw
0x244  ldloc.3
0x245  ldc.i4.1
0x246  add
0x247  stloc.3
0x248  ldloc.3
0x249  ldarg.2
0x24a  ldarg.3
0x24b  add
0x24c  blt.s    loc_1DA
0x24e  ret
```
