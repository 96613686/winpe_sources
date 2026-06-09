# Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulateParty

- ea: `0x2780`
- end: `0x2845`
- name: `Microsoft.Crm.Common.Application.Platform.ActivityBase::PrePopulateParty`
- size: `197`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2850`
- `0x32d0`

## callees

- `0x2780`

## string_xrefs

- `0x2801`: `ispartydeleted`

## pseudocode

```c

```

## disassembly

```asm
0x2780  ldarg.0
0x2781  call     instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x2786  ldstr    aPartyPrePopula// "Party pre-population should only occur "...
0x278b  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x2790  ldstr    aActivityparty// "activityparty"
0x2795  ldarg.0
0x2796  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x279b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x27a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27a5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x27aa  stloc.0
0x27ab  ldloc.0
0x27ac  ldstr    aPartyid// "partyid"
0x27b1  ldarg.2
0x27b2  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27b7  box      [mscorlib]System.Guid
0x27bc  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x27c1  ldloc.0
0x27c2  ldstr    aPartyidname// "partyidname"
0x27c7  ldarg.3
0x27c8  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x27cd  ldloc.0
0x27ce  ldstr    aPartyobjecttyp// "partyobjecttypecode"
0x27d3  ldarg.s  4
0x27d5  ldarg.0
0x27d6  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x27db  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x27e0  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x27e5  call     instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_LogicalName()
0x27ea  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x27ef  ldloc.0
0x27f0  ldstr    aPartyiddsc// "partyiddsc"
0x27f5  ldc.i4.0
0x27f6  box      [mscorlib]System.Int32
0x27fb  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2800  ldloc.0
0x2801  ldstr    aIspartydeleted// "ispartydeleted"
0x2806  ldc.i4.0
0x2807  box      [mscorlib]System.Boolean
0x280c  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2811  ldarg.s  5
0x2813  brfalse.s loc_282C
0x2815  ldarg.s  5
0x2817  callvirt instance int32 [mscorlib]System.String::get_Length()
0x281c  ldc.i4.0
0x281d  ble.s    loc_282C
0x281f  ldloc.0
0x2820  ldstr    aAddressused// "addressused"
0x2825  ldarg.s  5
0x2827  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x282c  ldc.i4.1
0x282d  newarr   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity
0x2832  dup
0x2833  ldc.i4.0
0x2834  ldloc.0
0x2835  stelem.ref
0x2836  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>)
0x283b  stloc.1
0x283c  ldarg.0
0x283d  ldarg.1
0x283e  ldloc.1
0x283f  call     instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x2844  ret
```
