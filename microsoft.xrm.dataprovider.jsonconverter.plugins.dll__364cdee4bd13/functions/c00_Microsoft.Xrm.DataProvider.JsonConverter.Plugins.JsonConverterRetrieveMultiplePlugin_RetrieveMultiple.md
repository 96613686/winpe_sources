# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::RetrieveMultiple

- ea: `0xc00`
- end: `0xd1b`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrieveMultiplePlugin::RetrieveMultiple`
- size: `283`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0xc00`

## pseudocode

```c

```

## disassembly

```asm
0xc00  nop
0xc01  ldarg.s  4
0xc03  callvirt instance bool [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.Security.IAuthorizationService::IsOrganizationSystemUser()
0xc08  brtrue.s loc_C16
0xc0a  ldarg.s  4
0xc0c  callvirt instance bool [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.Security.IAuthorizationService::IsUserSystemAdministrator()
0xc11  ldc.i4.0
0xc12  ceq
0xc14  br.s     loc_C17
0xc16  ldc.i4.0
0xc17  stloc.0
0xc18  ldarg.1
0xc19  ldstr    aQuery// "Query"
0xc1e  call     T0x2B00000B
0xc23  dup
0xc24  brtrue.s loc_C32
0xc26  pop
0xc27  ldarg.2
0xc28  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_LogicalName()
0xc2d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0xc32  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression
0xc37  stloc.1
0xc38  ldarg.2
0xc39  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.DefaultTypeMapFactory::.ctor()
0xc3e  ldnull
0xc3f  call     class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMapFactory::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.ITypeMapFactory, string)
0xc44  stloc.2
0xc45  ldloc.2
0xc46  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap>::.ctor()
0xc4b  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.QueryMap::.ctor(class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap>)
0xc50  stloc.3
0xc51  ldloc.1
0xc52  ldloc.3
0xc53  call     class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Extensions.QueryExpressionExtensions::ConvertSchema(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.QueryMap)
0xc58  stloc.s  4
0xc5a  ldloc.0
0xc5b  stloc.s  9
0xc5d  ldloc.s  9
0xc5f  brfalse.s loc_C76
0xc61  nop
0xc62  ldarg.s  5
0xc64  ldstr    aStrippedSecret// "Stripped secrets"
0xc69  ldc.i4.0
0xc6a  newarr   [mscorlib]System.Object
0xc6f  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0xc74  nop
0xc75  nop
0xc76  ldarg.0
0xc77  ldarg.2
0xc78  ldarg.3
0xc79  call     T0x2B00000C
0xc7e  stloc.s  5
0xc80  ldarg.0
0xc81  ldloc.s  5
0xc83  ldloc.0
0xc84  call     T0x2B00000D
0xc89  call     T0x2B00000E
0xc8e  stloc.s  6
0xc90  ldloc.s  6
0xc92  ldloc.s  4
0xc94  call     T0x2B00000F
0xc99  stloc.s  7
0xc9b  ldloc.s  7
0xc9d  ldloc.2
0xc9e  call     T0x2B000010
0xca3  stloc.s  8
0xca5  ldloc.3
0xca6  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.QueryMap::get_PrimaryEntityMap()
0xcab  brfalse.s loc_CBD
0xcad  ldloc.3
0xcae  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.QueryMap::get_PrimaryEntityMap()
0xcb3  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap::get_NameMap()
0xcb8  ldnull
0xcb9  cgt.un
0xcbb  br.s     loc_CBE
0xcbd  ldc.i4.0
0xcbe  stloc.s  0xA
0xcc0  ldloc.s  0xA
0xcc2  brfalse.s loc_CDE
0xcc4  nop
0xcc5  ldloc.s  8
0xcc7  ldloc.3
0xcc8  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.QueryMap::get_PrimaryEntityMap()
0xccd  callvirt instance class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap::get_NameMap()
0xcd2  callvirt instance string [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.NameMap::get_XrmName()
0xcd7  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::set_EntityName(string)
0xcdc  nop
0xcdd  nop
0xcde  ldarg.1
0xcdf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0xce4  ldstr    aBusinessentity// "BusinessEntityCollection"
0xce9  ldloc.s  8
0xceb  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0xcf0  nop
0xcf1  ldarg.s  5
0xcf3  ldstr    aResultSetHas0R// "Result set has {0} rows"
0xcf8  ldloc.s  8
0xcfa  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0xcff  call     T0x2B000011
0xd04  box      [mscorlib]System.Int32
0xd09  call     string [mscorlib]System.String::Format(string, object)
0xd0e  ldc.i4.0
0xd0f  newarr   [mscorlib]System.Object
0xd14  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0xd19  nop
0xd1a  ret
```
