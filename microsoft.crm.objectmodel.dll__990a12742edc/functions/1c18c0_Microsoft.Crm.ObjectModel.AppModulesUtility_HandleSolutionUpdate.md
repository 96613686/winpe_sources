# Microsoft.Crm.ObjectModel.AppModulesUtility::HandleSolutionUpdate

- ea: `0x1c18c0`
- end: `0x1c1d51`
- name: `Microsoft.Crm.ObjectModel.AppModulesUtility::HandleSolutionUpdate`
- size: `1169`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1f0970`

## callees

- `0x14a60`
- `0x14a80`
- `0x14ac0`
- `0x14ae0`
- `0x14b60`
- `0x14cf0`
- `0x158c0`
- `0x1c1400`
- `0x1c1440`
- `0x1c1490`
- `0x1c16f0`
- `0x1c1710`
- `0x1c1800`
- `0x1c1820`
- `0x1c18c0`
- `0x1c1dc0`

## string_xrefs

- `0x1c1aad`: `appmodulexmlmanaged`
- `0x1c18ff`: `AppModulesUtility.HandleSolutionUpdate(): [isSolutionDelete:{0}]`
- `0x1c1c19`: `AppModulesUtility.HandleSolutionUpdate(): [isSolutionDelete:{0}]`
- `0x1c1961`: `AppModulesUtility.HandleSolutionUpdate(): [appModuleStates.count:{0}]`
- `0x1c19d5`: `AppModulesUtility.HandleSolutionUpdate(): appModuleInstance[SolutionId:{0}],[ComponentState:{1}]`
- `0x1c1a54`: `AppModulesUtility.HandleSolutionUpdate(): currentAppModule[appmoduleid:{0}],[appmoduleidunique:{1}]`
- `0x1c1aca`: `AppModulesUtility.HandleSolutionUpdate(): [originalManagedDiff:{0}]`
- `0x1c1b64`: `AppModulesUtility.HandleSolutionUpdate(): [appModuleInstance.SolutionId:{0}],[currentSolutionId:{1}]`
- `0x1c1bad`: `AppModulesUtility.HandleSolutionUpdate(): [prevInstance==null:{0}]`
- `0x1c1ce7`: `AppModulesUtility.HandleSolutionUpdate(): Update Solution layers`
- `0x1c1d40`: `AppModulesUtility.HandleSolutionUpdate(): END`

## pseudocode

```c

```

## disassembly

```asm
0x1c18c0  ldarg.0
0x1c18c1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c18c6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c18cb  ldc.i4.s 0x47
0x1c18cd  ldstr    aAppmodulesutil_26// "AppModulesUtility.DiffAppModule(): STAR"...
0x1c18d2  ldc.i4.0
0x1c18d3  newarr   [mscorlib]System.Object
0x1c18d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c18dd  ldarg.0
0x1c18de  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c18e3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x1c18e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.ISolutionContext::get_SolutionId()
0x1c18ed  stloc.0
0x1c18ee  ldc.i4.0
0x1c18ef  stloc.1
0x1c18f0  ldnull
0x1c18f1  stloc.2
0x1c18f2  ldarg.0
0x1c18f3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c18f8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c18fd  ldc.i4.s 0x47
0x1c18ff  ldstr    aAppmodulesutil_27// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1904  ldc.i4.1
0x1c1905  newarr   [mscorlib]System.Object
0x1c190a  dup
0x1c190b  ldc.i4.0
0x1c190c  ldarg.s  4
0x1c190e  box      [mscorlib]System.Boolean
0x1c1913  stelem.ref
0x1c1914  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1919  ldarg.s  4
0x1c191b  brtrue.s loc_1C1932
0x1c191d  ldarg.0
0x1c191e  ldfld    class Microsoft.Crm.AppModule.AppModuleXmlParser Microsoft.Crm.ObjectModel.AppModulesUtility::_appModuleXmlParser
0x1c1923  ldarg.1
0x1c1924  ldarg.2
0x1c1925  callvirt instance class Microsoft.Crm.AppModule.AppModuleDefinition Microsoft.Crm.AppModule.AppModuleXmlParser::GenerateAppModuleDefinition(class [System.Xml]System.Xml.XmlNode appModuleXmlNode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> localizedColumnValuePair)
0x1c192a  stloc.2
0x1c192b  ldarg.0
0x1c192c  ldloc.2
0x1c192d  call     instance void Microsoft.Crm.ObjectModel.AppModulesUtility::ConvertSchemaNameToGuids(class Microsoft.Crm.AppModule.AppModuleDefinition appModule)
0x1c1932  ldarg.0
0x1c1933  ldarg.3
0x1c1934  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_BasePublishedInstance()
0x1c1939  ldstr    aAppmoduleid// "appmoduleid"
0x1c193e  callvirt instance object [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_Item(string)
0x1c1943  unbox.any [mscorlib]System.Guid
0x1c1948  call     instance class Microsoft.Crm.AppModule.AppModuleDefinition Microsoft.Crm.ObjectModel.AppModulesUtility::CalculateCustomizationDiff(valuetype [mscorlib]System.Guid appModuleId)
0x1c194d  stloc.3
0x1c194e  ldnull
0x1c194f  stloc.s  4
0x1c1951  ldnull
0x1c1952  stloc.s  5
0x1c1954  ldarg.0
0x1c1955  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c195a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c195f  ldc.i4.s 0x47
0x1c1961  ldstr    aAppmodulesutil_28// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1966  ldc.i4.1
0x1c1967  newarr   [mscorlib]System.Object
0x1c196c  dup
0x1c196d  ldc.i4.0
0x1c196e  ldarg.3
0x1c196f  brtrue.s loc_1C197D
0x1c1971  ldloca.s 6
0x1c1973  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1c1979  ldloc.s  6
0x1c197b  br.s     loc_1C199D
0x1c197d  ldarg.3
0x1c197e  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x1c1983  dup
0x1c1984  brtrue.s loc_1C1993
0x1c1986  pop
0x1c1987  ldloca.s 6
0x1c1989  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x1c198f  ldloc.s  6
0x1c1991  br.s     loc_1C199D
0x1c1993  call     instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Count()
0x1c1998  newobj   instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x1c199d  box      valuetype [mscorlib]System.Nullable`1<int32>
0x1c19a2  stelem.ref
0x1c19a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c19a8  ldarg.3
0x1c19a9  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance> [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentState::get_Instances()
0x1c19ae  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::GetEnumerator()
0x1c19b3  stloc.s  7
0x1c19b5  br       loc_1C1D17
0x1c19ba  ldloca.s 7
0x1c19bc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance>::get_Current()
0x1c19c1  castclass [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance
0x1c19c6  stloc.s  8
0x1c19c8  ldarg.0
0x1c19c9  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c19ce  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c19d3  ldc.i4.s 0x47
0x1c19d5  ldstr    aAppmodulesutil_29// "AppModulesUtility.HandleSolutionUpdate("...
0x1c19da  ldc.i4.2
0x1c19db  newarr   [mscorlib]System.Object
0x1c19e0  dup
0x1c19e1  ldc.i4.0
0x1c19e2  ldloc.s  8
0x1c19e4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1c19e9  box      [mscorlib]System.Guid
0x1c19ee  stelem.ref
0x1c19ef  dup
0x1c19f0  ldc.i4.1
0x1c19f1  ldloc.s  8
0x1c19f3  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x1c19f8  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState
0x1c19fd  stelem.ref
0x1c19fe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1a03  ldloc.s  8
0x1c1a05  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1c1a0a  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x1c1a0f  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c1a14  brfalse.s loc_1C1A20
0x1c1a16  ldloc.s  8
0x1c1a18  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.ComponentState [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_ComponentState()
0x1c1a1d  ldc.i4.1
0x1c1a1e  beq.s    loc_1C1A32
0x1c1a20  ldloc.1
0x1c1a21  brtrue.s loc_1C1A3B
0x1c1a23  ldloc.s  8
0x1c1a25  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1c1a2a  ldloc.0
0x1c1a2b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c1a30  brfalse.s loc_1C1A3B
0x1c1a32  ldloc.s  8
0x1c1a34  stloc.s  4
0x1c1a36  br       loc_1C1D17
0x1c1a3b  ldc.i4.0
0x1c1a3c  stloc.s  9
0x1c1a3e  ldloc.s  8
0x1c1a40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x1c1a45  stloc.s  0xA
0x1c1a47  ldarg.0
0x1c1a48  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c1a4d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c1a52  ldc.i4.s 0x47
0x1c1a54  ldstr    aAppmodulesutil_30// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1a59  ldc.i4.2
0x1c1a5a  newarr   [mscorlib]System.Object
0x1c1a5f  dup
0x1c1a60  ldc.i4.0
0x1c1a61  ldloc.s  0xA
0x1c1a63  ldstr    aAppmoduleid// "appmoduleid"
0x1c1a68  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1a6d  stelem.ref
0x1c1a6e  dup
0x1c1a6f  ldc.i4.1
0x1c1a70  ldloc.s  0xA
0x1c1a72  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x1c1a77  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1a7c  stelem.ref
0x1c1a7d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1a82  ldarg.0
0x1c1a83  ldloc.s  0xA
0x1c1a85  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x1c1a8a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1a8f  unbox.any [mscorlib]System.Guid
0x1c1a94  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppModulesUtility::RetrieveAppModuleComponents(valuetype [mscorlib]System.Guid appModuleIdUnique)
0x1c1a99  stloc.s  0xB
0x1c1a9b  ldloc.s  0xA
0x1c1a9d  ldloc.s  0xB
0x1c1a9f  ldnull
0x1c1aa0  ldnull
0x1c1aa1  newobj   instance void Microsoft.Crm.AppModule.AppModuleDefinition::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleComponents, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleRoleMaps, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> roleIdToRoleTemplateIdMap)
0x1c1aa6  stloc.s  0xC
0x1c1aa8  ldnull
0x1c1aa9  stloc.s  0xD
0x1c1aab  ldloc.s  0xA
0x1c1aad  ldstr    aAppmodulexmlma// "appmodulexmlmanaged"
0x1c1ab2  ldloca.s 0xD
0x1c1ab4  callvirt T0x2B00003D
0x1c1ab9  pop
0x1c1aba  ldnull
0x1c1abb  stloc.s  0xE
0x1c1abd  ldarg.0
0x1c1abe  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c1ac3  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c1ac8  ldc.i4.s 0x47
0x1c1aca  ldstr    aAppmodulesutil_31// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1acf  ldc.i4.1
0x1c1ad0  newarr   [mscorlib]System.Object
0x1c1ad5  dup
0x1c1ad6  ldc.i4.0
0x1c1ad7  ldloc.s  0xD
0x1c1ad9  stelem.ref
0x1c1ada  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1adf  ldloc.s  0xD
0x1c1ae1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1c1ae6  brfalse.s loc_1C1AFA
0x1c1ae8  ldloc.s  0xA
0x1c1aea  ldloc.s  0xB
0x1c1aec  ldnull
0x1c1aed  ldnull
0x1c1aee  newobj   instance void Microsoft.Crm.AppModule.AppModuleDefinition::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleComponents, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleRoleMaps, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> roleIdToRoleTemplateIdMap)
0x1c1af3  stloc.s  0xE
0x1c1af5  ldc.i4.1
0x1c1af6  stloc.s  9
0x1c1af8  br.s     loc_1C1B57
0x1c1afa  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x1c1aff  starg.s  2
0x1c1b01  ldarg.2
0x1c1b02  ldstr    aName// "name"
0x1c1b07  ldloc.s  0xA
0x1c1b09  ldstr    aName// "name"
0x1c1b0e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1b13  castclass [mscorlib]System.String
0x1c1b18  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1c1b1d  ldarg.2
0x1c1b1e  ldstr    aDescription// "description"
0x1c1b23  ldloc.s  0xA
0x1c1b25  ldstr    aDescription// "description"
0x1c1b2a  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1b2f  castclass [mscorlib]System.String
0x1c1b34  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::set_Item(var<u1>, !!T0)
0x1c1b39  ldarg.0
0x1c1b3a  ldfld    class Microsoft.Crm.AppModule.AppModuleXmlParser Microsoft.Crm.ObjectModel.AppModulesUtility::_appModuleXmlParser
0x1c1b3f  ldarg.0
0x1c1b40  ldloc.s  0xD
0x1c1b42  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Crm.ObjectModel.AppModulesUtility::GetXmlNode(string xmlNode)
0x1c1b47  ldarg.2
0x1c1b48  callvirt instance class Microsoft.Crm.AppModule.AppModuleDefinition Microsoft.Crm.AppModule.AppModuleXmlParser::GenerateAppModuleDefinition(class [System.Xml]System.Xml.XmlNode appModuleXmlNode, class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> localizedColumnValuePair)
0x1c1b4d  stloc.s  0xE
0x1c1b4f  ldarg.0
0x1c1b50  ldloc.s  0xE
0x1c1b52  call     instance void Microsoft.Crm.ObjectModel.AppModulesUtility::ConvertSchemaNameToGuids(class Microsoft.Crm.AppModule.AppModuleDefinition appModule)
0x1c1b57  ldarg.0
0x1c1b58  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c1b5d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c1b62  ldc.i4.s 0x47
0x1c1b64  ldstr    aAppmodulesutil_32// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1b69  ldc.i4.2
0x1c1b6a  newarr   [mscorlib]System.Object
0x1c1b6f  dup
0x1c1b70  ldc.i4.0
0x1c1b71  ldloc.s  8
0x1c1b73  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1c1b78  box      [mscorlib]System.Guid
0x1c1b7d  stelem.ref
0x1c1b7e  dup
0x1c1b7f  ldc.i4.1
0x1c1b80  ldloc.0
0x1c1b81  box      [mscorlib]System.Guid
0x1c1b86  stelem.ref
0x1c1b87  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1b8c  ldloc.s  8
0x1c1b8e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.ComponentInstance::get_SolutionId()
0x1c1b93  ldloc.0
0x1c1b94  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1c1b99  brfalse  loc_1C1C3A
0x1c1b9e  ldc.i4.1
0x1c1b9f  stloc.1
0x1c1ba0  ldarg.0
0x1c1ba1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c1ba6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c1bab  ldc.i4.s 0x47
0x1c1bad  ldstr    aAppmodulesutil_33// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1bb2  ldc.i4.1
0x1c1bb3  newarr   [mscorlib]System.Object
0x1c1bb8  dup
0x1c1bb9  ldc.i4.0
0x1c1bba  ldloc.s  4
0x1c1bbc  ldnull
0x1c1bbd  ceq
0x1c1bbf  box      [mscorlib]System.Boolean
0x1c1bc4  stelem.ref
0x1c1bc5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1c1bca  ldloc.s  4
0x1c1bcc  brtrue.s loc_1C1BDA
0x1c1bce  ldloc.s  0xC
0x1c1bd0  ldc.i4.0
0x1c1bd1  newobj   instance void Microsoft.Crm.AppModule.AppModuleDefinition::.ctor(class Microsoft.Crm.AppModule.AppModuleDefinition srcAppModule, bool copyComponents)
0x1c1bd6  stloc.s  5
0x1c1bd8  br.s     loc_1C1C09
0x1c1bda  ldloc.s  4
0x1c1bdc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.SolutionAwareComponents.BusinessComponentInstance::get_Entity()
0x1c1be1  stloc.s  0x12
0x1c1be3  ldarg.0
0x1c1be4  ldloc.s  0x12
0x1c1be6  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x1c1beb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x1c1bf0  unbox.any [mscorlib]System.Guid
0x1c1bf5  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.ObjectModel.AppModulesUtility::RetrieveAppModuleComponents(valuetype [mscorlib]System.Guid appModuleIdUnique)
0x1c1bfa  stloc.s  0x13
0x1c1bfc  ldloc.s  0x12
0x1c1bfe  ldloc.s  0x13
0x1c1c00  ldnull
0x1c1c01  ldnull
0x1c1c02  newobj   instance void Microsoft.Crm.AppModule.AppModuleDefinition::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity appModule, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleComponents, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection appModuleRoleMaps, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> roleIdToRoleTemplateIdMap)
0x1c1c07  stloc.s  5
0x1c1c09  ldloc.2
0x1c1c0a  stloc.s  0xE
0x1c1c0c  ldarg.0
0x1c1c0d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.ObjectModel.AppModulesUtility::_context
0x1c1c12  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x1c1c17  ldc.i4.s 0x47
0x1c1c19  ldstr    aAppmodulesutil_27// "AppModulesUtility.HandleSolutionUpdate("...
0x1c1c1e  ldc.i4.1
  ... truncated ...
```
