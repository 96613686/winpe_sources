# Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::PopulateParty

- ea: `0xb80`
- end: `0xc46`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::PopulateParty`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x970`

## callees

- `0x960`
- `0xb80`

## pseudocode

```c

```

## disassembly

```asm
0xb80  ldarg.0
0xb81  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::CreateTargetEntityIfNecessary()
0xb86  ldarg.0
0xb87  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xb8c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0xb91  ldstr    aPartyPrePopula// "Party pre-population should only occur "...
0xb96  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0xb9b  ldc.i4.1
0xb9c  stloc.0
0xb9d  ldarg.0
0xb9e  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xba3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Metadata()
0xba8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0xbad  ldarg.0
0xbae  call     instance string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::get_PartyParticipationTypeName()
0xbb3  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata>::get_Item(!!T0)
0xbb8  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata
0xbbd  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32> [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.LookupAttributeMetadata::get_LookupTypes()
0xbc2  stloc.1
0xbc3  ldloc.1
0xbc4  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::get_Count()
0xbc9  ldc.i4.0
0xbca  ble.s    loc_C1E
0xbcc  ldc.i4.0
0xbcd  stloc.0
0xbce  ldarg.1
0xbcf  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0xbd4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0xbd9  castclass [mscorlib]System.String
0xbde  ldarg.0
0xbdf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0xbe4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0xbe9  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xbee  stloc.2
0xbef  ldloc.1
0xbf0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<int32>::GetEnumerator()
0xbf5  stloc.3
0xbf6  br.s     loc_C0A
0xbf8  ldloc.3
0xbf9  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<int32>::get_Current()
0xbfe  ldloc.2
0xbff  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_TypeCode()
0xc04  bne.un.s loc_C0A
0xc06  ldc.i4.1
0xc07  stloc.0
0xc08  leave.s  loc_C1E
0xc0a  ldloc.3
0xc0b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xc10  brtrue.s loc_BF8
0xc12  leave.s  loc_C1E
0xc14  ldloc.3
0xc15  brfalse.s loc_C1D
0xc17  ldloc.3
0xc18  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xc1d  endfinally
0xc1e  ldloc.0
0xc1f  brfalse.s loc_C45
0xc21  ldc.i4.1
0xc22  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity
0xc27  dup
0xc28  ldc.i4.0
0xc29  ldarg.1
0xc2a  stelem.ref
0xc2b  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0xc30  stloc.s  4
0xc32  ldarg.0
0xc33  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntity()
0xc38  ldarg.0
0xc39  call     instance string Microsoft.Crm.Common.Application.Utility.ActivityPartyMap::get_PartyParticipationTypeName()
0xc3e  ldloc.s  4
0xc40  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0xc45  ret
```
