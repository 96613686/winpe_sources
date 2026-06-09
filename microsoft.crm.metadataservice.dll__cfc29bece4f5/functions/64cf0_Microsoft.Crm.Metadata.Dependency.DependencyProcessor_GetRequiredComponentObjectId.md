# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRequiredComponentObjectId

- ea: `0x64cf0`
- end: `0x64d93`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::GetRequiredComponentObjectId`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x63870`

## callees

- `0x64cf0`

## string_xrefs

- `0x64d5f`: `requiredcomponentobjectid`
- `0x64cf6`: `requiredcomponenttype`
- `0x64d39`: `requiredcomponentnodeid`
- `0x64d77`: `requiredcomponentnodeid`

## pseudocode

```c

```

## disassembly

```asm
0x64cf0  ldarg.1
0x64cf1  brtrue.s loc_64CF5
0x64cf3  ldnull
0x64cf4  ret
0x64cf5  ldarg.1
0x64cf6  ldstr    aRequiredcompon_0// "requiredcomponenttype"
0x64cfb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64d00  unbox.any [mscorlib]System.Int32
0x64d05  stloc.0
0x64d06  ldnull
0x64d07  stloc.1
0x64d08  ldloc.0
0x64d09  ldc.i4   0x3ED
0x64d0e  beq.s    loc_64D38
0x64d10  ldloc.0
0x64d11  ldc.i4   0x3EE
0x64d16  beq.s    loc_64D38
0x64d18  ldloc.0
0x64d19  ldc.i4   0x3EF
0x64d1e  beq.s    loc_64D38
0x64d20  ldloc.0
0x64d21  ldc.i4   0x3F0
0x64d26  beq.s    loc_64D38
0x64d28  ldloc.0
0x64d29  ldc.i4   0x3F2
0x64d2e  beq.s    loc_64D38
0x64d30  ldloc.0
0x64d31  ldc.i4   0x3F3
0x64d36  bne.un.s loc_64D4B
0x64d38  ldarg.1
0x64d39  ldstr    aRequiredcompon_2// "requiredcomponentnodeid"
0x64d3e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64d43  castclass [mscorlib]System.String
0x64d48  stloc.1
0x64d49  br.s     loc_64D91
0x64d4b  ldarg.1
0x64d4c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PlatformName()
0x64d51  ldstr    aDependency// "Dependency"
0x64d56  ldc.i4.1
0x64d57  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x64d5c  brfalse.s loc_64D76
0x64d5e  ldarg.1
0x64d5f  ldstr    aRequiredcompon// "requiredcomponentobjectid"
0x64d64  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64d69  unbox.any [mscorlib]System.Guid
0x64d6e  box      [mscorlib]System.Guid
0x64d73  stloc.1
0x64d74  br.s     loc_64D91
0x64d76  ldarg.1
0x64d77  ldstr    aRequiredcompon_2// "requiredcomponentnodeid"
0x64d7c  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x64d81  callvirt instance string [mscorlib]System.Object::ToString()
0x64d86  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x64d8b  box      [mscorlib]System.Guid
0x64d90  stloc.1
0x64d91  ldloc.1
0x64d92  ret
```
