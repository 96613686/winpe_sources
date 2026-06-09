# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity_2

- ea: `0x4e2a0`
- end: `0x4e3c9`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity_2`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4dbd0`
- `0x4e220`

## callees

- `0x4e2a0`
- `0x4e3d0`

## string_xrefs

- `0x4e2c4`: `issecurityintersect`
- `0x4e2df`: `Intersect or Security Intersect entities cannot participate in custom relationships`
- `0x4e32c`: `Cannot create relationships involving CustomerAddress`

## pseudocode

```c

```

## disassembly

```asm
0x4e2a0  ldarg.1
0x4e2a1  ldstr    aName// "name"
0x4e2a6  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e2ab  castclass [mscorlib]System.String
0x4e2b0  stloc.0
0x4e2b1  ldarg.1
0x4e2b2  ldstr    aIsintersect// "isintersect"
0x4e2b7  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e2bc  unbox.any [mscorlib]System.Boolean
0x4e2c1  brtrue.s loc_4E2D5
0x4e2c3  ldarg.1
0x4e2c4  ldstr    aIssecurityinte// "issecurityintersect"
0x4e2c9  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e2ce  unbox.any [mscorlib]System.Boolean
0x4e2d3  brfalse.s loc_4E2E7
0x4e2d5  ldarg.s  4
0x4e2d7  ldc.i4   0x80047003
0x4e2dc  stind.i4
0x4e2dd  ldarg.s  5
0x4e2df  ldstr    aIntersectOrSec// "Intersect or Security Intersect entitie"...
0x4e2e4  stind.ref
0x4e2e5  ldc.i4.0
0x4e2e6  ret
0x4e2e7  ldarg.2
0x4e2e8  brfalse.s loc_4E310
0x4e2ea  ldarg.s  4
0x4e2ec  ldc.i4   0x8004432E
0x4e2f1  stind.i4
0x4e2f2  ldarg.s  5
0x4e2f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e2f9  ldstr    aEntity0EitherH// "Entity: {0} either has no primary field"...
0x4e2fe  ldc.i4.1
0x4e2ff  newarr   [mscorlib]System.Object
0x4e304  dup
0x4e305  ldc.i4.0
0x4e306  ldloc.0
0x4e307  stelem.ref
0x4e308  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e30d  stind.ref
0x4e30e  ldc.i4.0
0x4e30f  ret
0x4e310  ldloc.0
0x4e311  ldstr    aCustomeraddres// "CustomerAddress"
0x4e316  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4e31b  brfalse.s loc_4E33F
0x4e31d  ldarg.s  4
0x4e31f  ldc.i4   0x80047003
0x4e324  stind.i4
0x4e325  ldarg.s  5
0x4e327  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e32c  ldstr    aCannotCreateRe// "Cannot create relationships involving C"...
0x4e331  ldc.i4.0
0x4e332  newarr   [mscorlib]System.Object
0x4e337  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e33c  stind.ref
0x4e33d  ldc.i4.0
0x4e33e  ret
0x4e33f  ldarg.3
0x4e340  brtrue.s loc_4E368
0x4e342  ldarg.s  4
0x4e344  ldc.i4   0x80044337
0x4e349  stind.i4
0x4e34a  ldarg.s  5
0x4e34c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e351  ldstr    aEntity0CannotB_4// "Entity {0} cannot be a referenced entit"...
0x4e356  ldc.i4.1
0x4e357  newarr   [mscorlib]System.Object
0x4e35c  dup
0x4e35d  ldc.i4.0
0x4e35e  ldloc.0
0x4e35f  stelem.ref
0x4e360  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e365  stind.ref
0x4e366  ldc.i4.0
0x4e367  ret
0x4e368  ldarg.1
0x4e369  ldstr    aCanbeprimaryen// "canbeprimaryentityinrelationship"
0x4e36e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4e373  unbox.any [mscorlib]System.Boolean
0x4e378  brtrue.s loc_4E38C
0x4e37a  ldarg.s  4
0x4e37c  ldc.i4   0x80047003
0x4e381  stind.i4
0x4e382  ldarg.s  5
0x4e384  ldstr    aTheReferencedE_0// "The referenced entity of a relationship"...
0x4e389  stind.ref
0x4e38a  ldc.i4.0
0x4e38b  ret
0x4e38c  ldarg.0
0x4e38d  ldloc.0
0x4e38e  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::IsEntitySupportedAsReferencedEntityInUI(string entityPlatformName)
0x4e393  brtrue.s loc_4E3BB
0x4e395  ldarg.s  4
0x4e397  ldc.i4   0x80047003
0x4e39c  stind.i4
0x4e39d  ldarg.s  5
0x4e39f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4e3a4  ldstr    aEntity0IsNotSu// "Entity {0} is not supported as a refere"...
0x4e3a9  ldc.i4.1
0x4e3aa  newarr   [mscorlib]System.Object
0x4e3af  dup
0x4e3b0  ldc.i4.0
0x4e3b1  ldloc.0
0x4e3b2  stelem.ref
0x4e3b3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4e3b8  stind.ref
0x4e3b9  ldc.i4.0
0x4e3ba  ret
0x4e3bb  ldarg.s  4
0x4e3bd  ldc.i4.0
0x4e3be  stind.i4
0x4e3bf  ldarg.s  5
0x4e3c1  ldsfld   string [mscorlib]System.String::Empty
0x4e3c6  stind.ref
0x4e3c7  ldc.i4.1
0x4e3c8  ret
```
