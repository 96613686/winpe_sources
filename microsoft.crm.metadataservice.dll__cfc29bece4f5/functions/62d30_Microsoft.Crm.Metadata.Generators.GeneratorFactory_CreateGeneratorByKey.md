# Microsoft.Crm.Metadata.Generators.GeneratorFactory::CreateGeneratorByKey

- ea: `0x62d30`
- end: `0x6308c`
- name: `Microsoft.Crm.Metadata.Generators.GeneratorFactory::CreateGeneratorByKey`
- size: `860`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x629e0`

## callees

- `0x62d30`
- `0x75380`

## string_xrefs

- `0x62f22`: `CustomControlDefaultConfig`
- `0x62e8f`: `BusinessProcessTaskFlow`
- `0x62ece`: `PluginType`
- `0x62fdf`: `ComplexControl`

## pseudocode

```c

```

## disassembly

```asm
0x62d30  ldnull
0x62d31  stloc.0
0x62d32  ldarg.1
0x62d33  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x62d38  stloc.1
0x62d39  ldloc.1
0x62d3a  ldc.i4   0x7C676B44
0x62d3f  bgt.un   loc_62DD3
0x62d44  ldloc.1
0x62d45  ldc.i4   0x1E717A3A
0x62d4a  bgt.un.s loc_62D8A
0x62d4c  ldloc.1
0x62d4d  ldc.i4   0x12D21220
0x62d52  bgt.un.s loc_62D6F
0x62d54  ldloc.1
0x62d55  ldc.i4   0x10EA0C9A
0x62d5a  beq      loc_62E64
0x62d5f  ldloc.1
0x62d60  ldc.i4   0x12D21220
0x62d65  beq      loc_62EF7
0x62d6a  br       loc_63079
0x62d6f  ldloc.1
0x62d70  ldc.i4   0x1C5BF4D4
0x62d75  beq      loc_62F60
0x62d7a  ldloc.1
0x62d7b  ldc.i4   0x1E717A3A
0x62d80  beq      loc_62F75
0x62d85  br       loc_63079
0x62d8a  ldloc.1
0x62d8b  ldc.i4   0x4D3A4A77
0x62d90  bgt.un.s loc_62DAD
0x62d92  ldloc.1
0x62d93  ldc.i4   0x34DEB923
0x62d98  beq      loc_62F36
0x62d9d  ldloc.1
0x62d9e  ldc.i4   0x4D3A4A77
0x62da3  beq      loc_62FC9
0x62da8  br       loc_63079
0x62dad  ldloc.1
0x62dae  ldc.i4   0x5F4E41FE
0x62db3  beq      loc_62F0C
0x62db8  ldloc.1
0x62db9  ldc.i4   0x61F7D251
0x62dbe  beq      loc_62EE2
0x62dc3  ldloc.1
0x62dc4  ldc.i4   0x7C676B44
0x62dc9  beq      loc_62FB4
0x62dce  br       loc_63079
0x62dd3  ldloc.1
0x62dd4  ldc.i4   0xA4FC0E2D
0x62dd9  bgt.un.s loc_62E24
0x62ddb  ldloc.1
0x62ddc  ldc.i4   0x902B7E39
0x62de1  bgt.un.s loc_62DFE
0x62de3  ldloc.1
0x62de4  ldc.i4   0x7E620DE8
0x62de9  beq      loc_62EA3
0x62dee  ldloc.1
0x62def  ldc.i4   0x902B7E39
0x62df4  beq      loc_62F9F
0x62df9  br       loc_63079
0x62dfe  ldloc.1
0x62dff  ldc.i4   0x9828037A
0x62e04  beq      loc_62ECD
0x62e09  ldloc.1
0x62e0a  ldc.i4   0xA43DDDD2
0x62e0f  beq      loc_62F21
0x62e14  ldloc.1
0x62e15  ldc.i4   0xA4FC0E2D
0x62e1a  beq      loc_62F8A
0x62e1f  br       loc_63079
0x62e24  ldloc.1
0x62e25  ldc.i4   0xCA73AFC5
0x62e2a  bgt.un.s loc_62E41
0x62e2c  ldloc.1
0x62e2d  ldc.i4   0xC906B2C4
0x62e32  beq.s    loc_62E79
0x62e34  ldloc.1
0x62e35  ldc.i4   0xCA73AFC5
0x62e3a  beq.s    loc_62E8E
0x62e3c  br       loc_63079
0x62e41  ldloc.1
0x62e42  ldc.i4   0xE9F43F78
0x62e47  beq      loc_62FDE
0x62e4c  ldloc.1
0x62e4d  ldc.i4   0xFE3110C8
0x62e52  beq.s    loc_62EB8
0x62e54  ldloc.1
0x62e55  ldc.i4   0xFF063348
0x62e5a  beq      loc_62F4B
0x62e5f  br       loc_63079
0x62e64  ldarg.1
0x62e65  ldstr    aSystemform// "SystemForm"
0x62e6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62e6f  brtrue   loc_62FF3
0x62e74  br       loc_63079
0x62e79  ldarg.1
0x62e7a  ldstr    aUserform// "UserForm"
0x62e7f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62e84  brtrue   loc_62FFE
0x62e89  br       loc_63079
0x62e8e  ldarg.1
0x62e8f  ldstr    aBusinessproces_2// "BusinessProcessTaskFlow"
0x62e94  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62e99  brtrue   loc_63009
0x62e9e  br       loc_63079
0x62ea3  ldarg.1
0x62ea4  ldstr    aBusinessproces_3// "BusinessProcessFlow"
0x62ea9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62eae  brtrue   loc_63011
0x62eb3  br       loc_63079
0x62eb8  ldarg.1
0x62eb9  ldstr    aWorkflow// "Workflow"
0x62ebe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62ec3  brtrue   loc_63019
0x62ec8  br       loc_63079
0x62ecd  ldarg.1
0x62ece  ldstr    aPlugintype// "PluginType"
0x62ed3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62ed8  brtrue   loc_6308A
0x62edd  br       loc_63079
0x62ee2  ldarg.1
0x62ee3  ldstr    aWebresource// "WebResource"
0x62ee8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62eed  brtrue   loc_6308A
0x62ef2  br       loc_63079
0x62ef7  ldarg.1
0x62ef8  ldstr    aSavedquery// "SavedQuery"
0x62efd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f02  brtrue   loc_6308A
0x62f07  br       loc_63079
0x62f0c  ldarg.1
0x62f0d  ldstr    aUserquery// "UserQuery"
0x62f12  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f17  brtrue   loc_63021
0x62f1c  br       loc_63079
0x62f21  ldarg.1
0x62f22  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x62f27  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f2c  brtrue   loc_63029
0x62f31  br       loc_63079
0x62f36  ldarg.1
0x62f37  ldstr    aCustomcontrol_0// "CustomControl"
0x62f3c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f41  brtrue   loc_63031
0x62f46  br       loc_63079
0x62f4b  ldarg.1
0x62f4c  ldstr    aSitemap// "SiteMap"
0x62f51  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f56  brtrue   loc_63039
0x62f5b  br       loc_63079
0x62f60  ldarg.1
0x62f61  ldstr    aSavedqueryvisu// "SavedQueryVisualization"
0x62f66  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f6b  brtrue   loc_63041
0x62f70  br       loc_63079
0x62f75  ldarg.1
0x62f76  ldstr    aUserqueryvisua// "UserQueryVisualization"
0x62f7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f80  brtrue   loc_63049
0x62f85  br       loc_63079
0x62f8a  ldarg.1
0x62f8b  ldstr    aMultientitysea_0// "MultiEntitySearch"
0x62f90  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62f95  brtrue   loc_63051
0x62f9a  br       loc_63079
0x62f9f  ldarg.1
0x62fa0  ldstr    aRole// "Role"
0x62fa5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62faa  brtrue   loc_63059
0x62faf  br       loc_63079
0x62fb4  ldarg.1
0x62fb5  ldstr    aAppmodule// "AppModule"
0x62fba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62fbf  brtrue   loc_63061
0x62fc4  br       loc_63079
0x62fc9  ldarg.1
0x62fca  ldstr    aRibbonclientme// "RibbonClientMetadata"
0x62fcf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62fd4  brtrue   loc_63069
0x62fd9  br       loc_63079
0x62fde  ldarg.1
0x62fdf  ldstr    aComplexcontrol// "ComplexControl"
0x62fe4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x62fe9  brtrue   loc_63071
0x62fee  br       loc_63079
0x62ff3  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SystemFormGenerator::.ctor()
0x62ff8  stloc.0
0x62ff9  br       loc_6308A
0x62ffe  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserDashboardGenerator::.ctor()
0x63003  stloc.0
0x63004  br       loc_6308A
0x63009  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.TaskBasedFlowGenerator::.ctor()
0x6300e  stloc.0
0x6300f  br.s     loc_6308A
0x63011  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.BusinessProcessFlowGenerator::.ctor()
0x63016  stloc.0
0x63017  br.s     loc_6308A
0x63019  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.ProcessActionOperationGenerator::.ctor()
0x6301e  stloc.0
0x6301f  br.s     loc_6308A
0x63021  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserQueryGenerator::.ctor()
0x63026  stloc.0
0x63027  br.s     loc_6308A
0x63029  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CustomControlConfigurationGenerator::.ctor()
0x6302e  stloc.0
0x6302f  br.s     loc_6308A
0x63031  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.CustomControlGenerator::.ctor()
0x63036  stloc.0
0x63037  br.s     loc_6308A
0x63039  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SiteMapGenerator::.ctor()
0x6303e  stloc.0
0x6303f  br.s     loc_6308A
0x63041  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SavedQueryVisualizationGenerator::.ctor()
0x63046  stloc.0
0x63047  br.s     loc_6308A
0x63049  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.UserQueryVisualizationGenerator::.ctor()
0x6304e  stloc.0
0x6304f  br.s     loc_6308A
0x63051  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.SearchConfigurationGenerator::.ctor()
0x63056  stloc.0
0x63057  br.s     loc_6308A
0x63059  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.RoleGenerator::.ctor()
0x6305e  stloc.0
0x6305f  br.s     loc_6308A
0x63061  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.AppModuleGenerator::.ctor()
0x63066  stloc.0
0x63067  br.s     loc_6308A
0x63069  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.RibbonClientMetadataGenerator::.ctor()
0x6306e  stloc.0
0x6306f  br.s     loc_6308A
0x63071  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.Metadata.Generators.ComplexControlGenerator::.ctor()
0x63076  stloc.0
0x63077  br.s     loc_6308A
0x63079  ldarg.1
0x6307a  ldstr    aDoesnTHaveAGen// " doesn't have a generator implemented"
0x6307f  call     string [mscorlib]System.String::Concat(string, string)
0x63084  newobj   instance void [mscorlib]System.NotImplementedException::.ctor(string)
0x63089  throw
0x6308a  ldloc.0
0x6308b  ret
```
