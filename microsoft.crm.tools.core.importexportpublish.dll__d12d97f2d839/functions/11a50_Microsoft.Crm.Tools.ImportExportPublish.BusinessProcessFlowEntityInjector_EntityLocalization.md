# Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::EntityLocalization

- ea: `0x11a50`
- end: `0x1244e`
- name: `Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::EntityLocalization`
- size: `2558`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x11640`

## callees

- `0x11230`
- `0x11250`

## string_xrefs

- `0x11bbe`: `CreatedOnInfoDisplayName`
- `0x11b9b`: `CreatedByInfoDescription`
- `0x11b78`: `CreatedByInfoDisplayName`
- `0x11c04`: `CreatedOnBehalfByInfoDisplayName`
- `0x1206c`: `TraversedPathInfoDescription`
- `0x12049`: `TraversedPathInfoDisplayName`
- `0x11b55`: `CompletedOnInfoDescription`
- `0x11b32`: `CompletedOnInfoDisplayName`
- `0x11e57`: `OverriddenCreatedOnDescription`
- `0x11e34`: `OverriddenCreatedOnDisplayName`
- `0x11b27`: `{LOCALIZED_SM_CompletedOnInfoDisplayName}`
- `0x11b4a`: `{LOCALIZED_SM_CompletedOnInfoDescription}`
- `0x11b6d`: `{LOCALIZED_SM_CreatedByInfoDisplayName}`
- `0x11b90`: `{LOCALIZED_SM_CreatedByInfoDescription}`
- `0x11bb3`: `{LOCALIZED_SM_CreatedOnInfoDisplayName}`
- `0x11bd6`: `{LOCALIZED_SM_CreatedOnAttributeDescription}`
- `0x11be1`: `CreatedOnAttributeDescription`
- `0x11bf9`: `{LOCALIZED_SM_CreatedOnBehalfByInfoDisplayName}`
- `0x11c1c`: `{LOCALIZED_SM_CreatedOnBehalfByAttributeDescription}`
- `0x11c27`: `CreatedOnBehalfByAttributeDescription`
- `0x11e29`: `{LOCALIZED_SM_OverriddenCreatedOnDisplayName}`
- `0x11e4c`: `{LOCALIZED_SM_OverriddenCreatedOnDescription}`
- `0x1203e`: `{LOCALIZED_SM_TraversedPathInfoDisplayName}`
- `0x12061`: `{LOCALIZED_SM_TraversedPathInfoDescription}`

## pseudocode

```c

```

## disassembly

```asm
0x11a50  ldarg.1
0x11a51  ldstr    aLocalizedOmBas// "{LOCALIZED_OM_BaseEntity.Description}"
0x11a56  ldarg.0
0x11a57  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11a5c  ldstr    aBaseentityDesc// "BaseEntity.Description"
0x11a61  ldc.i4.1
0x11a62  newarr   [mscorlib]System.String
0x11a67  dup
0x11a68  ldc.i4.0
0x11a69  ldarg.2
0x11a6a  stelem.ref
0x11a6b  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromOMResources(string key, string[] values)
0x11a70  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11a75  starg.s  1
0x11a77  ldarg.1
0x11a78  ldstr    aLocalizedSmAct// "{LOCALIZED_SM_ActiveStageInfoDisplayNam"...
0x11a7d  ldarg.0
0x11a7e  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11a83  ldstr    aActivestageinf_0// "ActiveStageInfoDisplayName"
0x11a88  ldc.i4.0
0x11a89  newarr   [mscorlib]System.String
0x11a8e  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11a93  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11a98  starg.s  1
0x11a9a  ldarg.1
0x11a9b  ldstr    aLocalizedSmAct_0// "{LOCALIZED_SM_ActiveStageInfoDescriptio"...
0x11aa0  ldarg.0
0x11aa1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11aa6  ldstr    aActivestageinf// "ActiveStageInfoDescription"
0x11aab  ldc.i4.0
0x11aac  newarr   [mscorlib]System.String
0x11ab1  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11ab6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11abb  starg.s  1
0x11abd  ldarg.1
0x11abe  ldstr    aLocalizedSmAct_1// "{LOCALIZED_SM_ActiveStageStartedOnInfoD"...
0x11ac3  ldarg.0
0x11ac4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11ac9  ldstr    aActivestagesta_1// "ActiveStageStartedOnInfoDisplayName"
0x11ace  ldc.i4.0
0x11acf  newarr   [mscorlib]System.String
0x11ad4  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11ad9  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11ade  starg.s  1
0x11ae0  ldarg.1
0x11ae1  ldstr    aLocalizedSmAct_2// "{LOCALIZED_SM_ActiveStageStartedOnInfoD"...
0x11ae6  ldarg.0
0x11ae7  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11aec  ldstr    aActivestagesta_0// "ActiveStageStartedOnInfoDescription"
0x11af1  ldc.i4.0
0x11af2  newarr   [mscorlib]System.String
0x11af7  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11afc  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11b01  starg.s  1
0x11b03  ldarg.1
0x11b04  ldstr    aLocalizedSmPri// "{LOCALIZED_SM_PrimaryKeyAttributeDescri"...
0x11b09  ldarg.0
0x11b0a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11b0f  ldstr    aPrimarykeyattr// "PrimaryKeyAttributeDescription"
0x11b14  ldc.i4.0
0x11b15  newarr   [mscorlib]System.String
0x11b1a  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11b1f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11b24  starg.s  1
0x11b26  ldarg.1
0x11b27  ldstr    aLocalizedSmCom// "{LOCALIZED_SM_CompletedOnInfoDisplayNam"...
0x11b2c  ldarg.0
0x11b2d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11b32  ldstr    aCompletedoninf_0// "CompletedOnInfoDisplayName"
0x11b37  ldc.i4.0
0x11b38  newarr   [mscorlib]System.String
0x11b3d  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11b42  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11b47  starg.s  1
0x11b49  ldarg.1
0x11b4a  ldstr    aLocalizedSmCom_0// "{LOCALIZED_SM_CompletedOnInfoDescriptio"...
0x11b4f  ldarg.0
0x11b50  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11b55  ldstr    aCompletedoninf// "CompletedOnInfoDescription"
0x11b5a  ldc.i4.0
0x11b5b  newarr   [mscorlib]System.String
0x11b60  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11b65  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11b6a  starg.s  1
0x11b6c  ldarg.1
0x11b6d  ldstr    aLocalizedSmCre// "{LOCALIZED_SM_CreatedByInfoDisplayName}"
0x11b72  ldarg.0
0x11b73  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11b78  ldstr    aCreatedbyinfod_0// "CreatedByInfoDisplayName"
0x11b7d  ldc.i4.0
0x11b7e  newarr   [mscorlib]System.String
0x11b83  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11b88  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11b8d  starg.s  1
0x11b8f  ldarg.1
0x11b90  ldstr    aLocalizedSmCre_0// "{LOCALIZED_SM_CreatedByInfoDescription}"
0x11b95  ldarg.0
0x11b96  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11b9b  ldstr    aCreatedbyinfod// "CreatedByInfoDescription"
0x11ba0  ldc.i4.0
0x11ba1  newarr   [mscorlib]System.String
0x11ba6  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11bab  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11bb0  starg.s  1
0x11bb2  ldarg.1
0x11bb3  ldstr    aLocalizedSmCre_1// "{LOCALIZED_SM_CreatedOnInfoDisplayName}"
0x11bb8  ldarg.0
0x11bb9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11bbe  ldstr    aCreatedoninfod_0// "CreatedOnInfoDisplayName"
0x11bc3  ldc.i4.0
0x11bc4  newarr   [mscorlib]System.String
0x11bc9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11bce  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11bd3  starg.s  1
0x11bd5  ldarg.1
0x11bd6  ldstr    aLocalizedSmCre_2// "{LOCALIZED_SM_CreatedOnAttributeDescrip"...
0x11bdb  ldarg.0
0x11bdc  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11be1  ldstr    aCreatedonattri// "CreatedOnAttributeDescription"
0x11be6  ldc.i4.0
0x11be7  newarr   [mscorlib]System.String
0x11bec  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11bf1  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11bf6  starg.s  1
0x11bf8  ldarg.1
0x11bf9  ldstr    aLocalizedSmCre_3// "{LOCALIZED_SM_CreatedOnBehalfByInfoDisp"...
0x11bfe  ldarg.0
0x11bff  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11c04  ldstr    aCreatedonbehal_1// "CreatedOnBehalfByInfoDisplayName"
0x11c09  ldc.i4.0
0x11c0a  newarr   [mscorlib]System.String
0x11c0f  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11c14  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11c19  starg.s  1
0x11c1b  ldarg.1
0x11c1c  ldstr    aLocalizedSmCre_4// "{LOCALIZED_SM_CreatedOnBehalfByAttribut"...
0x11c21  ldarg.0
0x11c22  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11c27  ldstr    aCreatedonbehal_5// "CreatedOnBehalfByAttributeDescription"
0x11c2c  ldc.i4.0
0x11c2d  newarr   [mscorlib]System.String
0x11c32  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11c37  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11c3c  starg.s  1
0x11c3e  ldarg.1
0x11c3f  ldstr    aLocalizedSmImp// "{LOCALIZED_SM_ImportSequenceNumberDispl"...
0x11c44  ldarg.0
0x11c45  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11c4a  ldstr    aImportsequence_1// "ImportSequenceNumberDisplayName"
0x11c4f  ldc.i4.0
0x11c50  newarr   [mscorlib]System.String
0x11c55  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11c5a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11c5f  starg.s  1
0x11c61  ldarg.1
0x11c62  ldstr    aLocalizedSmImp_0// "{LOCALIZED_SM_ImportSequenceNumberDescr"...
0x11c67  ldarg.0
0x11c68  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11c6d  ldstr    aImportsequence_0// "ImportSequenceNumberDescription"
0x11c72  ldc.i4.0
0x11c73  newarr   [mscorlib]System.String
0x11c78  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11c7d  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11c82  starg.s  1
0x11c84  ldarg.1
0x11c85  ldstr    aLocalizedSmMod// "{LOCALIZED_SM_ModifiedByInfoDisplayName"...
0x11c8a  ldarg.0
0x11c8b  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11c90  ldstr    aModifiedbyinfo_0// "ModifiedByInfoDisplayName"
0x11c95  ldc.i4.0
0x11c96  newarr   [mscorlib]System.String
0x11c9b  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11ca0  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11ca5  starg.s  1
0x11ca7  ldarg.1
0x11ca8  ldstr    aLocalizedSmMod_0// "{LOCALIZED_SM_ModifiedByInfoDescription"...
0x11cad  ldarg.0
0x11cae  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11cb3  ldstr    aModifiedbyinfo// "ModifiedByInfoDescription"
0x11cb8  ldc.i4.0
0x11cb9  newarr   [mscorlib]System.String
0x11cbe  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11cc3  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11cc8  starg.s  1
0x11cca  ldarg.1
0x11ccb  ldstr    aLocalizedSmMod_1// "{LOCALIZED_SM_ModifiedOnInfoDisplayName"...
0x11cd0  ldarg.0
0x11cd1  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11cd6  ldstr    aModifiedoninfo_0// "ModifiedOnInfoDisplayName"
0x11cdb  ldc.i4.0
0x11cdc  newarr   [mscorlib]System.String
0x11ce1  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11ce6  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11ceb  starg.s  1
0x11ced  ldarg.1
0x11cee  ldstr    aLocalizedSmMod_2// "{LOCALIZED_SM_ModifiedOnInfoDescription"...
0x11cf3  ldarg.0
0x11cf4  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11cf9  ldstr    aModifiedoninfo// "ModifiedOnInfoDescription"
0x11cfe  ldc.i4.0
0x11cff  newarr   [mscorlib]System.String
0x11d04  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11d09  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d0e  starg.s  1
0x11d10  ldarg.1
0x11d11  ldstr    aLocalizedSmMod_3// "{LOCALIZED_SM_ModifiedOnBehalfByInfoDis"...
0x11d16  ldarg.0
0x11d17  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11d1c  ldstr    aModifiedonbeha_1// "ModifiedOnBehalfByInfoDisplayName"
0x11d21  ldc.i4.0
0x11d22  newarr   [mscorlib]System.String
0x11d27  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11d2c  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d31  starg.s  1
0x11d33  ldarg.1
0x11d34  ldstr    aLocalizedSmMod_4// "{LOCALIZED_SM_ModifiedOnBehalfByInfoDes"...
0x11d39  ldarg.0
0x11d3a  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11d3f  ldstr    aModifiedonbeha_0// "ModifiedOnBehalfByInfoDescription"
0x11d44  ldc.i4.0
0x11d45  newarr   [mscorlib]System.String
0x11d4a  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11d4f  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d54  starg.s  1
0x11d56  ldarg.1
0x11d57  ldstr    aLocalizedOmDur// "{LOCALIZED_OM_DurationAttribute.Display"...
0x11d5c  ldarg.0
0x11d5d  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11d62  ldstr    aDurationattrib// "DurationAttribute.DisplayName"
0x11d67  ldc.i4.0
0x11d68  newarr   [mscorlib]System.String
0x11d6d  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromOMResources(string key, string[] values)
0x11d72  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d77  starg.s  1
0x11d79  ldarg.1
0x11d7a  ldstr    aLocalizedOmDur_0// "{LOCALIZED_OM_DurationAttribute.Descrip"...
0x11d7f  ldarg.0
0x11d80  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11d85  ldstr    aDurationattrib_0// "DurationAttribute.Description"
0x11d8a  ldc.i4.0
0x11d8b  newarr   [mscorlib]System.String
0x11d90  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromOMResources(string key, string[] values)
0x11d95  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11d9a  starg.s  1
0x11d9c  ldarg.1
0x11d9d  ldstr    aLocalizedOmPri// "{LOCALIZED_OM_PrimaryAttribute.Name}"
0x11da2  ldarg.0
0x11da3  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11da8  ldstr    aPrimaryattribu// "PrimaryAttribute.Name"
0x11dad  ldc.i4.0
0x11dae  newarr   [mscorlib]System.String
0x11db3  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromOMResources(string key, string[] values)
0x11db8  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11dbd  starg.s  1
0x11dbf  ldarg.1
0x11dc0  ldstr    aLocalizedOmPri_0// "{LOCALIZED_OM_PrimaryAttribute.Descript"...
0x11dc5  ldarg.0
0x11dc6  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11dcb  ldstr    aPrimaryattribu_0// "PrimaryAttribute.Description"
0x11dd0  ldc.i4.0
0x11dd1  newarr   [mscorlib]System.String
0x11dd6  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromOMResources(string key, string[] values)
0x11ddb  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11de0  starg.s  1
0x11de2  ldarg.1
0x11de3  ldstr    aLocalizedSmOrg// "{LOCALIZED_SM_OrgIdInfoDisplayName}"
0x11de8  ldarg.0
0x11de9  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11dee  ldstr    aOrgidinfodispl// "OrgIdInfoDisplayName"
0x11df3  ldc.i4.0
0x11df4  newarr   [mscorlib]System.String
0x11df9  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11dfe  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11e03  starg.s  1
0x11e05  ldarg.1
0x11e06  ldstr    aLocalizedSmOrg_0// "{LOCALIZED_SM_OrgIdInfoDescription}"
0x11e0b  ldarg.0
0x11e0c  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11e11  ldstr    aOrgidinfodescr// "OrgIdInfoDescription"
0x11e16  ldc.i4.0
0x11e17  newarr   [mscorlib]System.String
0x11e1c  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11e21  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11e26  starg.s  1
0x11e28  ldarg.1
0x11e29  ldstr    aLocalizedSmOve// "{LOCALIZED_SM_OverriddenCreatedOnDispla"...
0x11e2e  ldarg.0
0x11e2f  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11e34  ldstr    aOverriddencrea_1// "OverriddenCreatedOnDisplayName"
0x11e39  ldc.i4.0
0x11e3a  newarr   [mscorlib]System.String
0x11e3f  callvirt instance string Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer::GetLocalizedStringFromSMResources(string key, string[] values)
0x11e44  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x11e49  starg.s  1
0x11e4b  ldarg.1
0x11e4c  ldstr    aLocalizedSmOve_0// "{LOCALIZED_SM_OverriddenCreatedOnDescri"...
0x11e51  ldarg.0
0x11e52  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjectorLocalizer Microsoft.Crm.Tools.ImportExportPublish.BusinessProcessFlowEntityInjector::localizer
0x11e57  ldstr    aOverriddencrea_0// "OverriddenCreatedOnDescription"
0x11e5c  ldc.i4.0
  ... truncated ...
```
