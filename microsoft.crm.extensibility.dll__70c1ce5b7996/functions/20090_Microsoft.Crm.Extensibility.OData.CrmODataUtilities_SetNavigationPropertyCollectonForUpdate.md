# Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetNavigationPropertyCollectonForUpdate

- ea: `0x20090`
- end: `0x20148`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataUtilities::SetNavigationPropertyCollectonForUpdate`
- size: `184`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1e790`
- `0x1ff90`

## callees

- `0x20020`
- `0x20090`
- `0x20150`

## string_xrefs

- `0x200a9`: `Update Navigation Property is only supported on communication activities.`

## pseudocode

```c

```

## disassembly

```asm
0x20090  ldarg.1
0x20091  call     class [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext Microsoft.Crm.Extensibility.OData.CrmODataUtilities::GetOrganizationContext()
0x20096  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.EntityClassFactory::CreateInstance(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2009b  isinst   [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity
0x200a0  stloc.0
0x200a1  ldloc.0
0x200a2  brtrue.s loc_200BA
0x200a4  ldc.i4   0x190
0x200a9  ldstr    aUpdateNavigati_0// "Update Navigation Property is only supp"...
0x200ae  ldc.i4.0
0x200af  newarr   [mscorlib]System.Object
0x200b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x200b9  throw
0x200ba  ldloc.0
0x200bb  callvirt instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingCollection [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity::get_PartyMappingTable()
0x200c0  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x200c5  stloc.1
0x200c6  br.s     loc_200F3
0x200c8  ldloc.1
0x200c9  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x200ce  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem
0x200d3  stloc.2
0x200d4  ldarg.0
0x200d5  ldloc.2
0x200d6  callvirt instance string [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_LogicalName()
0x200db  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x200e0  brtrue.s loc_200F3
0x200e2  ldarg.0
0x200e3  ldloc.2
0x200e4  callvirt instance string [Microsoft.Crm.Entities]Microsoft.Crm.Entities.PartyMappingItem::get_LogicalName()
0x200e9  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::.ctor()
0x200ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x200f3  ldloc.1
0x200f4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x200f9  brtrue.s loc_200C8
0x200fb  leave.s  loc_2010E
0x200fd  ldloc.1
0x200fe  isinst   [mscorlib]System.IDisposable
0x20103  stloc.3
0x20104  ldloc.3
0x20105  brfalse.s loc_2010D
0x20107  ldloc.3
0x20108  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2010d  endfinally
0x2010e  ldarg.2
0x2010f  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x20114  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x20119  stloc.s  4
0x2011b  br.s     loc_20130
0x2011d  ldloc.s  4
0x2011f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x20124  stloc.s  5
0x20126  ldarg.0
0x20127  ldloc.s  5
0x20129  ldloc.0
0x2012a  call     bool Microsoft.Crm.Extensibility.OData.CrmODataUtilities::TrySetActivityParty(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activity, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity activityParty, class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.CommunicationActivity communicationActivity)
0x2012f  pop
0x20130  ldloc.s  4
0x20132  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x20137  brtrue.s loc_2011D
0x20139  leave.s  loc_20147
0x2013b  ldloc.s  4
0x2013d  brfalse.s loc_20146
0x2013f  ldloc.s  4
0x20141  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20146  endfinally
0x20147  ret
```
