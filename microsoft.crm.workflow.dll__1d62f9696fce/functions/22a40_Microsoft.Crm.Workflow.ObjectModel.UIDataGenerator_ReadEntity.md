# Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity

- ea: `0x22a40`
- end: `0x22bf8`
- name: `Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::ReadEntity`
- size: `440`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f660`
- `0x1f710`
- `0x1f990`
- `0x1fc10`
- `0x1fd50`
- `0x1ffb0`
- `0x20030`
- `0x200f0`
- `0x201a0`
- `0x202c0`
- `0x203d0`
- `0x20440`
- `0x206f0`
- `0x209c0`
- `0x22ce0`
- `0x24c10`

## callees

- `0x22a40`

## string_xrefs

- `0x22b09`: `relatedlinked_`
- `0x22b2b`: `relatedlinked_`
- `0x22b37`: `relatedlinked_`

## pseudocode

```c

```

## disassembly

```asm
0x22a40  ldnull
0x22a41  stloc.0
0x22a42  ldarg.1
0x22a43  ldc.i4.s 0x22
0x22a45  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x22a4a  ldc.i4.1
0x22a4b  add
0x22a4c  stloc.1
0x22a4d  ldarg.1
0x22a4e  ldc.i4.s 0x22
0x22a50  ldloc.1
0x22a51  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x22a56  stloc.2
0x22a57  ldarg.1
0x22a58  ldloc.1
0x22a59  ldloc.2
0x22a5a  ldloc.1
0x22a5b  sub
0x22a5c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22a61  stloc.3
0x22a62  ldloc.3
0x22a63  ldsfld   string Microsoft.Crm.Workflow.ObjectModel.WorkflowDefinitionVisitorBase::TemporaryEntitySuffix
0x22a68  ldc.i4.5
0x22a69  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x22a6e  brfalse.s loc_22A80
0x22a70  ldloc.3
0x22a71  ldc.i4.0
0x22a72  ldloc.3
0x22a73  callvirt instance int32 [mscorlib]System.String::get_Length()
0x22a78  ldc.i4.5
0x22a79  sub
0x22a7a  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22a7f  stloc.3
0x22a80  ldloc.3
0x22a81  ldstr    aPrimaryentity// "primaryEntity"
0x22a86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22a8b  brfalse.s loc_22AB0
0x22a8d  ldarg.0
0x22a8e  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22a93  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.PrimaryEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep)
0x22a98  stloc.0
0x22a99  ldarg.2
0x22a9a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22a9f  brtrue   loc_22BF6
0x22aa4  ldloc.0
0x22aa5  ldarg.2
0x22aa6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityBase::set_EntityName(string)
0x22aab  br       loc_22BF6
0x22ab0  ldloc.3
0x22ab1  ldstr    aRelated// "related_"
0x22ab6  ldc.i4.5
0x22ab7  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22abc  brfalse.s loc_22B08
0x22abe  ldloc.3
0x22abf  ldarg.2
0x22ac0  ldc.i4.4
0x22ac1  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x22ac6  stloc.s  4
0x22ac8  ldloc.3
0x22ac9  ldstr    aRelated// "related_"
0x22ace  call     instance int32 [mscorlib]System.String::get_Length()
0x22ad3  ldloc.s  4
0x22ad5  ldstr    aRelated// "related_"
0x22ada  call     instance int32 [mscorlib]System.String::get_Length()
0x22adf  sub
0x22ae0  ldc.i4.1
0x22ae1  sub
0x22ae2  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22ae7  stloc.s  5
0x22ae9  ldloc.3
0x22aea  ldloc.s  4
0x22aec  callvirt instance string [mscorlib]System.String::Substring(int32)
0x22af1  stloc.s  6
0x22af3  ldarg.0
0x22af4  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22af9  ldloc.s  5
0x22afb  ldloc.s  6
0x22afd  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string)
0x22b02  stloc.0
0x22b03  br       loc_22BF6
0x22b08  ldloc.3
0x22b09  ldstr    aRelatedlinked// "relatedlinked_"
0x22b0e  ldc.i4.5
0x22b0f  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x22b14  brfalse.s loc_22B76
0x22b16  ldloc.3
0x22b17  ldarg.2
0x22b18  ldc.i4.4
0x22b19  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x22b1e  stloc.s  7
0x22b20  ldloc.3
0x22b21  ldloc.s  7
0x22b23  callvirt instance string [mscorlib]System.String::Substring(int32)
0x22b28  stloc.s  8
0x22b2a  ldloc.3
0x22b2b  ldstr    aRelatedlinked// "relatedlinked_"
0x22b30  call     instance int32 [mscorlib]System.String::get_Length()
0x22b35  ldloc.s  7
0x22b37  ldstr    aRelatedlinked// "relatedlinked_"
0x22b3c  call     instance int32 [mscorlib]System.String::get_Length()
0x22b41  sub
0x22b42  ldc.i4.1
0x22b43  sub
0x22b44  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22b49  ldc.i4.1
0x22b4a  newarr   [mscorlib]System.Char
0x22b4f  dup
0x22b50  ldc.i4.0
0x22b51  ldc.i4.s 0x23
0x22b53  stelem.i2
0x22b54  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x22b59  stloc.s  9
0x22b5b  ldarg.0
0x22b5c  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22b61  ldloc.s  9
0x22b63  ldc.i4.1
0x22b64  ldelem.ref
0x22b65  ldloc.s  8
0x22b67  ldloc.s  9
0x22b69  ldc.i4.0
0x22b6a  ldelem.ref
0x22b6b  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.RelatedEntityLinked::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string, string, string)
0x22b70  stloc.0
0x22b71  br       loc_22BF6
0x22b76  ldarg.0
0x22b77  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x22b7c  ldloc.3
0x22b7d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::ContainsKey(var<u1>)
0x22b82  brfalse.s loc_22B93
0x22b84  ldarg.0
0x22b85  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x22b8a  ldloc.3
0x22b8b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::get_Item(void)
0x22b90  stloc.0
0x22b91  br.s     loc_22BF6
0x22b93  ldarg.1
0x22b94  ldc.i4.s 0x22
0x22b96  ldloc.2
0x22b97  ldc.i4.1
0x22b98  add
0x22b99  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x22b9e  stloc.1
0x22b9f  ldloc.1
0x22ba0  ldc.i4.m1
0x22ba1  beq.s    loc_22BE6
0x22ba3  ldloc.1
0x22ba4  ldc.i4.1
0x22ba5  add
0x22ba6  stloc.1
0x22ba7  ldarg.1
0x22ba8  ldc.i4.s 0x22
0x22baa  ldloc.1
0x22bab  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x22bb0  stloc.2
0x22bb1  ldloc.2
0x22bb2  ldc.i4.m1
0x22bb3  beq.s    loc_22BE6
0x22bb5  ldloc.3
0x22bb6  ldstr    asc_3068C// "#"
0x22bbb  ldarg.1
0x22bbc  ldloc.1
0x22bbd  ldloc.2
0x22bbe  ldloc.1
0x22bbf  sub
0x22bc0  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x22bc5  call     string [mscorlib]System.String::Concat(string, string, string)
0x22bca  stloc.3
0x22bcb  ldarg.0
0x22bcc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x22bd1  ldloc.3
0x22bd2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::ContainsKey(var<u1>)
0x22bd7  brfalse.s loc_22BE6
0x22bd9  ldarg.0
0x22bda  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep> Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_createdEntities
0x22bdf  ldloc.3
0x22be0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.EntityCreatedByStep>::get_Item(void)
0x22be5  stloc.0
0x22be6  ldloc.0
0x22be7  brtrue.s loc_22BF6
0x22be9  ldarg.0
0x22bea  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Workflow.ObjectModel.UIDataGenerator::_workflow
0x22bef  ldloc.3
0x22bf0  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.Expressions.InvalidEntity::.ctor(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep, string)
0x22bf5  stloc.0
0x22bf6  ldloc.0
0x22bf7  ret
```
