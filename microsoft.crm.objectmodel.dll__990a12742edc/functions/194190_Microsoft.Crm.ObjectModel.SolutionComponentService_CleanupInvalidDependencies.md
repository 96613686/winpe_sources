# Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupInvalidDependencies

- ea: `0x194190`
- end: `0x1943d4`
- name: `Microsoft.Crm.ObjectModel.SolutionComponentService::CleanupInvalidDependencies`
- size: `580`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x194190`
- `0x1b2450`
- `0x1b2df0`
- `0x1b2e50`
- `0x2441e0`

## string_xrefs

- `0x1941be`: `Select DISTINCT(ComponentType) from DependencyNodeBase`
- `0x194271`: `DELETE FROM dbo.DependencyBase WHERE DependencyId IN\n									  (SELECT DependencyId FROM dbo.Dependency\n										WHERE RequiredComponentType = @ComponentType AND RequiredComponentObjectId NOT IN (SELECT {0} FROM {1})); \n\n									  DELETE FROM dbo.DependencyBase WHERE DependencyId IN\n									  (SELECT DependencyId FROM dbo.Dependency\n										WHERE DependentComponentType = @ComponentType AND DependentComponentObjectId NOT IN (SELECT {0} FROM {1}));`
- `0x194295`: `@ComponentType`
- `0x194304`: `@ComponentType`
- `0x1942e0`: `DELETE FROM dbo.DependencyNodeBase WHERE ComponentType = @ComponentType and ObjectId NOT IN (SELECT {0} FROM {1})`
- `0x194368`: `ThreadAbort Exception in CleanupSolutionComponents.CleanupInvalidDependencies: {0}`
- `0x19438a`: ` CleanupInvalidDependencies failed for ComponentType: `

## pseudocode

```c

```

## disassembly

```asm
0x194190  newobj   instance void <>c__DisplayClass67_0::.ctor()
0x194195  stloc.0
0x194196  ldloc.0
0x194197  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x19419c  stfld    class [mscorlib]System.Collections.Generic.List`1<int32> <>c__DisplayClass67_0::componentTypes
0x1941a1  ldc.i4.0
0x1941a2  stloc.1
0x1941a3  ldsfld   string [mscorlib]System.String::Empty
0x1941a8  stloc.2
0x1941a9  ldnull
0x1941aa  stloc.3
0x1941ab  ldsfld   class [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::DefaultInstance
0x1941b0  ldarg.1
0x1941b1  ldc.i4.0
0x1941b2  ldc.i4.0
0x1941b3  ldc.i4.0
0x1941b4  ldnull
0x1941b5  ldc.i4.0
0x1941b6  ldc.i4.0
0x1941b7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess [Microsoft.Crm.Core]Microsoft.Crm.Core.DataServices.Connection.CrmSqlAccesserFactory::Get(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ConnectionAccessType, int32, string, bool, int32)
0x1941bc  stloc.s  4
0x1941be  ldstr    aSelectDistinct_3// "Select DISTINCT(ComponentType) from Dep"...
0x1941c3  ldc.i4.1
0x1941c4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x1941c9  stloc.s  5
0x1941cb  ldloc.s  4
0x1941cd  ldloc.s  5
0x1941cf  ldloc.0
0x1941d0  ldftn    instance void <>c__DisplayClass67_0::<CleanupInvalidDependencies>b__0(class [System.Data]System.Data.IDataReader reader)
0x1941d6  newobj   instance void class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>::.ctor(object, native int)
0x1941db  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteReaderAction(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo, class [mscorlib]System.Action`1<class [System.Data]System.Data.IDataReader>)
0x1941e0  ldarg.1
0x1941e1  ldc.i4.0
0x1941e2  ldc.i4.0
0x1941e3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x1941e8  ldarg.1
0x1941e9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.SqlExecutionContext::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x1941ee  stloc.s  6
0x1941f0  ldloc.s  6
0x1941f2  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1941f7  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadataDictionary [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataForMetadata::get_MetadataEntities()
0x1941fc  stloc.3
0x1941fd  leave.s  loc_19420B
0x1941ff  ldloc.s  6
0x194201  brfalse.s loc_19420A
0x194203  ldloc.s  6
0x194205  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19420a  endfinally
0x19420b  nop
0x19420c  ldloc.3
0x19420d  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata>::get_Values()
0x194212  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata>::GetEnumerator()
0x194217  stloc.s  7
0x194219  br       loc_194344
0x19421e  ldloca.s 7
0x194220  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata>::get_Current()
0x194225  stloc.s  8
0x194227  ldloc.0
0x194228  ldfld    class [mscorlib]System.Collections.Generic.List`1<int32> <>c__DisplayClass67_0::componentTypes
0x19422d  ldloc.s  8
0x19422f  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_TypeCode()
0x194234  callvirt instance bool class [mscorlib]System.Collections.Generic.List`1<int32>::Contains(var<u1>)
0x194239  brfalse  loc_194344
0x19423e  ldloc.s  8
0x194240  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_PrimaryIdAttribute()
0x194245  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataAttributeMetadata::get_PhysicalName()
0x19424a  stloc.s  9
0x19424c  ldloc.s  8
0x19424e  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_TableName()
0x194253  stloc.s  0xA
0x194255  ldsfld   string [mscorlib]System.String::Empty
0x19425a  pop
0x19425b  ldloc.s  8
0x19425d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataObjectTypeCode [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata::get_TypeCode()
0x194262  stloc.1
0x194263  ldc.i4.0
0x194264  stloc.s  0xB
0x194266  ldstr    aDboDependencyb// "dbo.DependencyBase"
0x19426b  stloc.2
0x19426c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x194271  ldstr    aDeleteFromDboD// "DELETE FROM dbo.DependencyBase WHERE De"...
0x194276  ldc.i4.2
0x194277  newarr   [mscorlib]System.Object
0x19427c  dup
0x19427d  ldc.i4.0
0x19427e  ldloc.s  9
0x194280  stelem.ref
0x194281  dup
0x194282  ldc.i4.1
0x194283  ldloc.s  0xA
0x194285  stelem.ref
0x194286  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19428b  ldc.i4.1
0x19428c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x194291  stloc.s  0xC
0x194293  ldloc.s  0xC
0x194295  ldstr    aComponenttype_3// "@ComponentType"
0x19429a  ldloc.1
0x19429b  box      [mscorlib]System.Int32
0x1942a0  ldloca.s 0xD
0x1942a2  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1942a8  ldloc.s  0xD
0x1942aa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x1942af  ldloc.s  4
0x1942b1  ldloc.s  0xC
0x1942b3  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteNonQuery(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo)
0x1942b8  stloc.s  0xB
0x1942ba  ldloc.s  0xB
0x1942bc  ldc.i4.0
0x1942bd  ble.s    loc_1942D5
0x1942bf  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x1942c4  ldarg.1
0x1942c5  ldloc.s  0xB
0x1942c7  ldloc.2
0x1942c8  ldloc.1
0x1942c9  ldloc.s  0xA
0x1942cb  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x1942d0  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::CleanupInvalidDependencies(valuetype [mscorlib]System.Guid organizationId, int32 numberOfRows, string dependencyTableName, int32 componentType, string tableName, string applicationVersion)
0x1942d5  ldstr    aDboDependencyn// "dbo.DependencyNodeBase"
0x1942da  stloc.2
0x1942db  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1942e0  ldstr    aDeleteFromDboD_0// "DELETE FROM dbo.DependencyNodeBase WHER"...
0x1942e5  ldc.i4.2
0x1942e6  newarr   [mscorlib]System.Object
0x1942eb  dup
0x1942ec  ldc.i4.0
0x1942ed  ldloc.s  9
0x1942ef  stelem.ref
0x1942f0  dup
0x1942f1  ldc.i4.1
0x1942f2  ldloc.s  0xA
0x1942f4  stelem.ref
0x1942f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1942fa  ldc.i4.1
0x1942fb  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::.ctor(string, valuetype [System.Data]System.Data.CommandType)
0x194300  stloc.s  0xC
0x194302  ldloc.s  0xC
0x194304  ldstr    aComponenttype_3// "@ComponentType"
0x194309  ldloc.1
0x19430a  box      [mscorlib]System.Int32
0x19430f  ldloca.s 0xD
0x194311  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x194317  ldloc.s  0xD
0x194319  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo::AddParameterWithValue(string, object, valuetype [mscorlib]System.Nullable`1<int32>)
0x19431e  ldloc.s  4
0x194320  ldloc.s  0xC
0x194322  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.ISqlDataAccess::ExecuteNonQuery(class [Microsoft.Crm.Core]Microsoft.Crm.Core.SqlAccess.SqlCommandInfo)
0x194327  stloc.s  0xB
0x194329  ldloc.s  0xB
0x19432b  ldc.i4.0
0x19432c  ble.s    loc_194344
0x19432e  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x194333  ldarg.1
0x194334  ldloc.s  0xB
0x194336  ldloc.2
0x194337  ldloc.1
0x194338  ldloc.s  0xA
0x19433a  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x19433f  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::CleanupInvalidDependencies(valuetype [mscorlib]System.Guid organizationId, int32 numberOfRows, string dependencyTableName, int32 componentType, string tableName, string applicationVersion)
0x194344  ldloca.s 7
0x194346  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata>::MoveNext()
0x19434b  brtrue   loc_19421E
0x194350  leave.s  loc_194360
0x194352  ldloca.s 7
0x194354  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataEntityMetadata>
0x19435a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x19435f  endfinally
0x194360  leave.s  loc_1943D3
0x194362  stloc.s  0xE
0x194364  ldloc.s  0xE
0x194366  ldarg.1
0x194367  ldc.i4.6
0x194368  ldstr    aThreadabortExc_1// "ThreadAbort Exception in CleanupSolutio"...
0x19436d  ldc.i4.1
0x19436e  newarr   [mscorlib]System.Object
0x194373  dup
0x194374  ldc.i4.0
0x194375  ldloc.s  0xE
0x194377  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19437c  stelem.ref
0x19437d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x194382  rethrow
0x194384  dup
0x194385  callvirt instance string [mscorlib]System.Exception::get_Message()
0x19438a  ldstr    aCleanupinvalid_0// " CleanupInvalidDependencies failed for "...
0x19438f  ldloca.s 1
0x194391  call     instance string [mscorlib]System.Int32::ToString()
0x194396  call     string [mscorlib]System.String::Concat(string, string, string)
0x19439b  stloc.s  0xF
0x19439d  ldarg.1
0x19439e  ldc.i4.s 0x38
0x1943a0  ldloc.s  0xF
0x1943a2  ldc.i4.0
0x1943a3  newarr   [mscorlib]System.Object
0x1943a8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1943ad  call     class Microsoft.Crm.ObjectModel.SolutionTelemetryEvents Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::get_Instance()
0x1943b2  ldarg.1
0x1943b3  ldloc.1
0x1943b4  ldloc.2
0x1943b5  ldloc.s  0xF
0x1943b7  ldc.i4.6
0x1943b8  stloc.s  0x10
0x1943ba  ldloca.s 0x10
0x1943bc  constrained. CleanupAction
0x1943c2  callvirt instance string [mscorlib]System.Object::ToString()
0x1943c7  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Telemetry.CrmTelemetryHelper::get_ApplicationVersion()
0x1943cc  callvirt instance void Microsoft.Crm.ObjectModel.SolutionTelemetryEvents::CleanupInvalidDependenciesFailure(valuetype [mscorlib]System.Guid organizationId, int32 componentType, string dependencyTableName, string errorMsg, string cleanUpAction, string applicationVersion)
0x1943d1  leave.s  loc_1943D3
0x1943d3  ret
```
