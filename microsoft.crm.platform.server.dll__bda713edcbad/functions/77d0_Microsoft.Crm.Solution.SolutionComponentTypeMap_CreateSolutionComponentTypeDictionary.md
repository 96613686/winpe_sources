# Microsoft.Crm.Solution.SolutionComponentTypeMap::CreateSolutionComponentTypeDictionary

- ea: `0x77d0`
- end: `0x8081`
- name: `Microsoft.Crm.Solution.SolutionComponentTypeMap::CreateSolutionComponentTypeDictionary`
- size: `2225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x7770`
- `0x77c0`

## callees

- `0x74c0`
- `0x77d0`
- `0x8090`
- `0x82a0`

## string_xrefs

- `0x792b`: `RolePrivileges`
- `0x798c`: `RibbonCommand`
- `0x79f0`: `RibbonTabToCommandMap`
- `0x7a54`: `Template`
- `0x7a86`: `ContractTemplate`
- `0x7a9f`: `KbArticleTemplate`
- `0x7ab8`: `MailMergeTemplate`
- `0x7b4e`: `FieldSecurityProfile`
- `0x7c53`: `PluginAssembly`
- `0x7c6c`: `PluginType`
- `0x7cb7`: `ServiceEndpoint`
- `0x7dd9`: `CustomControlDefaultConfig`
- `0x7e65`: `ChannelAccessProfileRule`
- `0x7e81`: `ChannelAccessProfileRuleItem`
- `0x7e9d`: `ChannelAccessProfile`
- `0x7eb9`: `ChannelAccessProfileEntityAccessLevel`
- `0x7f20`: `RecommendationModel`
- `0x7f3c`: `RecommendationModelMapping`
- `0x7f58`: `TopicModelConfiguration`
- `0x7fe1`: `AppConfig`
- `0x7ffd`: `AppConfigInstance`
- `0x806d`: `GlobalSearchConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x77d0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData>::.ctor()
0x77d5  dup
0x77d6  ldc.i4.1
0x77d7  ldstr    aEntity// "Entity"
0x77dc  ldc.i4.1
0x77dd  ldc.i4.1
0x77de  ldc.i4.1
0x77df  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x77e4  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x77e9  dup
0x77ea  ldc.i4.2
0x77eb  ldstr    aAttribute// "Attribute"
0x77f0  ldc.i4.2
0x77f1  ldc.i4.1
0x77f2  ldc.i4.0
0x77f3  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x77f8  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x77fd  dup
0x77fe  ldc.i4.3
0x77ff  ldstr    aRelationship// "Relationship"
0x7804  ldc.i4.3
0x7805  ldc.i4.1
0x7806  ldc.i4.0
0x7807  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x780c  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7811  dup
0x7812  ldc.i4.4
0x7813  ldstr    aAttributepickl// "AttributePicklistValue"
0x7818  ldc.i4.4
0x7819  ldc.i4.1
0x781a  ldc.i4.0
0x781b  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7820  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7825  dup
0x7826  ldc.i4.5
0x7827  ldstr    aAttributelooku// "AttributeLookupValue"
0x782c  ldc.i4.5
0x782d  ldc.i4.1
0x782e  ldc.i4.0
0x782f  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7834  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7839  dup
0x783a  ldc.i4.6
0x783b  ldstr    aViewattribute// "ViewAttribute"
0x7840  ldc.i4.6
0x7841  ldc.i4.1
0x7842  ldc.i4.0
0x7843  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7848  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x784d  dup
0x784e  ldc.i4.7
0x784f  ldstr    aLocalizedlabel// "LocalizedLabel"
0x7854  ldc.i4.7
0x7855  ldc.i4.1
0x7856  ldc.i4.0
0x7857  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x785c  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7861  dup
0x7862  ldc.i4.8
0x7863  ldstr    aRelationshipex// "RelationshipExtraCondition"
0x7868  ldc.i4.8
0x7869  ldc.i4.1
0x786a  ldc.i4.0
0x786b  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7870  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7875  dup
0x7876  ldc.i4.s 0xA
0x7878  ldstr    aEntityrelation// "EntityRelationship"
0x787d  ldc.i4.s 0xC
0x787f  ldc.i4.1
0x7880  ldc.i4.0
0x7881  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7886  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x788b  dup
0x788c  ldc.i4.s 0xB
0x788e  ldstr    aEntityrelation_0// "EntityRelationshipRole"
0x7893  ldc.i4.s 0xD
0x7895  ldc.i4.1
0x7896  ldc.i4.0
0x7897  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x789c  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x78a1  dup
0x78a2  ldc.i4.s 0xC
0x78a4  ldstr    aEntityrelation_1// "EntityRelationshipRelationships"
0x78a9  ldc.i4.s 0xE
0x78ab  ldc.i4.1
0x78ac  ldc.i4.0
0x78ad  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x78b2  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x78b7  dup
0x78b8  ldc.i4.s 9
0x78ba  ldstr    aOptionset// "OptionSet"
0x78bf  ldc.i4.s 0xF
0x78c1  ldc.i4.1
0x78c2  ldc.i4.1
0x78c3  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x78c8  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x78cd  dup
0x78ce  ldc.i4.s 0xD
0x78d0  ldstr    aManagedpropert// "ManagedProperty"
0x78d5  ldc.i4.s 0x10
0x78d7  ldc.i4.1
0x78d8  ldc.i4.1
0x78d9  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x78de  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x78e3  dup
0x78e4  ldc.i4.s 0xE
0x78e6  ldstr    aEntitykey// "EntityKey"
0x78eb  ldc.i4.s 0x12
0x78ed  ldc.i4.1
0x78ee  ldc.i4.0
0x78ef  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x78f4  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x78f9  dup
0x78fa  ldc.i4.s 0xF
0x78fc  ldstr    aEntitykeyattri// "EntityKeyAttribute"
0x7901  ldc.i4.s 0x13
0x7903  ldc.i4.1
0x7904  ldc.i4.0
0x7905  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x790a  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x790f  dup
0x7910  ldc.i4.s 0x14
0x7912  ldstr    aRole// "Role"
0x7917  ldc.i4   0x40C
0x791c  ldc.i4.0
0x791d  ldc.i4.1
0x791e  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7923  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7928  dup
0x7929  ldc.i4.s 0x15
0x792b  ldstr    aRoleprivileges// "RolePrivileges"
0x7930  ldc.i4.s 0xC
0x7932  ldc.i4.0
0x7933  ldc.i4.0
0x7934  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7939  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x793e  dup
0x793f  ldc.i4.s 0x16
0x7941  ldstr    aDisplaystring// "DisplayString"
0x7946  ldc.i4   0x1006
0x794b  ldc.i4.0
0x794c  ldc.i4.0
0x794d  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7952  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7957  dup
0x7958  ldc.i4.s 0x17
0x795a  ldstr    aDisplaystringm// "DisplayStringMap"
0x795f  ldc.i4   0x1005
0x7964  ldc.i4.0
0x7965  ldc.i4.0
0x7966  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x796b  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7970  dup
0x7971  ldc.i4.s 0x32
0x7973  ldstr    aRibboncustomiz// "RibbonCustomization"
0x7978  ldc.i4   0x460
0x797d  ldc.i4.0
0x797e  ldc.i4.1
0x797f  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7984  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7989  dup
0x798a  ldc.i4.s 0x30
0x798c  ldstr    aRibboncommand// "RibbonCommand"
0x7991  ldc.i4   0x45C
0x7996  ldc.i4.0
0x7997  ldc.i4.0
0x7998  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x799d  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x79a2  dup
0x79a3  ldc.i4.s 0x31
0x79a5  ldstr    aRibboncontextg// "RibbonContextGroup"
0x79aa  ldc.i4   0x45B
0x79af  ldc.i4.0
0x79b0  ldc.i4.0
0x79b1  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x79b6  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x79bb  dup
0x79bc  ldc.i4.s 0x37
0x79be  ldstr    aRibbondiff// "RibbonDiff"
0x79c3  ldc.i4   0x46A
0x79c8  ldc.i4.0
0x79c9  ldc.i4.0
0x79ca  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x79cf  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x79d4  dup
0x79d5  ldc.i4.s 0x34
0x79d7  ldstr    aRibbonrule// "RibbonRule"
0x79dc  ldc.i4   0x45D
0x79e1  ldc.i4.0
0x79e2  ldc.i4.0
0x79e3  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x79e8  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x79ed  dup
0x79ee  ldc.i4.s 0x35
0x79f0  ldstr    aRibbontabtocom// "RibbonTabToCommandMap"
0x79f5  ldc.i4   0x459
0x79fa  ldc.i4.0
0x79fb  ldc.i4.0
0x79fc  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a01  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a06  dup
0x7a07  ldc.i4.s 0x18
0x7a09  ldstr    aOrganizationui// "OrganizationUI"
0x7a0e  ldc.i4   0x3FD
0x7a13  ldc.i4.0
0x7a14  ldc.i4.0
0x7a15  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a1a  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a1f  dup
0x7a20  ldc.i4.s 0x1D
0x7a22  ldstr    aWorkflow// "Workflow"
0x7a27  ldc.i4   0x125F
0x7a2c  ldc.i4.0
0x7a2d  ldc.i4.1
0x7a2e  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a33  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a38  dup
0x7a39  ldc.i4.s 0x1E
0x7a3b  ldstr    aProcesstrigger// "ProcessTrigger"
0x7a40  ldc.i4   0x1268
0x7a45  ldc.i4.0
0x7a46  ldc.i4.0
0x7a47  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a4c  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a51  dup
0x7a52  ldc.i4.s 0x24
0x7a54  ldstr    aTemplate// "Template"
0x7a59  ldc.i4   0x7DA
0x7a5e  ldc.i4.0
0x7a5f  ldc.i4.1
0x7a60  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a65  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a6a  dup
0x7a6b  ldc.i4.s 0x23
0x7a6d  ldstr    aActivitymimeat// "ActivityMimeAttachment"
0x7a72  ldc.i4   0x3E9
0x7a77  ldc.i4.0
0x7a78  ldc.i4.0
0x7a79  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a7e  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a83  dup
0x7a84  ldc.i4.s 0x25
0x7a86  ldstr    aContracttempla// "ContractTemplate"
0x7a8b  ldc.i4   0x7DB
0x7a90  ldc.i4.0
0x7a91  ldc.i4.1
0x7a92  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7a97  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7a9c  dup
0x7a9d  ldc.i4.s 0x26
0x7a9f  ldstr    aKbarticletempl// "KbArticleTemplate"
0x7aa4  ldc.i4   0x3F8
0x7aa9  ldc.i4.0
0x7aaa  ldc.i4.1
0x7aab  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7ab0  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7ab5  dup
0x7ab6  ldc.i4.s 0x27
0x7ab8  ldstr    aMailmergetempl// "MailMergeTemplate"
0x7abd  ldc.i4   0x2392
0x7ac2  ldc.i4.0
0x7ac3  ldc.i4.1
0x7ac4  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7ac9  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7ace  dup
0x7acf  ldc.i4.s 0x2E
0x7ad1  ldstr    aEntitymap// "EntityMap"
0x7ad6  ldc.i4   0x11F8
0x7adb  ldc.i4.0
0x7adc  ldc.i4.0
0x7add  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7ae2  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7ae7  dup
0x7ae8  ldc.i4.s 0x2F
0x7aea  ldstr    aAttributemap// "AttributeMap"
0x7aef  ldc.i4   0x11F9
0x7af4  ldc.i4.0
0x7af5  ldc.i4.0
0x7af6  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7afb  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7b00  dup
0x7b01  ldc.i4.s 0x3D
0x7b03  ldstr    aWebresource// "WebResource"
0x7b08  ldc.i4   0x2475
0x7b0d  ldc.i4.0
0x7b0e  ldc.i4.1
0x7b0f  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7b14  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7b19  dup
0x7b1a  ldc.i4.s 0x3E
0x7b1c  ldstr    aSitemap// "SiteMap"
0x7b21  ldc.i4   0x1265
0x7b26  ldc.i4.0
0x7b27  ldc.i4.1
0x7b28  newobj   instance void Microsoft.Crm.Solution.ComponentTypeMapData::.ctor(int32 componentType, string platformName, int32 otc, bool isMetadata, bool isRoot)
0x7b2d  call     void Microsoft.Crm.Solution.SolutionComponentTypeMap::AddData(class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.Crm.Solution.ComponentTypeMapData> components, class Microsoft.Crm.Solution.ComponentTypeMapData data)
0x7b32  dup
0x7b33  ldc.i4.s 0x3F
0x7b35  ldstr    aConnectionrole// "ConnectionRole"
  ... truncated ...
```
