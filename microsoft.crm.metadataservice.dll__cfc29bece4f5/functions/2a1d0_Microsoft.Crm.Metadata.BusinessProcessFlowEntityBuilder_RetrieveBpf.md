# Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::RetrieveBpf

- ea: `0x2a1d0`
- end: `0x2a2af`
- name: `Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::RetrieveBpf`
- size: `223`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x292c0`
- `0x293c0`

## callees

- `0x2a1d0`
- `0x2a310`

## string_xrefs

- `0x2a256`: `triggeroncreate`
- `0x2a25f`: `triggerondelete`
- `0x2a268`: `triggeronupdateattributelist`

## pseudocode

```c

```

## disassembly

```asm
0x2a1d0  ldarg.0
0x2a1d1  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::moniker
0x2a1d6  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_EntityMetadata()
0x2a1db  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x2a1e0  ldarg.0
0x2a1e1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::context
0x2a1e6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x2a1eb  stloc.0
0x2a1ec  ldloc.0
0x2a1ed  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x2a1f2  ldc.i4.s 0x10
0x2a1f4  newarr   [mscorlib]System.String
0x2a1f9  dup
0x2a1fa  ldc.i4.0
0x2a1fb  ldstr    aXaml// "xaml"
0x2a200  stelem.ref
0x2a201  dup
0x2a202  ldc.i4.1
0x2a203  ldstr    aCategory// "category"
0x2a208  stelem.ref
0x2a209  dup
0x2a20a  ldc.i4.2
0x2a20b  ldstr    aStatecode_1// "statecode"
0x2a210  stelem.ref
0x2a211  dup
0x2a212  ldc.i4.3
0x2a213  ldstr    aName// "name"
0x2a218  stelem.ref
0x2a219  dup
0x2a21a  ldc.i4.4
0x2a21b  ldstr    aUniquename// "uniquename"
0x2a220  stelem.ref
0x2a221  dup
0x2a222  ldc.i4.5
0x2a223  ldstr    aWorkflowiduniq// "workflowidunique"
0x2a228  stelem.ref
0x2a229  dup
0x2a22a  ldc.i4.6
0x2a22b  ldstr    aPrimaryentity_0// "primaryentity"
0x2a230  stelem.ref
0x2a231  dup
0x2a232  ldc.i4.7
0x2a233  ldstr    aType// "type"
0x2a238  stelem.ref
0x2a239  dup
0x2a23a  ldc.i4.8
0x2a23b  ldstr    aScope// "scope"
0x2a240  stelem.ref
0x2a241  dup
0x2a242  ldc.i4.s 9
0x2a244  ldstr    aOndemand// "ondemand"
0x2a249  stelem.ref
0x2a24a  dup
0x2a24b  ldc.i4.s 0xA
0x2a24d  ldstr    aSubprocess// "subprocess"
0x2a252  stelem.ref
0x2a253  dup
0x2a254  ldc.i4.s 0xB
0x2a256  ldstr    aTriggeroncreat// "triggeroncreate"
0x2a25b  stelem.ref
0x2a25c  dup
0x2a25d  ldc.i4.s 0xC
0x2a25f  ldstr    aTriggerondelet// "triggerondelete"
0x2a264  stelem.ref
0x2a265  dup
0x2a266  ldc.i4.s 0xD
0x2a268  ldstr    aTriggeronupdat// "triggeronupdateattributelist"
0x2a26d  stelem.ref
0x2a26e  dup
0x2a26f  ldc.i4.s 0xE
0x2a271  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x2a276  stelem.ref
0x2a277  dup
0x2a278  ldc.i4.s 0xF
0x2a27a  ldstr    aBusinessproces// "businessprocesstype"
0x2a27f  stelem.ref
0x2a280  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x2a285  ldarg.0
0x2a286  ldloc.0
0x2a287  ldarg.0
0x2a288  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::moniker
0x2a28d  call     instance class [Microsoft.Crm.Entities]Microsoft.Crm.Entities.WorkflowEntity Microsoft.Crm.Metadata.BusinessProcessFlowEntityBuilder::RetrieveWorkflow(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression entityExpression, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker entityMoniker)
0x2a292  stloc.1
0x2a293  ldloc.1
0x2a294  brtrue.s loc_2A298
0x2a296  ldnull
0x2a297  ret
0x2a298  ldloc.1
0x2a299  ldstr    aCategory// "category"
0x2a29e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x2a2a3  unbox.any [mscorlib]System.Int32
0x2a2a8  ldc.i4.4
0x2a2a9  bne.un.s loc_2A2AD
0x2a2ab  ldloc.1
0x2a2ac  ret
0x2a2ad  ldnull
0x2a2ae  ret
```
