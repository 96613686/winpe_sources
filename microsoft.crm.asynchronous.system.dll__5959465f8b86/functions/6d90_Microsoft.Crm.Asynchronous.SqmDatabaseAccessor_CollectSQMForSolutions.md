# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForSolutions

- ea: `0x6d90`
- end: `0x6f50`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSQMForSolutions`
- size: `448`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x4ba0`

## callees

- `0x6d90`
- `0x6f50`
- `0x6fd0`
- `0x7030`
- `0xeac0`

## string_xrefs

- `0x6e67`: `SELECT COUNT(*) FROM SolutionComponent WHERE ComponentType = @ComponentType AND SolutionId = @SolutionId`
- `0x6eae`: `SELECT COUNT(*) FROM MetadataSchema.Entity AS e INNER JOIN SolutionComponent AS sol ON sol.ObjectId = e.EntityId WHERE sol.ComponentType = @ComponentType AND sol.SolutionId = @SolutionId AND e.IsCustomEntity = 1`
- `0x6edc`: `SELECT COUNT(*) FROM AttributeView AS A INNER JOIN SolutionComponent AS sol ON sol.ObjectId = A.EntityId  WHERE A.IsCustomField=1 AND sol.ComponentType = @ComponentType AND sol.SolutionId = @SolutionId`
- `0x6f0a`: `SELECT COUNT(*) FROM RelationshipView AS r INNER JOIN SolutionComponent AS sol ON sol.ObjectId = r.ReferencingEntityId WHERE r.IsCustomRelationship=1 AND sol.ComponentType = @ComponentType AND sol.SolutionId = @SolutionId`

## pseudocode

```c

```

## disassembly

```asm
0x6d90  newobj   instance void <>c__DisplayClass28_0::.ctor()
0x6d95  stloc.0
0x6d96  ldloc.0
0x6d97  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x6d9c  stfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass28_0::solutionIds
0x6da1  call     class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::NewCommand()
0x6da6  stloc.1
0x6da7  ldloc.1
0x6da8  ldstr    aSelectDistinct_0// "SELECT distinct SolutionId FROM Solutio"...
0x6dad  callvirt instance void [System.Data]System.Data.IDbCommand::set_CommandText(string)
0x6db2  ldarg.0
0x6db3  ldloc.1
0x6db4  ldloc.0
0x6db5  ldftn    instance void <>c__DisplayClass28_0::<CollectSQMForSolutions>b__0(object[] values)
0x6dbb  newobj   instance void [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor::.ctor(object, native int)
0x6dc0  call     instance int32 [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase::ExecuteSqlCommandAndProcessRecords(class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Asynchronous]Microsoft.Crm.Asynchronous.DataAccessBase/RecordProcessor)
0x6dc5  pop
0x6dc6  leave.s  loc_6DD2
0x6dc8  ldloc.1
0x6dc9  brfalse.s loc_6DD1
0x6dcb  ldloc.1
0x6dcc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6dd1  endfinally
0x6dd2  ldloc.0
0x6dd3  ldfld    class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> <>c__DisplayClass28_0::solutionIds
0x6dd8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x6ddd  stloc.2
0x6dde  br       loc_6F33
0x6de3  ldloca.s 2
0x6de5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::get_Current()
0x6dea  stloc.3
0x6deb  ldloc.3
0x6dec  call     bool [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::IsRestrictedSolution(valuetype [mscorlib]System.Guid)
0x6df1  brtrue   loc_6F33
0x6df6  ldarg.1
0x6df7  ldc.i4   0x1FC
0x6dfc  ldc.i4.s 0xA
0x6dfe  ldarg.0
0x6dff  ldloc.3
0x6e00  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionProperties(valuetype [mscorlib]System.Guid solutionId)
0x6e05  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e0a  ldarg.1
0x6e0b  ldc.i4   0x1FC
0x6e10  ldc.i4.s 0xA
0x6e12  ldarg.0
0x6e13  ldloc.3
0x6e14  ldc.i4.1
0x6e15  ldc.i4.0
0x6e16  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount(valuetype [mscorlib]System.Guid solutionId, bool isTotalWebResourceCount, int32 webResourceType)
0x6e1b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e20  ldarg.1
0x6e21  ldc.i4   0x1FC
0x6e26  ldc.i4.s 0xA
0x6e28  ldarg.0
0x6e29  ldloc.3
0x6e2a  ldc.i4.0
0x6e2b  ldc.i4.3
0x6e2c  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount(valuetype [mscorlib]System.Guid solutionId, bool isTotalWebResourceCount, int32 webResourceType)
0x6e31  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e36  ldarg.1
0x6e37  ldc.i4   0x1FC
0x6e3c  ldc.i4.s 0xA
0x6e3e  ldarg.0
0x6e3f  ldloc.3
0x6e40  ldc.i4.0
0x6e41  ldc.i4.1
0x6e42  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount(valuetype [mscorlib]System.Guid solutionId, bool isTotalWebResourceCount, int32 webResourceType)
0x6e47  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e4c  ldarg.1
0x6e4d  ldc.i4   0x1FC
0x6e52  ldc.i4.s 0xA
0x6e54  ldarg.0
0x6e55  ldloc.3
0x6e56  ldc.i4.0
0x6e57  ldc.i4.8
0x6e58  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetWebResourcesPerSolutionCount(valuetype [mscorlib]System.Guid solutionId, bool isTotalWebResourceCount, int32 webResourceType)
0x6e5d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e62  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6e67  ldstr    aSelectCountFro_8// "SELECT COUNT(*) FROM SolutionComponent "...
0x6e6c  ldc.i4.0
0x6e6d  newarr   [mscorlib]System.Object
0x6e72  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6e77  stloc.s  4
0x6e79  ldarg.1
0x6e7a  ldc.i4   0x1FC
0x6e7f  ldc.i4.s 0xA
0x6e81  ldarg.0
0x6e82  ldloc.s  4
0x6e84  ldc.i4.s 9
0x6e86  ldloc.3
0x6e87  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount(string commandStr, int32 solutionComponentType, valuetype [mscorlib]System.Guid solutionId)
0x6e8c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6e91  ldarg.1
0x6e92  ldc.i4   0x1FC
0x6e97  ldc.i4.s 0xA
0x6e99  ldarg.0
0x6e9a  ldloc.s  4
0x6e9c  ldc.i4.s 0x5B
0x6e9e  ldloc.3
0x6e9f  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount(string commandStr, int32 solutionComponentType, valuetype [mscorlib]System.Guid solutionId)
0x6ea4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6ea9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6eae  ldstr    aSelectCountFro_9// "SELECT COUNT(*) FROM MetadataSchema.Ent"...
0x6eb3  ldc.i4.0
0x6eb4  newarr   [mscorlib]System.Object
0x6eb9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6ebe  stloc.s  4
0x6ec0  ldarg.1
0x6ec1  ldc.i4   0x1FC
0x6ec6  ldc.i4.s 0xA
0x6ec8  ldarg.0
0x6ec9  ldloc.s  4
0x6ecb  ldc.i4.1
0x6ecc  ldloc.3
0x6ecd  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount(string commandStr, int32 solutionComponentType, valuetype [mscorlib]System.Guid solutionId)
0x6ed2  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6ed7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6edc  ldstr    aSelectCountFro_10// "SELECT COUNT(*) FROM AttributeView AS A"...
0x6ee1  ldc.i4.0
0x6ee2  newarr   [mscorlib]System.Object
0x6ee7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6eec  stloc.s  4
0x6eee  ldarg.1
0x6eef  ldc.i4   0x1FC
0x6ef4  ldc.i4.s 0xA
0x6ef6  ldarg.0
0x6ef7  ldloc.s  4
0x6ef9  ldc.i4.1
0x6efa  ldloc.3
0x6efb  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount(string commandStr, int32 solutionComponentType, valuetype [mscorlib]System.Guid solutionId)
0x6f00  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6f05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f0a  ldstr    aSelectCountFro_11// "SELECT COUNT(*) FROM RelationshipView A"...
0x6f0f  ldc.i4.0
0x6f10  newarr   [mscorlib]System.Object
0x6f15  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x6f1a  stloc.s  4
0x6f1c  ldarg.1
0x6f1d  ldc.i4   0x1FC
0x6f22  ldc.i4.s 0xA
0x6f24  ldarg.0
0x6f25  ldloc.s  4
0x6f27  ldc.i4.1
0x6f28  ldloc.3
0x6f29  call     instance int32 Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::GetSolutionComponentCount(string commandStr, int32 solutionComponentType, valuetype [mscorlib]System.Guid solutionId)
0x6f2e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.ISqmSession::AddToStreamDWord(valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32, int32)
0x6f33  ldloca.s 2
0x6f35  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>::MoveNext()
0x6f3a  brtrue   loc_6DE3
0x6f3f  leave.s  loc_6F4F
0x6f41  ldloca.s 2
0x6f43  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<valuetype [mscorlib]System.Guid>
0x6f49  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6f4e  endfinally
0x6f4f  ret
```
