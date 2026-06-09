# Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::FillVersionInformation

- ea: `0x20d60`
- end: `0x2244b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::FillVersionInformation`
- size: `5867`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x20d20`

## callees

- `0x20d60`
- `0x52390`
- `0x523e0`
- `0x95ca0`
- `0x95cf0`
- `0x95e20`

## string_xrefs

- `0x21505`: `RemoveDocumentEntityUpgradeHandler`
- `0x21516`: `Customization.Upgrade_RemoveDocumentEntity_DisplayName`
- `0x21526`: `Customization.Upgrade_RemoveDocumentEntity_Description`
- `0x2154b`: `RemoveOutlookCommandUpgradeHandler`
- `0x2155c`: `Customization.Upgrade_RemoveOutlookCommand_DisplayName`
- `0x2156c`: `Customization.Upgrade_RemoveOutlookCommand_Description`
- `0x216a9`: `RemoveCustomizationsForNonCustomizableOptionSetsFromBetaHandler`
- `0x2177b`: `AdjustCascadeDeletePropertyForParentalReflexiveRelationshipsHandler`
- `0x21807`: `RemoveHiddenWebResources`
- `0x21893`: `RemoveDuplicateFilterTemplateSavedQueries`
- `0x21965`: `RemoveTransactionCurrencyAndExchangeRateFromKbArticle`
- `0x21ac3`: `RemoveVersionNumberFieldFromEntities`
- `0x21b4f`: `RemoveIsDuplicateCheckSupportedForCustomerAddressEntity`
- `0x21bdb`: `HandleChangedIsReadOnlyInMobile`
- `0x21c67`: `UpdateCascadePropertyForRelationshipHandler`
- `0x21cad`: `UpdateMobileClientPropertiesForSharepointDocumentHandler`
- `0x21cf3`: `UpdateMobileClientPropertiesForConnectionRole`
- `0x21d39`: `RemoveMobileClientMashupEnabledNode`
- `0x21d7f`: `UpdateMobileClientPropertiesForTemplate`
- `0x21dc5`: `UpdateMobileClientPropertiesForCompetitorAddress`
- `0x21e0b`: `UpdateMobileClientPropertiesForPriceLevelAndProductPriceLevel`
- `0x21e51`: `UpdateStreamTileParamsForIcDash`
- `0x21e97`: `UpgradeReadprivilegeForOfficeGraph`
- `0x21f23`: `UpdateUserSettingsPrivilegeDepth`
- `0x21faf`: `UpgradeSolutionsFormXml`
- `0x21ff5`: `UpgradeSolutionsRibbonXml`
- `0x22081`: `RemoveUnnecessaryMissingDependencyNode`
- `0x22092`: `Customization.Update_Solutionxml`
- `0x220a2`: `Customization.Update_Solutionxml`
- `0x2210d`: `HandleChangedIsQuickCreateEnabledOnSolutionImport`
- `0x22153`: `UpdateMobileClientPropertiesForKnowledgeArticle`
- `0x22199`: `RemoveUnnecessaryRecommendationModelNode`
- `0x221df`: `UpdateDisplayMaskForKnowledgeArticle`
- `0x222b1`: `HandleChangedIsReadOnlyInMobileOnSolutionImport`
- `0x222f7`: `RemoveSystemAttributeMaps`
- `0x2233d`: `UpdateFormHeaderSectionToIncludePrefix`
- `0x22383`: `UpdateMobileClientPropertiesForGoalRelatedEntities`
- `0x223c9`: `UpgradeHandlerForAutoCreatedV9EntityRelationships`

## pseudocode

```c

```

## disassembly

```asm
0x20d60  ldarg.1
0x20d61  call     string Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::ReadVersion(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x20d66  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x20d6b  stloc.0
0x20d6c  ldstr    aTestallowupgra// "TestAllowUpgradeSolutionPackageData"
0x20d71  call     int32 Microsoft.Crm.Tools.ImportExportPublish.ImportHelper::ReadDwordRegistryValue(string name)
0x20d76  ldc.i4.1
0x20d77  ceq
0x20d79  dup
0x20d7a  brfalse.s loc_20DCC
0x20d7c  ldarg.0
0x20d7d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20d82  ldc.i4.1
0x20d83  ldc.i4.6
0x20d84  ldc.i4.0
0x20d85  ldc.i4.0
0x20d86  ldc.i4.0
0x20d87  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20d8c  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20d91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20d96  ldarg.0
0x20d97  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20d9c  ldc.i4.2
0x20d9d  ldc.i4.6
0x20d9e  ldc.i4.0
0x20d9f  ldc.i4.0
0x20da0  ldc.i4.0
0x20da1  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20da6  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20dab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20db0  ldarg.0
0x20db1  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20db6  ldc.i4.3
0x20db7  ldc.i4.6
0x20db8  ldc.i4.0
0x20db9  ldc.i4.0
0x20dba  ldc.i4.0
0x20dbb  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20dc0  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20dc5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20dca  br.s     loc_20DEA
0x20dcc  ldarg.0
0x20dcd  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20dd2  ldc.i4.1
0x20dd3  ldc.i4.5
0x20dd4  ldc.i4.0
0x20dd5  ldc.i4   0x2571
0x20dda  ldc.i4.0
0x20ddb  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20de0  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20de5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20dea  ldarg.0
0x20deb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20df0  ldc.i4.s 0xA
0x20df2  ldc.i4.5
0x20df3  ldc.i4.0
0x20df4  ldc.i4   0x2592
0x20df9  ldc.i4.0
0x20dfa  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20dff  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e04  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20e09  ldarg.0
0x20e0a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20e0f  ldc.i4.s 0xB
0x20e11  ldc.i4.5
0x20e12  ldc.i4.0
0x20e13  ldc.i4   0x259D
0x20e18  ldc.i4.0
0x20e19  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20e1e  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e23  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20e28  ldarg.0
0x20e29  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20e2e  ldc.i4.s 0xC
0x20e30  ldc.i4.5
0x20e31  ldc.i4.0
0x20e32  ldc.i4   0x25B0
0x20e37  ldc.i4.0
0x20e38  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20e3d  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e42  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20e47  ldarg.0
0x20e48  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20e4d  ldc.i4.s 0xD
0x20e4f  ldc.i4.5
0x20e50  ldc.i4.0
0x20e51  ldc.i4   0x25BC
0x20e56  ldc.i4.0
0x20e57  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20e5c  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e61  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20e66  ldarg.0
0x20e67  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20e6c  ldc.i4.s 0xE
0x20e6e  ldc.i4.5
0x20e6f  ldc.i4.0
0x20e70  ldc.i4   0x25C2
0x20e75  ldc.i4.0
0x20e76  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20e7b  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e80  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20e85  ldarg.0
0x20e86  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20e8b  ldc.i4.s 0xF
0x20e8d  ldc.i4.5
0x20e8e  ldc.i4.0
0x20e8f  ldc.i4   0x25C5
0x20e94  ldc.i4.0
0x20e95  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20e9a  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20e9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20ea4  ldarg.0
0x20ea5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20eaa  ldc.i4.s 0x10
0x20eac  ldc.i4.5
0x20ead  ldc.i4.0
0x20eae  ldc.i4   0x25D0
0x20eb3  ldc.i4.0
0x20eb4  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20eb9  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20ebe  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20ec3  ldarg.0
0x20ec4  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20ec9  ldc.i4.s 0x11
0x20ecb  ldc.i4.5
0x20ecc  ldc.i4.0
0x20ecd  ldc.i4   0x25D1
0x20ed2  ldc.i4.0
0x20ed3  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20ed8  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20edd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20ee2  ldarg.0
0x20ee3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20ee8  ldc.i4.s 0x12
0x20eea  ldc.i4.5
0x20eeb  ldc.i4.0
0x20eec  ldc.i4   0x25D3
0x20ef1  ldc.i4.0
0x20ef2  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20ef7  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20efc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20f01  ldarg.0
0x20f02  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20f07  ldc.i4.s 0x13
0x20f09  ldc.i4.5
0x20f0a  ldc.i4.0
0x20f0b  ldc.i4   0x25D3
0x20f10  ldc.i4.0
0x20f11  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20f16  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20f1b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20f20  ldarg.0
0x20f21  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20f26  ldc.i4.s 0x14
0x20f28  ldc.i4.5
0x20f29  ldc.i4.0
0x20f2a  ldc.i4   0x25D8
0x20f2f  ldc.i4.7
0x20f30  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20f35  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20f3a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20f3f  ldarg.0
0x20f40  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20f45  ldc.i4.s 0x15
0x20f47  ldc.i4.5
0x20f48  ldc.i4.0
0x20f49  ldc.i4   0x25D8
0x20f4e  ldc.i4.7
0x20f4f  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20f54  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20f59  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20f5e  ldarg.0
0x20f5f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20f64  ldc.i4.s 0x16
0x20f66  ldc.i4.5
0x20f67  ldc.i4.0
0x20f68  ldc.i4   0x25D8
0x20f6d  ldc.i4   0x20A
0x20f72  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20f77  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20f7c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20f81  ldarg.0
0x20f82  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20f87  ldc.i4.s 0x17
0x20f89  ldc.i4.5
0x20f8a  ldc.i4.0
0x20f8b  ldc.i4   0x25D8
0x20f90  ldc.i4   0x20E
0x20f95  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20f9a  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20f9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20fa4  ldarg.0
0x20fa5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20faa  ldc.i4.s 0x18
0x20fac  ldc.i4.5
0x20fad  ldc.i4.0
0x20fae  ldc.i4   0x25D8
0x20fb3  ldc.i4   0x225
0x20fb8  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20fbd  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20fc2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20fc7  ldarg.0
0x20fc8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20fcd  ldc.i4.s 0x19
0x20fcf  ldc.i4.5
0x20fd0  ldc.i4.0
0x20fd1  ldc.i4   0x25D8
0x20fd6  ldc.i4   0x23E
0x20fdb  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x20fe0  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x20fe5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x20fea  ldarg.0
0x20feb  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x20ff0  ldc.i4.s 0x1A
0x20ff2  ldc.i4.5
0x20ff3  ldc.i4.0
0x20ff4  ldc.i4   0x25D8
0x20ff9  ldc.i4   0x23E
0x20ffe  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21003  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x21008  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x2100d  ldarg.0
0x2100e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x21013  ldc.i4.s 0x1B
0x21015  ldc.i4.6
0x21016  ldc.i4.0
0x21017  ldc.i4.0
0x21018  ldc.i4.0
0x21019  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x2101e  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x21023  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x21028  ldarg.0
0x21029  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x2102e  ldc.i4.s 0x1C
0x21030  ldc.i4.6
0x21031  ldc.i4.0
0x21032  ldc.i4.0
0x21033  ldc.i4.0
0x21034  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21039  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x2103e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x21043  ldarg.0
0x21044  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x21049  ldc.i4.s 0x1D
0x2104b  ldc.i4.6
0x2104c  ldc.i4.0
0x2104d  ldc.i4.0
0x2104e  ldc.i4.0
0x2104f  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21054  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x21059  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x2105e  ldarg.0
0x2105f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x21064  ldc.i4.s 0x1E
0x21066  ldc.i4.6
0x21067  ldc.i4.0
0x21068  ldc.i4.0
0x21069  ldc.i4   0x131
0x2106e  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21073  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x21078  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x2107d  ldarg.0
0x2107e  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x21083  ldc.i4.s 0x1F
0x21085  ldc.i4.6
0x21086  ldc.i4.0
0x21087  ldc.i4.0
0x21088  ldc.i4   0x135
0x2108d  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x21092  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x21097  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x2109c  ldarg.0
0x2109d  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x210a2  ldc.i4.s 0x20
0x210a4  ldc.i4.6
0x210a5  ldc.i4.0
0x210a6  ldc.i4.0
0x210a7  ldc.i4.0
0x210a8  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x210ad  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x210b2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x210b7  ldarg.0
0x210b8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x210bd  ldc.i4.s 0x21
0x210bf  ldc.i4.6
0x210c0  ldc.i4.1
0x210c1  ldc.i4.0
0x210c2  ldc.i4.0
0x210c3  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x210c8  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
0x210cd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class VersionInfo>::Add(var<u1>)
0x210d2  ldarg.0
0x210d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class VersionInfo> Microsoft.Crm.Tools.ImportExportPublish.SolutionPackageUpgrade::_pivotVersions
0x210d8  ldc.i4.s 0x22
0x210da  ldc.i4.7
0x210db  ldc.i4.0
0x210dc  ldc.i4.0
0x210dd  ldc.i4.0
0x210de  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x210e3  newobj   instance void VersionInfo::.ctor(int32 id, class [mscorlib]System.Version version)
  ... truncated ...
```
