# Microsoft.Crm.Workflow.Services.SetStateActivityService::CreateClosingActivity

- ea: `0x1a170`
- end: `0x1a1f4`
- name: `Microsoft.Crm.Workflow.Services.SetStateActivityService::CreateClosingActivity`
- size: `132`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x19fb0`
- `0x19ff0`
- `0x1a030`
- `0x1a070`
- `0x1a0b0`
- `0x1a0f0`
- `0x1a130`

## callees

- `0x1a170`

## string_xrefs

- `0x1a1c2`: `isworkflowcreated`

## pseudocode

```c

```

## disassembly

```asm
0x1a170  ldsfld   string [mscorlib]System.String::Empty
0x1a175  stloc.0
0x1a176  ldarg.3
0x1a177  brfalse.s loc_1A1AB
0x1a179  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x1a17e  stloc.1
0x1a17f  ldloc.1
0x1a180  ldarg.3
0x1a181  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1a186  ldarg.0
0x1a187  ldarg.1
0x1a188  ldarg.2
0x1a189  ldloc.1
0x1a18a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x1a18f  stloc.2
0x1a190  ldloc.2
0x1a191  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x1a196  ldarg.3
0x1a197  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1a19c  brfalse.s loc_1A1AB
0x1a19e  ldloc.2
0x1a19f  ldarg.3
0x1a1a0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1a1a5  isinst   [mscorlib]System.String
0x1a1aa  stloc.0
0x1a1ab  ldarg.s  4
0x1a1ad  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::.ctor(string)
0x1a1b2  dup
0x1a1b3  ldarg.s  5
0x1a1b5  ldarg.1
0x1a1b6  ldarg.2
0x1a1b7  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x1a1bc  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a1c1  dup
0x1a1c2  ldstr    aIsworkflowcrea// "isworkflowcreated"
0x1a1c7  ldc.i4.1
0x1a1c8  box      [mscorlib]System.Boolean
0x1a1cd  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a1d2  dup
0x1a1d3  ldstr    aActualend// "actualend"
0x1a1d8  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1a1dd  box      [mscorlib]System.DateTime
0x1a1e2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a1e7  dup
0x1a1e8  ldstr    aSubject// "subject"
0x1a1ed  ldloc.0
0x1a1ee  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Item(string, object)
0x1a1f3  ret
```
