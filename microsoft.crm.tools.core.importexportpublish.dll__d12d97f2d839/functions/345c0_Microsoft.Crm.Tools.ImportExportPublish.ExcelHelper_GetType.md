# Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetType

- ea: `0x345c0`
- end: `0x34c8b`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::GetType`
- size: `1739`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x32e10`
- `0x33930`
- `0x34c90`

## callees

- `0x345c0`

## string_xrefs

- `0x34b16`: `FieldSecurityProfile`
- `0x34ab6`: `PluginAssembly`
- `0x34af6`: `ServiceEndpoint`
- `0x346f6`: `securityrole`
- `0x345d6`: `solutionManifest`
- `0x34636`: `formXml`
- `0x3463b`: `Customization.Type_FormXml`
- `0x346fb`: `Customization.Type_SecurityRole`
- `0x34776`: `isvconfig`
- `0x3477b`: `Customization.Type_ClientExtensions`
- `0x3479b`: `Customization.Type_ClientExtensions`
- `0x349fb`: `Customization.Type_ClientExtensions`
- `0x347b6`: `templates`
- `0x347bb`: `Customization.Type_Template`
- `0x347db`: `Customization.Type_ArticleTemplate`
- `0x347fb`: `Customization.Type_EmailTemplate`
- `0x3481b`: `Customization.Type_ContractTemplate`
- `0x3483b`: `Customization.Type_MailMergeTemplate`
- `0x34abb`: `Customization.Type_PluginAssembly`
- `0x34afb`: `Customization.Type_ServiceEndpoint`
- `0x34b1b`: `Customization.Type_FieldSecurityProfile`
- `0x34b36`: `rootComponent`
- `0x34b3b`: `Customization.Type_RootComponent`

## pseudocode

```c

```

## disassembly

```asm
0x345c0  ldarg.0
0x345c1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x345c6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x345cb  brtrue   loc_34C6A
0x345d0  ldarg.0
0x345d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x345d6  ldstr    aSolutionmanife_1// "solutionManifest"
0x345db  ldstr    aCustomizationT_2// "Customization.Type_Solution"
0x345e0  ldarg.0
0x345e1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x345e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x345eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x345f0  ldarg.0
0x345f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x345f6  ldstr    aEntity// "entity"
0x345fb  ldstr    aCustomizationT_3// "Customization.Type_Entity"
0x34600  ldarg.0
0x34601  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34606  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3460b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34610  ldarg.0
0x34611  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34616  ldstr    aSavedquery_0// "savedQuery"
0x3461b  ldstr    aCustomizationT_4// "Customization.Type_SavedQuery"
0x34620  ldarg.0
0x34621  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34626  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3462b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34630  ldarg.0
0x34631  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34636  ldstr    aFormxml_1// "formXml"
0x3463b  ldstr    aCustomizationT_5// "Customization.Type_FormXml"
0x34640  ldarg.0
0x34641  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34646  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3464b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34650  ldarg.0
0x34651  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34656  ldstr    aEntityicons// "entityIcons"
0x3465b  ldstr    aCustomizationT_6// "Customization.Type_Icons"
0x34660  ldarg.0
0x34661  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34666  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3466b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34670  ldarg.0
0x34671  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34676  ldstr    aEntitycustomre// "entityCustomResources"
0x3467b  ldstr    aCustomizationT_7// "Customization.Type_Message"
0x34680  ldarg.0
0x34681  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34686  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3468b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34690  ldarg.0
0x34691  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34696  ldstr    aEntityribbon// "entityRibbon"
0x3469b  ldstr    aCustomizationT_8// "Customization.Type_EntityRibbon"
0x346a0  ldarg.0
0x346a1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x346a6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x346ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x346b0  ldarg.0
0x346b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x346b6  ldstr    aSavedqueryvisu_2// "savedQueryVisualization"
0x346bb  ldstr    aCustomizationT_9// "Customization.Type_SavedQueryVisualizat"...
0x346c0  ldarg.0
0x346c1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x346c6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x346cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x346d0  ldarg.0
0x346d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x346d6  ldstr    aEntityrelation_20// "entityrelationship"
0x346db  ldstr    aCustomizationT_10// "Customization.Type_EntityRelationship"
0x346e0  ldarg.0
0x346e1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x346e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x346eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x346f0  ldarg.0
0x346f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x346f6  ldstr    aSecurityrole_0// "securityrole"
0x346fb  ldstr    aCustomizationT_11// "Customization.Type_SecurityRole"
0x34700  ldarg.0
0x34701  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34706  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3470b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34710  ldarg.0
0x34711  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34716  ldstr    aWorkflow_1// "workflow"
0x3471b  ldstr    aCustomizationT_12// "Customization.Type_Workflow"
0x34720  ldarg.0
0x34721  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34726  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3472b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34730  ldarg.0
0x34731  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34736  ldstr    aLanguage// "language"
0x3473b  ldstr    aCustomizationT_13// "Customization.Type_Language"
0x34740  ldarg.0
0x34741  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34746  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3474b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34750  ldarg.0
0x34751  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34756  ldstr    aPublish// "publish"
0x3475b  ldstr    aCustomizationT_14// "Customization.Type_Publish"
0x34760  ldarg.0
0x34761  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34766  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3476b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34770  ldarg.0
0x34771  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34776  ldstr    aIsvconfig_0// "isvconfig"
0x3477b  ldstr    aCustomizationT_15// "Customization.Type_ClientExtensions"
0x34780  ldarg.0
0x34781  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34786  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3478b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34790  ldarg.0
0x34791  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34796  ldstr    aSitemap_0// "sitemap"
0x3479b  ldstr    aCustomizationT_15// "Customization.Type_ClientExtensions"
0x347a0  ldarg.0
0x347a1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x347a6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x347ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x347b0  ldarg.0
0x347b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x347b6  ldstr    aTemplates_0// "templates"
0x347bb  ldstr    aCustomizationT_16// "Customization.Type_Template"
0x347c0  ldarg.0
0x347c1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x347c6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x347cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x347d0  ldarg.0
0x347d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x347d6  ldstr    a1016// "1016"
0x347db  ldstr    aCustomizationT_17// "Customization.Type_ArticleTemplate"
0x347e0  ldarg.0
0x347e1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x347e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x347eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x347f0  ldarg.0
0x347f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x347f6  ldstr    a2010// "2010"
0x347fb  ldstr    aCustomizationT_18// "Customization.Type_EmailTemplate"
0x34800  ldarg.0
0x34801  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34806  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3480b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34810  ldarg.0
0x34811  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34816  ldstr    a2011// "2011"
0x3481b  ldstr    aCustomizationT_19// "Customization.Type_ContractTemplate"
0x34820  ldarg.0
0x34821  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34826  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3482b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34830  ldarg.0
0x34831  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34836  ldstr    a9106// "9106"
0x3483b  ldstr    aCustomizationT_20// "Customization.Type_MailMergeTemplate"
0x34840  ldarg.0
0x34841  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34846  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3484b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34850  ldarg.0
0x34851  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34856  ldstr    aRelationshipro_0// "relationshiproles"
0x3485b  ldstr    aCustomizationT_21// "Customization.Type_RelationshipRole"
0x34860  ldarg.0
0x34861  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34866  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3486b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34870  ldarg.0
0x34871  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34876  ldstr    aAutonumbering// "autoNumbering"
0x3487b  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x34880  ldarg.0
0x34881  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34886  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3488b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34890  ldarg.0
0x34891  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34896  ldstr    aCalendar// "calendar"
0x3489b  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x348a0  ldarg.0
0x348a1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x348a6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x348ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x348b0  ldarg.0
0x348b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x348b6  ldstr    aCustomization// "customization"
0x348bb  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x348c0  ldarg.0
0x348c1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x348c6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x348cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x348d0  ldarg.0
0x348d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x348d6  ldstr    aOutlooksynchro// "outlookSynchronization"
0x348db  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x348e0  ldarg.0
0x348e1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x348e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x348eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x348f0  ldarg.0
0x348f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x348f6  ldstr    aEmail_0// "email"
0x348fb  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x34900  ldarg.0
0x34901  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34906  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3490b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34910  ldarg.0
0x34911  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34916  ldstr    aGeneral// "general"
0x3491b  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x34920  ldarg.0
0x34921  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34926  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3492b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34930  ldarg.0
0x34931  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34936  ldstr    aMarketing// "marketing"
0x3493b  ldstr    aCustomizationT_22// "Customization.Type_Settings"
0x34940  ldarg.0
0x34941  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34946  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3494b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34950  ldarg.0
0x34951  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34956  ldstr    aSuccess// "success"
0x3495b  ldstr    aCustomizationS_0// "Customization.Status_Success"
0x34960  ldarg.0
0x34961  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34966  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3496b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34970  ldarg.0
0x34971  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34976  ldstr    aWarning// "warning"
0x3497b  ldstr    aCustomizationS_1// "Customization.Status_Warning"
0x34980  ldarg.0
0x34981  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34986  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x3498b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34990  ldarg.0
0x34991  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34996  ldstr    aFailure// "failure"
0x3499b  ldstr    aCustomizationS_2// "Customization.Status_Failure"
0x349a0  ldarg.0
0x349a1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x349a6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x349ab  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x349b0  ldarg.0
0x349b1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x349b6  ldstr    aError// "error"
0x349bb  ldstr    aCustomizationS_2// "Customization.Status_Failure"
0x349c0  ldarg.0
0x349c1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x349c6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x349cb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x349d0  ldarg.0
0x349d1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x349d6  ldstr    aOptionset_1// "optionSet"
0x349db  ldstr    aCustomizationT_23// "Customization.Type_OptionSet"
0x349e0  ldarg.0
0x349e1  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x349e6  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x349eb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x349f0  ldarg.0
0x349f1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x349f6  ldstr    aRibbon// "ribbon"
0x349fb  ldstr    aCustomizationT_15// "Customization.Type_ClientExtensions"
0x34a00  ldarg.0
0x34a01  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34a06  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x34a0b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34a10  ldarg.0
0x34a11  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34a16  ldstr    aWebresource_0// "webResource"
0x34a1b  ldstr    aCustomizationT_24// "Customization.Type_WebResource"
0x34a20  ldarg.0
0x34a21  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34a26  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x34a2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34a30  ldarg.0
0x34a31  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34a36  ldstr    aPublishworkflo// "publishworkflow"
0x34a3b  ldstr    aCustomizationT_25// "Customization.Type_PublishWorkflow"
0x34a40  ldarg.0
0x34a41  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34a46  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x34a4b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x34a50  ldarg.0
0x34a51  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_types
0x34a56  ldstr    aConnectionrole// "ConnectionRole"
0x34a5b  ldstr    aCustomizationT_26// "Customization.Type_ConnectionRole"
0x34a60  ldarg.0
0x34a61  ldfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.Crm.Tools.ImportExportPublish.ExcelHelper::_exportCultureInfo
0x34a66  call     string [Microsoft.Crm.ObjectModel]Microsoft.Crm.Resources.ObjectModelResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x34a6b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
  ... truncated ...
```
