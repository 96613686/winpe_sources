# Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::RegardingParentalRelationshipExists

- ea: `0xe50`
- end: `0xeb3`
- name: `Microsoft.Crm.Common.Application.Utility.ActivityRegardingMap::RegardingParentalRelationshipExists`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xc70`

## callees

- `0xe50`

## pseudocode

```c

```

## disassembly

```asm
0xe50  ldarg.0
0xe51  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::get_Metadata()
0xe56  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IRelationshipCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_ReferencesTo()
0xe5b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0xe60  stloc.0
0xe61  br.s     loc_E94
0xe63  ldloc.0
0xe64  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0xe69  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship
0xe6e  stloc.1
0xe6f  ldloc.1
0xe70  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingEntity()
0xe75  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0xe7a  ldarg.1
0xe7b  bne.un.s loc_E94
0xe7d  ldloc.1
0xe7e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Relationship::get_ReferencingAttribute()
0xe83  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_PlatformName()
0xe88  ldarg.2
0xe89  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe8e  brfalse.s loc_E94
0xe90  ldc.i4.1
0xe91  stloc.2
0xe92  leave.s  loc_EB1
0xe94  ldloc.0
0xe95  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xe9a  brtrue.s loc_E63
0xe9c  leave.s  loc_EAF
0xe9e  ldloc.0
0xe9f  isinst   [mscorlib]System.IDisposable
0xea4  stloc.3
0xea5  ldloc.3
0xea6  brfalse.s loc_EAE
0xea8  ldloc.3
0xea9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xeae  endfinally
0xeaf  ldc.i4.0
0xeb0  ret
0xeb1  ldloc.2
0xeb2  ret
```
