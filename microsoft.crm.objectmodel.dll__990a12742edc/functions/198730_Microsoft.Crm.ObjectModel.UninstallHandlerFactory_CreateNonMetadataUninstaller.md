# Microsoft.Crm.ObjectModel.UninstallHandlerFactory::CreateNonMetadataUninstaller

- ea: `0x198730`
- end: `0x198a34`
- name: `Microsoft.Crm.ObjectModel.UninstallHandlerFactory::CreateNonMetadataUninstaller`
- size: `772`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1983b0`

## callees

- `0x16d9a0`
- `0x195c80`
- `0x195d00`
- `0x195e00`
- `0x195f70`
- `0x195fd0`
- `0x196180`
- `0x196610`
- `0x196aa0`
- `0x196db0`
- `0x1977e0`
- `0x197950`
- `0x198730`
- `0x1994b0`
- `0x199510`
- `0x199580`
- `0x1bedc0`
- `0x1f09f0`
- `0x22be40`

## string_xrefs

- `0x198987`: `CustomControlDefaultConfig`
- `0x198861`: `FieldSecurityProfile`
- `0x1988f4`: `PluginAssembly`
- `0x198909`: `Template`
- `0x1989ed`: `Template`
- `0x198730`: `CommonUnInstallFactory`

## pseudocode

```c

```

## disassembly

```asm
0x198730  ldstr    aCommonuninstal// "CommonUnInstallFactory"
0x198735  call     object [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::BusinessProcessReflectionUtiltity(string)
0x19873a  castclass Microsoft.Crm.ObjectModel.ICommonUnInstallFactory
0x19873f  stloc.0
0x198740  ldarg.0
0x198741  callvirt instance string [Microsoft.Crm.Platform.Server]Microsoft.Crm.Solution.ComponentTypeMapData::get_PlatformName()
0x198746  stloc.1
0x198747  ldloc.1
0x198748  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x19874d  stloc.2
0x19874e  ldloc.2
0x19874f  ldc.i4   0x6DEFD58A
0x198754  bgt.un   loc_1987DD
0x198759  ldloc.2
0x19875a  ldc.i4   0x34DEB923
0x19875f  bgt.un.s loc_19879F
0x198761  ldloc.2
0x198762  ldc.i4   0x12D21220
0x198767  bgt.un.s loc_198784
0x198769  ldloc.2
0x19876a  ldc.i4   0x10EA0C9A
0x19876f  beq      loc_19888A
0x198774  ldloc.2
0x198775  ldc.i4   0x12D21220
0x19877a  beq      loc_19891D
0x19877f  br       loc_198A2E
0x198784  ldloc.2
0x198785  ldc.i4   0x1563FA76
0x19878a  beq      loc_198971
0x19878f  ldloc.2
0x198790  ldc.i4   0x34DEB923
0x198795  beq      loc_1989AD
0x19879a  br       loc_198A2E
0x19879f  ldloc.2
0x1987a0  ldc.i4   0x4681FA0B
0x1987a5  bgt.un.s loc_1987C2
0x1987a7  ldloc.2
0x1987a8  ldc.i4   0x3F43BB84
0x1987ad  beq      loc_198932
0x1987b2  ldloc.2
0x1987b3  ldc.i4   0x4681FA0B
0x1987b8  beq      loc_1988C9
0x1987bd  br       loc_198A2E
0x1987c2  ldloc.2
0x1987c3  ldc.i4   0x65966B2B
0x1987c8  beq      loc_198908
0x1987cd  ldloc.2
0x1987ce  ldc.i4   0x6DEFD58A
0x1987d3  beq      loc_1988F3
0x1987d8  br       loc_198A2E
0x1987dd  ldloc.2
0x1987de  ldc.i4   0x9C52B721
0x1987e3  bgt.un.s loc_198820
0x1987e5  ldloc.2
0x1987e6  ldc.i4   0x902B7E39
0x1987eb  bgt.un.s loc_198805
0x1987ed  ldloc.2
0x1987ee  ldc.i4   0x7C676B44
0x1987f3  beq      loc_19899B
0x1987f8  ldloc.2
0x1987f9  ldc.i4   0x902B7E39
0x1987fe  beq.s    loc_198875
0x198800  br       loc_198A2E
0x198805  ldloc.2
0x198806  ldc.i4   0x97E841F3
0x19880b  beq      loc_1988DE
0x198810  ldloc.2
0x198811  ldc.i4   0x9C52B721
0x198816  beq      loc_19895C
0x19881b  br       loc_198A2E
0x198820  ldloc.2
0x198821  ldc.i4   0xC79BAA2F
0x198826  bgt.un.s loc_198843
0x198828  ldloc.2
0x198829  ldc.i4   0xA43DDDD2
0x19882e  beq      loc_198986
0x198833  ldloc.2
0x198834  ldc.i4   0xC79BAA2F
0x198839  beq      loc_198947
0x19883e  br       loc_198A2E
0x198843  ldloc.2
0x198844  ldc.i4   0xD33F7082
0x198849  beq.s    loc_198860
0x19884b  ldloc.2
0x19884c  ldc.i4   0xFE3110C8
0x198851  beq.s    loc_1988B4
0x198853  ldloc.2
0x198854  ldc.i4   0xFF063348
0x198859  beq.s    loc_19889F
0x19885b  br       loc_198A2E
0x198860  ldloc.1
0x198861  ldstr    aFieldsecurityp// "FieldSecurityProfile"
0x198866  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19886b  brtrue   loc_1989BC
0x198870  br       loc_198A2E
0x198875  ldloc.1
0x198876  ldstr    aRole// "Role"
0x19887b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198880  brtrue   loc_1989C2
0x198885  br       loc_198A2E
0x19888a  ldloc.1
0x19888b  ldstr    aSystemform// "SystemForm"
0x198890  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198895  brtrue   loc_1989C8
0x19889a  br       loc_198A2E
0x19889f  ldloc.1
0x1988a0  ldstr    aSitemap// "SiteMap"
0x1988a5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1988aa  brtrue   loc_1989CE
0x1988af  br       loc_198A2E
0x1988b4  ldloc.1
0x1988b5  ldstr    aWorkflow// "Workflow"
0x1988ba  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1988bf  brtrue   loc_1989D4
0x1988c4  br       loc_198A2E
0x1988c9  ldloc.1
0x1988ca  ldstr    aReport// "Report"
0x1988cf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1988d4  brtrue   loc_1989DA
0x1988d9  br       loc_198A2E
0x1988de  ldloc.1
0x1988df  ldstr    aSdkmessageproc_0// "SdkMessageProcessingStep"
0x1988e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1988e9  brtrue   loc_1989E0
0x1988ee  br       loc_198A2E
0x1988f3  ldloc.1
0x1988f4  ldstr    aPluginassembly_0// "PluginAssembly"
0x1988f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1988fe  brtrue   loc_1989E6
0x198903  br       loc_198A2E
0x198908  ldloc.1
0x198909  ldstr    aTemplate_0// "Template"
0x19890e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198913  brtrue   loc_1989EC
0x198918  br       loc_198A2E
0x19891d  ldloc.1
0x19891e  ldstr    aSavedquery// "SavedQuery"
0x198923  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198928  brtrue   loc_1989F8
0x19892d  br       loc_198A2E
0x198932  ldloc.1
0x198933  ldstr    aEntitymap// "EntityMap"
0x198938  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19893d  brtrue   loc_1989FE
0x198942  br       loc_198A2E
0x198947  ldloc.1
0x198948  ldstr    aAttributemap// "AttributeMap"
0x19894d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198952  brtrue   loc_198A04
0x198957  br       loc_198A2E
0x19895c  ldloc.1
0x19895d  ldstr    aActivitymimeat_1// "ActivityMimeAttachment"
0x198962  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198967  brtrue   loc_198A0A
0x19896c  br       loc_198A2E
0x198971  ldloc.1
0x198972  ldstr    aHierarchyrule// "HierarchyRule"
0x198977  call     bool [mscorlib]System.String::op_Equality(string, string)
0x19897c  brtrue   loc_198A16
0x198981  br       loc_198A2E
0x198986  ldloc.1
0x198987  ldstr    aCustomcontrold// "CustomControlDefaultConfig"
0x19898c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x198991  brtrue   loc_198A1C
0x198996  br       loc_198A2E
0x19899b  ldloc.1
0x19899c  ldstr    aAppmodule// "AppModule"
0x1989a1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1989a6  brtrue.s loc_198A22
0x1989a8  br       loc_198A2E
0x1989ad  ldloc.1
0x1989ae  ldstr    aCustomcontrol// "CustomControl"
0x1989b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1989b8  brtrue.s loc_198A28
0x1989ba  br.s     loc_198A2E
0x1989bc  newobj   instance void Microsoft.Crm.ObjectModel.FieldSecurityProfileUninstallHandler::.ctor()
0x1989c1  ret
0x1989c2  newobj   instance void Microsoft.Crm.ObjectModel.RoleUninstallHandler::.ctor()
0x1989c7  ret
0x1989c8  newobj   instance void Microsoft.Crm.ObjectModel.SystemFormUninstallHandler::.ctor()
0x1989cd  ret
0x1989ce  newobj   instance void Microsoft.Crm.ObjectModel.SiteMapUninstallHandler::.ctor()
0x1989d3  ret
0x1989d4  newobj   instance void Microsoft.Crm.ObjectModel.WorkflowUninstallHandler::.ctor()
0x1989d9  ret
0x1989da  newobj   instance void Microsoft.Crm.ObjectModel.ReportUninstallHandler::.ctor()
0x1989df  ret
0x1989e0  newobj   instance void Microsoft.Crm.ObjectModel.SdkMessageProcessingStepUninstallHandler::.ctor()
0x1989e5  ret
0x1989e6  newobj   instance void Microsoft.Crm.ObjectModel.PluginAssemblyUninstallHandler::.ctor()
0x1989eb  ret
0x1989ec  ldloc.0
0x1989ed  ldstr    aTemplate_0// "Template"
0x1989f2  callvirt instance class Microsoft.Crm.ObjectModel.UninstallHandler Microsoft.Crm.ObjectModel.ICommonUnInstallFactory::RetrieveTypeFromUninstallFactory(string platFormName)
0x1989f7  ret
0x1989f8  newobj   instance void Microsoft.Crm.ObjectModel.SavedQueryUninstallHandler::.ctor()
0x1989fd  ret
0x1989fe  newobj   instance void Microsoft.Crm.ObjectModel.EntityMapUninstallHandler::.ctor()
0x198a03  ret
0x198a04  newobj   instance void Microsoft.Crm.ObjectModel.AttributeMapUninstallHandler::.ctor()
0x198a09  ret
0x198a0a  ldloc.0
0x198a0b  ldstr    aActivitymimeat_1// "ActivityMimeAttachment"
0x198a10  callvirt instance class Microsoft.Crm.ObjectModel.UninstallHandler Microsoft.Crm.ObjectModel.ICommonUnInstallFactory::RetrieveTypeFromUninstallFactory(string platFormName)
0x198a15  ret
0x198a16  newobj   instance void Microsoft.Crm.ObjectModel.HierarchyRuleUninstallHandler::.ctor()
0x198a1b  ret
0x198a1c  newobj   instance void Microsoft.Crm.ObjectModel.CustomControDefaultConfigUninstallHandler::.ctor()
0x198a21  ret
0x198a22  newobj   instance void Microsoft.Crm.ObjectModel.Solution.Uninstall.AppModuleUninstallHandler::.ctor()
0x198a27  ret
0x198a28  newobj   instance void Microsoft.Crm.ObjectModel.CustomControlUninstallHandler::.ctor()
0x198a2d  ret
0x198a2e  newobj   instance void Microsoft.Crm.ObjectModel.NonMetadataUninstallHandler::.ctor()
0x198a33  ret
```
