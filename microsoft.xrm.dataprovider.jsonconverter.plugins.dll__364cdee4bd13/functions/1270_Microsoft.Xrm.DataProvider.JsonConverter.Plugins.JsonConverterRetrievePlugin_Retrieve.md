# Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::Retrieve

- ea: `0x1270`
- end: `0x13a4`
- name: `Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonConverterRetrievePlugin::Retrieve`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1270`
- `0x1540`
- `0x1560`
- `0x1570`

## pseudocode

```c

```

## disassembly

```asm
0x1270  nop
0x1271  ldarg.1
0x1272  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0x1277  ldstr    aTarget// "Target"
0x127c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1281  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1286  stloc.0
0x1287  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor()
0x128c  stloc.1
0x128d  ldloc.1
0x128e  ldstr    aConnectiondefi// "connectiondefinition"
0x1293  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x1298  nop
0x1299  ldloc.1
0x129a  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0x129f  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x12a4  nop
0x12a5  ldloc.1
0x12a6  ldstr    aEntitydatasour_0// "entitydatasourceid"
0x12ab  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x12b0  nop
0x12b1  ldarg.3
0x12b2  ldstr    aEntitydatasour// "entitydatasource"
0x12b7  ldloc.0
0x12b8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x12bd  ldloc.1
0x12be  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x12c3  stloc.2
0x12c4  ldloc.2
0x12c5  ldnull
0x12c6  ceq
0x12c8  stloc.s  7
0x12ca  ldloc.s  7
0x12cc  brfalse.s loc_12F9
0x12ce  nop
0x12cf  ldarg.1
0x12d0  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x12d5  ldstr    aBusinessentity_0// "BusinessEntity"
0x12da  ldnull
0x12db  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x12e0  nop
0x12e1  ldarg.s  5
0x12e3  ldstr    aResultSetHas0R_0// "Result set has 0 rows"
0x12e8  ldc.i4.0
0x12e9  newarr   [mscorlib]System.Object
0x12ee  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0x12f3  nop
0x12f4  br       loc_13A3
0x12f9  newobj   instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::.ctor()
0x12fe  stloc.3
0x12ff  ldloc.3
0x1300  ldloc.2
0x1301  ldstr    aConnectiondefi// "connectiondefinition"
0x1306  callvirt T0x2B000013
0x130b  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinition(string value)
0x1310  nop
0x1311  ldarg.s  4
0x1313  callvirt instance bool [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.Security.IAuthorizationService::IsOrganizationSystemUser()
0x1318  brtrue.s loc_1323
0x131a  ldarg.s  4
0x131c  callvirt instance bool [Microsoft.Xrm.Kernel.Contracts]Microsoft.Xrm.Kernel.Contracts.Security.IAuthorizationService::IsUserSystemAdministrator()
0x1321  br.s     loc_1324
0x1323  ldc.i4.1
0x1324  stloc.s  8
0x1326  ldloc.s  8
0x1328  brfalse.s loc_1340
0x132a  nop
0x132b  ldloc.3
0x132c  ldloc.2
0x132d  ldstr    aConnectiondefi_0// "connectiondefinitionsecrets"
0x1332  callvirt T0x2B000013
0x1337  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0x133c  nop
0x133d  nop
0x133e  br.s     loc_1361
0x1340  nop
0x1341  ldloc.3
0x1342  ldsfld   string [mscorlib]System.String::Empty
0x1347  callvirt instance void Microsoft.Xrm.DataProvider.JsonConverter.Plugins.JsonDataSource::set_ConnectionDefinitionSecrets(string value)
0x134c  nop
0x134d  ldarg.s  5
0x134f  ldstr    aStrippedSecret// "Stripped secrets"
0x1354  ldc.i4.0
0x1355  newarr   [mscorlib]System.Object
0x135a  call     void [Microsoft.Xrm.Log]Microsoft.Xrm.Log.LoggerExtension::Debug(class [Microsoft.Xrm.Log]Microsoft.Xrm.Log.ILogger, string, object[])
0x135f  nop
0x1360  nop
0x1361  ldloc.3
0x1362  call     T0x2B000014
0x1367  stloc.s  4
0x1369  ldarg.2
0x136a  newobj   instance void [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.DefaultTypeMapFactory::.ctor()
0x136f  ldnull
0x1370  call     class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMap [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.EntityMapFactory::Create(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata, class [Microsoft.Xrm.Sdk.Data]Microsoft.Xrm.Sdk.Data.Mappings.ITypeMapFactory, string)
0x1375  stloc.s  5
0x1377  ldloc.s  4
0x1379  ldloc.s  5
0x137b  call     T0x2B000016
0x1380  stloc.s  6
0x1382  ldloc.s  6
0x1384  ldloc.0
0x1385  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x138a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::set_Id(valuetype [mscorlib]System.Guid)
0x138f  nop
0x1390  ldarg.1
0x1391  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_OutputParameters()
0x1396  ldstr    aBusinessentity_0// "BusinessEntity"
0x139b  ldloc.s  6
0x139d  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x13a2  nop
0x13a3  ret
```
