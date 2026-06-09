# Microsoft.Crm.Application.Utility.PlatformEntityMap::ProcessParameters

- ea: `0x3b0f0`
- end: `0x3b190`
- name: `Microsoft.Crm.Application.Utility.PlatformEntityMap::ProcessParameters`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x3b080`
- `0x3b090`
- `0x3b0f0`
- `0x5a460`
- `0x6a0d0`
- `0x6a2d0`

## string_xrefs

- `0x3b0f8`: `_CreateFromId`
- `0x3b115`: `_CreateFromId`
- `0x3b108`: `_CreateFromType`
- `0x3b121`: `_CreateFromType`

## pseudocode

```c

```

## disassembly

```asm
0x3b0f0  ldarg.0
0x3b0f1  ldarg.1
0x3b0f2  call     instance void Microsoft.Crm.Application.Utility.EntityAttributeMapBase::set_TargetEntity(class Microsoft.Crm.Application.Platform.Entity value)
0x3b0f7  ldarg.2
0x3b0f8  ldstr    aCreatefromid// "_CreateFromId"
0x3b0fd  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x3b102  brfalse  loc_3B18F
0x3b107  ldarg.2
0x3b108  ldstr    aCreatefromtype// "_CreateFromType"
0x3b10d  callvirt instance bool class [System.Core]System.Collections.Generic.HashSet`1<string>::Contains(var<u1>)
0x3b112  brfalse.s loc_3B18F
0x3b114  ldarg.3
0x3b115  ldstr    aCreatefromid// "_CreateFromId"
0x3b11a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b11f  stloc.0
0x3b120  ldarg.3
0x3b121  ldstr    aCreatefromtype// "_CreateFromType"
0x3b126  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x3b12b  stloc.1
0x3b12c  ldloc.0
0x3b12d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b132  brtrue.s loc_3B18F
0x3b134  ldloc.1
0x3b135  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3b13a  brtrue.s loc_3B18F
0x3b13c  ldloc.1
0x3b13d  ldarg.0
0x3b13e  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0x3b143  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3b148  newobj   instance void Microsoft.Crm.Application.Platform.EntityType::.ctor(string logicalName, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3b14d  stloc.2
0x3b14e  ldloc.2
0x3b14f  ldloc.0
0x3b150  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3b155  ldarg.0
0x3b156  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0x3b15b  ldc.i4.0
0x3b15c  ldarg.0
0x3b15d  call     instance class Microsoft.Crm.Application.Platform.EntityType Microsoft.Crm.Application.Utility.EntityAttributeMapBase::get_TargetEntityType()
0x3b162  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext Microsoft.Crm.Application.Platform.EntityType::get_Context()
0x3b167  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::InitializeFrom(class Microsoft.Crm.Application.Platform.EntityType sourceEntityType, valuetype [mscorlib]System.Guid sourceEntityId, class Microsoft.Crm.Application.Platform.EntityType targetEntityType, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.TargetFieldType transformType, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x3b16c  starg.s  1
0x3b16e  leave.s  loc_3B185
0x3b170  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x3b175  ldc.i4   0x80040E01
0x3b17a  bne.un.s loc_3B181
0x3b17c  ldnull
0x3b17d  starg.s  1
0x3b17f  br.s     loc_3B183
0x3b181  rethrow
0x3b183  leave.s  loc_3B185
0x3b185  ldarg.1
0x3b186  brfalse.s loc_3B18F
0x3b188  ldarg.0
0x3b189  ldarg.1
0x3b18a  call     instance void Microsoft.Crm.Application.Utility.EntityAttributeMapBase::set_TargetEntity(class Microsoft.Crm.Application.Platform.Entity value)
0x3b18f  ret
```
