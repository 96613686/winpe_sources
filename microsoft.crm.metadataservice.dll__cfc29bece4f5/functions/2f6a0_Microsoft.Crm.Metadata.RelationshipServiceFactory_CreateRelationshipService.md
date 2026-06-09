# Microsoft.Crm.Metadata.RelationshipServiceFactory::CreateRelationshipService

- ea: `0x2f6a0`
- end: `0x2f6d9`
- name: `Microsoft.Crm.Metadata.RelationshipServiceFactory::CreateRelationshipService`
- size: `57`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x2f0c0`
- `0x2f150`
- `0x2f180`
- `0x2f1e0`
- `0x2f340`
- `0x2f360`
- `0x2f390`
- `0x2f3d0`
- `0x2f400`
- `0x2f430`
- `0x2f470`
- `0x2f4b0`
- `0x2f500`
- `0x2f720`

## callees

- `0x2f6a0`
- `0x47130`
- `0x4edf0`

## string_xrefs

- `0x2f6ba`: `There is no relationship service for relationship of type {0}`

## pseudocode

```c

```

## disassembly

```asm
0x2f6a0  ldarg.0
0x2f6a1  brfalse.s loc_2F6A9
0x2f6a3  ldarg.0
0x2f6a4  ldc.i4.1
0x2f6a5  beq.s    loc_2F6AF
0x2f6a7  br.s     loc_2F6B5
0x2f6a9  newobj   instance void Microsoft.Crm.Metadata.RelationshipService::.ctor()
0x2f6ae  ret
0x2f6af  newobj   instance void Microsoft.Crm.Metadata.ManyToManyRelationshipService::.ctor()
0x2f6b4  ret
0x2f6b5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2f6ba  ldstr    aThereIsNoRelat// "There is no relationship service for re"...
0x2f6bf  ldc.i4.1
0x2f6c0  newarr   [mscorlib]System.Object
0x2f6c5  dup
0x2f6c6  ldc.i4.0
0x2f6c7  ldarg.0
0x2f6c8  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityRelationshipType
0x2f6cd  stelem.ref
0x2f6ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2f6d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x2f6d8  throw
```
