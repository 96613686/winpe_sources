# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity_2

- ea: `0x4e010`
- end: `0x4e1b1`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity_2`
- size: `417`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4de20`
- `0x4dfe0`

## callees

- `0x4e010`

## string_xrefs

- `0x4e023`: `issecurityintersect`
- `0x4e03e`: `Intersect or Security Intersect entities cannot participate in custom relationships`
- `0x4e0b0`: `Cannot create relationships involving CustomerAddress`
- `0x4e17d`: `Entity {0} cannot be a referencing entity because it represents a solution component`

## pseudocode

```c

```

## disassembly

```asm
0x4e010  ldarg.1
0x4e011  ldstr    aIsintersect// "isintersect"
0x4e016  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e01b  unbox.any [mscorlib]System.Boolean
0x4e020  brtrue.s loc_4E034
0x4e022  ldarg.1
0x4e023  ldstr    aIssecurityinte// "issecurityintersect"
0x4e028  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e02d  unbox.any [mscorlib]System.Boolean
0x4e032  brfalse.s loc_4E046
0x4e034  ldarg.s  4
0x4e036  ldc.i4   0x80047003
0x4e03b  stind.i4
0x4e03c  ldarg.s  5
0x4e03e  ldstr    aIntersectOrSec// "Intersect or Security Intersect entitie"...
0x4e043  stind.ref
0x4e044  ldc.i4.0
0x4e045  ret
0x4e046  ldarg.1
0x4e047  ldarg.3
0x4e048  call     bool [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataHelper::IsEntityCustomizable(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4e04d  brtrue.s loc_4E061
0x4e04f  ldarg.s  4
0x4e051  ldc.i4   0x80047003
0x4e056  stind.i4
0x4e057  ldarg.s  5
0x4e059  ldstr    aCannotHaveANon// "Cannot have a non customizable referenc"...
0x4e05e  stind.ref
0x4e05f  ldc.i4.0
0x4e060  ret
0x4e061  ldarg.1
0x4e062  ldstr    aCanberelateden// "canberelatedentityinrelationship"
0x4e067  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e06c  unbox.any [mscorlib]System.Boolean
0x4e071  brtrue.s loc_4E085
0x4e073  ldarg.s  4
0x4e075  ldc.i4   0x80047003
0x4e07a  stind.i4
0x4e07b  ldarg.s  5
0x4e07d  ldstr    aTheReferencing_0// "The referencing entity of a relationshi"...
0x4e082  stind.ref
0x4e083  ldc.i4.0
0x4e084  ret
0x4e085  ldarg.1
0x4e086  ldstr    aName// "name"
0x4e08b  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e090  castclass [mscorlib]System.String
0x4e095  ldstr    aCustomeraddres// "CustomerAddress"
0x4e09a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e09f  brfalse.s loc_4E0C3
0x4e0a1  ldarg.s  4
0x4e0a3  ldc.i4   0x80047003
0x4e0a8  stind.i4
0x4e0a9  ldarg.s  5
0x4e0ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e0b0  ldstr    aCannotCreateRe// "Cannot create relationships involving C"...
0x4e0b5  ldc.i4.0
0x4e0b6  newarr   [mscorlib]System.Object
0x4e0bb  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e0c0  stind.ref
0x4e0c1  ldc.i4.0
0x4e0c2  ret
0x4e0c3  ldc.i4.1
0x4e0c4  stloc.0
0x4e0c5  ldarg.1
0x4e0c6  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x4e0cb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e0d0  stloc.1
0x4e0d1  ldloc.1
0x4e0d2  brfalse.s loc_4E0FB
0x4e0d4  ldloc.1
0x4e0d5  unbox.any [mscorlib]System.Boolean
0x4e0da  brfalse.s loc_4E0FB
0x4e0dc  ldarg.3
0x4e0dd  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4e0e2  ldarg.1
0x4e0e3  ldstr    aEntityid// "entityid"
0x4e0e8  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e0ed  unbox.any [mscorlib]System.Guid
0x4e0f2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::TryGetEntity(valuetype [mscorlib]System.Guid)
0x4e0f7  brtrue.s loc_4E0FB
0x4e0f9  ldc.i4.0
0x4e0fa  stloc.0
0x4e0fb  ldarg.2
0x4e0fc  ldc.i4.0
0x4e0fd  ceq
0x4e0ff  ldloc.0
0x4e100  and
0x4e101  brfalse.s loc_4E138
0x4e103  ldarg.s  4
0x4e105  ldc.i4   0x80044338
0x4e10a  stind.i4
0x4e10b  ldarg.s  5
0x4e10d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e112  ldstr    aEntity0CannotB_2// "Entity {0} cannot be a referencing enti"...
0x4e117  ldc.i4.1
0x4e118  newarr   [mscorlib]System.Object
0x4e11d  dup
0x4e11e  ldc.i4.0
0x4e11f  ldarg.1
0x4e120  ldstr    aName// "name"
0x4e125  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e12a  castclass [mscorlib]System.String
0x4e12f  stelem.ref
0x4e130  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e135  stind.ref
0x4e136  ldc.i4.0
0x4e137  ret
0x4e138  ldloca.s 2
0x4e13a  ldstr    aAe7fdf89Aa6249// "ae7fdf89-aa62-490a-95f5-216e8789ada7"
0x4e13f  call     instance void [mscorlib]System.Guid::.ctor(string)
0x4e144  ldarg.1
0x4e145  ldstr    aIssolutionawar// "issolutionaware"
0x4e14a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e14f  unbox.any [mscorlib]System.Boolean
0x4e154  brfalse.s loc_4E1A3
0x4e156  ldarg.1
0x4e157  ldstr    aEntityid// "entityid"
0x4e15c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e161  unbox.any [mscorlib]System.Guid
0x4e166  ldloc.2
0x4e167  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4e16c  brfalse.s loc_4E1A3
0x4e16e  ldarg.s  4
0x4e170  ldc.i4   0x80044350
0x4e175  stind.i4
0x4e176  ldarg.s  5
0x4e178  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e17d  ldstr    aEntity0CannotB_3// "Entity {0} cannot be a referencing enti"...
0x4e182  ldc.i4.1
0x4e183  newarr   [mscorlib]System.Object
0x4e188  dup
0x4e189  ldc.i4.0
0x4e18a  ldarg.1
0x4e18b  ldstr    aName// "name"
0x4e190  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e195  castclass [mscorlib]System.String
0x4e19a  stelem.ref
0x4e19b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e1a0  stind.ref
0x4e1a1  ldc.i4.0
0x4e1a2  ret
0x4e1a3  ldarg.s  4
0x4e1a5  ldc.i4.0
0x4e1a6  stind.i4
0x4e1a7  ldarg.s  5
0x4e1a9  ldsfld   string [mscorlib]System.String::Empty
0x4e1ae  stind.ref
0x4e1af  ldc.i4.1
0x4e1b0  ret
```
